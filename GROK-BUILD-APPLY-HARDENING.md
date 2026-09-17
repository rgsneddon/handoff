# Goal list item — apply security hardening (after ShearK abort / honest H/s)

Operator copy of `C:\Users\rgsne\Downloads\GROK-BUILD-APPLY-HARDENING.md`. Listed from [WINDOWS-ADMITv2.md](WINDOWS-ADMITv2.md) §7. Do not start until the ADMITv2 VPS cut is up and the ShearK two-meter ticket has shipped (P0-2 / P0-3 may land in parallel).

---

# Shear testnet — apply security hardening (Grok Build brief)

**Audience:** Coding agent (Grok Build / Cursor) implementing fixes in the Shear monorepo.  
**Repo:** `https://github.com/rgsneddon/shear-testnet` (public monorepo; pin ~`ce59170` / `main` / `feat/admit-v2` as available).  
**Chain:** `shear-testnet-v4` (magic / book law: ADMITv2 + `RANGE=bpplus` + ShearHash-v3 RX light).  
**Mode:** Defensive hardening only. Do **not** add exploit PoCs, attack recipes, or offensive tooling.  
**Goal:** Implement the ranked fixes below with tests, then open a PR (or series of PRs) with clear commit messages.

---

## 0. Ground rules

1. Prefer small, reviewable PRs grouped by P0 theme (wallet crypto, store/fast-sync, pool auth/ban, p2p, docs/ops).
2. **Do not regress** existing positive controls:
   - `pool/src/hash_credit.js`: `clientHashes` / HUD hashrate must never mint; mint uses `roundActualHashes` / proven `roundHashes` only.
   - Closed-round grace without round credit; claimed 64-hex digest required; share fingerprint `jobId:nonce:hash`.
   - ADMITv2: native verify fail-closed if missing; ADMITv1 reject; unique spend tags (`admit_link_tag`).
   - `SHARE_BIND = rx + noteCommit`; max shares/block 8192.
3. After each theme: run relevant existing tests (`node`/`pool`/`wallet`/`crypto` test suites) and add new regression tests named in each task.
4. If a path differs in the live tree, search for the symbol names given and fix the equivalent site — do not invent new consensus rules without matching `specs/`.

---

## P0-1 — Wallet: native ADMITv2 + BP+ on send (Critical)

### Problem
Flutter/Dart still proves **ADMITv1 LSAG** (`DST shear-admit-v1`) and **bit-OR ranges**, while the book requires **ADMITv2** + **BP+**.

### Files (start here)
- `wallet/lib/shear_admit.dart` — `admitProve`, DST `shear-admit-v1`
- `wallet/lib/shear_note.dart` — `proveRange` / `bitOrProveBytes` / `sealNote`
- `wallet/lib/shear_ledger.dart` — `proveFlowSpend` send path
- Specs: `specs/admit-v2.md`, `specs/confidential.md`
- Native: `crypto/native/admit/` (prove + `bpplus.rs`), `crypto/admit.js`, `crypto/note.js`
- Node verify: `node/src/chain.js` (`admit_verify`, range/BP+)

### Implement
1. Wire GUI/CLI **send** through **native** ADMITv2 prove + BP+ range prove (FFI / subprocess / existing native node bindings — prefer the same blobs the node verifies).
2. Quarantine Dart `admitProve` / bit-OR from production send (debug-only or delete from release path).
3. On `kBookMagic == shear-testnet-v4` (and mainnet `shear-v1`), **fail closed** if proof version ≠ ADMITv2 / range ≠ BP+ marker.
4. CI: reject any production path that emits DST `shear-admit-v1` or bit-OR ranges for v4+ magic.

### Acceptance
- [ ] A wallet-built flow spend verifies on node (`admit_verify` + range) against a local testnet node.
- [ ] Unit/integration test: forged/legacy v1 blob rejected; v2+BP+ accepted.
- [ ] CI step fails if `shear-admit-v1` / `bitOrProve` appear on the release send path.
- [ ] No PoC / attack tooling added.

---

## P0-2 — Bech32 checksum verification (Critical)

### Problem
`decodeBech32Payload` strips 6 checksum words but never checks `polymod == 1`, so typos can silently become a wrong 20-byte dest.

### Files
- `wallet/lib/shear_identity.dart` — `decodeBech32Payload`
- `crypto/address.js` — `decodeBech32Payload` (encode already uses polymod)

