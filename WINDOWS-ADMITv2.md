# Windows box — ADMITv2 / shear-testnet-v4 (PRIMARY work machine)

**Written:** 2026-09-15. **Live:** 2026-09-17T21:00Z — **Dedicated-de is dead** (SSH wiped). Windows installs the **complete Shear site + pool + main node** on **`77.42.91.84`**. Extra P2P nodes: **`157.180.70.100`** and **`2.28.8.89`**. Book **shear-testnet-v4**. Miner pin **ShearK 2.2**. Fingerprint `MTP_FUTURE_MS=7200000`.  
**This is not [WINDOWS.md](WINDOWS.md).** That file is the formatted-disk leftover for **v3 / wallet 0.30–0.33 / ShearK 1.6**. Do **not** mix this book into that note. Do **not** recut those old tags.

**From 2026-09-17 the Windows box is the primary Shear workstation.** The MacBook goes back to a child. Do **not** wait on Darwin for node, pool, miner, tests, VPS soak, or Windows/Linux/Arch zips. Come back to a Mac **only** to cut Apple-signed clients (macOS DMG notarize, iOS). Everything else must be cloneable from GitHub onto this PC.

**URL (point the Windows machine here):** https://github.com/rgsneddon/handoff/blob/main/WINDOWS-ADMITv2.md

Repo `rgsneddon/handoff` is **private**. After `gh auth login` as **`rgsneddon`**:

```
gh repo clone rgsneddon/handoff %USERPROFILE%\handoff
notepad %USERPROFILE%\handoff\WINDOWS-ADMITv2.md
```

Use **Command Prompt** (`cmd.exe`) for Windows commands. Use **WSL Ubuntu** for Linux and Arch zips.

---

## Machine split (read this first)

| Work | Where |
|------|--------|
| Node, pool, ShearK source, tests, VPS SSH, dest-bind, ADMITv2 native, soak | **This Windows box** (plus WSL for linux/arch zips) |
| Wallet **0.34** Windows / Linux / Arch GUI+CLI | **This box** |
| ShearK **2.2** Windows zip | **This box** (linux zip already on GitHub) |
| macOS DMG (drag-to-Applications) + notarize, iOS | **Mac later** — not blocking Windows work |
| Validating tip | **`77.42.91.84`** (main node), never this PC |

Mac leftover that is **not** required to continue:

- macOS wallet **0.34** DMG is **not** on the tag yet (only `shear-0.34-macos` CLI + Android APK). Do **not** block Windows zips on that. When a Mac is free: `wallet/pack_macos.sh` with `BUILD_NUMBER=50`, `SYNC_POOL_WALLET=0`, then `gh release upload 0.34 dist/shear-wallet-0.34-macos.dmg` onto **existing** tag **0.34**. Do **not** recut **0.34**.

---

## Clone everything (formatted disk → full live tree)

Nothing exists on this disk until clone. After `gh auth login` as **`rgsneddon`**:

```
gh repo clone rgsneddon/handoff %USERPROFILE%\handoff
gh repo clone rgsneddon/shear-testnet %USERPROFILE%\shear-testnet
gh repo clone rgsneddon/shear %USERPROFILE%\shear
gh repo clone rgsneddon/shear-wallet %USERPROFILE%\shear-wallet
gh repo clone rgsneddon/ShearK %USERPROFILE%\ShearK
gh repo clone rgsneddon/shear-pool %USERPROFILE%\shear-pool
cd /d %USERPROFILE%\shear-testnet
git fetch
git checkout feat/admit-v2
git pull
notepad %USERPROFILE%\handoff\WINDOWS-ADMITv2.md
```

`feat/admit-v2` on **`rgsneddon/shear-testnet`** is the source of truth for node + pool + native admit + ShearK C + wallet tree. `rgsneddon/shear` is the public mirror of that tree. Pack from **`shear-testnet` `feat/admit-v2`**, not from `main` (v3 leftover) and not from `fix/privacy-class-v3` (0.33).

Confirm before any zip:

