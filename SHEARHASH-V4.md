# Full clean paste — **North Star** replaced with **ShearHash-v4**

Source on this box: `C:\Users\rgsne\Downloads\shearhash-v4-goal-rejects-hashrate.md`.

Paste the `/goal` block below after the ADMITv2 VPS + 0.34 / ShearK 2.2 client cut. This ticket is **not** the ShearHash-v4 consensus cut.

---

# `/goal` — ShearK zero spurious rejects + honest hashrate (keep round hashes for bonus) — then ShearHash-v4

## Name

**ShearHash-v4** = the follow-on PoW / book cut (intended end-state: full/fast RandomX mine + light verify, same digest, frozen ShearHash params — details in that later epic).

This ticket is **not** ShearHash-v4. It clears blockers in front of it:

1. Miner-console **spurious rejects** (stale job / restamp).
2. Pool **erroneous hashrate spikes** right after **block found**.
3. While doing (2), **preserve** accurate **`hashes this round` / `proven_round` per hasher dest** for node **hash-bonus** minting.

## Problems

### A — Rejects

Fleet-wide, ShearK shows rejected shares on the miner console. Live pool (`pool.shear.digital`) accepts large volumes from ShearK **2.2** on magic `shear-testnet-v4`, `rxMode: light`. Leading cause: miners **keep hashing an old job** after a new job / restamp, then submit a digest for a header that is no longer current.

### B — Hashrate spike after block found

Pool UI/API shows an unreal hashrate jump right after a block is found. That usually means **round tallies are being shown or used as H/s** when the round resets. Operators need honest rate; consensus still needs round hash counts for bonuses.

PoW mode (light vs full) fixes neither. Do not redesign RandomX or cut ShearHash-v4 in this change.

## Goal

1. **Near-zero spurious rejects** at the miner console under normal pool operation.
2. **Honest hashrate (H/s)** on pool and miner: no phantom spike/cliff at block found or job change.
3. **Keep and correctly report `hashes this round` / `proven_round` per dest to nodes** so consensus can mint **individual hash-bonus** rewards.

Targets:

- Spurious rejects (old job finished → shown as reject): **→ 0**
- True stales: rare; label `stale` separately
- `hashrate`: time-window / EMA; no systematic post-block spike
- `proven_round`: accurate accepted work this round; **may reset at block** (expected)

## In scope

1. **ShearK** — job abort, reject/stale labelling, local hashrate meter if any.
2. **Pool stratum + `/api/stats` + dashboard** — share accounting, hashrate formula, round counters, block-found behaviour, per-worker stats.
3. **Node-facing round hash reporting** for hash-bonus minting (per hasher dest).
4. Telemetry reasons: `stale` | `bad_hash` | `low_diff` | `wrong_job` | `submit_fail` | `aborted_stale` (debug only).
5. Short README notes.

## Out of scope (ShearHash-v4 / later)

- Cutting or implementing **ShearHash-v4** consensus / personalisation bump
- Full-mem vs light-only consensus policy change
- XMRig / multi-miner ecosystem
- New PoW family
- Unrelated mainnet ceremony
- Refactors not needed for abort + accounting split

## Required behaviour — rejects (A)

**On `mining.notify` / clean job / restamp (prev, merkle/continuity, bits, time, job id):**

1. Bump monotonic **job generation** / current `jobId`.
2. **Abort** all in-flight hashes for the previous generation immediately.
3. **Do not submit** results whose generation ≠ current.
4. **Do not** increment reject / print Rejected for aborted work — `aborted_stale` at debug only.
5. Start new hashes only on the new job/header.

**On submit:** bind `jobId` (or generation) + exact header identity. Pool outdated job → `stale`; no retry.

**Pool:** verify against that **job’s header**; explicit `stale` vs `bad_hash` vs `low_diff`.

## Required behaviour — two meters (B) — do not conflate

### Meter 1 — `proven_round` / `hashesThisRound` (consensus / hash-bonus — KEEP)