### Implement
1. On every decode (`she1` / `ssa1` / `shear1` and any other HRP using this helper), verify bech32 checksum; **reject** on mismatch before any spend/pay/mine use.
2. Share the same test vectors across Dart and JS.

### Acceptance
- [ ] Vectors: valid addresses decode; single-char corruption / truncation → reject (not wrong payload).
- [ ] Identical behavior in Dart and `crypto/address.js`.
- [ ] Existing valid fixtures still pass.

---

## P0-3 — Split `SHEAR_FAST_SYNC` from `skipSharePow` (Critical)

### Problem
In `node/src/store.js` `append`, `skipSharePow` is ORed with `archiveFast` (`SHEAR_FAST_SYNC` / `--fast-sync`), including **peer ingest**. Help text implies archival prune; share PoW is also skipped → mint integrity risk on validating nodes.

### Files
- `node/src/store.js` (~`append` / `skipSharePow` / `archiveFast`, ~L576)
- `node/src/node.js` — `SHEAR_FAST_SYNC` / `--fast-sync`
- `node/scripts/watch_prune.mjs` (already warns — align messaging)
- Tests: `node/tests/test_p2p.js` and share/hash-bonus tests

### Implement
1. **Split** disk/archive prune behavior from consensus `skipSharePow`.
2. Peer `ingest` / untrusted appends must **always** verify share PoW (never inherit fast-sync skip).
3. Keep skip only on explicit **local trusted** paths (e.g. `submitHeader` with already-validated local pow), never from P2P.
4. Document: validators must not set `SHEAR_FAST_SYNC` for consensus skip (flag may remain for prune-only if renamed).

### Acceptance
- [ ] With `SHEAR_FAST_SYNC=1`, peer-ingested blocks with invalid share PoW are rejected.
- [ ] Local trusted submit path still works as designed.
- [ ] Regression test covers: fast-sync ON + bad share batch via ingest → fail.
- [ ] Help/README text matches actual behavior.

---

## P0-4 — ADMITv2 + BP+ consensus hardening (Critical)

### Problem
Need frozen fail-closed vectors and explicit BP+ hygiene on the in-tree prover/verifier.

### Files
- `crypto/native/admit/` (`prove.rs`, `bpplus.rs`, verify path)
- `crypto/admit.js`, `node/src/chain.js`
- `specs/admit-v2.md`
- Tests under `tests/adversary/`, `crypto/`, `node/`

### Implement
1. Ensure `verifyBlock` / flow verify always uses **native** `admit_verify` (fail closed if native missing) — confirm and add regression if any JS-only fallback remains on the hot path.
2. Freeze/expand consensus vectors for at least:
   - ADMITv1 blob → reject  
   - Oversized proof (>32768) → reject  
   - Spend-tag reuse → reject  
   - Kernel conservation / dest-P bind failures → reject  
   - Mixed-index / CDS fail cases per spec  
3. In `bpplus.rs`: explicit reject for **zero Fiat–Shamir challenge**, identity/bad decompress already fail-closed — add tests.
4. Binding vector suite: range proof bound to note commitment / admit leaf as specified.

### Acceptance
- [ ] Vector suite runs in CI on every PR.
- [ ] Zero-challenge and ADMITv1 cases fail closed.
- [ ] No change that re-enables ADMITv1 on v4 magic.

---

## P0-5 — P2P eclipse resistance (code + seed config)

### Problem
Thin topology + DNS seed drift; `p2p.js` lacks peer scoring / ban / outbound diversity. DNS `p2p.shear.digital` A record may disagree with ops HANDOFF seed IP.

### Files
- `node/src/p2p.js` (`P2P_MAX_FRAME` default 16 MiB)
- Seed/bootstrap config (env, README, deploy docs, `HANDOFF_OPS` if in-tree)
- Ops docs as needed

### Implement (code)
1. Add per-peer counters for invalid headers / failed expensive verifies; disconnect + temporary ban past threshold.
2. Cap inbound per subnet (/24); prefer diverse outbound + feeler peer if feasible without huge redesign.
3. Lower default `P2P_MAX_FRAME` for testnet→mainnet readiness (keep env override); cheap rejects before Admit/BP+/RX verify.
4. Support **hardcoded seed multiaddrs/IPs** in addition to DNS; refuse “DNS-only” as sole bootstrap in docs/defaults.

### Implement (ops — document in PR if you cannot change DNS)
5. Note/fix: `p2p.shear.digital` A vs intended seed IP must match; target ≥3 independent geo validators; pool node ≠ sole validating path; post-wipe gate = same height + `jroot` on all boxes.