```
findstr kWalletVersion wallet\lib\main.dart
findstr kBookMagic wallet\lib\shear_identity.dart
findstr SHEAR_VERSION sheark-miner\src\shear_hash.h
findstr ADMIT=ADMITv2 crypto\asert.js
```

Must print `'0.34'`, `'shear-testnet-v4'`, **2.2**, and `ADMIT=ADMITv2`.

---

## Live fleet — Windows installs this (do not put the tip on this PC)

**Dedicated-de `178.105.187.178` is dead** (SSH keys wiped; Hetzner rescue not in play). Do **not** rsync, SSH, or wait on it. Do **not** use old seed `46.224.132.83` as the install target.

| Box | Address | Role — **install this** |
|-----|---------|-------------------------|
| **Main (site + pool + node)** | **`77.42.91.84`** | **Complete Shear public stack.** Nginx site (`shear.digital`, `www`, `pool.shear.digital`, explorer). Pool **is** the main node: `shear-pool-v4` (stratum `:1111`, HTTP loopback `:8088`, P2P `:30303`). Tree `/opt/shear-v4`. Data `/var/lib/shear/testnet-v4`. Optional AFK miner `sheark-v4-afk`. RPC if used stays loopback `:18332` — **do not** bind RPC to `0.0.0.0`. |
| P2P node | **`157.180.70.100`** | Validating peer only. `shear-ibd-v4`, P2P `:30303`, same book. No public pool, no public site. |
| P2P node | **`2.28.8.89`** | Second validating peer. Same as above. |

SSH as **root** with the operator ed25519 key (Mac path was `~/.ssh/id_ed25519_restore_privacy_eu`). Do **not** put admin hostnames in git. Pool admin is `SHEAR_ADMIN_HOST` env only.

**Windows next work (priority):** from `shear-testnet` `feat/admit-v2`, install the **full** site + pool + main node on **`77.42.91.84`**, then stand **`157.180.70.100`** and **`2.28.8.89`** as P2P nodes peering that main node (`SHEAR_SEEDS` includes `77.42.91.84:30303` plus each other). Rebuild Linux `shearadmit.node` on a box that has gcc; **do not** copy a Darwin `.node`. Always copy `node/src/bootstrap.js` with `node/src/store.js`.

Public names (A records after the stack is up — never raw IP in public copy):

- Site / pool / explorer → **`77.42.91.84`**
- Seed hostname **`p2p.shear.digital:30303`** → a P2P node (**`157.180.70.100`** unless you point it at the main node on purpose)
- Stratum **`pool.shear.digital:1111`** → **`77.42.91.84`**
- Magic **`shear-testnet-v4`**
- Fingerprint pins: `ADMIT=ADMITv2`, `RANGE=bpplus`, `LEVY=weight`, `SHARE_BIND=rx+noteCommit`, `BITS=q16.16`, `MTP_FUTURE_MS=7200000` (2 h — **not** 15 min)

AFK miner dest (ShearK **2.2**, long Copy dest `dest20||B` + worker) if you run one on the main box:

`ssa1qkdevt2u9k0494ynhkresghyjnugalv0muzzjf8gmd4reugrt072qc7y7dk94sjph0zuqaq7p4ytx9apymseshr3ft0.de2`

Drop-in: `/etc/systemd/system/sheark-v4-afk.service.d/dest.conf`. Do **not** dual-accept RandomX-floor when dest is present.

Soak / reorg / reserve / vort1 use **temp stores** (`node/soak_vps.js`). Never point those at `/var/lib/shear/testnet-v4`.

---

## What is already on GitHub vs what this box still cuts