- Report **per hasher dest** to nodes so hash-bonus can be minted for that round.
- Count only **consensus-valid accepted** work this round (valid ShearHash digest, correct job/header, dest-bound).
- **Aborted / stale / wrong-job / bad_hash work: never included.**
- **May reset to zero at block found / round boundary** — correct and required.
- Inside the same round across restamps: **no double-count**; one accept → one credit.
- This meter is for **bonus minting**, not for displaying H/s.

### Meter 2 — `hashrate` (operators — FIX)

- Source of truth = accepted work over a **sliding time window / EMA** (e.g. 60–300s), **not** raw `proven_round` at reset.
- On block found: round counters may reset; **H/s must not jump** from that reset (no re-attribute, no double-count, no “round_hashes as instantaneous rate”).
- On new job / restamp: aborted work contributes **0** to hashrate.
- Per-worker and pool totals use the **same** H/s formula; UI matches API.
- Label clearly in API/UI:
  - `hashrate` → time-based H/s
  - `proven_round` / `hashesThisRound` → round tally for **hash-bonus** (resets each block)

**Invariant:**  
`proven_round` feeds **hash-bonus consensus**; `hashrate` feeds **operators**. Never use the round tally as H/s; never drop round reporting to “fix” the spike.

## Acceptance tests

### Rejects

1. Restamp storm → no old-job submits; reject counter does not climb from aborts.
2. Stable job → accepts continue; no reject spam.
3. Late share → pool `stale`; miner labels `stale`.
4. Bad digest → `bad_hash` still visible.

### Round hashes (bonus)

5. After accepts in a round, per-dest `proven_round` matches accepted valid shares for that dest.
6. On block found, `proven_round` resets; **hash-bonus inputs for the sealed round were the pre-reset tallies** (not lost, not double-applied next round).
7. Aborted/stale work never appears in `proven_round`.

### Hashrate

8. Several block boundaries: hashrate at T−30s / T_block / T+5s / T+30s — fail if post-block H/s jumps sharply without matching accept rate in the time window.
9. Job-change storm without blocks — no phantom H/s spike.
10. Sum of worker hashrates ≈ pool hashrate within tolerance.

### Regression

11. Current ShearHash-v3 selftest passes; live pin (ShearK **2.2** / `shear-testnet-v4`) unchanged unless required for job-id wiring. **Do not** bump personalisation to ShearHash-v4 in this PR.

## Definition of done

- Soak: miner-visible **spurious rejects ≈ 0** under job churn.
- After block found: **no erroneous H/s spike**; `proven_round` still correct for bonus minting.
- Documented: hashrate formula + round-hash semantics + what resets at block.
- README/changelog covering abort-on-new-job **and** the two-meter split.
- **ShearHash-v4** remains a later epic — not shipped here.

## Relationship to ShearHash-v4 (document only)

**ShearHash-v4** (next epic, after this ships) is expected to cover the PoW cut toward **full mine + light verify** (same digest under frozen params), higher real H/s for the hash-bonus economy, and any version/personalisation bump that implies — plus Shear-capable external miners later if desired.

Ship trustworthy rejects + rate/bonus accounting on the **current** ShearHash-v3 / testnet-v4 pin first so ShearHash-v4 isn’t debugged through noisy stats.

### ShearHash-v4 one-liner (roadmap only)

**ShearHash-v4 = full mine + light verify (same digest) + honest H/s + intact per-dest round hashes for hash-bonus — after ShearK spurious rejects are gone.**

## Implementation preference

- Smallest correct patches: ShearK abort + pool H/s window/EMA + keep/fix round-hash pipeline to nodes.
- Prefer generation-counter abort; prefer time-window H/s; never delete `proven_round`.
- No ShearHash-v4 consensus param / personalisation changes in this PR.
- Repo: `rgsneddon/shear-testnet` (`sheark-miner/`, `pool/`, node paths that consume round hashes).

## One-line `/goal`

**Abort ShearK in-flight work on new stratum job/restamp (never submit or show it as rejected); keep accurate per-dest hashes-this-round for node hash-bonus minting; fix displayed hashrate to a time-window so block-found round resets cannot phantom-spike H/s — before ShearHash-v4.**
