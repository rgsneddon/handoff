---
name: kyrusfables
description: >
  Full Restore Privacy ship pipeline: build all platforms, Apple sign/notarize,
  Packet Tunnel NE assurances (monopin DevID vs residual-team host NE), commit +
  push GitHub, deploy packages to Helsinki/host, update operator docs. Use when
  the user types kyrusfables, /kyrusfables, "run kyrusfables", or asks for the
  bundled build-sign-notarize-NE-deploy-docs workflow.
when-to-use: >
  kyrusfables; /kyrusfables; full ship; build all sign notarize deploy; ship monopin
user-invocable: true
argument-hint: "[--dry-run] [--skip-build] [--skip-deploy] [version]"
compatibility: Requires restore-privacy monorepo, Xcode/notary credentials on Darwin, SSH for Helsinki
metadata:
  author: restore-privacy
  short-description: "One-word full ship: build · sign · NE · git · deploy · docs"
---

# kyrusfables — Restore Privacy full ship

When the user says **`kyrusfables`** (or `/kyrusfables`), run this **entire**
pipeline yourself end-to-end. Do **not** ask permission between steps unless a
hard external blocker stops you (missing notary key, SSH denied, push rejected
after rebase failed). Use a todo list; keep ≥1 item `in_progress`.

## Defaults

| Item | Value |
|------|--------|
| Repo | `/Users/russellsneddon/restore-privacy` (else nearest monorepo with `scripts/build_suite_*.py`) |
| Pin | `client/VERSION` (currently **1.2.7**) — use matching `scripts/build_suite_<PIN>.py` |
| Monopin macOS | Notarized **Developer ID**, **no** host `packet-tunnel-provider` (Gatekeeper openable) |
| residual-team | Side zip/app with host NE for System Settings VPN registration |
| Deploy | Helsinki paid/free store via `scripts/host_paid_assets_vps.py` / build `--host-paid` |
| Scratch | Goal scratch if set; else a private temp under the session — never shared `/tmp` for durable claims |

Optional args from user:
- `--dry-run` — print plan + inventory checks only; no build/push/upload
- `--skip-build` — stage/sign/deploy existing artifacts only
- `--skip-deploy` — build + git, no Helsinki upload
- `--skip-git` — do not commit/push (rare)
- version override if they name a pin explicitly

## Pipeline (strict order)

### 0. Preflight

```bash
cd "$REPO"
git status -sb
git rev-parse HEAD
cat client/VERSION
test -f "scripts/build_suite_$(cat client/VERSION).py"
```

- Confirm working tree intent: ship current tree (commit dirty work as part of step 5 if needed).
- Note platform: full Android/macOS/iOS native build on Darwin; Windows/Linux may carry-forward per build script honesty.

### 1. Tests / NE honesty gates (before long build)

Drive **shipped** tests, not re-implemented checks:

```bash
cd client_app
flutter test \
  test/macos_settings_and_vpn_ne_test.dart \
  test/macos_vpn_permission_sequence_test.dart \
  test/ios_vpn_prepare_honesty_test.dart \
  test/apple_vpn_prepare_before_connect_test.dart \
  test/connect_status_test.dart
```

Structural NE contract (must hold):
- macOS prepare: `loadOrCreateManager` + `isEnabled` + `saveToPreferences`; prepared only after save + honest host NE
- iOS prepare: same honesty; `hostHasPacketTunnelEntitlement` never emitted `false`
- Flutter: `applePlatformNeedsVpnPrepare` + `macosVpnActionFromPrepareMap` (missing host NE key ≠ missing NE)
- Seal tradeoff: monopin DevID openable **without** host NE; residual-team **with** host NE + launch alive when produced

Fail-closed: do not deploy monopin that fails Gatekeeper/DevID seal or residual-as-monopin.

### 2. Build all (catalog pin)

```bash
cd "$REPO"
python3 "scripts/build_suite_$(cat client/VERSION).py"
# or with deploy in one shot when host SSH is ready:
# python3 "scripts/build_suite_$(cat client/VERSION).py" --host-paid
```