| Item | Status |
|------|--------|
| Book source `feat/admit-v2` | **`git pull` this branch first** (Mac pushed 2026-09-17 night: 2h MTP, live ASERT jobs, dest-bind, native admit bind) |
| Native ADMITv2 bind | dest_leaf + C̃ at one FS index; blob **does not** carry `P` or original `C`; tests re-blind victim paths then assert dest_leaf / self-minted C̃ / mixed index fail |
| Dest-bind shares | `SHARE_BIND=rx+noteCommit`; pool `shareBind: dest`; ShearK 2.2 long dest OK; **do not** accept RandomX-floor when dest is present |
| Pool stale grace | `PREV_JOB_GRACE_MS=12000`; ASERT `blockBitsNow()` from parent+wall so a long round can ease one bit |
| Bits-stuck-at-22 | Root cause was `MTP_FUTURE_MS=15min` leaving ~3 s of legal stamp, so ASERT hardened +2 every template. Live pin is **2 h**. After h129 the job eased to **18.97**. Do **not** revert to 15 min. |
| Deploy trap | `store.js` imports `reorgBreaksCheckpoint` from `bootstrap.js`. A partial copy of `store.js` without that export crash-loops the node (SyntaxError). Copy **both**. Soak uses **temp stores**, not `/var/lib/shear/testnet-v4`. |
| Wallet **0.34** Android APK | on tag |
| Wallet **0.34** macOS CLI `shear-0.34-macos` | on tag |
| Wallet **0.34** macOS **DMG** | **missing** — Mac later |
| Wallet **0.34** Windows / Linux / Arch GUI+CLI | **this box** |
| ShearK **2.2** linux zip | on tag, sha256 `4c479f582ebd165de25f472a7d5a1dacab070513b83faaacff7ca26ad5c913e6` |
| ShearK **2.2** Windows zip | **this box** |
| VPS soak | `SOAK_DESTBIND_PASS` 2026-09-17T03:14:54Z; dest-bind soak `SOAK_RECHECK_PASS` 2026-09-16T17:55:24Z. Benches 1k/10k/100k verify tens of ms. |
| Mainnet `shear-v1` | **blocked**. In-tree genesis `2026-09-18T21:00:00+01:00`. Do not invent another. |

Do **not** recut wallet **0.34** / **0.33** / **0.32**. Do **not** recut ShearK **2.2** / **2.1** / **2.0**. Attach new zips onto **existing** tags.

---

## ADMITv2 bind (do not regress)

Membership is Pasta Curve Trees, leaf `H_to_field("shear-admit-leaf-v2" || P)`, circuit = membership of leaf only. Verify:

- unique parent slots on dest path and C path must match
- selected dest leaf and C leaf at `d0` go into Fiat-Shamir `e` / `e2`
- compact Flow blob must **not** contain `P` or original `C` (tests: `proof_blob_does_not_name_p_or_c`, JS re-blind splice)
- attacker `x` + victim path (re-blinded under attacker nonce so fold hits jroot) must fail
- self-minted `C̃` must fail
- mixed dest/C indices must fail
- Forests share one path-bit commitment

`nativeArity()` is **32**. Spec pin `pad_to_arity`. Soak nodes load `/opt/shear-v4/crypto/native/shearadmit.node`. Rebuild on Linux with `make -C crypto/native shearadmit.node` (needs `/root/.cargo/bin` on P2pnode). Do **not** copy a Darwin `.node` onto the VPS.

---

## What this box is for

Cut the **new** client set for **ADMITv2**:

| Cut | Asset | Notes |
|-----|--------|--------|
| **Windows** | `shear-wallet-0.34-windows.zip` | Flutter PE, **no miner inside** |
| **Linux** | `shear-wallet-0.34-linux.zip` | ELF `shear_wallet`, **no miner inside**, bundle libsodium |
| **Arch Linux** | `shear-wallet-0.34-archlinux.zip` | `PKGBUILD` + same linux bundle, `pkgver=0.34` |
| **Windows miner** | `ShearK-Miner-2.2-windows.zip` | `ShearK-Miner.exe` (MZ) + `example.bat` — **this box packs and uploads** |
| **Linux miner** | `ShearK-Miner-2.2-linux.zip` | ELF already on tag `2.2` — do **not** re-upload |

**0.34 is the v4 wallet.** `kWalletVersion = '0.34'` and `kBookMagic = 'shear-testnet-v4'` in `wallet/lib/shear_identity.dart`. A 0.34 zip that still speaks `shear-testnet-v3` is the wrong book — do not ship it. Flutter file version `0.34.0+50` is **not** the pin.

