# Mainnet cutover notes (do not enact)

**Status:** notes only. Do **not** emit `shear-v1`, do **not** flip live boxes, do **not** invent a genesis datetime. In-tree genesis stays `2026-09-18T21:00:00+01:00`. Today the live book is **shear-testnet-v4** (ADMITv2).

Written: 2026-09-16.

## Repo map (public)

| Repo | Role at cutover |
|------|-----------------|
| https://github.com/rgsneddon/shear | **Main tree.** Node, crypto, specs, wallet source, pool source, ShearK source, site. README is the build-your-own-node how-to. Unarchived. |
| https://github.com/rgsneddon/shear-wallet | **Wallet releases.** GUI + CLI. Every tag ships executables for macOS, Windows, Linux, Arch, Android. Full release notes per pin in `RELEASES.md`. Unarchived. |
| https://github.com/rgsneddon/ShearK | Miner pin + how-to. Tag **1.7**. 128-byte job. |
| https://github.com/rgsneddon/shear-pool | Open-source pool + deploy how-to. Admin host via `SHEAR_ADMIN_HOST` env only. |
| https://github.com/rgsneddon/shear-testnet | **Stays testnet-v4.** Do not delete. Do not mix v4 chain.bin into mainnet datadir. |

Do not put operator admin hostnames, raw seed IPs, PEMs, or `admin.enc` in any of these repos.

## What “cut mainnet” will mean (later)

1. Wait for the frozen genesis instant. `mainnetMayEmit()` already gates `SHEAR_NETWORK=shear-v1`.
2. New datadir (`/var/lib/shear/mainnet`). Never reuse `testnet-v4`.
3. Public seed hostname (not a raw IP) in `DEFAULT_SEEDS`.
4. Publish **as a set**: node (this tree), wallet pin on shear-wallet (all platforms), ShearK pin, pool, site/explorer.
5. `kBookMagic` / `SHEAR_NETWORK` = `shear-v1`. Wallet refuses a v4 shewall against v1 without explicit reset (already the `shewall_reset_required` path).
6. Pool: `SHEAR_NETWORK=shear-v1`, new `SHEAR_DATA`, same 128-byte job if the header is unchanged.
7. shear-testnet remains the v4 book for history.

Do not dual-stack v4 and v1 in one process.

## Wallet Closure (GUI + CLI)

Backup file is encrypted `shewall.bin`. GUI Export and CLI `shear backup` call `exportEncryptedShewall`. GUI Import and CLI `shear restore` call `importEncryptedShewall`. v1 (PBKDF2) files still open and reseal to v2 (Argon2id). Archive carries dests, txs, Reserve snapshot, vortice roster.

## Not in this note

- Do not start Grok schedulers.
- Do not list the soak box raw IP in public copy.
- Do not recut wallet 0.33 / ShearK 1.6 as mainnet.