Expect under `releases/<PIN>/`:
- windows / android / macos / ios / linux catalog names
- macOS: `*-macos.zip` (DevID notarized monopin)
- side: `*-macos-residual-team.zip` when residual resign + host NE + launch probe succeed

If build script already signs/notarizes macOS, do not double-break seals. If a step failed, fix and re-run that platform path.

### 3. Sign + notarize + NE assurances (explicit re-check)

```bash
# Monopin zip / app — Developer ID + notary + launch probe
python3 scripts/sign_and_notarize_macos.py --help  # confirm flags if needed
# Residual-team side (host packet-tunnel-provider) — never replace monopin basename
python3 scripts/sign_macos_residual_team.py --help
python3 scripts/apple_ship_gates.py  # or project seal audit if present
```

Verify with tools:
- `codesign -dv --verbose=4` leaf **Developer ID Application** for monopin
- monopin entitlements: **no** host `packet-tunnel-provider`
- residual-team: **has** `packet-tunnel-provider`; `PacketTunnel.appex` present
- `stapler validate` / notarization ticket stapled when applicable
- launch probe alive (not AMFI 137)

Capture evidence paths in the response (or goal SCRATCH).

### 4. Documentation update

Update only what the ship changes (do not invent marketing):
- `README.md` — pin version / package table if pin or filenames changed
- platform handoffs under `client/windows/`, `docs/`, `releases/<PIN>/` notes if the repo pattern uses them
- public site copy only if product behaviour or download names changed (`status_page/public_chrome.py`, `public_site/`)
- NE honesty: residual-team / `sign_macos_residual_team.py` path documented where operators look

If docs already match the pin, record “docs no-op” with evidence (grep version).

### 5. Commit + push GitHub

```bash
git status -sb
git add -A   # only ship-related paths; never secrets/ (check .gitignore)
git commit -m "ship(<PIN>): build, Apple seals, NE tradeoff, docs"
git pull --rebase origin main
git push origin HEAD
git rev-parse HEAD
```

- Never force-push `main` unless the user explicitly ordered it.
- Never commit notarization passwords, `.p8`, SSH keys, or `secrets/`.
- If nothing to commit (artifacts gitignored only), still push any prior commits and report “tree clean; artifacts local/Helsinki only”.

### 6. Deploy to host (Helsinki)

```bash
# Preferred if not already done via build --host-paid:
python3 scripts/host_paid_assets_vps.py --stage --upload --force
# or project’s free_direct / free_dl path if that is the live storefront route
```

- Confirm upload inventory matches catalog pin.
- Soft-fail only when SSH/network is unavailable: report exact error and what remains for the operator.
- Public audit / free monopin basename must stay Gatekeeper-openable DevID (not residual-team).

### 7. Final report (required)

Return a compact ship card:

```
kyrusfables COMPLETE | FAIL
pin: X.Y.Z
tip: <sha>
build: platforms ok/fail
macos monopin: DevID + notarized + host_NE=false + launch
residual-team: host_NE=true + launch (or skipped reason)
deploy: Helsinki ok/fail/skipped
docs: updated | no-op
git: pushed | clean | blocked
```

## Hard rules

1. **Tradeoff never inverted:** monopin free_direct = openable DevID without host NE; residual Connect registration = residual-team or `sign_macos_residual_team.py`.
2. **Honesty:** never claim prepared/VPN registered on catalog DevID without host NE.
3. **No half-ship narrative:** if deploy fails after build, say so; do not mark complete.
4. **Confirm only for destructive surprises** (force push, deleting remote assets, production DNS changes). Normal ship steps are pre-authorized by **kyrusfables**.
5. Prefer existing `scripts/build_suite_<PIN>.py`, `sign_and_notarize_macos.py`, `sign_macos_residual_team.py`, `host_paid_assets_vps.py`, `apple_ship_gates.py` over inventing new pipelines.

## Related files

- [references/pipeline.md](references/pipeline.md) — command cheatsheet
- Repo: `scripts/build_suite_<PIN>.py` (PIN from `client/VERSION`, currently 1.2.7), `scripts/sign_and_notarize_macos.py`, `scripts/sign_macos_residual_team.py`, `scripts/host_paid_assets_vps.py`