The rest of this cut must match the same book:

| Piece | v4 pin |
|-------|--------|
| Wallet | **0.34**, magic `shear-testnet-v4`, ADMITv2, refuse v3 shewall without explicit reset |
| Miner | **ShearK 2.2**, 128-byte job, magic `shear-testnet-v4`, dest-bound shares, long Copy dest OK |
| Node / pool / site | same magic + fingerprint (`ADMIT=ADMITv2`, `RANGE=bpplus`, `LEVY=weight`, `BITS=q16.16`) |

Do **not** recut wallet **0.33** / **0.32** / **0.31** / **0.30**. Do **not** recut ShearK **2.1** / **2.0** / **1.9** / **1.6**. Attach the Windows miner zip to **existing** tag **`2.2`**. Wallet zips still go to **`0.34`**.

---

## Book (read this before packing)

- **ADMIT** = Anonymous Destination Membership Integer Transactions. Short form **ADMITv2** (small v). Never AdmitV2 / ADMITV2.
- Magic: **`shear-testnet-v4`**. Fingerprint includes `ADMIT=ADMITv2`, `RANGE=bpplus`, `LEVY=weight`, `BITS=q16.16`.
- Membership: Pasta Curve Trees, leaf `H_to_field("shear-admit-leaf-v2" \|\| P)`, circuit = membership of leaf only.
- Amounts: Pedersen + Bulletproofs+. Levy is **weight × rate**, not 2 bps of `v`. Cap 0.001 SHE is a brake, not the advertised price.
- Public copy: ADMITv2, confidential amounts, thin-set footnote. Not FCMP++.

**Public v4 is being re-homed.** Dedicated-de is gone. Windows stands site+pool+main node on **`77.42.91.84`**, P2P on **`157.180.70.100`** and **`2.28.8.89`**. Default seed hostname **`p2p.shear.digital:30303`** (never raw IP in public copy). Stratum **`pool.shear.digital:1111`**. Soak wrote `SOAK_RECHECK_PASS` **2026-09-16T17:55:24Z** on the old fleet (history).

- Do **not** dual-stack v3 and v4 in one process.
- **Mainnet `shear-v1` stays blocked.** Genesis datetime already in-tree: `2026-09-18T21:00:00+01:00`. Do not invent another.

Pack Windows **now**: wallet **0.34** still, miner **ShearK 2.2**. Linux miner zip is **already on** `rgsneddon/ShearK` tag **`2.2`**. This box only uploads **`ShearK-Miner-2.2-windows.zip`** to that same tag. Attach wallet zips to **`rgsneddon/shear-wallet`** tag `0.34`. The validating tip stays on the VPS, not this PC.

Repo map:

| Repo | Use on this box |
|------|-----------------|
| `rgsneddon/shear-testnet` branch `feat/admit-v2` | Source to pack (wallet + sheark-miner) |
| `rgsneddon/shear` | Same tree, public main repo |
| `rgsneddon/shear-wallet` | **Wallet release host** — upload `0.34` here |
| `rgsneddon/ShearK` | Miner how-to + upload **`2.2` Windows zip only** (linux already on tag) |
| `rgsneddon/shear-pool` | Pool deploy how-to (not packed on Windows) |

---

## 0) Tools

1. **Git for Windows** — https://git-scm.com/download/win  
2. **GitHub CLI** — https://cli.github.com/  
3. `gh auth login` as **`rgsneddon`** (yes, authenticate Git with GitHub).  
4. **Flutter** stable (same channel as `wallet/pack/github-wallet-windows.yml`, 3.44.x) + **Visual Studio** with “Desktop development with C++” for `flutter build windows`.  
5. **WSL Ubuntu** + Flutter linux desktop + `libsodium` for linux/arch zips.  
6. **MinGW-w64** (or the existing Windows C toolchain) for `ShearK-Miner.exe`.