### Acceptance
- [ ] Misbehaving peer is disconnected after N expensive failures (unit or integration test with fake peer if available).
- [ ] Default frame limit reduced or justified with comment + env docs.
- [ ] README lists ≥2 bootstrap methods (DNS + static seeds).

---

## P0-6 — Stratum TLS / bind + optional authenticated login

### Problem
Cleartext stratum on `0.0.0.0:1111`; login is format-valid dest only (no ownership proof).

### Files
- `pool/src/pool.js` / `main.js` — `net.createServer`, `admitClient`, `isMineLogin`
- `deploy/nginx-pool.shear.digital.conf`, `deploy/shear-pool.service`
- Related: ShearK login UX (sibling) — document only if out of tree

### Implement
1. Prefer TLS termination for stratum (or Stratum V2 Noise) with documented pool identity/fingerprint; bind intentional interface (not all-ifaces by default in prod config).
2. Add **optional** challenge/signed login proving control of payout dest (or one-time wallet challenge); rate-limit new identities.
3. Until auth exists: treat unauthenticated login as ephemeral tag; document threat model.
4. Healthchecks for stratum + HTTP API; fix deploy docs (80 vs 443) to match reality.

### Acceptance
- [ ] Prod example config does not advertise cleartext-all-interfaces as the mainnet recommendation.
- [ ] Optional auth path tested (or clearly behind feature flag with tests for the flag).
- [ ] `/api/stats` or docs expose how miners should verify pool identity.

---

## P0-7 — Auto-ban grief (dest ban without ownership)

### Problem
`need_hash` / `client_refused` / early `bad_hash` can durable-ban **dest/tag** via `rememberInvalid` / `banInvalidKeys` while login has no shared secret → impersonator can ban an honest miner’s dest.

### Files
- `pool/src/pool.js` — `rememberInvalid`, `banInvalidKeys`, `shouldDropOnReject`, `admitClient`, `pool-bans.json`

### Implement
1. First-contact / unauthenticated: **per-IP soft deny + strike system** only.
2. **Never** durable dest/tag ban without ownership proof (or after N confirmed accepts from that dest on this pool).
3. Expire bans; require multiple strikes before durable ban even with auth.
4. Keep wrong-algo farm protection without dest grief.

### Acceptance
- [ ] Test: unauthenticated client triggering `need_hash` cannot write a durable dest ban for a victim dest.
- [ ] Authenticated / post-accept path can still ban abusive keys with strikes.
- [ ] Ban file schema/docs updated.

---

## P0-8 — Operator fee transparency + admin audit

### Problem
Admin (password+TOTP) can pause/kick/ban/withdraw; dual-login `.fee` reuses hasher job; fee opacity.

### Files
- `pool/src/admin.js`, `pool/src/pool.js` (`shearFeeRoute`, `POOL_FEE_BPS`, `splitPot`)
- Stats API fields

### Implement
1. Publish `POOL_FEE_BPS` and fee dest on `/api/stats` (and UI if present).
2. Append-only audit log for admin actions (pause, kick, ban, withdraw, restart).
3. Separate/hot-path withdraw controls (confirm + role separation if practical).
4. Surface `.fee` shares in operator reports (not invisible).

### Acceptance
- [ ] Stats JSON includes fee bps + fee dest.
- [ ] Admin mutating call appends an audit record (test).
- [ ] Docs state operator-trust model explicitly.

---

## P0-9 — Round-hash integrity (lost work + publish path)

### Problem
Mint correctly uses `roundActualHashes` only (keep). Gaps: external tip / `resetOpenRound` can zero `roundHashes` without credit; round-hash publish is pool-centralized (`noteOpenRound` + `p2p.publishWork`).

### Files
- `pool/src/pool.js`, `hash_credit.js`, `pull_book.js`
- Node paths consuming open-round / hash-bonus (`noteOpenRound`, share batch / hash_bonus in `node` + `crypto`)

### Implement
1. Invariant: open-round reset must **not discard** uncredited `roundActualHashes` without seal/credit or durable “lost-work” accounting + alert.
2. Keep two meters everywhere: never “fix H/s” by dropping proven round reporting.
3. Label API fields explicitly: `hashrate` (HUD) vs `proven_round` / `roundActualHashes`.
4. Medium-term: document or stub redundant publishers / non-pool path for round-hash inputs (at minimum: alert if publish path fails).