Flutter / VS / WSL **are** required for this pin. This is a **new** cut, not a leftover download.

---

## 1) Clone (nothing exists until this)

```
gh repo clone rgsneddon/handoff %USERPROFILE%\handoff
gh repo clone rgsneddon/shear-testnet %USERPROFILE%\shear-testnet
gh repo clone rgsneddon/shear-wallet %USERPROFILE%\shear-wallet
gh repo clone rgsneddon/ShearK %USERPROFILE%\ShearK
cd /d %USERPROFILE%\shear-testnet
git fetch
git checkout feat/admit-v2
git pull
notepad %USERPROFILE%\handoff\WINDOWS-ADMITv2.md
```

`feat/admit-v2` is on GitHub. Do **not** pack `fix/privacy-class-v3` (that is **0.33** / v3). Do **not** pack `main` if it is still v3.

Confirm pin **and magic** before any zip:

```
findstr kWalletVersion wallet\lib\main.dart
findstr kBookMagic wallet\lib\shear_identity.dart
```

Must print `'0.34'` and `'shear-testnet-v4'`. A 0.34 title on v3 magic is not this cut. Confirm miner header:

```
findstr SHEAR_VERSION %USERPROFILE%\shear-testnet\sheark-miner\src\shear_hash.h
```

Must be **2.2**. Magic **`shear-testnet-v4`**. Header length **128**. Long Copy dest dest-binds (`blen` cap 160). (`rgsneddon/ShearK` is the how-to + zip host; miner **source** is `sheark-miner/` in the Shear tree, `feat/admit-v2`.)

---

## 2) Cut wallet — Windows, Linux, Arch

Wallet zip is **GUI only**. Never put ShearK inside it.

### Windows (`cmd.exe`)

```
cd /d %USERPROFILE%\shear-testnet\wallet
flutter config --enable-windows-desktop
flutter pub get
flutter build windows --release --build-name=0.34 --build-number=50
cd /d %USERPROFILE%\shear-testnet
python wallet\pack\zip_windows.py
```

Expect `dist\shear-wallet-0.34-windows.zip`. Zip-root Flutter `shear_wallet.exe` (MZ), title **Shear 0.34**, **no miner**.

Create tag **`0.34`** on **`rgsneddon/shear-wallet`** if it does not exist, then attach. Also upload the same zip to `rgsneddon/shear-testnet` tag `0.34` if that tag exists. **Every 0.34 release must include Windows + Linux + Arch + Android + CLI executables.**

Tag **`0.34` already exists** on `rgsneddon/shear-wallet` and `rgsneddon/shear-testnet` (Android + macOS CLI already attached). Upload Windows onto that tag. Also compile the Windows CLI:

```
gh release upload 0.34 dist\shear-wallet-0.34-windows.zip --repo rgsneddon/shear-wallet
gh release upload 0.34 dist\shear-wallet-0.34-windows.zip --repo rgsneddon/shear-testnet
certutil -hashfile dist\shear-wallet-0.34-windows.zip SHA256
dart compile exe wallet\bin\shear.dart -o dist\shear-0.34-windows.exe
gh release upload 0.34 dist\shear-0.34-windows.exe --repo rgsneddon/shear-wallet
gh release upload 0.34 dist\shear-0.34-windows.exe --repo rgsneddon/shear-testnet
```

Do **not** recut **0.33**. Do **not** `--clobber` assets Mac already attached.

GitHub Action `wallet/pack/github-wallet-windows.yml` can pack Windows if this box cannot. Dispatch with pin **`0.34`** and build-number **`50`**. Prefer a local cut on this machine when VS is installed.

### Linux + Arch (WSL Ubuntu)

Do **not** zip a Darwin or PE binary as `*-linux.zip`. The linux zip must be **ELF**. Bundle **libsodium** (native ADMIT). Set `pkgver=0.34` in `wallet/pack/archlinux/PKGBUILD`.

```
wsl
cd ~/shear-testnet   # clone inside WSL, or /mnt/c/Users/.../shear-testnet
git checkout feat/admit-v2
git pull
# Flutter linux desktop + libsodium.so on this WSL
cd wallet
flutter config --enable-linux-desktop
flutter pub get
flutter build linux --release --build-name=0.34.0 --build-number=50
```

Then pack both zips from the linux **bundle** (not from `wallet/pack/zip_linux.sh` — that script is a stale 0.30 leftover with hardcoded paths). Mirror `wallet/pack/pack_linux_de.sh`: zip the bundle to `shear-wallet-0.34-linux.zip`; zip `PKGBUILD` + bundle to `shear-wallet-0.34-archlinux.zip`.

```
# still in WSL, after the linux build:
python3 - <<'PY'
import os, zipfile
ver = "0.34"
repo = os.path.expanduser("~/shear-testnet")  # adjust if the clone is elsewhere
bundle = os.path.join(repo, "wallet/build/linux/x64/release/bundle")
dist = os.path.join(repo, "dist")
pkgbuild = os.path.join(repo, "wallet/pack/archlinux/PKGBUILD")
os.makedirs(dist, exist_ok=True)

def add_tree(z, root):
    for dp, _, fns in os.walk(root):
        for fn in fns:
            p = os.path.join(dp, fn)
            z.write(p, os.path.relpath(p, root))

linux = os.path.join(dist, f"shear-wallet-{ver}-linux.zip")
with zipfile.ZipFile(linux, "w", zipfile.ZIP_DEFLATED) as z:
    add_tree(z, bundle)
arch = os.path.join(dist, f"shear-wallet-{ver}-archlinux.zip")
with zipfile.ZipFile(arch, "w", zipfile.ZIP_DEFLATED) as z:
    z.write(pkgbuild, "PKGBUILD")
    add_tree(z, bundle)
print("wrote", linux, os.path.getsize(linux))
print("wrote", arch, os.path.getsize(arch))
PY
file dist/shear-wallet-0.34-linux.zip
# first bytes of the unpacked binary must be ELF (7f454c46), never Mach-O
```

Upload to existing tag **`0.34`** on **both** repos (Mac already attached Android + macOS CLI):

```
gh release upload 0.34 dist/shear-wallet-0.34-linux.zip dist/shear-wallet-0.34-archlinux.zip dist/shear-0.34-linux --repo rgsneddon/shear-wallet
gh release upload 0.34 dist/shear-wallet-0.34-linux.zip dist/shear-wallet-0.34-archlinux.zip dist/shear-0.34-linux --repo rgsneddon/shear-testnet
certutil -hashfile dist\shear-wallet-0.34-linux.zip SHA256
```

Do **not** `--clobber` the Android APK or macOS CLI already on the tag.

WSL CLI (ELF):

```
wsl
cd ~/shear-testnet
dart compile exe wallet/bin/shear.dart -o dist/shear-0.34-linux
file dist/shear-0.34-linux   # must be ELF
```

---

## 3) Cut ShearK 2.2 — Windows only (linux already on GitHub)

128-byte ShearHash-v3 job. Default `--backend jit-full`. Packed header bits are Q16.16. Share floor is dest-bound (`shareBind: dest`). Login is wallet **Copy dest** `ssa1….worker` — short dest20 (~43) or long dest20||B (~95) both dest-bind. Never `shear1`.

Do **not** recut tag **2.1** / **2.0** / **1.9** / **1.6**. Tag **`2.2` already exists** with the linux zip. This box **uploads the Windows zip onto `2.2`**.

Testers download:

- Windows (after you upload): https://github.com/rgsneddon/ShearK/releases/download/2.2/ShearK-Miner-2.2-windows.zip
- Linux (live now): https://github.com/rgsneddon/ShearK/releases/download/2.2/ShearK-Miner-2.2-linux.zip
- Release: https://github.com/rgsneddon/ShearK/releases/tag/2.2

### Windows miner

Pull **`feat/admit-v2`** (`7830bd5` or later). `SHEAR_VERSION` in `sheark-miner\src\shear_hash.h` must be **2.2**.