### Acceptance
- [ ] Test: tip advance / `resetOpenRound` does not silently destroy credited-but-unpublished accepts (or records lost-work metric).
- [ ] API docs/fields distinguish HUD vs proven.
- [ ] Existing tests still assert `clientHashes` never mint.

---

## P0-10 — Concentration / second mining path (ops + product)

### Problem
Thin testnet H/s + single public pool concentration (~80% top worker in one capture). Mostly ops/product, some code.

### Implement
1. Add pool metrics/alerts for hashrate share by dest and shares-vs-blocks (BWH-shaped) anomalies.
2. Docs: how to run a second pool or solo template; bake-off before “decentralized mining” claims.
3. Do **not** claim multi-party security until second path exists.

### Acceptance
- [ ] Stats or admin metrics expose top-dest share % and share:block ratio.
- [ ] README section: solo / third-party pool pointer (`SHARE_BIND` already law-friendly).

---

## P1 — implement after P0s (batch OK)

### P1-A Pool verify DoS / vardiff / dedup
- Fail-fast claimed digest vs memoized header hashes; per-IP/conn submit token bucket; alert on `busy` rate (`pool.js`, `hash_worker.js`).
- Tighten vardiff prior-bits window (~12s); credit `min(assigned, bitsMet)`; **persist shareBits by dest across reconnects** (anti easy-share reopen).
- Dedupe `openShares` on same fingerprint as `rememberShare` (not nonce-only).

### P1-B ShearK restamp (sibling repo if in workspace)
- Abort-on-new-job; never submit aborted work; align reject taxonomy with pool (`stale` ≠ `bad_hash`).

### P1-C Wallet session / RPC / UX
- `shear_lock.dart` / `shear_session.dart`: Argon2id session seal (align with shewall v2); refuse plaintext `session.json` on load; `chmod 0600`.
- `shear_biometrics.dart`: store unlock token, not full backup password; re-auth for Export.
- No `viewKey` in URL query (`shear_ledger.dart`, `node/src/rpc.js`) — POST body only.
- Clipboard TTL; miner one-click copy = **ssa1** only.

### P1-D Protocol / crypto / release
- `submitHeader` trusted pow: assert unreachable from P2P (regression test).
- ShearHash light selftest gate on published node/pool/miner artifacts.
- Thin |J| anonymity: docs + wallet UX warning; mining dest rotation guidance.
- Incentive docs: real pay is PROP pot (− fee); hash-bonus is tiny — align marketing/README.

### P1-E Mainnet emit checklist (docs + guards)
- `SHEAR_MAINNET_EMIT` unset by default; new datadir; fingerprint pins; no dual-stack ADMITv1+v2.

---

## P2 — nice to have

- Clipboard / fee fingerprint notes; weight-levy CAP fuzz; release Darwin/Linux native binary guardrails.
- Strike/expiry polish on bans; more PROP UI transparency.

---

## Suggested PR order

1. **PR-A:** P0-3 fast-sync / skipSharePow split + tests  
2. **PR-B:** P0-2 Bech32 verify (JS + Dart) + vectors  
3. **PR-C:** P0-1 wallet native ADMITv2+BP+ send path + CI ban on v1  
4. **PR-D:** P0-4 BP+ zero-challenge + admit vector suite  
5. **PR-E:** P0-7 ban grief + P0-6 stratum bind/TLS config + P0-8 fee/stats/audit  
6. **PR-F:** P0-9 round-hash lost-work + API meter labels  
7. **PR-G:** P0-5 p2p scoring/frame/seeds  
8. **PR-H:** P1 batch (vardiff reconnect, verify DoS, wallet session, viewKey POST)

---

## Out of scope for this build (do not invent)

- Changing emission schedule / consensus constants without an explicit Russell-approved hardfork spec.
- Private `rgsneddon/shear` (404) — work in `shear-testnet` monorepo.
- Exploit demonstrations, red-team payloads, or “how to attack the pool” writeups.
- Live DNS/registrar changes (document required ops deltas in the PR description).

---

## Definition of done

- [ ] All P0 code tasks merged or in open PRs with tests green.
- [ ] Dual-meter and ADMIT fail-closed positives still green.
- [ ] PR descriptions reference this brief section IDs (`P0-1` …).
- [ ] Short CHANGELOG / hardening notes for operators (fast-sync, bans, fee stats, seeds).

---

*Generated by Chief of Staff from the 2026-09-17 six-specialist Shear pre-mainnet audit. Findings and hardening only.*