```
cd /d %USERPROFILE%\shear-testnet
git fetch
git checkout feat/admit-v2
git pull
cd sheark-miner
mingw32-make
ShearK-Miner.exe --selftest
ShearK-Miner.exe --print-config
```

`--selftest` digest `98818c31d739ef821db0242f76bd244b96f1fb5049d27ea9a192e95c67b39a8b`. `--print-config` `version` **2.2**.

Zip **`ShearK-Miner.exe` + `example.bat`** as `ShearK-Miner-2.2-windows.zip`. `example.bat` banner is already **2.2**. PE (`MZ`). SmartScreen may warn; unsigned is fine.

```
gh release upload 2.2 ShearK-Miner-2.2-windows.zip --repo rgsneddon/ShearK
certutil -hashfile ShearK-Miner-2.2-windows.zip SHA256
```

Do **not** `--clobber` linux. Do **not** upload this zip onto **2.1**.

### Linux miner (already shipped)

Do **not** rebuild or re-upload `ShearK-Miner-2.2-linux.zip`. Dedicated-de packed it. sha256 `4c479f582ebd165de25f472a7d5a1dacab070513b83faaacff7ca26ad5c913e6`. This box does **not** attach Darwin as linux.

---

## 4) Must / must not

Must:

- Cut **windows + linux + archlinux** wallet zips for **0.34**.
- Cut **windows** ShearK **2.2** zip and upload to tag **2.2**.
- Keep miner out of the wallet zip.
- Keep the 128-byte job.
- Spell **ADMITv2**.
- `gh auth` as `rgsneddon`.

Must not:

- Recut **0.33** / **0.30** / ShearK **2.1** / **1.6**.
- Follow [WINDOWS.md](WINDOWS.md) leftover download steps for this book.
- Dual-stack v3/v4.
- Attach Darwin as `*-linux.zip`.
- Put the validating tip on this PC (Mac/Windows). Tip stays on **`77.42.91.84`** (main node) / public seed **`p2p.shear.digital:30303`**.
- Invent a mainnet genesis datetime.
- Hunt `C:\Users\rgsne\…` on the formatted disk for old zips.
- List a raw IP in public copy.

---

## 5) After the zips exist

Public ADMITv2 testnet **is live**:

1. VPS benches 1k/10k/100k green on P2pnode.
2. Two nodes share jroot.
3. `SOAK_RECHECK_PASS` **2026-09-16T17:55:24Z**.
4. Public seed **`p2p.shear.digital:30303`**. Public pool **`pool.shear.digital:1111`** (`shear-testnet-v4`).
5. Wallet pin **0.34** (GUI + CLI). Miner pin **ShearK 2.2**.

This box packs the **Windows miner zip** for tag **2.2** (linux already on GitHub) and still packs Windows/WSL wallet **0.34**. Upload miner to `rgsneddon/ShearK` tag **2.2**. Upload wallet to `rgsneddon/shear-wallet` tag **0.34**. Mainnet waits.

When you have sha256s for the three wallet zips and the ShearK **2.2** Windows zip, paste them into **this file** on `main` and into the top of [HANDOFF.md](HANDOFF.md). Do **not** rewrite [WINDOWS.md](WINDOWS.md) (that file stays v3 leftover).

### VPS from this PC

```
ssh -i %USERPROFILE%\.ssh\id_ed25519_restore_privacy_eu root@77.42.91.84
ssh -i %USERPROFILE%\.ssh\id_ed25519_restore_privacy_eu root@157.180.70.100
ssh -i %USERPROFILE%\.ssh\id_ed25519_restore_privacy_eu root@2.28.8.89
```

Do **not** SSH `178.105.187.178` (dead). Do **not** treat `46.224.132.83` as the new install target.

Tip / pool HTTP on the **main** box (`77.42.91.84`): `curl http://127.0.0.1:8088/api/stats` (not `/stats`). RPC if present is loopback only. Do **not** bind RPC to `0.0.0.0`. Soak reorg/reserve/vort1 use **temp stores** (`node node/soak_vps.js reorg|reserve|vort1`).
