# Operator handoff — all repos, all platforms

**Written:** 2026-08-16 (Europe/London) from the outgoing Mac (`/Users/russellsneddon`).  

**Updated:** 2026-09-17T21:00Z — **Dedicated-de `178.105.187.178` is dead** (SSH wiped). Windows installs the **complete Shear site + pool + main node** on **`77.42.91.84`**. Extra P2P nodes: **`157.180.70.100`** and **`2.28.8.89`**. Do **not** rsync DE. A records: site/pool/explorer → `77.42.91.84`; public seed `p2p.shear.digital` → a P2P node. How-to: **[WINDOWS-ADMITv2.md](WINDOWS-ADMITv2.md)**.

**Updated:** 2026-09-17T05:01Z — Fleet restored on **shear-testnet-v4** after a partial deploy crash-looped seed/peer-2/p2pnode2 (`store.js` imported `reorgBreaksCheckpoint` from a Sep-13 `bootstrap.js` that lacked the export). Dedicated-de pool was **not** bounced. Tip height **129**, shared jroot, fingerprint `MTP_FUTURE_MS=7200000` (2 h — the bits-stuck-at-22 fix). `feat/admit-v2` on GitHub now has that tree. How-to: **[WINDOWS-ADMITv2.md](WINDOWS-ADMITv2.md)**.

**Updated:** 2026-09-17 (evening) — **Windows is the primary Shear workstation.** The MacBook is going back to a child. Continue on the formatted Windows box from GitHub only. How-to: **[WINDOWS-ADMITv2.md](WINDOWS-ADMITv2.md)**. Mac returns later **only** for Apple-signed clients (macOS DMG notarize / iOS). Do **not** block Windows zips on the missing 0.34 DMG.

Live book **`shear-testnet-v4`**. Source **`rgsneddon/shear-testnet` `feat/admit-v2`**. Wallet pin **0.34**. Miner pin **ShearK 2.2**. **Main site+pool+node `77.42.91.84`.** P2P **`157.180.70.100`** and **`2.28.8.89`**. Seed hostname **`p2p.shear.digital:30303`**. Pool **`pool.shear.digital:1111`**. ADMITv2 native bind is in-tree (blob does not name `P`/`C`; dest-bind shares; long Copy dest OK). Miner dest if AFK on the main box: `ssa1qkdevt2u9k0494ynhkresghyjnugalv0muzzjf8gmd4reugrt072qc7y7dk94sjph0zuqaq7p4ytx9apymseshr3ft0.de2`. Mainnet **`shear-v1` blocked** (in-tree genesis `2026-09-18T21:00:00+01:00` — do not invent another). Do **not** recut **0.34** / **2.2** / **2.1** / **0.33**.

**This box packs:** wallet **0.34** Windows + Linux + Arch GUI+CLI onto existing tag **`0.34`** (`rgsneddon/shear-wallet` and `rgsneddon/shear-testnet`); ShearK **2.2** Windows zip onto existing tag **`2.2`**. Mac already attached Android APK + macOS CLI. How-to: [WINDOWS-ADMITv2.md](WINDOWS-ADMITv2.md).

**Updated:** 2026-09-17 — **Wallet 0.34** tag is live. Mac attached **Android APK + macOS CLI**. **This box packs Windows + Linux + Arch (GUI zip + CLI)** and uploads onto existing tag **`0.34`** on **both** `rgsneddon/shear-wallet` and `rgsneddon/shear-testnet`. Do **not** recut **0.33**. Miner pin still **ShearK 2.2** Windows zip onto tag `2.2`. How-to: [WINDOWS-ADMITv2.md](WINDOWS-ADMITv2.md).

Wallet testers:

| | URL |
|--|--|
| Release | https://github.com/rgsneddon/shear-wallet/releases/tag/0.34 |
| Android (live) | https://github.com/rgsneddon/shear-wallet/releases/download/0.34/shear-wallet-0.34-android.apk |
| macOS CLI (live) | https://github.com/rgsneddon/shear-wallet/releases/download/0.34/shear-0.34-macos |
| Windows GUI (this box) | https://github.com/rgsneddon/shear-wallet/releases/download/0.34/shear-wallet-0.34-windows.zip |
| Linux GUI (this box) | https://github.com/rgsneddon/shear-wallet/releases/download/0.34/shear-wallet-0.34-linux.zip |
| Arch (this box) | https://github.com/rgsneddon/shear-wallet/releases/download/0.34/shear-wallet-0.34-archlinux.zip |

**Updated:** 2026-09-16 — **Live book `shear-testnet-v4`.** Miner pin **ShearK 2.2**. Linux zip is on tag. **Windows zip is this box’s job** — pack PE + `example.bat`, upload to the **existing** tag `2.2` (do **not** recut **2.1** / **2.0** / **1.9**). Long Copy dest (`dest20||B`, ~95 chars) dest-binds. Source: `rgsneddon/shear-testnet` `feat/admit-v2` (`7830bd5`). How-to: [WINDOWS-ADMITv2.md](WINDOWS-ADMITv2.md).

| | URL |
|--|--|
| **Windows miners (after this box uploads the zip)** | https://github.com/rgsneddon/ShearK/releases/download/2.2/ShearK-Miner-2.2-windows.zip |
| Release page (linux zip live now) | https://github.com/rgsneddon/ShearK/releases/tag/2.2 |
| Linux testers | https://github.com/rgsneddon/ShearK/releases/download/2.2/ShearK-Miner-2.2-linux.zip |
| Windows pack recipe | https://github.com/rgsneddon/handoff/blob/main/WINDOWS-ADMITv2.md |

Linux `ShearK-Miner-2.2-linux.zip` sha256 `4c479f582ebd165de25f472a7d5a1dacab070513b83faaacff7ca26ad5c913e6` (ELF `ShearK-Miner` + `example.sh`). Pool `pool.shear.digital:1111`. Seed `p2p.shear.digital:30303`. Dedicated-de `sheark-v4-afk` is **2.2** two-thread. P7 is **2.2** 40-thread long dest. Do **not** recut **2.1**.

**Updated:** 2026-09-14 — **[testnet] Shear wallet 0.32** is the soak pin on GitHub **default `main`** (`c702ea4`, kWalletVersion 0.32). Tag **`0.33`** (`854ce9d`) is the **latest client** (splash v3-sync / drop leftover v2) — macOS/Android/Linux/Arch already on that tag. **Windows zip is packed on the Windows box**, not on Darwin (Darwin cannot `flutter build windows`). Do **not** recut **0.33** / **0.32** / **0.31**. MAGIC **`shear-testnet-v3`**. Seed **`shear.digital:30303`**. Miner **ShearK 1.6**. Frozen flyclient `main` is **`archive/main-flyclient-f1fc184`**. Soak through **2026-09-18**. Mainnet is **not** cut. Windows start: [WINDOWS.md](WINDOWS.md) — clone, install Flutter 3.44.6 + VS C++, checkout tag **0.33**, `flutter build windows --release --build-name=0.33 --build-number=49`, `python wallet\pack\zip_windows.py`, `gh release upload 0.33 dist\shear-wallet-0.33-windows.zip`. Leftover **0.30** Windows + ShearK **1.6** stay history.

Assets on tag **`0.32`** (live soak pin; title **Shear 0.32**; **no miner inside**; macOS Developer ID + notarized + stapled, notary `1bd94c94-bcf6-471b-b7e0-ec1338721b5b`):

| Asset | sha256 |
|-------|--------|
| `shear-wallet-0.32-macos.dmg` | `9f1874b6d5d6e31e7b5a708a263ce9f76c6474170d75d778f60123d1487dce3d` |
| `shear-wallet-0.32-android.apk` | `75e06fa7108ae8d5c766984da61570be5708005e221b871502cdbf75d122586a` |
| `shear-wallet-0.32-linux.zip` | `6528e4596e2590e8bc032f83a6acf49443424a7fc92cb1c5cc484740f7ca81d5` |
| `shear-wallet-0.32-archlinux.zip` | `cd40a3e0a047f800cf2b97c37da221400f4e2c02a0f664961250d75f88dc012e` (`pkgver=0.32`) |

**No iOS zip. No 0.32 Windows zip** (do **not** recut 0.32 to add one). Flutter file version `0.32.0+48` is not the public pin. Do **not** recut **0.32** / **0.33** / **0.31** / **0.30** / **0.29** / ShearK **1.6**.

**Latest client:** tag **`0.33`** (`854ce9d`) — splash v3-sync / drop leftover v2. macOS/android/linux/arch on that tag. **Windows zip is this box’s job** (see [WINDOWS.md](WINDOWS.md) §1b). Do **not** recut the tag; attach `shear-wallet-0.33-windows.zip` only.

| Asset | sha256 |
|-------|--------|
| `shear-wallet-0.33-macos.dmg` | `1e63c92c11659f1827f6d819b15bff36cb08f656c115f74c085e19e098ab2ade` |
| `shear-wallet-0.33-android.apk` | `ea266b35e2e2440147419e59449f5a5b640141481b405ec6d252052adbad39af` |
| `shear-wallet-0.33-linux.zip` | `032807fb3d530cfc71f7e2ee47aa9bf48c469b3c3f95e5be4110ab8494916dfb` |
| `shear-wallet-0.33-archlinux.zip` | `f9051f51b367b90e7d86d0af0d373ca000fddb2c8c90b37d5694c5e7023cd261` |

**Leftover (historical, not the live pin):** 2026-09-13 — **[testnet] Shear wallet 0.31** on tag `0.31` `4bb6d31` (flyclient-era). Do **not** recut. Live pin is **0.32** above. On-chain lock `lock-1789255817128` h198 (π), vote `vote-1789255932568` h199 hold. Pool cwd **`/opt/shear-v3`**, `SHEAR_DATA=/var/lib/shear/testnet-v3`. Miner pin **ShearK 1.6**. v2 snapshot still boots: `/var/lib/shear/snapshots/testnet-v2-worthy-20260912Tprivacy-v3/datadir` (MAGIC `shear-testnet-v2`). Mainnet `shear-v1` genesis **`2026-09-18T21:00:00+01:00`** (18 Sep 2026 21:00 UK). Clients refuse to emit before that instant. Formatted Windows box: clone **`main`** (0.32); leftover **0.30** Windows + ShearK **1.6** as history.

Assets on tag **`0.31`** (recut; title **Shear 0.31**; **no miner inside**; macOS stapled notary `36879086-8c87-488e-98d6-f227d6ab3dc2`; app `136d104a-0ff2-4236-ba14-e2a8656f604f`):

| Asset | sha256 |
|-------|--------|
| `shear-wallet-0.31-macos.dmg` | `893f9554c42fb0857dc4aa843764e85a9a7adba25fa07bc988dac2fbe885ca2d` |
| `shear-wallet-0.31-android.apk` | `d2876c4223aaceb6af6aa1dcefb226571d3670b16c0a4f0a8cd8cb173d59f83a` |
| `shear-wallet-0.31-linux.zip` | `dfa23340bb7afe8ae3d3637d4c7a31be2b551e0227ba35a4910415a3fed08763` |
| `shear-wallet-0.31-archlinux.zip` | `8a842e8ca1bd5b2ae9775319f280069bde92ec34bd43fb452fdb620fec06afca` (`pkgver=0.31`) |

**No iOS zip. No 0.31 Windows zip.** Linux + Arch packed on Dedicated-de (ELF + libsodium). Do **not** attach Darwin as `*-linux.zip`. Flutter file version `0.31.0+47` is not the pin.

**Updated:** 2026-09-12 — **Windows box is formatted. There is no repo on that disk.** Wipe was 2026-09-11 to recover from an error. There is **no** `C:\Users\rgsne\handoff`, **no** `C:\Users\rgsne\shear-testnet`, **no** leftover zip, **no** Flutter SDK, **no** Visual Studio / WSL tree. Start from GitHub only. Do **not** hunt old `C:\Users\rgsne\…` trees. Do **not** attach zips from the dead disk. Do **not** `git -C` a path until after `gh repo clone`. Every leftover block below that says `git -C ~/handoff pull` is **historical** — clone first. Shear wallet **0.30** Windows zip **is on tag**. ShearK **1.6** Windows zip **is on tag**. MY PERC Windows leftover on tag is **1.1.6** (1.1.8 Windows was never attached). Restore Privacy GitHub Windows installer is **1.2.5** (1.2.7 PE lived only on the laptop and is gone). Download; do **not** recut; do **not** pack a second windows zip.

**Windows start (formatted box, no local repo):** https://github.com/rgsneddon/handoff/blob/main/WINDOWS.md — `gh repo clone`, install Flutter 3.44.6 + VS C++, pack **0.33** Windows zip onto tag `0.33`. Download leftover **0.30** Windows + ShearK **1.6** as history. Live public book is **`shear-testnet-v3`**. Default `main` soak pin is **0.32**. Latest client is **0.33**. Tag **0.31** is leftover flyclient. Do **not** recut **0.33** / **0.32** / **0.31** / **0.30** / **0.29** / ShearK **1.6**. Darwin does **not** pack Windows.

**Updated:** 2026-09-11 — **[testnet] Shear wallet 0.30** on tag (`rgsneddon/shear-testnet` tag **`0.30`**, Amelia `2e82bbb`). Title **`[testnet] Shear wallet 0.30`**. Dest-bind: paid dests are `ssa1` (wallet **Copy dest** / destCommit). `she1` stratum without `--dest` is unpaid. Hash bonus is **per hasher dest** (`kind:hash`, 256u per proven floor share). Live MAGIC **`shear-testnet-v2`**. Pool process cwd **`/opt/shear-worthy`**, `SHEAR_DATA=/var/lib/shear/testnet-v2-worthy`. Live HTML is `/var/www/shear.digital` and pool pages via `/var/www/pool.shear.digital` → `/opt/shear-pool/pool/public`. Public WALLET pin **0.30**. Assets on tag: macos.dmg `c324a643ebe2679c1de69b4eb194ea04cb0f6cf8cd3b2ee178b0ce83fa42fdc0`, android.apk `ed8bdb88702c59f7c51b1284191d694db2616f8e2f3c1749f2d5e2a2397fc24c`, linux.zip `90adfd46a087aaa8ae3051ebbce9e65af939098d66a7b46ef4ca76a325907c35` (ELF, packed on Dedicated-de), archlinux.zip `081763cbd5abb71b2a072128d70c34ebcf9c3b3019702fd554e28bc86ca520b1` (`pkgver=0.30`), windows.zip `8bc28d5255e14935e2ec7afc5cd43d89a217c84247eff40edfe25da667bc29a8` (zip-root Flutter `shear_wallet.exe` MZ, title **Shear 0.30**, **no miner inside**). **No iOS zip.** **Windows zip is on this same `0.30` tag (GitHub).** The formatted disk has no copy — download it. Public site still omits the wallet Windows menu link; Amelia can restore it. Flutter file version `0.30.0+42` is not the pin. **Tag `0.29` stays.** Do **not** recut **0.30**. Do **not** recut **0.29**. Miner pin **ShearK 1.6**. Canonical tree **`rgsneddon/shear-testnet`**. Keep **`rgsneddon/ShearK`** and **`rgsneddon/handoff`**.

**Windows (formatted) — no local repo.** Full recipe: **[WINDOWS.md](WINDOWS.md)** (`https://github.com/rgsneddon/handoff/blob/main/WINDOWS.md`). Clone from GitHub, then download. **0.30** Windows zip is already on tag. ShearK **1.6** Windows zip is already on tag. Do **not** recut **0.30**. Do **not** re-upload linux/arch. Do **not** pack a second windows zip. Public site still omits `data-pack="wallet-windows"`; Amelia can restore that link.

```
# Fresh box — nothing exists until you clone. Use cmd.exe. handoff is private — gh repo clone.
# 1) Install Git for Windows + GitHub CLI, then:
gh auth login
gh repo clone rgsneddon/handoff %USERPROFILE%\handoff
gh repo clone rgsneddon/shear-testnet %USERPROFILE%\shear-testnet
gh repo clone rgsneddon/ShearK %USERPROFILE%\ShearK
cd /d %USERPROFILE%\shear-testnet
git checkout main
git pull
notepad %USERPROFILE%\handoff\WINDOWS.md

# Optional later (only if you work those products on this box):
# gh repo clone rgsneddon/gnfp-wallet %USERPROFILE%\gnfp-wallet
# gh repo clone rgsneddon/gnfp-cminer %USERPROFILE%\gnfp-cminer
# gh repo clone rgsneddon/gnfp-node %USERPROFILE%\gnfp-node
# gh repo clone rgsneddon/perccent-wallet %USERPROFILE%\perccent-wallet
# gh repo clone rgsneddon/evolve %USERPROFILE%\evolve

# 2) Miner 1.6 — already on tag (PE + example.bat with YOUR_SSA1.worker). Download, do not recut:
# sha256 879a0024297962cd9a97bf544dcd1fe1656a546d82ea37cfa6f6a2615befb5fb
gh release download 1.6 --repo rgsneddon/ShearK --pattern ShearK-Miner-1.6-windows.zip --dir %USERPROFILE%\Downloads\sheark-1.6
# How-to: https://github.com/rgsneddon/ShearK/blob/main/README.md
# Login: wallet Copy dest → ssa1….worker  (she1 without --dest is unpaid)

# 3) Wallet 0.30 Windows zip — already on tag. Download, do not recut, do not re-upload.
# sha256 8bc28d5255e14935e2ec7afc5cd43d89a217c84247eff40edfe25da667bc29a8
gh release download 0.30 --repo rgsneddon/shear-testnet --pattern shear-wallet-0.30-windows.zip --dir %USERPROFILE%\Downloads\shear-0.30
# Zip root is Flutter shear_wallet.exe, title Shear 0.30, no miner inside.
# Linux + Arch 0.30 stay on the tag (packed on Dedicated-de, ELF). Do not re-upload those.
# Amelia can restore the site Windows wallet download link.
```

ShearK **1.6** (`rgsneddon/ShearK` tag **`1.6`**, README `bc4d1be`): `ShearK-Miner-1.6-windows.zip` sha256 `879a0024297962cd9a97bf544dcd1fe1656a546d82ea37cfa6f6a2615befb5fb` (zip root `ShearK-Miner.exe` MZ + `example.bat` — `--user YOUR_SSA1.worker`). `ShearK-Miner-1.6-linux.zip` sha256 `e04e8b57d4700c25f2912b6636c9ef444b1d3f40b3128dd3a168a5388271c2d1` (zip root `ShearK-Miner` ELF + `example.sh`). ShearHash-v3, magic `shear-testnet-v2`. Do **not** recut **1.6** binary. Do **not** recut **1.5**. Do **not** recut Shear-Miner **1.1** / **1.0**. No macos miner zip on 1.6.

**Updated:** 2026-09-09 — **[testnet] Shear wallet 0.29** on tag (`rgsneddon/shear-testnet` tag **`0.29`**, commit `ed71fa9`). Title **`[testnet] Shear wallet 0.29`**. First live genesis bind drops leftover pre-reset txs (old session has no genesis). FlyClient locators restored (`1,2,4,…tip`). Pool miners table heading **Hashes reported**. Live static is `/opt/shear-pool/pool/public` (nginx www); process cwd **worthy** `/opt/shear-worthy`. **`/opt/shear-pool` withdraw is tomorrow, not done now.** Mac `shear-wallet-0.29-macos.dmg` sha256 `994617218385fd3adfef404b0cf9912e3f646c335d827290b1629ec333e43b85` (Developer ID + notarized + stapled, notary `33e495e7-b612-4898-88f7-78198d9e34f1`). Android `shear-wallet-0.29-android.apk` sha256 `5eae82a4483968aef6d2fa57cc2d1c938c548b36ef96169206098df96ae47296` (versionName **0.29**, versionCode **41**). Linux `shear-wallet-0.29-linux.zip` sha256 `807481070f5c39cea7cd58d81ed6c3f6c3d8b291a32fd0a91adfd9655594331b` (ELF `shear_wallet`, no miner). Arch `shear-wallet-0.29-archlinux.zip` sha256 `e9f97c02653eec521fcb3f2236de7d9466d7101c1bb56e2e12c0577e159b18d6` (`pkgver=0.29`). **No iOS zip. No Windows Flutter zip on this tag** (gh token lacks `workflow` scope). **Do not attach leftover zips from the dead Windows laptop.** Miner pin **ShearK 1.6**. Flutter file version `0.29.0+41` is not the pin. **Tag `0.28` stays.** Do **not** recut **0.29**. Do **not** recut **0.28**. Canonical GitHub tree is **`rgsneddon/shear-testnet`**. Keep **`rgsneddon/ShearK`** and **`rgsneddon/handoff`**. Duplicate `rgsneddon/shear`, `rgsneddon/shear-pool`, `rgsneddon/shear-wallet` are archived.

**New Win10 — 0.29 clone block — superseded.** Disk was formatted 2026-09-11. Use the **0.30** bootstrap at the top of this file. Do **not** `git -C` a path that does not exist.

**Updated:** 2026-09-09 — **[testnet] Shear wallet 0.28** leftover **on tag** (`rgsneddon/shear-testnet` tag **`0.28`**, commit `a0d783e`). Title **`[testnet] Shear wallet 0.28`**. Wallet **reads headers 1…tip** (FlyClient locators removed). skipFlow only after **1000 confirms**; prune drops fat sample/share bodies only; money vouts and headers stay. P2P IBD catch-up deployed (locator + seed redial). Pool public H/s is miner hashes/elapsed (no EMA/hold spikes) on **worthy** `/opt/shear-worthy` — **`/opt/shear-pool` withdraw is tomorrow, not done now.** Mac `shear-wallet-0.28-macos.dmg` sha256 `5c6e2cd7463518c8f0c58f160934ab6b20aefda9ed1cc1a670e005246189c507` (Developer ID + notarized + stapled, notary `5c258af2-a8cf-42ed-884c-b278187eb880`). Android `shear-wallet-0.28-android.apk` sha256 `67df5ad10845b936e303ebe6f1a350dc5d94634c23a4ec0be16e4d608500e1e0` (`aapt` versionName **0.28**, versionCode **40**). Linux `shear-wallet-0.28-linux.zip` sha256 `397447301169cbc9a374c24b8a7095113ba639af6a5520f228e7d158e5cef6b6` (ELF `shear_wallet`, no miner). Arch `shear-wallet-0.28-archlinux.zip` sha256 `5ddb1b083d89c3a1f6a40b4f02976be00c97b29c0152877bc7418cb5460687b0` (`pkgver=0.28`). **No iOS zip. No Windows Flutter zip on this tag** (gh token lacks `workflow` scope). **Do not attach leftover zips from the dead Windows laptop.** Miner pin **ShearK 1.6**. Flutter file version `0.28.0+40` is not the pin. **Tag `0.27` stays.** Do **not** recut **0.28**. Do **not** recut **0.27**.

**Windows laptop — wallet 0.28 leftover — superseded.** Disk formatted. **0.30 Windows zip is on tag.** Do **not** recut. Do **not** `git -C` a path that does not exist. Do **not** attach leftover zips from the dead disk.

ShearK **1.6** live hashes are at the top of this file (`879a0024…` windows / `e04e8b57…` linux). Older `dcfd9df2…` / `d6497082…` were the pre-`example.bat` restamp — ignore. Do **not** recut **1.6**. Do **not** recut **1.5**. Do **not** recut Shear-Miner **1.1** / **1.0**.

**Updated:** 2026-09-07 — **[testnet] Shear wallet 0.27** leftover **on tag** (`rgsneddon/shear-testnet` tag **`0.27`**, commit `4a197e1`). Title **`[testnet] Shear wallet 0.27`**. Whitepaper preview **`#view=FitH`**. Reserve **Your deposits** is a two-row scrollable viewport. Tab ListView offset survives the 1s tick. Vortex **Remove vortice** drops a pasted vort1 from **this wallet only** (origin unchanged); The Reserve cannot be removed. Levy still 50/50 finder / Reserve vault, cap **0.001 SHE**. Mac `shear-wallet-0.27-macos.dmg` sha256 `144ae73633eca22558d9dfcd07a10dd5b4d36c5b72227b869619ad3768fa6df3` (Developer ID + notarized + stapled, notary `289cf31e-4ba7-4412-9a30-fdd728b36b04`). Android `shear-wallet-0.27-android.apk` sha256 `425b5168f94354a1692804a820f9c1c1f44d49fa91b6148d22e8dcc72c61a01f` (`aapt` `application-label:'Shear 0.27'`, versionName 0.27, versionCode 39). **No iOS zip.** Laptop attached Windows/Linux/Arch to **this same** `0.27` (zip-root Flutter `shear_wallet.exe`, title **Shear 0.27**, **no miner inside**): `shear-wallet-0.27-windows.zip` sha256 `99f7f5a67eb87a59c0c0af38cc2de192b1b11add85bd808a3528cf7d1f4f6ba8`, `-linux.zip` sha256 `c1a98273498a6838603e99e13c9cd753e3f36e7866be497d315112b07f4ad103` (ELF `7f454c46`), `-archlinux.zip` sha256 `1955d8330664ee9c8f3d13b8367b5e93c646a52de89fd0339b3be07b46250322` (`pkgver=0.27`). Public site WALLET pin **0.27**. **Tag `0.26` stays** (dmg `716a0bd01fa7fd5ecaac00bb49773c215ae50c42f41c10285ce04dc16290bd6d`, apk `b7686576490fd5bb7965be0e47da2e709b1d328999440e734ecc10da52cd511f`). Do **not** recut **0.27**. Do **not** recut **0.26**. Miner pin **ShearK 1.5**. Flutter file version `0.27.0+39` is not the pin.

**Windows laptop — wallet 0.27 leftover — on tag:**

```
git -C ~/handoff pull
git -C ~/shear-testnet pull

# Cut Windows/Linux/Arch for pin 0.27. Same tag. No miner inside.
python wallet/pack/zip_windows.py
# WSL: wallet/pack/zip_linux.sh
gh release upload 0.27 shear-wallet-0.27-windows.zip shear-wallet-0.27-linux.zip shear-wallet-0.27-archlinux.zip --repo rgsneddon/shear-testnet
```

**Updated:** 2026-09-07 — **[testnet] Shear wallet 0.26** leftover **on tag** (`rgsneddon/shear-testnet` tag **`0.26`**, commit `0cd9d45`). Title **`[testnet] Shear wallet 0.26`**. Flow Send keeps **sent** (green neon) / **not sent - try again** (red neon) on the tab. Shearview lists Flow at **1 conf** as **pending sending / receiving**; pending drops at **6**, row stays **sent / received**. Continuum pies: sender **sending**, recipient **receive**. Levy **never exceeds 0.001 SHE** (live pool `rgsneddon/shear-pool` **`43f709c`**). Mac `shear-wallet-0.26-macos.dmg` sha256 `716a0bd01fa7fd5ecaac00bb49773c215ae50c42f41c10285ce04dc16290bd6d` (Developer ID + notarized + stapled, notary `80812f59-e72e-4e1b-b081-89feb4a54c27`). Android `shear-wallet-0.26-android.apk` sha256 `b7686576490fd5bb7965be0e47da2e709b1d328999440e734ecc10da52cd511f` (`aapt` `application-label:'Shear 0.26'`, versionName 0.26, versionCode 38). **No iOS zip.** Laptop attached Windows/Linux/Arch to **this same** `0.26` (zip-root Flutter `shear_wallet.exe`, title **Shear 0.26**, **no miner inside**): `shear-wallet-0.26-windows.zip` sha256 `3e4947b8d7b0e292c0726b0b2459a295337380aa7d04ccb7c5c29e7ff8f3e665`, `-linux.zip` sha256 `f6ca024063860ed461c6bfa772c7aedbbadcf30f8c98a9f5293a372efb154a04` (ELF `7f454c46`), `-archlinux.zip` sha256 `d334d0a7b9747a57c981521730aaaa3164da0a073ea986120f326ca1fe7efd5c` (`pkgver=0.26`). Public site WALLET pin **0.26**. **Tag `0.25` stays** (dmg `c81981870688ffa5a46b72546c5241995f4ee3f6f4aadcdd43fdeb04a88a63b7`, apk `d057c5bec48f7e0a5d74dadf77c6fc67e079e5a1a8e717d76ac1024ea2b2582b`). Do **not** recut **0.26**. Do **not** recut **0.25**. Miner pin **ShearK 1.5**. Flutter file version `0.26.0+38` is not the pin.

**Windows laptop — wallet 0.26 leftover — on tag:**

```
git -C ~/handoff pull
git -C ~/shear-testnet pull

# Cut Windows/Linux/Arch for pin 0.26. Same tag. No miner inside.
python wallet/pack/zip_windows.py
# WSL: wallet/pack/zip_linux.sh
gh release upload 0.26 shear-wallet-0.26-windows.zip shear-wallet-0.26-linux.zip shear-wallet-0.26-archlinux.zip --repo rgsneddon/shear-testnet
```

**Updated:** 2026-09-07 — **[testnet] Shear wallet 0.25** leftover **on tag** (`rgsneddon/shear-testnet` tag **`0.25`**, commit `defafb0`). Title **`[testnet] Shear wallet 0.25`**. After a sealed epoch vote the Vortex pane **remembers** the choice: green check on the selected option, other boxes gone, **Cast vote** gone. **Your vote:** glow box below Vote results. Hashbonus **`Miner's HashBonus now = `** with 11-decimal SHE. **`Oracle observed Apr *.**%`**. Your sums left and justified. Mac `shear-wallet-0.25-macos.dmg` sha256 `c81981870688ffa5a46b72546c5241995f4ee3f6f4aadcdd43fdeb04a88a63b7` (Developer ID + notarized + stapled). Android `shear-wallet-0.25-android.apk` sha256 `d057c5bec48f7e0a5d74dadf77c6fc67e079e5a1a8e717d76ac1024ea2b2582b` (`aapt` `application-label:'Shear 0.25'`). **No iOS zip.** Laptop: attach Windows/Linux/Arch to **this same** `0.25`. Public site WALLET pin **0.25**. **Tag `0.24` stays** (dmg `1437af6ec1c53319f81502001190d793c9d71b24613fe3811290e8f9b3020ccf`, apk `67c911787c73962ad4278eb1f3107da4de51c82904182619a2a74e1338f0c4b9`). Do **not** recut **0.25**. Do **not** recut **0.24**. Miner pin **ShearK 1.5**. Flutter file version `0.25.0+37` is not the pin.

**Windows laptop — wallet 0.25 leftover — on tag:**

```
git -C ~/handoff pull
git -C ~/shear-testnet pull

# Cut Windows/Linux/Arch for pin 0.25. Same tag. No miner inside.
python wallet/pack/zip_windows.py
# WSL: wallet/pack/zip_linux.sh
gh release upload 0.25 shear-wallet-0.25-windows.zip shear-wallet-0.25-linux.zip shear-wallet-0.25-archlinux.zip --repo rgsneddon/shear-testnet
```

**Updated:** 2026-09-07 — **[testnet] Shear wallet 0.24** leftover **on tag** (`rgsneddon/shear-testnet` tag **`0.24`**, commit `2c9ee25`). Title **`[testnet] Shear wallet 0.24`**. Continuum mempool levy on Reserve **lock** and **vote** (one Flow **L** each, quoted from current mempool depth at that step). Continuum spendable pays **L**; vote owner field stays portal dest. Live pool `rgsneddon/shear-pool` **`4efae25`** on `/opt/shear-pool` (lock/vote mempool **L**; Continuum levy row on seal). Mac `shear-wallet-0.24-macos.dmg` sha256 `1437af6ec1c53319f81502001190d793c9d71b24613fe3811290e8f9b3020ccf` (Developer ID + notarized + stapled). Android `shear-wallet-0.24-android.apk` sha256 `67c911787c73962ad4278eb1f3107da4de51c82904182619a2a74e1338f0c4b9` (`aapt` `application-label:'Shear 0.24'`). **No iOS zip.** Laptop attached Windows/Linux/Arch to **this same** `0.24` (zip-root Flutter `shear_wallet.exe`, title **Shear 0.24**, **no miner inside**): `shear-wallet-0.24-windows.zip` sha256 `580062142ec6e83490d7eb686b71a9204ec1df201fc30ffb527d5a7893a0a13f`, `-linux.zip` sha256 `f9a41361cdabbf1d501b0ed6a18f920dc96bd36d6b6dc1eb0c5fd107e1c5c5f1` (ELF `7f454c46`), `-archlinux.zip` sha256 `6ce1057ff28e04cd15f44f6b7cd94775d39029b943db656fc1638180912eafb9` (`pkgver=0.24`). **Tag `0.23` stays** (dmg `8052ef45c417ee2b8c6ca3b49bba0fa9172f65fd1c2c38c6657ca11131603f13`, apk `0c0b532fcb54fb692383cae655fa06e7bf3e596ad2b7d59a5be801d5cda9e3d7`). Do **not** recut **0.24**. Do **not** recut **0.23**. Miner pin **ShearK 1.5**. Flutter file version `0.24.0+36` is not the pin.

**Windows laptop — wallet 0.24 leftover — on tag:**

```
git -C ~/handoff pull
git -C ~/shear-testnet pull

# Cut Windows/Linux/Arch for pin 0.24. Same tag. No miner inside.
python wallet/pack/zip_windows.py
# WSL: wallet/pack/zip_linux.sh
gh release upload 0.24 shear-wallet-0.24-windows.zip shear-wallet-0.24-linux.zip shear-wallet-0.24-archlinux.zip --repo rgsneddon/shear-testnet
```

**Updated:** 2026-09-06 — **[testnet] Shear wallet 0.23** leftover **on tag** (`rgsneddon/shear-testnet` tag **`0.23`**, commit `e34c0e6`). Title **`[testnet] Shear wallet 0.23`**. **Cast vote** (not Update vote). First ≥π vote uses **portal dest-opening** so Sign is not **`not_owner`**. Second vote stays **`vote_locked`**. Vortex: **CURRENT HASHBONUS…** glow box; Your sums nested; APR glow box. AppBar: `n% synchronising...` / `no network` / `100% synchronised` (no fill bar). Live pool `rgsneddon/shear-pool` **`5117fe1`** on `/opt/shear-pool` admits the same vote **after tally is ok** (`reserveVote` before `queueSend`; queued `voteTx.from` is the portal dest when that dest-opening admitted the vote so `applyReserveBlock` replay counts it; a rejected portal vote does not enter the template). Mac `shear-wallet-0.23-macos.dmg` sha256 `8052ef45c417ee2b8c6ca3b49bba0fa9172f65fd1c2c38c6657ca11131603f13` (Developer ID + notarized + stapled). Android `shear-wallet-0.23-android.apk` sha256 `0c0b532fcb54fb692383cae655fa06e7bf3e596ad2b7d59a5be801d5cda9e3d7` (`aapt` `application-label:'Shear 0.23'`). **No iOS zip.** Laptop: attach Windows/Linux/Arch to **this same** `0.23`. Public site WALLET pin **0.23**. **Tag `0.22` stays** (dmg `3ecf04f4392b56edb5c22e4b92b3f42ed99eb5399575df8f92197b612d4c29fe`, apk `d2a0d843b9a1427a698f8700973342a3fcd76f5ebd0f1b36c9fb5cf75f5de48b`). Do **not** recut **0.23**. Do **not** recut **0.22**. Miner pin **ShearK 1.5**. Flutter file version `0.23.0+35` is not the pin.

**Windows laptop — wallet 0.23 leftover — on tag:**

```
git -C ~/handoff pull
git -C ~/shear-testnet pull

# Cut Windows/Linux/Arch for pin 0.23. Same tag. No miner inside.
python wallet/pack/zip_windows.py
# WSL: wallet/pack/zip_linux.sh
gh release upload 0.23 shear-wallet-0.23-windows.zip shear-wallet-0.23-linux.zip shear-wallet-0.23-archlinux.zip --repo rgsneddon/shear-testnet
```

**Updated:** 2026-09-06 — **Live pool deployed Reserve epochBps + proven hash bonus.** `rgsneddon/shear-pool` **`fb9273a`** (law **`61dfe8c`**) on `/opt/shear-pool`. MAGIC `shear-testnet-v2` unflipped. `epochBps` **264**, `hashBonusNanos` **1**, votes sealed (`vote_locked`). Explorer Enacted tile **open epoch**. Height **1448**, locked **18.48 SHE** (honest; was 4 SHE at freeze). Unit **active**, NRestarts **0**. Raskul hasher 1 thread left running. Snapshot still `/root/snapshots/shear-pool-reserve-bonus-pre-20260906.tar.gz` sha256 `ce12b80e8cadd76b897e264408fde2267eec4feb43d2e0059f9db04a74809023`. **Do not cut a mainnet genesis zip. Do not flip MAGIC until 11 September 2026 21:00 UK.** Miner stays **ShearK 1.5**. Product **0.4**.

**Updated:** 2026-09-06 — **[testnet] Shear wallet 0.22** leftover **on tag** (`rgsneddon/shear-testnet` tag **`0.22`**, commit `d978944`). Title **`[testnet] Shear wallet 0.22`**. **YOUR VOTE WILL BE SEALED** / type **CONFIRM** then **reserve-vote-sign**. Epoch interest is frozen **epochBps** (genesis **264**). Mac `shear-wallet-0.22-macos.dmg` sha256 `3ecf04f4392b56edb5c22e4b92b3f42ed99eb5399575df8f92197b612d4c29fe` (Developer ID + notarized + stapled). Android `shear-wallet-0.22-android.apk` sha256 `d2a0d843b9a1427a698f8700973342a3fcd76f5ebd0f1b36c9fb5cf75f5de48b` (`aapt` `application-label:'Shear 0.22'`). **No iOS zip.** Laptop: attach Windows/Linux/Arch to **this same** `0.22` (zip-root Flutter `shear_wallet.exe`, title **Shear 0.22**, **no miner inside**). Public site WALLET pin **0.22**. **Tag `0.21` stays** (Mac dmg sha256 `92bbc98bf151521507e84d7bf54aff835251542cfbd4629c2e999546c0b1d38f`, apk `3288d6655a833fa399395a712949ced7c89da751f24a3e9ee5ce6b7b2923d496`). Do **not** recut **0.22**. Do **not** recut **0.21**. Miner pin **ShearK 1.5**. Flutter file version `0.22.0+34` is not the pin.

**Windows laptop — wallet 0.22 leftover — on tag:**

```
git -C ~/handoff pull
git -C ~/shear-testnet pull

# Cut Windows/Linux/Arch for pin 0.22. Same tag. No miner inside.
python wallet/pack/zip_windows.py
# WSL: wallet/pack/zip_linux.sh
gh release upload 0.22 shear-wallet-0.22-windows.zip shear-wallet-0.22-linux.zip shear-wallet-0.22-archlinux.zip --repo rgsneddon/shear-testnet
```

**Updated:** 2026-09-06 — **Live pool snapshot (pre Reserve epochBps + proven hash bonus).** Git tag **`snapshot/reserve-bonus-pre-20260906`** on `rgsneddon/shear-pool` **`f5888d2`** and `rgsneddon/shear-testnet` **`0d7fa8d`**. Live cwd **only** `/opt/shear-pool`. Tarball `/root/snapshots/shear-pool-reserve-bonus-pre-20260906.tar.gz` sha256 `ce12b80e8cadd76b897e264408fde2267eec4feb43d2e0059f9db04a74809023` (taken 20260906T1942Z; also `shear-pool-reserve-bonus-pre-20260906-20260906T1942Z.tar.gz`). Datadir `/root/snapshots/testnet-v2-reserve-bonus-pre-20260906.tar.gz` sha256 `8bc4c2fc1e486d3331df6829b077b971361524341345c0810b3ac7ebe8ef3223`. Height **1366**, MAGIC `shear-testnet-v2`, locked 4 SHE. **Do not cut a mainnet genesis zip. Do not flip MAGIC until 11 September 2026 21:00 UK.** Rollback: stop unit, tar xzf pool tarball into `/opt`, start unit. Miner stays **ShearK 1.5**. Product **0.4**.

**Updated:** 2026-09-06 — **[testnet] Shear wallet 0.21** leftover **on tag** (`rgsneddon/shear-testnet` tag **`0.21`**, commit `0d7fa8d`). Title **`[testnet] Shear wallet 0.21`**. Signed Reserve votes post `kind=vote`; nodes collate program tallies into `/api/vault/reserve` so every wallet paints the same `+ / − / hold`. Continuum **VAULT** and **Extra minted** follow those vault totals. Vote controls sit under Overall sums when THIS portal holds ≥ π. AppBar is a green fill bar plus `n% synchronised`; **HONEST is gone**. Explorer full-width **COINS IN THE RESERVE VAULT**. Live pool `rgsneddon/shear-pool` **`f5888d2`** on `/opt/shear-pool` (vote tx + stats vault fields). Mac `shear-wallet-0.21-macos.dmg` sha256 `92bbc98bf151521507e84d7bf54aff835251542cfbd4629c2e999546c0b1d38f` (Developer ID + notarized + stapled). Android `shear-wallet-0.21-android.apk` sha256 `3288d6655a833fa399395a712949ced7c89da751f24a3e9ee5ce6b7b2923d496` (`aapt` `application-label:'Shear 0.21'`). **No iOS zip.** Laptop attached Windows/Linux/Arch to **this same** `0.21` (zip-root Flutter `shear_wallet.exe`, title **Shear 0.21**, **no miner inside**): `shear-wallet-0.21-windows.zip` sha256 `67e944e194fb7adf5daa169d9e160fc1ad44cb646f48c0aa85945a9f617f29c6`, `-linux.zip` sha256 `a8e81fd3ac33d50ab27ea5da31ced27e26a6df01f51b66627e237f68b359c2f9` (ELF `7f454c46`), `-archlinux.zip` sha256 `dfd49756c4251f0c3980e096bdfd641a55b43a8778a90b50f922058b1a3037b7` (`pkgver=0.21`). Public site WALLET Windows/Linux/Arch pin **0.21**. **Tag `0.20` is gone.** Do **not** recut **0.21**. Do **not** restore **0.20**. Miner pin **ShearK 1.5**. Flutter file version `0.21.0+33` is not the pin. Standing rule: a new wallet pin deletes previous wallet GitHub releases.

**Windows laptop — wallet 0.21 leftover — on tag:**

```
git -C ~/handoff pull
git -C ~/shear-testnet pull

# Cut Windows/Linux/Arch for pin 0.21. Same tag. No miner inside.
python wallet/pack/zip_windows.py
# WSL: wallet/pack/zip_linux.sh
gh release upload 0.21 shear-wallet-0.21-windows.zip shear-wallet-0.21-linux.zip shear-wallet-0.21-archlinux.zip --repo rgsneddon/shear-testnet
```

**Updated:** 2026-09-05 — **Live pool snapshot (current tree).** `rgsneddon/shear-pool` **`91f9ccc`** branch/tag **`snapshot/mainnet-cut-20260911`**. Live cwd **only** `/opt/shear-pool`. Tarball `/root/snapshots/shear-pool-mainnet-cut-20260911.tar.gz` sha256 `850e8069cc61c192f6ba6a604042a516146f392235d33c2ce83d7c189b9d1220` (taken 20260905T2114Z; also `shear-pool-mainnet-cut-20260905T2114Z.tar.gz`). Datadir `/root/snapshots/testnet-v2-mainnet-cut-20260911.tar.gz` sha256 `a29b63fb8361364e75f4d52739e23bb28a48fbcc479017553939c476bd109cdf`. Height 346, 3 miners, NODES ONLINE = p2p `syncedOnline` (1 on this one-node testnet), AVG BLOCK TIME = sealed-chain mean (~135s). One pool tree; `/opt/shear-v2/pool` and `/opt/shear/pool` symlink in. **Do not cut a mainnet genesis zip. Do not flip MAGIC until 11 September 2026 21:00 UK.** Miner stays **ShearK 1.5**. Product **0.4**.

**Updated:** 2026-09-05 — **[testnet] Shear wallet 0.20** — **SUPERSEDED. Do not restore.** Tag **`0.20` is gone.** Laptop had attached Windows/Linux/Arch to that tag (`windows` sha256 `69757fb2466c07e13b1ed6e2ec3c16016695e8de30137d7d2a033445beb4de20`, `linux` `364004ee8bedf81577684ed43d505e943ca3c125df7b611a0e66c7e3b15714e9`, `archlinux` `3734f1c48603866fc6c18818a68ce84c1938ad6574191707e66ce3c66270cf53`); those zips went with the tag. Miner stays **1.5**. Do **not** `gh release upload 0.20`. Attach Windows/Linux/Arch to **`0.21`**.

**Windows laptop — wallet 0.20 leftover — superseded.** Tag **`0.20` is gone.** Do **not** `gh release upload 0.20`. Attach Windows/Linux/Arch to **`0.21`**.

**Updated:** 2026-09-05 — **Mainnet-cut freeze (UI + single live tree).** `rgsneddon/shear-pool` **`8c189f3`** branch/tag **`snapshot/mainnet-cut-20260911`**. Live cwd is **only** `/opt/shear-pool` (unit WorkingDirectory + tree.conf). Duplicate pool code at `/opt/shear-v2/pool` and `/opt/shear/pool` is now a symlink into `/opt/shear-pool/pool`. `/var/www/pool.shear.digital` is a symlink to `/opt/shear-pool/pool/public`. Wallets stay at `/opt/shear-v2/wallet*`. `/opt/shear-pre-recut-120` and `/var/lib/shear/testnet-0.1` left in place. Miner dedicated Blocks and withdrawals: newest first, **10-row** in-table scroll. Pool miners table dropped Accepted work / Stale shares. Snapshot `/root/snapshots/shear-pool-mainnet-cut-20260911.tar.gz` sha256 `65d9e80d61cbae8a26f253ab898ee8c70c9fdb8f64b4236529d68d0b67b78bf3` (taken 20260905T2022Z; also `shear-pool-mainnet-cut-20260905T2022Z.tar.gz`). Datadir `/root/snapshots/testnet-v2-mainnet-cut-20260911.tar.gz` sha256 `b773d2d761ac7a9c9c3e2ee8573b06a278778a6c5db9cb35cf84335ec6946dad`. Dup-repo archives `/root/snapshots/archive-dup-pool-repos-20260905T2019Z/`. `rgsneddon/shear-testnet` **`89e3b1f`** also tagged `snapshot-mainnet-cut-20260911` (MAIN nav no DAG). **Do not cut a mainnet genesis zip. Do not flip MAGIC until 11 September 2026 21:00 UK.** Miner stays **ShearK 1.5**. Product version string on the pool remains **0.4**.

**Updated:** 2026-09-05 — **Deployed.** `rgsneddon/shear-pool` **`82a5d0d`** and `rgsneddon/shear-testnet` **`00afd89`** on Dedicated-de `/opt/shear-v2` (running unit) + `/opt/shear-pool`. PROP on the live accept path: `creditRound(provenWorkRows)` by session shareBits. First EIP-712 `/api/pool/withdraw` after unsigned pending is `ok`. Miner page green **sent**. Wallet pin **0.20** sources at `/opt/shear-v2/wallet` and `/opt/shear-v2/wallet-0.20`. Explorer **VAULT** label on explorer.shear.digital. **Testnet chain reset from height 0** (kept `pool-miner.json` + admin keys). Snapshot `/root/snapshots/testnet-v2-pre-prop-20260905T0817Z.tar.gz` sha256 `04c466a3441424178f225ae8290ab5475a6988d0ffadfc25cb7066fed4653431`. `shear-pool` + `sheark-miner` restarted. Mac/Android **0.20** installer was not on the tag at this deploy (gate was pin + tests). **Later:** tag **`0.20`** holds macos.dmg + android.apk. Do **not** restore **0.19**. Miner stays **ShearK 1.5**. Product version string on the pool remains **0.4**.

**Updated:** 2026-09-05 — **shear-pool 0.4** follow-up (`1532996`): Flow `/api/pool/withdraw` spends the **pool dest** for amount+levy (same as miner HTML pull). Dropped `levy_sponsor` on `poolFeeDest()`. Live Dedicated-de `/opt/shear-pool/pool/src/wallet_api.js` rsynced; `shear-pool` restarted. Tag **`0.4`** moved to `1532996`. `test_pool.js` 38/38 (90s restamp, product 0.4, no share_timeout). `rgsneddon/shear-testnet` `4a3527a` matches (`poolWithdrawTx.sponsor = from`). Wallet pin later moved to **0.20**. Do **not** restore **0.19**. Do **not** restore **0.18**.

**Updated:** 2026-09-04 — **[testnet] Shear wallet 0.19** — **SUPERSEDED. Do not restore.** Tag **`0.19` is gone.** Miner stays **1.5**. Do **not** `gh release upload 0.19`. Attach Windows/Linux/Arch to **`0.21`**.

**Windows laptop — wallet 0.19 leftover — superseded.** Tag **`0.19` is gone.** Do **not** `gh release upload 0.19`. Attach Windows/Linux/Arch to **`0.21`**.

**Updated:** 2026-09-04 — **[testnet] Shear wallet 0.18** — **SUPERSEDED. Do not restore.** Tag **`0.18` is gone.** Miner stays **1.5**. Do **not** `gh release upload 0.18`.

**Windows laptop — wallet 0.18 leftover — superseded.** Tag **`0.18` is gone.** Do **not** `gh release upload 0.18`. Attach Windows/Linux/Arch to **`0.21`**.

**Updated:** 2026-09-03 — **[testnet] Shear wallet 0.17** — **SUPERSEDED. Do not restore.** Tag **`0.17` is gone.** Miner stays **1.5**. Do **not** `gh release upload 0.17`.

**Updated:** 2026-09-02 — **[testnet] Shear wallet 0.16** leftover **on tag** (`rgsneddon/shear-testnet` tag **`0.16`**, commit `74eb9f5`). Title **`[testnet] Shear wallet 0.16`**. Splash Unlock with biometrics after Enable biometrics is sealed (Mac Touch ID entitlement). Continuum Integral Q is network circulating supply with a `(circulation)` advisory. Receive QR hidden until Show QR code. Admin Sign dest-opening matches the dest spent. Mac `shear-wallet-0.16-macos.dmg` sha256 `43afd58f37239f682942d505048460e858403153e813cbd8d3f0bb7b26b2e964` (Developer ID + notarized + stapled). Android `shear-wallet-0.16-android.apk` sha256 `c5d9c50cc01c15a2196e456a8d58194d5b923b946d6c1e0068c67621b60c5ad0` (`aapt` `application-label:'Shear 0.16'`). **No iOS zip.** Laptop attached Windows/Linux/Arch to **this same** `0.16` (zip-root Flutter `shear_wallet.exe`, title **Shear 0.16**, **no miner inside**): `shear-wallet-0.16-windows.zip` sha256 `04ef7b4b51a410a22ff8710c84869e2fe5cd83cea86dcc223f8d51de31ac293d`, `-linux.zip` sha256 `ea744cde3f71b2d446f899d8d6030c5a03efbb68b41b73414a99f836bb9002f6` (ELF `7f454c46`), `-archlinux.zip` sha256 `37c208fb0af96a165db0936d39c4910641f03624e1d6f444c4b0b485b57f8da5` (`pkgver=0.16`). Public site WALLET Windows/Linux/Arch pin **0.16**. Do **not** recut **0.16**. Do **not** restore **0.15** / **0.14** / **0.13** / **0.12**. Miner pin **ShearK 1.5**. Flutter file version `0.16.0+28` is not the pin. **Standing rule:** a new wallet pin deletes previous wallet GitHub releases (and their tags) so only the current pin is downloadable. Tag **`0.15`** is gone. Current testnet repos: **`rgsneddon/shear-testnet`** + **`rgsneddon/shear-pool`**. Keep **`rgsneddon/ShearK`** and **`rgsneddon/handoff`**. GitHub **`rgsneddon/shear`** is gone. Do **not** delete the local `/Users/russellsneddon/shear` folder.

**Windows laptop — wallet 0.16 leftover — on tag:**

```
git -C ~/handoff pull
git -C ~/shear-testnet pull   # or the local shear clone that tracks rgsneddon/shear-testnet

# Cut Windows/Linux/Arch for pin 0.16. Same tag. No miner inside.
# zip_windows.py + WSL zip_linux.sh. Zip root Flutter shear_wallet.exe, title Shear 0.16.
# pkgver=0.16. Do not recut 0.16. Do not restore 0.15, 0.14, 0.13 or 0.12. Do not attach Darwin as *-linux.zip.
python wallet/pack/zip_windows.py
# WSL: wallet/pack/zip_linux.sh
gh release upload 0.16 shear-wallet-0.16-windows.zip shear-wallet-0.16-linux.zip shear-wallet-0.16-archlinux.zip --repo rgsneddon/shear-testnet
```

**Updated:** 2026-09-02 — **[testnet] Shear wallet 0.15** — **SUPERSEDED. Do not restore.** Tag **`0.15` is gone.** Miner stays **1.5**. Do **not** `gh release upload 0.15`.

**Updated:** 2026-09-02 — **[testnet] Shear wallet 0.14** — **SUPERSEDED. Do not restore.** Tag **`0.14` is gone** (laptop had attached Windows/Linux/Arch to that tag; those zips went with it). Miner stays **1.5**. Do **not** `gh release upload 0.14`.

**Updated:** 2026-09-02 — **[testnet] Shear wallet 0.13** — **SUPERSEDED. Do not restore.** Tag **`0.13` is gone.** Miner stays **1.5**.

**Updated:** 2026-09-02 — **0.12 must not come back.** Tag **`0.12` is gone.** Do **not** `gh release upload 0.12`. Miner pin **ShearK 1.5**.

**Updated:** 2026-09-02 — **shear-pool** (`rgsneddon/shear-pool` `3ec9e31`) on Dedicated-de `/opt/shear-pool`. Dest-opening required for Flow send. Admin overlay only after `LOCKITUP`. Operators send only spendable (not miner coins); dest wallet signs she1 + ssa1 + amount. Unique `vort1.` per mint.

**Updated:** 2026-09-02 — **[testnet] Shear wallet 0.12** — **SUPERSEDED. Do not restore.** Historical leftover (commit `9675632`). Tag **`0.12` is gone.** Miner stays **1.5**.

**Updated:** 2026-09-02 — **shear-pool** (`rgsneddon/shear-pool`). Repo does **not** auto-lock. Dedicated-de testnet Flow is **unlocked** (no `SHEAR_POOL_WALLET_LOCK` on the live drop-in). Lock from the admin desk (`LOCKITUP`) at mainnet on 11 September 2026 — do not re-set the env on testnet. Miner pulls (90h cooldown) still spend the pool wallet. Admin desk: pool holdings + confirmed miner withdrawals. Do **not** recut wallet **0.11**.

**Updated:** 2026-09-02 — **GOD Join how-to on Dedicated-de.** `https://god.restoreprivacy.online` and `https://admin.shear.digital` serve the same page (A record already on de). Human-cadence GNFP→Shear mainnet how-to: wait for the published snapshot; Backup Join key; Vortex → The Join; pending until 6 confirms; leftover stays in the vault; same key is already claimed. Pins on the page: GNFP **0.2.6**, Shear testnet **0.11**. Do **not** arm mainnet Join genesis. Do **not** edit DAG/brand CSS.

**Updated:** 2026-09-02 — **GNFP wallet 0.2.6 paint-0 after Join — leftover on tag.** Mac/Android **on tag** `rgsneddon/gnfp-wallet` **`v0.2.6`** (commit `86fc48a`). Title **`$GNFP core wallet v0.2.6`**. After `join_clear`, spendable paints **0** (0.2.5 kept the old sum). Android installer / home-screen name is **`$GNFP core wallet v0.2.6`** (0.2.5 still showed **v0.1.9**). Unique join1 per gnfp1. Does not mine. Mac `gnfp-wallet-0.2.6-macos.dmg` sha256 `8743bc329f5a4d0718f1b626712b9b2323d7356f4d031e5a2c6e945bb4336354` (Developer ID + notarized + stapled). Android `gnfp-wallet-0.2.6-android.apk` sha256 `86d7725d353f3b89212173af917d319174618307cf8402da0512a11f8e68ed5c` (`aapt` `application-label:'$GNFP core wallet v0.2.6'`). macos.zip sha256 `5aab9f401ba24c7c6ee1750b808cb62030ddf2c2b9339b839746bcb593e1ad76`. **No iOS zip.** Laptop attached Windows/Linux/Arch to **this same** `v0.2.6` (**no cminer inside**, title `$GNFP core wallet v0.2.6`, `pack\gnfp-cli.cmd --version` `$GNFP core wallet v0.2.6 (cli)`): `gnfp-wallet-0.2.6-windows.zip` sha256 `aae4ccce07080cc7ce51403726a18e40248bd7c0dbfa638df6efe07c86b9eef3` (zip-root Flutter `gnfp_wallet.exe`), `-linux.zip` sha256 `202b77325ec3975c933a0ddf33c38ee90987a74eead14adfaff14fc850188598` (ELF `7f454c46`), `-archlinux.zip` sha256 `a8f9207f3e3357377d476202f456bddbdb578d33922d25cf3f956e49dda463e4` (`pkgver=0.2.6`). Removed wrong-pin `gnfp-wallet-0.0.2-*` from this tag. Do **not** recut **0.2.5**. Do **not** invent a sibling tag.

**Windows laptop — GNFP wallet 0.2.6 leftover (paint-0 + installer v0.2.6) — on tag:**

```
git -C ~/handoff pull
git -C ~/gnfp-wallet pull   # rgsneddon/gnfp-wallet master, pin 0.2.6

# Paint 0 after join_clear. Installer label v0.2.6. Unique join1. No cminer.
# zip_windows + WSL zip_linux. Title $GNFP core wallet v0.2.6. pkgver=0.2.6
# Do not recut 0.2.5.
gh release upload v0.2.6 gnfp-wallet-0.2.6-windows.zip gnfp-wallet-0.2.6-linux.zip gnfp-wallet-0.2.6-archlinux.zip --repo rgsneddon/gnfp-wallet
```

**Updated:** 2026-09-02 — **GNFP wallet 0.2.5 unique join1 — superseded by 0.2.6.** Mac/Android stay on tag `v0.2.5`. Laptop leftover moves to **0.2.6**. Do **not** recut **0.2.5**.

**Updated:** 2026-09-02 — **[testnet] Shear wallet 0.11** dest-recovery Join leftover **on tag** (`rgsneddon/shear-testnet` tag **`0.11`**, commit `895b586`). Title **`[testnet] Shear wallet 0.11`**. Mac `shear-wallet-0.11-macos.dmg` sha256 `38f72aeaaa0877289b512200b139021d3904ce062d8e5cf836147a9431abbefa`. Android `shear-wallet-0.11-android.apk` sha256 `d1a7dc3cfa8728e6765c30d02183c2048d2c1da87db45003955e3c01a40e019b`. **No iOS zip on GitHub**. **Do not recut 0.10.** Join: dest-at-claim-height remembered; mempool ok is pending; spendable after 6 confirms; vault leftover is not the user’s money. Laptop attached Windows/Linux/Arch to **this same** `0.11` (zip-root Flutter `shear_wallet.exe`, title **Shear 0.11**, **no miner inside**): `shear-wallet-0.11-windows.zip` sha256 `8c8761d1355f3c2fcacb55c6be6098d754d369cd4f9e0c21395040f22c24bb5f`, `-linux.zip` sha256 `92646fc67b058ece2150cc40fb417364257583ab106baf6e5dd58df763efb787` (ELF `7f454c46`), `-archlinux.zip` sha256 `99bfb24e6281969490b0c24d9a4dbbe750b27e3142605f833ec7af93b64bae42` (`pkgver=0.11`). Do **not** attach Darwin as `*-linux.zip`. Miner stays **1.5**. Flutter file version `0.11.0+23` is not the pin. Dedicated-de `/opt/shear-v2/wallet` is **0.11**. Public site WALLET Windows/Linux/Arch downloads now pin **0.11** (`site/index.html` + `site/tests/test_clients.js`; MAIN HTML on Dedicated-de `/var/www/shear.digital/index.html`). WALLET nav on MAIN / POOL / EXPLORER / DAG / MEMPOOL already points at tag **`0.11`**.

**Windows laptop — wallet 0.11 leftover — on tag:**

```
git -C ~/handoff pull
git -C ~/shear-testnet pull   # or the local shear clone that tracks rgsneddon/shear-testnet

# 1) Cut Windows/Linux/Arch for pin 0.11. Same tag. No miner inside.
# zip_windows.py + WSL zip_linux.sh. Zip root Flutter shear_wallet.exe, title Shear 0.11.
# pkgver=0.11. Do not recut 0.10 or 0.9. Do not attach Darwin as *-linux.zip.
python wallet/pack/zip_windows.py
# WSL: wallet/pack/zip_linux.sh
gh release upload 0.11 shear-wallet-0.11-windows.zip shear-wallet-0.11-linux.zip shear-wallet-0.11-archlinux.zip --repo rgsneddon/shear-testnet

# 2) ONLY after those three assets exist on tag 0.11, flip public WALLET platform
#    downloads 0.9 → 0.11. macOS + Android + WALLET nav tags are already 0.11.
#    Files that still pin Windows/Linux/Arch to 0.9:
#      shear/site/index.html
#        data-pack="wallet-windows|linux|archlinux" hrefs
#        pack-JS wallet.windows and wallet.linux URLs
#      shear/site/tests/test_clients.js  (assert 0.11 zips, not 0.9)
#    Other hosts (DAG / POOL / EXPLORER / MEMPOOL) only have WALLET → tag 0.11
#    already — do not edit brand CSS or DAG graph.

# 3) Deploy MAIN HTML to Dedicated-de (host `de`), not Helsinki:
scp site/index.html de:/var/www/shear.digital/index.html
# optional: run site/tests/test_clients.js before scp
```

**Updated:** 2026-09-02 — **[testnet] Shear wallet 0.10** Mac-cut **on tag** (`rgsneddon/shear-testnet` tag **`0.10`**, commit `aedb04b`). Title **`[testnet] Shear wallet 0.10`**. Mac `shear-wallet-0.10-macos.dmg` sha256 `38d3113158f26a8881cbfbe6bdf5364554a45565c395c9dc91c66078159ef392`. Android `shear-wallet-0.10-android.apk` sha256 `659ed63ab85998e28c8ceb8645543a8df3789a156745762721d9ee62d5fbfd47`. **No iOS zip on GitHub** — iPhone install is App Store / TestFlight later, not a downloadable zip. **Windows + Linux + Arch leftover on the Windows laptop:** attach `shear-wallet-0.10-windows.zip` (zip-root Flutter `shear_wallet.exe`, title **Shear 0.10**, **no miner inside**) plus `-linux.zip` and `-archlinux.zip` (`pkgver=0.10`) to **this same** `0.10` tag. Do **not** recut **0.9**. Do **not** attach Darwin as `*-linux.zip`. Miner stays **1.5**. Flutter file version `0.10.0+22` is not the pin. Dedicated-de `/opt/shear-v2/wallet` is **0.10**. Public site: macOS + Android WALLET downloads already pin **0.10**. **Do not switch the Windows / Linux / Arch WALLET dropdown (or pack JS) on https://shear.digital until those three zips are on tag `0.10`.** After upload: in `site/index.html` change the three `data-pack="wallet-windows|linux|archlinux"` hrefs and the `wallet.windows` / `wallet.linux` pack-JS URLs from `0.9` → `0.10`, then rsync that HTML to `/var/www/shear.digital/index.html`.

**Updated:** 2026-09-01 — **Historical Shear wallet leftover on tag (laptop).** Current pin leftover (ShearK-Miner **1.5** + wallet **0.9**) was already on tag. Laptop attached missing older leftover; did **not** recut miner/macos/apk already on those tags. Wallet **0.7** on `rgsneddon/shear-testnet` **`0.7`**: `shear-wallet-0.7-windows.zip` sha256 `ba2f2436f03ab4584457bc457da2fbdef759df89bf273d7c44ab13ff35b287d9` (zip-root Flutter `shear_wallet.exe`, **no miner inside**, title **Shear 0.7**, file version `0.7.0+19`), linux sha256 `7ecac783acb996ba4cde79c379cbda1e3cdd1657e57201c684544553d6357d6f` (ELF `7f454c46`), arch sha256 `638b35c47ed8b2f97cced0e47f3c864a580b9078e8ddf7bdf7d8396d779f8a9f` (`pkgver=0.7`). Wallet **0.5** Windows/Linux/Arch on **the same** miner tag **`0.5`** (miner zips untouched): windows sha256 `bbab520135f256a9de9639284e04652e8d83cb1b86e17adea2f02771b5990f53` (title **Shear 0.5**, file version `0.5.0+17`), linux sha256 `27a4320d6fff1b1bdfa95d2b1e029254a0c0a1df7b5a9b23eca496012dfe5917`, arch sha256 `3a0d7fb7246a57628bdac7d4451599dc430bb8ec036adacf4bdcf85e840a44ff` (`pkgver=0.5`). Wallet **0.1** Linux/Arch on **`0.1`** (Windows zip unchanged `e605be15…`): linux sha256 `1fef18f6fbdffc7da9c0b28303e8cd2396018ec50ad4d9e96e988a1c7681b420`, arch sha256 `d8996e33c16a4a9c396ac42393bea8b0d5f838c2fe47fdf57d73e15875d11fd5` (`pkgver=0.1`). Do **not** recut ShearK **1.5** / wallet **0.9**. Wallet **0.3** still has no Windows/Linux/Arch. No iOS.

**Updated:** 2026-08-31 — **Linux/Arch on tag from Dedicated-de; Windows leftover is PE only.** Amelia rsynced Darwin `ShearK-Miner` / `shearhash.node` onto DE once — that is **not** a GitHub linux zip. `ShearK-Miner-1.5-linux.zip` on `rgsneddon/ShearK` **`1.5`** is **ELF** `0755` sha256 `599701b106118e34724c195388906bc3e458403d8055aa6af33fac320607bb64` (`ShearK-Miner` + `example.sh`). First four bytes **`7f454c46`**, never Mach-O `cffaedfe`. Wallet **0.9** linux/arch also **on tag** `rgsneddon/shear-testnet` **`0.9`**: `shear-wallet-0.9-linux.zip` sha256 `28c497f8d55e0389dea1230eeef83cf26628429fe636f7054ff97dbb777fe378`, `shear-wallet-0.9-archlinux.zip` sha256 `a5f41fa2ce01b924e46c60f6df797fdeb0282e114ff4f4f6c9f6958cdca4cbfa` (`pkgver=0.9`, **no miner inside**). **Do not attach a Darwin binary as `*-linux.zip`.** Mac `ShearK-Miner-1.5-macos.zip` stays the arm64 zip already on `1.5`.

**Windows leftover (PE / Flutter Windows) — on tag.** Native PE `ShearK-Miner-1.5-windows.zip` sha256 `42a2d484dd769c4d4f83c33ccc80630deb4c2c2c281b1f70d9534efe60ff379c` (MZ `4D 5A`). Wallet `shear-wallet-0.9-windows.zip` sha256 `8a4981641c406a5110630fee814e1a6bfb757cc2ac6a46430f53c4d37acd729d`. Do **not** recut linux/macos/arch already on those tags.

**Windows laptop — wallet 0.10 leftover:**

```
git -C ~/handoff pull
# Wallet Windows/Linux/Arch → same shear-testnet tag 0.10.
# zip_windows.py + WSL zip_linux.sh. Zip root Flutter shear_wallet.exe, title Shear 0.10, no miner inside.
# pkgver=0.10. Do not recut 0.9. Do not attach Darwin as *-linux.zip.
gh release upload 0.10 shear-wallet-0.10-windows.zip shear-wallet-0.10-linux.zip shear-wallet-0.10-archlinux.zip --repo rgsneddon/shear-testnet
# AFTER those three are on the tag, update shear.digital WALLET Windows/Linux/Arch links 0.9 → 0.10
# (macOS + Android already 0.10). File: shear/site/index.html then rsync to /var/www/shear.digital/index.html.
```


Do **not** recut ShearK **1.4** or wallet **0.8**. Do **not** invent a sibling tag. Testnet `shear-testnet-v2` genesis was reset 2026-08-31; pool-only node on DE; do not start `shear-node`.

**Updated:** 2026-08-31 — **[Testnet] ShearK-Miner 1.5** Mac-cut **on tag** (`rgsneddon/ShearK` tag **`1.5`**, title **`[Testnet] ShearK-Miner 1.5`**). Holds last linear H/s across a blockfound RandomX-K rebuild. Banner / `--print-config` / login **1.5**. Mac `ShearK-Miner-1.5-macos.zip` sha256 `cbb9c19cd26fc13cc6aca32db5b5bde48b46378a869dbe83d7477549cfad3370` (`ShearK-Miner` + `example.sh`). **Windows + Linux leftover on the Windows laptop:** attach `ShearK-Miner-1.5-windows.zip` (`ShearK-Miner.exe` + `example.bat`) and `ShearK-Miner-1.5-linux.zip` (`ShearK-Miner` + `example.sh`, ELF `0755`) to **this same** `1.5` tag. Do **not** recut **1.4**. DE `.raskul` is **1.5** `--threads 1`.

**Updated:** 2026-08-31 — **[testnet] Shear wallet 0.9** Mac-cut **on tag** (`rgsneddon/shear-testnet` tag **`0.9`**, commit `d4856e1`). Title **`[testnet] Shear wallet 0.9`**. Sign-only pool pull (EIP-712 PoolWithdraw chainId 2701). Mac `shear-wallet-0.9-macos.dmg` sha256 `fb101a54d237496ca26b3315123aada8e4cef678cf58d55836ed7b1fcd33239e` (Developer ID + notarized + stapled). Android `shear-wallet-0.9-android.apk` sha256 `afb5a5558d90aed6a9d5d6df72bf542bf3c39b2de6660811b82463165d0890b9`. Signed pool-withdraw stays on Continuum through prune. **No miner inside.** Dedicated-de `/opt/shear-v2/wallet` is **0.9**. **Windows + Linux + Arch leftover on the Windows laptop:** attach `shear-wallet-0.9-windows.zip` (zip-root Flutter `shear_wallet.exe`, title **Shear 0.9**) plus `-linux.zip` and `-archlinux.zip` (`pkgver=0.9`) to **this same** `0.9` tag. Do **not** recut **0.8**. No iOS.

**Updated:** 2026-09-12 — **Standing cut rule.** Amelia Mac-cut is **macOS + Android**. Dedicated-de packed Linux+Arch **0.30** (ELF). **0.30 Windows zip is on tag** (`8bc28d52…`). Formatted Windows box leftover for **0.30 is done** — clone + download, do **not** recut. Future wallet pins: Windows Flutter zip only, from a **fresh clone**. Do **not** recut an older leftover tag in place. **No iOS.**


**Updated:** 2026-08-31 — **[Testnet] ShearK-Miner 1.4** leftover **on tag** (`rgsneddon/ShearK` tag **`1.4`**, title **`[Testnet] ShearK-Miner 1.4`**). Banner / `--print-config` / stratum login all declare **version 1.4**. One share in flight; pool `busy` is retried, not rejected. Timestamp restamp does not rebuild RandomX K. Pool keeps one job/K per height (mid-round login/vardiff no longer mint `shear-H-N` extras — that was the 1-thread 10× stale). Public pool H/s eases **60s** toward the hasher's own counter (~63% at 1 min, ~95% at 3 min). kyrusfables admin table shows **live** H/s separately. Mac `ShearK-Miner-1.4-macos.zip` sha256 `0a9fb641c69b44e2429ec6061f614dbff74fb282b6572d50279eac5bdc6dad17`. Linux `ShearK-Miner-1.4-linux.zip` sha256 `d345d93bd240c518fb0933f065671a0038647f882d232c9c64b2dd52567f737f` (`ShearK-Miner` + `example.sh`, ELF `0755`). Native PE `ShearK-Miner-1.4-windows.zip` sha256 `def483622fc7a6692f6a63e2ccaa13b7f4dd56d0223fd8d15397ce584fbd19ac` (`ShearK-Miner.exe` + `example.bat`, unsigned — SmartScreen may warn). Do **not** recut ShearK-Miner **1.3** / **1.2** / **1.1** / **1.0** or Shear-Miner **1.1** / **1.0**. Wallet leftover **0.8** **on tag**. DE `.raskul` is now **1.5** (public leftover still **1.4**). Node/pool **0.3** live on DE. No iOS.

**Updated:** 2026-08-31 — **[testnet] Shear wallet 0.8** leftover **on tag** (`rgsneddon/shear-testnet` tag **`0.8`**, commit `e50162a`). Title **`[testnet] Shear wallet 0.8`**. EIP-712 `PoolWithdraw` (chainId 2701); public amounts 9 digits; Flow levy from `mempoolPressure`. Hash bonuses stay coinbase. Mac `shear-wallet-0.8-macos.dmg` sha256 `55e38cff9ae9e11c3f0c4e506fa30b8347f213f6a34813c712b958264dbf6aa0` (Developer ID + notarized). Android `shear-wallet-0.8-android.apk` sha256 `089d742477f828d8ecb37c8c0e4965776b0d523e77458c99f163f0516dad4656`. **Rule for every wallet cut:** Amelia Mac-cut is **macos.dmg + android.apk only**. **Windows / Linux / Arch are always leftover on the Windows laptop** (WSL `build_linux.sh` + `zip_linux.sh`, Windows `zip_windows.py`). Do **not** pack those three from Amelia or Dedicated-de. Laptop attached Windows/Linux/Arch to **this same** `0.8` tag: `shear-wallet-0.8-windows.zip` sha256 `3489163b0bbf4b844412feccb23beef07efb5b35373c14f8ba02b81a6eceddd1` (zip-root Flutter `shear_wallet.exe`, **no miner inside**, window/ProductName **Shear 0.8**), `shear-wallet-0.8-linux.zip` sha256 `0156b0988aba400f3e2b4cd5ad50b82cb6c138e900361d65d256f2fc6b2b9cfd`, `shear-wallet-0.8-archlinux.zip` sha256 `b59a1ea92fc28d73927943ef98c6662d9c12c2989af17e2cbde81edd139f0f51` (`pkgver=0.8`). Flutter file version `0.8.0+20` is not the pin. Dedicated-de `/opt/shear-v2/wallet` is **0.8** (Mac pack rsyncs that pool tree on every wallet cut). Public site WALLET buttons on https://shear.digital (also pool/explorer/mempool) pin **0.8**. Node/pool **0.3** live on DE. Do **not** recut wallet **0.7**. No iOS.

**Updated:** 2026-08-30 — **[testnet] Shear wallet 0.7** leftover **on tag** (`rgsneddon/shear-testnet` tag **`0.7`**, commit `25b8ee5`). Title **`[testnet] Shear wallet 0.7`**. The Reserve vortice is Solidity (`contracts/Reserve.sol`) with an embedded Shear EVM (`crypto/reserve_evm.js`) plus a matching JS vault. Late-epoch deposits unlock a vote but earn no stake. Epoch-end plurality enacts ±1 live hash-bonus unit (ties: no change). Mac `shear-wallet-0.7-macos.dmg` sha256 `a0befb53616d5f19cbcbe66b16e18aa90a06411a20b7ec7a1b732b0f651175ea` (Developer ID + notarized app inside). Android `shear-wallet-0.7-android.apk` sha256 `1d16a91b2273c089a8a32eda104986d8df57e100971070b8b6446206d580c77f`. Laptop attached 2026-09-01: `shear-wallet-0.7-windows.zip` sha256 `ba2f2436f03ab4584457bc457da2fbdef759df89bf273d7c44ab13ff35b287d9` (Flutter `shear_wallet.exe`, **no miner inside**, title **Shear 0.7**) plus Linux `shear-wallet-0.7-linux.zip` sha256 `7ecac783acb996ba4cde79c379cbda1e3cdd1657e57201c684544553d6357d6f` and Arch `shear-wallet-0.7-archlinux.zip` sha256 `638b35c47ed8b2f97cced0e47f3c864a580b9078e8ddf7bdf7d8396d779f8a9f` (`pkgver=0.7`) to **this same** `0.7` tag. Flutter file version `0.7.0+19` is not the pin. Do **not** recut wallet **0.6**. No iOS.

**Updated:** 2026-08-30 — **[Testnet] ShearK-Miner 1.2** leftover **on tag** (`rgsneddon/ShearK` tag **`1.2`**, title **`[Testnet] ShearK-Miner 1.2`**). Banner / `--print-config` / stratum login all declare **version 1.2**. Submit carries the ShearHash-v2 digest. Mac `ShearK-Miner-1.2-macos.zip` sha256 `428be3d4559deff2a7ac5ae95b6fdfe7b78f6216443df677bd49b501703a3dd7`. Linux `ShearK-Miner-1.2-linux.zip` sha256 `8eae00fee6aea2699458ee19bba00149ab68a30e71436115019d5965bc8cff69` (`ShearK-Miner` + `example.sh`, ELF `0755`). Native PE `ShearK-Miner-1.2-windows.zip` sha256 `a5c57a2fafa1a819de1f6aaf1e9d57fe0e7cbb03ee43aae8f18368e27cba8506` (`ShearK-Miner.exe` + `example.bat`). Do **not** recut ShearK-Miner **1.1** / **1.0** or Shear-Miner **1.1** / **1.0**. Wallet leftover **0.6** **on tag**. DE `.raskul` is 1.2. No iOS.

**Updated:** 2026-08-30 — **[testnet] Shear wallet 0.6** leftover **on tag** (`rgsneddon/shear-testnet` tag **`0.6`**, commit `bdfc535`). Title **`[testnet] Shear wallet 0.6`**. Mac `shear-wallet-0.6-macos.dmg` sha256 `8ed16dbd5c9eac4442e4d7b16ebbf958e540dccbc49171d8d0773ba36380a9e5`. Android `shear-wallet-0.6-android.apk` sha256 `e1929a925eb7462223e16715df9235a0d25ea3cc0549bb426b9ea28a8815709f`. Windows `shear-wallet-0.6-windows.zip` sha256 `d8ce0320949de4956a961708bb272d1d951df258fbc5593707d92bb6b94a4210` (Flutter `shear_wallet.exe`, **no miner inside**, title **Shear 0.6**). Linux `shear-wallet-0.6-linux.zip` sha256 `7bf1b1e70e90976cc51d409696d3c1cea564655569cc8a4507de8830267497e8`. Arch `shear-wallet-0.6-archlinux.zip` sha256 `f4037ff7a9334d3ead28d635bf2c1fb5029c91d53387cf684a9089cdb251d731` (`pkgver=0.6`). Flutter file version `0.6.0+18` is not the pin. Do **not** recut wallet **0.5** / **0.4** or miner **1.1** / **1.0** / ShearK-Miner **1.1**. Node/pool stay **0.1**. No iOS.

**Updated:** 2026-08-30 — **[testnet] Shear wallet 0.5** leftover **on tag** (`rgsneddon/shear-testnet` tag **`0.5`**, same tag as miner 0.5 — do **not** recut miner zips). Title of that GitHub release remains miner 0.5; wallet assets are `shear-wallet-0.5-macos.dmg` (Developer ID + notarized, sha256 `f23c651dfae488303dd6c3cefcade3acf2b8381f2250a3a32f664b8c10041170`) and `shear-wallet-0.5-android.apk` (sha256 `6efa4f067c1a138b59a585b2e2097d6f5587a355ed75e92d56ad6f7aca2744c6`). Password seals `shewall.bin` (PBKDF2+AES-256-GCM); first run sets it, later runs and import need that exact password. Biometrics optional on-device only. Laptop attached 2026-09-01: `shear-wallet-0.5-windows.zip` sha256 `bbab520135f256a9de9639284e04652e8d83cb1b86e17adea2f02771b5990f53` (Flutter `shear_wallet.exe`, **no miner inside**, title **Shear 0.5**) plus Linux `shear-wallet-0.5-linux.zip` sha256 `27a4320d6fff1b1bdfa95d2b1e029254a0c0a1df7b5a9b23eca496012dfe5917` and Arch `shear-wallet-0.5-archlinux.zip` sha256 `3a0d7fb7246a57628bdac7d4451599dc430bb8ec036adacf4bdcf85e840a44ff` (`pkgver=0.5`) to **this same** `0.5` tag. Flutter file version `0.5.0+17` is not the pin. Do **not** recut wallet **0.4** or miner **1.1** / **1.0** / ShearK-Miner **1.1**. Node/pool stay **0.1**. No iOS.

**Updated:** 2026-08-30 — **[Testnet] ShearK-Miner 1.1** leftover **on tag** (`rgsneddon/ShearK` tag **`1.1`**). Title **`[Testnet] ShearK-Miner 1.1`**. Mac `ShearK-Miner-1.1-macos.zip` sha256 `a26f425bb918475f0b442e391d787069b007fa4589423233ef47a0a97b663ce0`. Native PE `ShearK-Miner-1.1-windows.zip` sha256 `a24bb2efaa176b4d683ed896545fd8fd8d360d8d6814e6d58ad3a23cef9a242b` (`ShearK-Miner.exe` + `example.bat`). Linux `ShearK-Miner-1.1-linux.zip` sha256 `2eead73697a47f12f9caae0890ef55621808e186e57280d7521174ee0a56f7f1` (`ShearK-Miner` + `example.sh`, ELF `0755`). Do **not** recut ShearK-Miner **1.0** or Shear-Miner **1.1** / **1.0**. Wallet **0.5** leftover **on tag**. Node/pool stay **0.1**. DE stays `--threads 1` `.raskul`. No iOS.

**Updated:** 2026-09-12 — **Windows starts at [WINDOWS.md](WINDOWS.md)** (`https://github.com/rgsneddon/handoff/blob/main/WINDOWS.md`). This file is the full inventory. The Windows box was **formatted** — no local repo. `gh repo clone` `handoff`, `shear-testnet`, `ShearK` from GitHub (bootstrap at top). **0.30 Windows zip is on tag** — download, do **not** recut. Miner **1.6** Windows zip is on tag (`example.bat` is `YOUR_SSA1.worker`). Linux/Arch **0.30** already on tag (Dedicated-de). Do **not** recut **0.29** / **0.28** / ShearK **1.5** / **1.6** binary. Do not treat `shear-testnet/WINDOWS_HANDOFF.md` as a second leftover.

**Updated:** 2026-08-30 — **[testnet] Shear wallet 0.4** leftover **on tag** (`rgsneddon/shear-testnet` tag **`0.4`**). Title **`[testnet] Shear wallet 0.4`**. Mac DMG + APK **on tag** (INTERNET). Windows `shear-wallet-0.4-windows.zip` sha256 `c86e4349621b7dd1373289280938a94a63f43c2362ed431ae65d68efd0bed283` (zip root Flutter `shear_wallet.exe`, **no miner inside**, title **Shear 0.4**). Linux `shear-wallet-0.4-linux.zip` sha256 `2b836a474f57e478bd1d6f537f7497348cba14838e7bb59bdbceb7478cd6cb20`. Arch `shear-wallet-0.4-archlinux.zip` sha256 `ce1a923fcfb335a3734c8c26d9680fe8edbcc3f926aa8c4c4c80bfedfc9f123a` (`pkgver=0.4`). Flutter file version `0.4.0+16` is not the pin. Do **not** recut miner **1.1** / **1.0** or ShearK-Miner **1.1** / **1.0**. Node/pool stay **0.1**. No iOS.

**Updated:** 2026-08-28 — **[testnet] Shear wallet 0.2** leftover **on tag** `0.2` (`rgsneddon/shear-testnet`). Title **`[testnet] Shear wallet 0.2`**. Mac DMG + APK + **Windows / Linux / Arch zips** on the tag (**no miner inside**). Windows zip sha256 `e896a824252044159e9865258a15ababea2e48676775878ce356fa624e010f57`. `kWalletVersion` **0.2**. Flutter file version `0.2.0+13` is not the pin. **https://shear.digital** WALLET/MINER/NODE buttons + `#pack-advisory` (version + sha256) deployed. Do **not** recut miner **1.1** / **1.0**. Node/pool stay **0.1**. No iOS.

**Updated:** 2026-08-28 — **[testnet] Shear** consensus spendable is **6 confirmations** (in the fingerprint). Merchant policy **12**. **Do not change spendable to 1** — flag the operator. Live `bookLawFingerprint` ends `:6:1`.

**Updated:** 2026-08-28 — **[testnet] Shear wallet 0.1** leftover **on tag** `0.1` (`rgsneddon/shear-testnet`). Title **`[testnet] Shear wallet 0.1`**. Asset `shear-wallet-0.1-windows.zip` (~13.7 MB, sha256 `e605be153627ebb63dfa970e4fdb1047b48059f265c6c07f4fa14d858ff740f5`, `shear_wallet.exe` at zip root, **no miner inside**). Mac DMG + APK already on the tag. Laptop attached 2026-09-01 Linux `shear-wallet-0.1-linux.zip` sha256 `1fef18f6fbdffc7da9c0b28303e8cd2396018ec50ad4d9e96e988a1c7681b420` and Arch `shear-wallet-0.1-archlinux.zip` sha256 `d8996e33c16a4a9c396ac42393bea8b0d5f838c2fe47fdf57d73e15875d11fd5` (`pkgver=0.1`). Flutter file version `0.1.0+12` is not the pin. Do **not** recut miner **1.1** / **1.0**. Clone `shear-testnet`. No iOS.

**Updated:** 2026-08-28 — **[testnet] Shear-Miner 1.1** (`rgsneddon/shear-testnet` `0b3037c`, tag **`1.1`**, title **`[testnet] Shear-Miner 1.1`**). **Free to use — no miner fee.** `--print-config` `feePct` **0**, `clientLogin` **direct**. Banner `Shear-Miner 1.1 (free to use, no miner fee)`. **1.0** stays on tag `1.0` with the 4% dual-login fee — do **not** recut it. Wallet / node / pool stay **0.1**. **Windows PE on both tags:** `Shear-Miner-1.1-windows.zip` on **`1.1`** and `Shear-Miner-1.0-windows.zip` on **`1.0`** (each zip root is `Shear-Miner.exe` + `example.bat`). macOS + Linux already on those tags. `--selftest` `5d00a242…`. DE 4-thread is **Shear-Miner 1.1** worker `.raskul` (public tag `she158cd3c2a`). Datadir `/var/lib/shear/testnet-0.1`. Clone `shear-testnet`. **Wallet Windows zip on tag `0.1`:** `shear-wallet-0.1-windows.zip` (no miner). **Linux / Arch leftover.** No iOS.

**Updated:** 2026-08-28 — **[testnet] Shear-Miner 1.0** (`rgsneddon/shear-testnet` `53b72c6`, tag **`1.0`**, title **`[testnet] Shear-Miner 1.0`**). Operator set the miner to **1.0**. Binary / banner / `--print-config` / pool login all paint **Shear-Miner** / **1.0**. Declared **4%** dual-login fee (`FEE_EVERY` 25, offset `0..24`) at `she1qlrll…fee`. Wallet / node / pool stay **0.1** — do **not** roll those to `1.*`. Do **not** recut miner **0.5**. macOS + Linux zips on the tag. **Windows leftover:** attach `Shear-Miner-1.0-windows.zip` (`Shear-Miner.exe` + `example.bat`) to **this same** `1.0` tag. `--selftest` `5d00a242…`. `--print-config` name **Shear-Miner**, version **1.0**, `feePct` **4**, `headerBytes` 128. Pool: connected proven hashers stay listed; ghosts drop **12s after full disconnect**. DE 4-thread is **Shear-Miner 1.0** worker `.raskul` (public tag `she158cd3c2a`). Datadir `/var/lib/shear/testnet-0.1` (do **not** load `/var/lib/shear/testnet` ~7995 snapshot). Clone `shear-testnet`. No iOS.

**Updated:** 2026-08-27 — **[testnet] Shear** recut live (`rgsneddon/shear-testnet`, commit `49476c2`). Product **0.1**, miner **0.5**. Tags `0.1` / `0.5` (not `0.1.0`). Titles **`[testnet] Shear wallet 0.1`** and **`[testnet] Shear miner 0.5`**. Book-law: 128-byte header, ssa1, 90s, 1 SHE pot, HASH_TX_LIVE=1, **consensus spendable 6**, merchant **min_confirms 12**. DE datadir `/var/lib/shear/testnet-0.1` (do **not** load `/var/lib/shear/testnet` ~7995 snapshot). Miner login reports **name** `shear-miner` plus version. **Windows leftover:** `shear-wallet-0.1-windows.zip` / `-linux.zip` / `-archlinux.zip` on tag `0.1` (no miner inside, PKGBUILD `pkgver=0.1`); `shear-miner-0.5-windows.zip` (`exe`+`example.bat`) on tag `0.5`. Clone `shear-testnet`, not `rgsneddon/shear`. No iOS. No `1.*`.

**Updated:** 2026-08-26 — Shear wallet **0.1.0** Mac-cut **on tag** (`04704b1`, https://github.com/rgsneddon/shear/releases/tag/v0.2.0). Product **0.1.0**. GitHub tag is **`v0.2.0`** because **`v0.1.0` is the miner pin — do not recut it.** Title **`[TESTNET] Shear wallet 0.1.0`**. Continuum loads reconstructed confirmed SHE on unlock; open-round pending settles on the next sealed block; header height follows `/api/stats` every second. Mac `shear-wallet-0.1.0-macos.dmg` Developer ID + notarized + stapled (sha256 `a6cbecda34dc60f045cfe2bed96cabd6b0371d338992a1a000d9f40f99a4054d`) / `-android.apk` (sha256 `daff9bbd3f68dcb1ccb517a61f8e0de03e8902c467bab25f709574cae4b26b65`, ~51 MB). **Windows leftover:** attach `-windows.zip` / `-linux.zip` / `-archlinux.zip` to **the same** `v0.2.0` (**no miner inside**, PKGBUILD `pkgver=0.1.0`). **No iOS / iPad zip.** Miner stays **0.1.7**. Do **not** recut **0.0.9**.

**Updated:** 2026-08-26 — Shear wallet **0.0.9** Mac-cut **done on Amelia** (`92783e2`, https://github.com/rgsneddon/shear/releases/tag/v0.0.9). Title **`[TESTNET] Shear wallet 0.0.9`**. Mac `shear-wallet-0.0.9-macos.dmg` Developer ID + notarized + stapled (sha256 `ddd5dcd315d4459ea1d4e38a681a3b0b0d2d18fbce95fe0d5b4e98b81f70df71`) / `-android.apk` (sha256 `0726846c2c17f7ae5ddf30c6844f068a548a86be54d6f49cb4d35c6b5de3bd03`, ~51 MB) clobbered onto **the same** tag. Laptop leftover `-windows.zip` / `-linux.zip` / `-archlinux.zip` already on tag (**no miner inside**). Continuum **live** pending miner hashes **and** mempool incoming receives. `kWalletVersion` / `pubspec` **0.0.9**. **No iOS / iPad zip.** Miner stays **0.1.7**. Do **not** recut **0.0.8**. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-26 — Shear miner **0.1.7**. Title **`[TESTNET] Shear miner 0.1.7`**. Sends this miner's own `hashes`/`hashrate` on each share; does not wait for ACK per share. Windows `exe` + `example.bat` and Linux zip on **the same** `v0.1.7`. Darwin leftover on Amelia. `--selftest` `6e95b903…`. **Do not recut** **0.1.6**. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-26 — Shear wallet **0.0.9** leftover **on tag** (`92783e2`, https://github.com/rgsneddon/shear/releases/tag/v0.0.9): laptop attached `-windows.zip` / `-linux.zip` / `-archlinux.zip` (**no miner inside**). Mac-cut **done on Amelia** (row above). Continuum **live** pending miner hashes **and** mempool incoming receives. Title **`[TESTNET] Shear wallet 0.0.9`**. `kWalletVersion` / `pubspec` **0.0.9**. **No iOS / iPad zip.** Miner stays **0.1.7**. Do **not** recut **0.0.8**. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-25 — gnfp-cminer **0.5** Windows PE + `example.bat` **on the same** `v0.5` (`--clobber`). Zip root is `gnfp-cminer.exe` + `example.bat` (static PE, no extra DLLs). Linux ELF tar.gz rebuilt (`0755`, `avx2-x8`). macOS **`.dmg`** added (`gnfp-cminer-0.5-macos.dmg`, Developer ID signed). `--selftest` `986437c4…`. Title **`gnfp-cminer 0.5`**. Do **not** recut **0.4**. Do **not** invent a sibling tag. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-25 — Shear miner pin is **0.1.6** (`9907ecc`, https://github.com/rgsneddon/shear/releases/tag/v0.1.6). Title **`[TESTNET] Shear miner 0.1.6`**. Declared **5%** dual-login fee; fee login `she1qlrll6hhdakpcrlygumhq5a2xqhcj49ys7j2lzj.fee` (mainnet amends this dest). Darwin arm64 + Linux x86_64 ELF on the tag. **Windows PE leftover on the laptop** — attach `shear-miner-0.1.6-windows.zip` to **the same** `v0.1.6`. `--selftest` `6e95b903…`. DE 1-thread is **0.1.6**. Pool hides `.fee` and holds proven H/s (`b61fb90`). **Do not recut 0.1.5**. **0.1.4 is deprecated**. Do **not** recut **0.1.3**. Wallet leftover **0.0.8** unchanged. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-25 — Shear miner pin is **0.1.5** (`81e4cf7`, https://github.com/rgsneddon/shear/releases/tag/v0.1.5). Title **`[TESTNET] Shear miner 0.1.5`**. Declared **5%** dual-login fee; fee login `she1qlrll6hhdakpcrlygumhq5a2xqhcj49ys7j2lzj.fee`. Darwin arm64 + Linux x86_64 ELF + Windows PE on the tag. `--selftest` `6e95b903…`. DE 1-thread is **0.1.5**. **0.1.4 is deprecated**. Do **not** recut **0.1.3**. Wallet leftover **0.0.8** unchanged. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-25 — **Helsinki emptied.** All HEL operator units stopped (nginx, paid store, perc_chain, perc pool, GOD, replica, redis, perc-mine). HEL listens **SSH :22 only**. Live store / perc / GOD / mineperc now on **Germany** `178.105.187.178`. GNFP replica + DE→HEL reverse tunnels **off**. perc_suite lives at `/opt/restore-privacy/perc_suite` (do **not** overwrite DE book `/opt/restore-privacy/perc_chain`). Public perc/paid HTTPS: `https://178.105.187.178.sslip.io/perc` and `/paid-assets`. **Namecheap still has god/mineperc/evolve/beam/hel A → 135.181.152.10** — paste A records to `178.105.187.178` or those names stay dark. Shipped clients pinned to HEL sslip.io will miss rendezvous until next ship. HEL data left on disk (not wiped) so the box can be reimaged.

**Updated:** 2026-08-25 — Official miner pin is **gnfp-cminer 0.5** (`9c99cc7`, https://github.com/rgsneddon/gnfp-cminer/releases/tag/v0.5). Same hasher as **0.4**. Only the 5% fee clock changed: per-process random offset `0..19` + lazy fee connect (second login on the first fee share). Wire still `GNFPHash` `1.1.2`. Darwin arm64 **DMG** + Linux x86_64 ELF (`0755`, `avx2-x8`) + Windows **`gnfp-cminer.exe` + `example.bat`** on the tag. `--selftest` `986437c4…`. Title **`gnfp-cminer 0.5`**. Latest. Do **not** recut **0.4**. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-25 — Official miner pin is **gnfp-cminer 0.4** (`de719c5`, https://github.com/rgsneddon/gnfp-cminer/releases/tag/v0.4). Desktop `gnfp_cminer_v0.4` as shipped — **no miner changes**. Windows zip is the Desktop `gnfp` folder unchanged (`gnfp_cminer_v0.4.exe` sha256 `b9f0328748c4a88e62b384d32b5078eb52b04355cc311a17a64132eb95e70528` + OpenSSL/MinGW DLLs). Darwin arm64 + Linux x86_64 ELF (`0755`, `avx2-x8`) compiled from that same miner, no source edits. `--selftest` `986437c4…`. Title **`gnfp-cminer 0.4`**. Latest on GitHub. **1.1.6 is not the pin** (title `gnfp-cminer 1.1.6 (prefer 0.4)`). Do **not** recut **1.1.6** / **0.4**. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-25 — Shear miner pin is **0.1.3** (`7220ecc`, https://github.com/rgsneddon/shear/releases/tag/v0.1.3). Title **`[TESTNET] Shear miner 0.1.3`**. Scalar-x8 independent hashes + header midstate. **1 hash = 1 tx**. **No miner fee.** `--selftest` `6e95b903…`. **0.1.4 is deprecated** (too slow) — GitHub title **`[TESTNET] [DEPRECATED] shear-miner 0.1.4`**. Do **not** recut **0.1.4**. Do **not** recut **0.1.3**. DE 1-thread is on **0.1.3**. Wallet leftover **0.0.8** unchanged. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-25 — Shear wallet **0.0.8** leftover **done on the laptop** (`74faa0b`, https://github.com/rgsneddon/shear/releases/tag/v0.0.8). Title **`[TESTNET] Shear wallet 0.0.8`**. Mac `shear-wallet-0.0.8-macos.dmg` Developer ID + notarized + stapled (sha256 `5b37b9b9192a93e1b9eef4084e62d97a84ac958e1572ca6fd49391054b40a1af`) / `-android.apk` (sha256 `dbd4d1ea5aed004c925b39d87cedcae2fceecc40b5e3cfb2dff76df36cf5e5f5`, ~51 MB). Laptop attached `-windows.zip` / `-linux.zip` / `-archlinux.zip` to **the same** `v0.0.8` (**no miner inside**, PKGBUILD `pkgver=0.0.8`). **Does not mine.** Offer **she1** (silent ID **and** login). Send to she1 pays shp1; never share shear1. 1 SHE/block + 1e-11/hash. **All Shear GitHub release titles are `[TESTNET] …` until mainnet.** Miner pin is **0.1.5** (0.1.4 deprecated). **No iOS / iPad zip.** Do **not** recut **0.0.7**. **No mainnet zip.** Do **not** invent a sibling tag. Do **not** upload Shear to the App Store. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-25 — New miner pins: gnfp-cminer **1.1.6** (`eda2602`, https://github.com/rgsneddon/gnfp-cminer/releases/tag/v1.1.6) runtime SHA-NI/AVX2 dispatch (auto picks the fastest CPUID-legal kernel; `--backend scalar` hatch). Shear miner **0.1.4** (`2b04af7`, https://github.com/rgsneddon/shear/releases/tag/v0.1.4) same dispatch. **1 hash = 1 tx**. Shear **no miner fee**. Laptop attached `gnfp-cminer-1.1.6-windows.zip` + `-linux.tar.gz` (ELF `0755`) and `shear-miner-0.1.4-windows.zip`. `--selftest` hashes unchanged (`986437c4…` / `6e95b903…`). Default CFLAGS stay scalar (not a 1.1.2 fat AVX2 binary). Do **not** recut **1.1.5** / **0.1.3**. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-25 — New miner pins: gnfp-cminer **1.1.5** (`fe9ad28`, https://github.com/rgsneddon/gnfp-cminer/releases/tag/v1.1.5) scalar-x8 + first-block midstate on long `preWork`; Shear miner **0.1.3** (`7220ecc`, https://github.com/rgsneddon/shear/releases/tag/v0.1.3) scalar-x8 independent hashes + header midstate. **1 hash = 1 tx** (each meeting nonce is its own share). Shear **no miner fee**. Laptop attached `gnfp-cminer-1.1.5-windows.zip` + `-linux.tar.gz` (ELF `0755`) and `shear-miner-0.1.3-windows.zip`. `--selftest` hashes unchanged (`986437c4…` / `6e95b903…`). DE probe 1.1.5: login ok, fee `fTAIL_worker`, shares accepted. Darwin 1.1.5 leftover on the Mac. Do **not** recut **1.1.4** / **0.1.2**. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-24 — Laptop attached gnfp-cminer **1.1.4** Windows PE + Linux ELF to **the same** `v1.1.4` (`b56ede9`). Scalar-only (`backend=scalar-x8`, ELF `ymm_lines=0`). In-zip `--selftest` `selftest ok 986437c40fee8a876e0ca3f1e58b14fa38785a179f57f98ebbb0fb03102bd4eb`. Help `GNFPHash C miner 1.1.4` + `fTAIL_worker`. PE static OpenSSL, no extra DLL. Zip root `example.bat`. GNFP wallet **0.2.4** Windows/Linux/Arch + CLI on **the same** `v0.2.4` (**no cminer inside**). Title `$GNFP core wallet v0.2.4`. Mac APK not on tag (dmg/zip already). Do **not** recut **1.1.3** / **0.2.3**. Do **not** ship leftover `1.0.6-max-autotune`. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-24 — Official miner pin **gnfp-cminer 1.1.3** (scalar-only, https://github.com/rgsneddon/gnfp-cminer/releases/tag/v1.1.3). `make` does not pass `-mavx2`. Linux ELF ymm_lines=0; Darwin `--selftest` `backend=scalar-x8`. Do **not** recut **1.1.2** (that Linux ELF still has AVX2 ymm). Windows PE leftover on the laptop. Shear miner **0.1.2** Windows PE ymm_lines=0 — **do not recut**. GNFP wallet **0.2.4** does not mine. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-24 — GNFP wallet **0.2.4** **does not mine**. No Mine tab. No bundled `gnfp-cminer`. Official hasher is standalone **gnfp-cminer 1.1.4**. Shear wallet **0.0.7** still has **no** `shear-miner`; Shear miner **0.1.2** `--selftest` ok. Do **not** recut **0.2.3** / **0.2.2** / miners **1.1.3** / **1.1.2** / **0.1.2**. Laptop leftover for **0.2.4** / **1.1.4** is **done**. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-24 — **Mac Gatekeeper.** Last-bundle Mac client apps were only Shear wallet **0.0.7** and GNFP wallet **0.2.3**. Both `.app` + DMG (GNFP zip too) re-signed Developer ID `Russell Sneddon (SFCBP95595)`, notarized, stapled, `--clobber` onto **the same** tags. `spctl --assess --type execute` = **Notarized Developer ID**. Miners **0.1.2** / **1.1.2** not recut (not in that bundle). **No sibling tag.**

**Updated:** 2026-08-24 — Laptop attached Shear wallet **0.0.7** Windows/Linux/Arch to **the same** `v0.0.7` with **no miner inside**. Title Shear 0.0.7. **Does not mine.** GNFP wallet **0.2.3** Windows/Linux/Arch + CLI + bundled `gnfp-cminer` to **the same** `v0.2.3`. Title `$GNFP core wallet v0.2.3`. In-zip `gnfp-cminer.exe --selftest` printed `selftest ok 986437c40fee8a876e0ca3f1e58b14fa38785a179f57f98ebbb0fb03102bd4eb`. Mac APKs second-eyed OK (~51 MB). 1e-11 hash bonus + eight-digit public frame already live on DE. Do **not** recut **0.0.6** / **0.2.2**. Do **not** recut miners **0.1.2** / **1.1.2**. **No mainnet zip.** Do **not** invent sibling tags. Do **not** upload Shear to the App Store. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-24 — Laptop attached Shear wallet **0.0.6** Windows/Linux/Arch to **the same** `v0.0.6` with **no miner inside**. Title Shear 0.0.6. GNFP wallet **0.2.2** Windows/Linux/Arch + CLI + bundled `gnfp-cminer` to **the same** `v0.2.2`. Do **not** recut **0.0.6** / **0.2.2**. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-24 — gnfp-cminer **1.1.2** on **the same** `v1.1.2` (`de719c5`, https://github.com/rgsneddon/gnfp-cminer/releases/tag/v1.1.2). Darwin **arm64** + Linux **x86_64 ELF** (`avx2-x8`) + Windows **PE** from Desktop `gnfp4` (`gnfp_cminer_v0.4.exe`, login version **1.1.2**, OpenSSL DLLs next to the exe) + **`example.bat`**. `--selftest` `selftest ok 986437c40fee8a876e0ca3f1e58b14fa38785a179f57f98ebbb0fb03102bd4eb`. **No `--threads` 256 clamp.** Do **not** recut **1.1.1**. Do **not** invent a sibling tag. Wallet **0.2.1** and node **1.2.7** stay — bonus / 10-digit frame is pool-side; do **not** recut those tags. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-24 — GNFP Germany book: per-hash bonus cut **1e-9 → 1e-10 GNFP** (`0.0000000001` per proven hash). **1 GNFP per formed block** unchanged. Amount frame is **10 fractional digits** (`0.0000000000`). Live on DE **17:42 UTC** (`rpt-gnfp-pool` restarted): `/api/network` `hashBonusGnfp=1e-10` `blockRewardGnfp=1` `nanosPerGnfp=10000000000`. Integer unit is **10^{-10} GNFP** (`NANOS_PER_GNFP=1e10`; name kept). Pool fee stays **1% of the pot**. **`HASH_TX_LIVE` stays 0** — that pin is **lean collate** (do not persist one open-window object per hash). It is **not** the bonus switch; the bonus is sealed into the block. **Shear inherit:** **1 SHE pot / block**, **0.0000000001 per hash**, 10-digit frame — acknowledge only; **no mainnet zip**; do **not** cut a live Shear mint.

**Updated:** 2026-08-24 — GNFP Germany book: difficulty was stuck at **4.29e9 (`2^32`)** while ~0.2–2 GH/s hashed, so blocks ran ~6–16s not 90s. Cause: `MAX_DIFFICULTY_BITS=32` + vardiff max **24**. Live fix on DE **16:48 UTC** (`rpt-gnfp-pool` restarted): block + share ceiling is **256 bits** (SHA-256 width). Tip climbed **32 → 33** on the first uptime retarget. GPU/ASIC still refused at login/nonce/solution. `HASH_TX_LIVE` stays **0**. **Shear inherit:** ASERT/`MAX_BITS` and share vardiff must be **256**, not 32/24 — do **not** copy the old GNFP lid.

**Updated:** 2026-08-24 — Laptop attached Shear wallet **0.0.5** Windows/Linux/Arch to **the same** `v0.0.5` with **no miner inside**. Title Shear 0.0.5. **Does not mine.** Official miner stays **0.1.2** on `v0.1.2` (**do not recut**). Mac APK second-eyed OK (~51 MB). Do **not** recut **0.0.4**. Do **not** upload Shear to the App Store. **No mainnet zip.** Do **not** invent a sibling tag.

**Updated:** 2026-08-24 — gnfp-cminer **1.1.1** Linux **x86_64 ELF** + Windows **PE** attached to **the same** `v1.1.1` (https://github.com/rgsneddon/gnfp-cminer/releases/tag/v1.1.1, `1fe25b5`). `--selftest` `selftest ok 986437c40fee8a876e0ca3f1e58b14fa38785a179f57f98ebbb0fb03102bd4eb`. PE static OpenSSL, no extra DLL. Darwin **arm64** already on that tag. Do **not** rebuild **1.1.0**. Do **not** invent a sibling tag. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-24 — GNFP Germany book: large farms (report `--threads 240` / worker `.rom16t` and others) were **TCP-kicked then banned** after valid shares. Cause: honesty on the **folded** (summed) worker row + persistent `bannedMiners` (`thread_cheat`). Live fix on DE **14:07 UTC**: **no miner bans**; honesty **per TCP session**; no socket kick on inflate/underreport; valid GNFPHash shares keep crediting. 256-thread farm cap removed on the book. Miner pin for that clamp is **1.1.1** (row above). After restart: ~15 miners / ~608 threads / 0 rejected; large farm back. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-24 — (historical) Laptop attached Shear miner **0.1.2** Windows zip to **the same** `v0.1.2` and wallet **0.0.4** Windows/Linux/Arch (miner **0.1.2 inside**) to **the same** `v0.0.4`. **Superseded:** current leftover is wallet **0.0.5** with **no miner inside**. Do **not** recut **0.0.4**. Miner **0.1.2** stays on `v0.1.2`. **No mainnet zip.** Do **not** invent a sibling tag.

**Updated:** 2026-08-24 — GNFP pool worker-thread flicker (EP01 32/32 ↔ 230/256 last-write). Miner book keys **per TCP session** and **sums** utilised + device inventory onto `wallet.worker` for the **table**. Honesty is **per session** (not the folded sum) and does **not** ban or kick. Shear: keep session fold for display; do **not** copy GNFP’s old `thread_cheat` ban. Do **not** last-write `threads`/`cpuCores`/`cpuThreads` on the login name. `HASH_TX_LIVE` stays **0**.

**Updated:** 2026-08-23 — Laptop attached Shear miner **0.1.1** Windows zip to **the same** `v0.1.1` and wallet **0.0.3** Windows/Linux/Arch (miner **0.1.1 inside**) to **the same** `v0.0.3`. In-zip `--selftest` printed `selftest ok 6e95b9033c5d044d08bbf854fb2e5343ca3103b96ae37bde101258d43cfacc63`. `--user sdcard1…` or `she1…`. Title Shear 0.0.3. Testnet only. **No mainnet zip.** Do **not** invent a sibling tag.

**Updated:** 2026-08-22 — Laptop attached wallet **0.2.1** Windows/Linux/Arch **+ CLI** to **the same** `v0.2.1`. Bundled `gnfp-cminer.exe --selftest` from **inside the wallet zip** is **ok**. Mac APK second-eyed OK (~51 MB). Do **not** rebuild **0.2.0** / C-miner PE. `HASH_TX_LIVE` stays **0**.
**GitHub home:** https://github.com/rgsneddon/handoff  
**Account:** `rgsneddon` (Russell G Sneddon)

This file is the **single status note** and the **only** GNFP client-release handoff. Read it on Amelia’s Mac **or the Windows laptop** before building anything. Per-repo `WINDOWS_HANDOFF.md` files are pointers here — do not treat them as a second pin list, and do not leave pin digits in those filenames.

## Shear (testnet — leftover)

**Public recut repo:** https://github.com/rgsneddon/shear-testnet (display **[testnet] Shear**). GitHub **`rgsneddon/shear`** is gone. Local `/Users/russellsneddon/shear` tracks `shear-testnet` — do **not** delete that folder.  
**Formatted Windows box reads [WINDOWS.md](WINDOWS.md) first** (`https://github.com/rgsneddon/handoff/blob/main/WINDOWS.md`). `shear-testnet/WINDOWS_HANDOFF.md` is a pointer, not a second leftover. There is **no** repo on that disk until after `git clone`.

**Standing cut rule — wallet, node, and miner:**
- **Amelia Mac** packs **macOS + Android**. Wallet: `shear-wallet-*-macos.dmg` + `-android.apk`. Miner macos zip only when a Darwin miner is cut (1.6 has **no** macos zip).
- **Exception 2026-09-11:** Dedicated-de packed **Linux + Arch 0.30** (ELF `shear_wallet`). Do **not** re-upload those from Windows. Do **not** attach Darwin as `*-linux.zip`.
- **Windows box (formatted 2026-09-11)** has **no leftover files** until you clone. **0.30 Windows zip is on tag** — download, do **not** recut. Miner **1.6** PE is on tag. Future pins: pack only the Windows Flutter zip from a **fresh clone** (`zip_windows.py`).
- **Never** recut an older leftover tag in place. **No iOS / iPad zip.** Do not upload Shear to the App Store.

**Network:** live Germany is **`shear-testnet-v2`** (`/opt/shear-v2`, `SHEAR_DATA=/var/lib/shear/testnet-v2`). Frozen v1 book stays at `/var/lib/shear/testnet-0.1` — do **not** overwrite it. **Do not** cut a mainnet genesis zip.  
**GitHub release titles** stay **`[testnet] …`** until mainnet is opened. Do not drop that prefix on a recut.

| Client | Pin | Formatted Windows box |
|--------|-----|-----------------------|
| **Miner** | **ShearK-Miner 1.6** (`rgsneddon/ShearK` tag **`1.6`**). How-to: repo README. Login **Copy dest** `ssa1….worker`. | Windows + Linux **on tag**. `ShearK-Miner-1.6-windows.zip` sha256 `879a0024297962cd9a97bf544dcd1fe1656a546d82ea37cfa6f6a2615befb5fb` (`ShearK-Miner.exe` + `example.bat` `YOUR_SSA1.worker`). `ShearK-Miner-1.6-linux.zip` sha256 `e04e8b57d4700c25f2912b6636c9ef444b1d3f40b3128dd3a168a5388271c2d1`. **No macos zip on 1.6.** Download; do **not** recut **1.6** binary / **1.5** / **1.4** or Shear-Miner **1.1** / **1.0**. Live hasher uses `--dest ssa1…`. |
| **Wallet** | **0.30** | Mac + Android + Linux + Arch + **Windows on tag** **`0.30`**. `shear-wallet-0.30-windows.zip` sha256 `8bc28d5255e14935e2ec7afc5cd43d89a217c84247eff40edfe25da667bc29a8` (Flutter `shear_wallet.exe`, title **Shear 0.30**, **no miner inside**). Download; do **not** recut. Public site still omits the wallet Windows menu link until Amelia restores it. **Tag `0.29` stays.** Flutter `0.30.0+42` is not the pin. Do **not** roll wallet to `1.*`. Miner stays **ShearK 1.6**. |
| **Node / pool** | live `shear-testnet-v2` on DE (`/opt/shear-worthy`, datadir `testnet-v2-worthy`) | No node zip leftover. Dest-bind + per-dest hash bonus already live. |

Do **not** attach Shear binaries to any other project’s GitHub tags. Do **not** invent sibling tags. Testnet first.

### 2026-08-30 — Windows leftover (Shear wallet 0.6) — **on tag**

Read this file first (`git -C ~/handoff pull`). Repo **`rgsneddon/shear-testnet`**. **No sibling tag.** Do **not** recut wallet **0.5** / **0.4** or miner **1.1** / **1.0** or ShearK-Miner **1.1**.

Laptop attached Windows/Linux/Arch to **the same** `0.6`. Title **`[testnet] Shear wallet 0.6`**. https://github.com/rgsneddon/shear-testnet/releases/tag/0.6

- Mac `shear-wallet-0.6-macos.dmg` sha256 `8ed16dbd5c9eac4442e4d7b16ebbf958e540dccbc49171d8d0773ba36380a9e5`
- Android `shear-wallet-0.6-android.apk` sha256 `e1929a925eb7462223e16715df9235a0d25ea3cc0549bb426b9ea28a8815709f`
- Windows `shear-wallet-0.6-windows.zip` sha256 `d8ce0320949de4956a961708bb272d1d951df258fbc5593707d92bb6b94a4210` zip root Flutter `shear_wallet.exe`, **no miner inside**, title **Shear 0.6**
- Linux `shear-wallet-0.6-linux.zip` sha256 `7bf1b1e70e90976cc51d409696d3c1cea564655569cc8a4507de8830267497e8`
- Arch `shear-wallet-0.6-archlinux.zip` sha256 `f4037ff7a9334d3ead28d635bf2c1fb5029c91d53387cf684a9089cdb251d731` (`pkgver=0.6`)

**No iOS / iPad zip.** Do not upload to the App Store.

### 2026-08-30 — Windows leftover (ShearK-Miner 1.2 PE) — **on tag**

Read this file first (`git -C ~/handoff pull`). Repo **`rgsneddon/ShearK`**. **No sibling tag.** Do **not** recut ShearK-Miner **1.1** / **1.0**. Do **not** attach ShearK zips to `shear-testnet`.

Laptop attached native PE to **the same** `1.2`. Title **`[Testnet] ShearK-Miner 1.2`**. https://github.com/rgsneddon/ShearK/releases/tag/1.2

- `ShearK-Miner-1.2-macos.zip` sha256 `428be3d4559deff2a7ac5ae95b6fdfe7b78f6216443df677bd49b501703a3dd7`
- `ShearK-Miner-1.2-linux.zip` sha256 `8eae00fee6aea2699458ee19bba00149ab68a30e71436115019d5965bc8cff69` zip root `ShearK-Miner` + `example.sh` (ELF `0755`)
- `ShearK-Miner-1.2-windows.zip` sha256 `a5c57a2fafa1a819de1f6aaf1e9d57fe0e7cbb03ee43aae8f18368e27cba8506` zip root `ShearK-Miner.exe` + `example.bat` (static PE)

`--print-config` name **ShearK-Miner**, version **1.2**, `feePct` **0**, `clientLogin` **direct**, `headerBytes` 128, `magic` `shear-testnet-v2`, `rxMode` `light`, `rxCacheMiB` 128, pool `pool.shear.digital:1111`. Banner `ShearK-Miner 1.2 (ShearHash-v2 light)`. `--selftest` `selftest ok 64d41fa97f5ebea8a7e2a2625b1824467ce9d081bf29b0b2ae0a7fe617599895`.

### 2026-08-30 — Windows leftover (ShearK-Miner 1.1 PE + Linux) — **on tag**

Read this file first (`git -C ~/handoff pull`). Repo **`rgsneddon/ShearK`** (downloads) + source in **`rgsneddon/shear-testnet`** `sheark-miner/` (`821e9b0`). **No sibling tag.** Do **not** recut ShearK-Miner **1.0**. Do **not** recut Shear-Miner **1.1** / **1.0** on `shear-testnet`. Do **not** attach ShearK zips to `shear-testnet`.

Laptop attached native PE + Linux ELF to **the same** `1.1`. Title **`[Testnet] ShearK-Miner 1.1`**. https://github.com/rgsneddon/ShearK/releases/tag/1.1

- `ShearK-Miner-1.1-macos.zip` sha256 `a26f425bb918475f0b442e391d787069b007fa4589423233ef47a0a97b663ce0` zip root `ShearK-Miner` + `example.sh` (Darwin arm64)
- `ShearK-Miner-1.1-windows.zip` sha256 `a24bb2efaa176b4d683ed896545fd8fd8d360d8d6814e6d58ad3a23cef9a242b` zip root `ShearK-Miner.exe` + `example.bat` (static PE)
- `ShearK-Miner-1.1-linux.zip` sha256 `2eead73697a47f12f9caae0890ef55621808e186e57280d7521174ee0a56f7f1` zip root `ShearK-Miner` + `example.sh` (ELF `0755`)

`--print-config` name **ShearK-Miner**, version **1.1**, `feePct` **0**, `clientLogin` **direct**, `headerBytes` 128, `magic` `shear-testnet-v2`, `rxMode` `light`, `rxCacheMiB` 128, pool `pool.shear.digital:1111`. Banner `ShearK-Miner 1.1 (ShearHash-v2 light)`. `--selftest` `selftest ok 64d41fa97f5ebea8a7e2a2625b1824467ce9d081bf29b0b2ae0a7fe617599895`. DE stays **`--threads 1`** `.raskul` until prompted. Do **not** inflate to 6.

### 2026-08-30 — Windows leftover (Shear wallet 0.4) — **on tag**

Read this file first (`git -C ~/handoff pull`). Repo **`rgsneddon/shear-testnet`**. **No sibling tag.** Do **not** recut miner **1.1** / **1.0** or ShearK-Miner **1.1** / **1.0**.

Laptop attached Windows/Linux/Arch to **the same** `0.4`. Title **`[testnet] Shear wallet 0.4`**. https://github.com/rgsneddon/shear-testnet/releases/tag/0.4

- Mac `shear-wallet-0.4-macos.dmg` sha256 `6cdc576c4e92aaede2695e0879043f8073bb0ac2e8539582772de0c606ff770c` Developer ID + notarized + stapled
- Android `shear-wallet-0.4-android.apk` sha256 `6aa28da196f671e61d04843f9437e3a98adcaa606799ba7169aeb05e892d7312` (`android.permission.INTERNET`, launcher **Shear 0.4**)
- Windows `shear-wallet-0.4-windows.zip` sha256 `c86e4349621b7dd1373289280938a94a63f43c2362ed431ae65d68efd0bed283` zip root Flutter `shear_wallet.exe` + DLLs/`data`, **no miner inside**, title **Shear 0.4**. Flutter file version `0.4.0+16` is **not** the public pin
- Linux `shear-wallet-0.4-linux.zip` sha256 `2b836a474f57e478bd1d6f537f7497348cba14838e7bb59bdbceb7478cd6cb20`
- Arch `shear-wallet-0.4-archlinux.zip` sha256 `ce1a923fcfb335a3734c8c26d9680fe8edbcc3f926aa8c4c4c80bfedfc9f123a` (`pkgver=0.4`)

**No iOS / iPad zip.** Do not upload to the App Store. Node/pool stay **0.1**. In-repo `#pack-advisory` is wallet **0.4** · miner **1.1** with ShearK download buttons.

### 2026-08-28 — Windows PE (Shear-Miner 1.1 + 1.0) — **on tag**

Read this file first (`git -C ~/handoff pull`). Pointer: `shear/WINDOWS_HANDOFF.md`. Repo **`rgsneddon/shear-testnet`**. **No sibling tag.** Official pin is **Shear-Miner 1.1** (free). **1.0** stays as the last fee build. Windows zips are **on both tags**. Each zip is only `Shear-Miner.exe` + `example.bat` at zip root. Wallet / node / pool stay **0.1**. Do **not** recut miner **0.5**. Wallet **0.1 Windows zip is on tag**; leftover is **Linux / Arch only**.

**1.1 (free) — on tag `1.1`**

1. **Shear-Miner 1.1** (`0b3037c`, https://github.com/rgsneddon/shear-testnet/releases/tag/1.1). Title **`[testnet] Shear-Miner 1.1`**. Mac + Linux + **`Shear-Miner-1.1-windows.zip`** on the tag.
2. Zip root **`Shear-Miner.exe` + `example.bat`**.
3. `--print-config` name **Shear-Miner**, version **1.1**, `feePct` **0**, `clientLogin` **direct**, `headerBytes` 128, pool `pool.shear.digital:1111`. Banner `Shear-Miner 1.1 (free to use, no miner fee)`. **No `.fee` socket.**
4. `--selftest` `selftest ok 5d00a24233609829e59d6e83d9fcd2f262c4014e772a23024fd3db4e66ee2066`. `example.bat` runs `Shear-Miner.exe --pool pool.shear.digital:1111 --user YOUR_SHE1.worker --threads 8`. Optional laptop second-eye: unzip and `--print-config`.

**1.0 (4% fee) — on tag `1.0`**

1. **Shear-Miner 1.0** (`53b72c6`, https://github.com/rgsneddon/shear-testnet/releases/tag/1.0). Title **`[testnet] Shear-Miner 1.0`**. Mac + Linux + **`Shear-Miner-1.0-windows.zip`** on the tag. Built from tag **`1.0`**, not from `main`.
2. Zip root **`Shear-Miner.exe` + `example.bat`**. Do **not** recut / do **not** put 1.1 binaries on this tag.
3. `--print-config` name **Shear-Miner**, version **1.0**, `feePct` **4**, `clientLogin` **dual-fee**, `feeDest` `she1qlrll6hhdakpcrlygumhq5a2xqhcj49ys7j2lzj`, `headerBytes` 128. Banner `Shear-Miner 1.0 (declared 4% fee, dual connection)`. Dual-login `.fee`, `FEE_EVERY` 25.
4. `--selftest` same hash `5d00a242…`. `example.bat` same launch line and mentions the 4% fee.

5. Wallet **Windows zip on tag `0.1`:** `shear-wallet-0.1-windows.zip` (**no miner inside**). Linux / Arch still leftover.

### 2026-08-28 — Windows leftover (Shear wallet 0.2) — **on tag**

Read this file first (`git -C ~/handoff pull`). Pointer: `shear/WINDOWS_HANDOFF.md`. Repo **`rgsneddon/shear-testnet`**. **No sibling tag.** Do **not** recut miner **1.1** / **1.0**.

1. **[testnet] Shear wallet 0.2** (https://github.com/rgsneddon/shear-testnet/releases/tag/0.2). Mac DMG + Android APK on the tag. Continuum/Shearview **full blocks only**.
2. Laptop attached `shear-wallet-0.2-windows.zip` (~13.7 MB, sha256 `e896a824252044159e9865258a15ababea2e48676775878ce356fa624e010f57`) to **the same** `0.2`. Zip root Flutter `shear_wallet.exe`. **No miner inside.** Window title **Shear 0.2**.
3. Also on tag: `-linux.zip` (sha256 `f785ebe3…`) / `-archlinux.zip` (sha256 `cb930fec…`, PKGBUILD `pkgver=0.2`).
4. **Last part done:** `site/index.html` buttons + `#pack-advisory` (macos `fd335b48…`, android `356bbb25…`, windows `e896a824…`, miner 1.1 shas) deployed to `/var/www/shear.digital`.

### 2026-08-28 — Windows leftover (Shear wallet 0.1) — **on tag**

Read this file first (`git -C ~/handoff pull`). Pointer: `shear/WINDOWS_HANDOFF.md`. Repo **`rgsneddon/shear-testnet`**. **No sibling tag.** Do **not** attach to frozen `rgsneddon/shear`. Do **not** recut miner **1.1** / **1.0**.

1. **[testnet] Shear wallet 0.1** (https://github.com/rgsneddon/shear-testnet/releases/tag/0.1). Title **`[testnet] Shear wallet 0.1`**. Mac DMG + Android APK already on the tag.
2. Laptop attached `shear-wallet-0.1-windows.zip` to **the same** `0.1`. Zip root is Flutter `shear_wallet.exe` + `flutter_windows.dll` / `data/` (~13.7 MB, sha256 `e605be153627ebb63dfa970e4fdb1047b48059f265c6c07f4fa14d858ff740f5`). **No miner inside** (`Shear-Miner.exe` / `shear-miner.exe` absent). Window title **Shear 0.1**. Flutter file version `0.1.0+12` is not the pin.
3. Laptop attached 2026-09-01: `shear-wallet-0.1-linux.zip` / `-archlinux.zip` (PKGBUILD `pkgver=0.1`). **No iOS / iPad zip.** Do not upload to the App Store.

### 2026-08-28 — Windows leftover (Shear-Miner 1.0 PE) — historical; still attach the zip

Read this file first (`git -C ~/handoff pull`). Pointer: `shear/WINDOWS_HANDOFF.md`. Repo **`rgsneddon/shear-testnet`**. **No sibling tag.** Do **not** recut miner **0.5**. Wallet / node / pool stay **0.1**. Operator set the miner to **1.0**. **Superseded as the pin by 1.1**; leave tag `1.0` as the last fee build, but **still attach** `Shear-Miner-1.0-windows.zip` (see above).

1. **Shear-Miner 1.0** (`53b72c6`, https://github.com/rgsneddon/shear-testnet/releases/tag/1.0). Title **`[testnet] Shear-Miner 1.0`**. Mac `Shear-Miner-1.0-macos.zip` and Linux `Shear-Miner-1.0-linux.zip` (ELF `0755`) already on the tag.
2. Attach `Shear-Miner-1.0-windows.zip` to **the same** `1.0`. Zip root is **`Shear-Miner.exe` + `example.bat`** (not `shear-miner.exe`).
3. `--print-config` must print name **Shear-Miner**, version **1.0**, `feePct` **4**, `headerBytes` 128, pool `pool.shear.digital:1111`. Banner `Shear-Miner 1.0 (declared 4% fee…)`. Pool login `name=Shear-Miner` `version=1.0`.
4. `--selftest` `selftest ok 5d00a24233609829e59d6e83d9fcd2f262c4014e772a23024fd3db4e66ee2066`. `--user she1…` or `ssa1…` (not `shear1`). Declared **4%** dual-login fee; `FEE_DEST` `she1qlrll6hhdakpcrlygumhq5a2xqhcj49ys7j2lzj` (`.fee`); `FEE_EVERY` 25. No 256 thread clamp.
5. Wallet leftover on tag `0.1` is unchanged (`shear-wallet-0.1-windows.zip` / `-linux.zip` / `-archlinux.zip`, **no miner inside**).

### 2026-08-26 — Mac-cut (Shear wallet 0.1.0) — **handoff for the laptop**

Read this file first. Mac-cut is **on tag** `v0.2.0`. Attach Windows/Linux/Arch to **the same** tag. **`v0.1.0` is the miner pin — do not recut it.** Keep the GitHub release title **`[TESTNET] Shear wallet 0.1.0`**. Do **not** recut **0.0.9**.

**Shear wallet 0.1.0** (reconstructed spendable on unlock; one-block pending settle; header tracks tip; no miner; offer she1):

1. Built from `rgsneddon/shear` `04704b1` / GitHub tag **`v0.2.0`**. Product `kWalletVersion` / `pubspec` **0.1.0** (`0.1.0+10`). Title **`[TESTNET] Shear wallet 0.1.0`**. https://github.com/rgsneddon/shear/releases/tag/v0.2.0
2. Continuum: reconstructed pool `balance` is spendable on first sync. Open-round `pending` hashes + `incoming` receives stay pending until sealed height advances by one. Header `block height` polls `/api/stats` every second. Settlement uses last-settled height so a tip paint cannot skip confirm.
3. Mac DMG sha256 `a6cbecda34dc60f045cfe2bed96cabd6b0371d338992a1a000d9f40f99a4054d` **Notarized Developer ID**. APK ~51 MB sha256 `daff9bbd3f68dcb1ccb517a61f8e0de03e8902c467bab25f709574cae4b26b65`.
4. Laptop attach to **the same** `v0.2.0`: `shear-wallet-0.1.0-windows.zip` / `-linux.zip` / `-archlinux.zip` (**no miner inside**, PKGBUILD `pkgver=0.1.0`). `pack/build_linux.sh` and `pack/zip_linux.sh` already pin **0.1.0**.
5. Miner **0.1.7** stays on `v0.1.7`. Do **not** recut wallet **0.0.9**. Do **not** recut miner **0.1.0**. **No iOS / iPad zip.** **No mainnet zip.** `HASH_TX_LIVE` stays **0**.
6. Live consensus to keep: **9s** ASERT, **0.1 SHE** pot, **1e-11**/hash, sample prune **1000**.

### 2026-08-26 — Mac-cut (Shear wallet 0.0.9) — **done on Amelia**

Read this file first. Laptop leftover Windows/Linux/Arch was **already on** `v0.0.9`. Apple DMG + APK clobbered onto **the same** tag. No sibling. Keep the GitHub release title **`[TESTNET] Shear wallet 0.0.9`**. Do **not** recut **0.0.8**.

**Shear wallet 0.0.9** (Continuum live pending hashes + mempool receives; spendable on sealed-height advance; no miner; offer she1):

1. Built from `rgsneddon/shear` tag **`v0.0.9`** (`92783e2`). `kWalletVersion` and `pubspec` **0.0.9** (`0.0.9+9`). Title **`[TESTNET] Shear wallet 0.0.9`**. https://github.com/rgsneddon/shear/releases/tag/v0.0.9
2. Continuum: pool `/api/wallet/balance` `pending` (miner hashes) + `incoming` (mempool pays). `syncCredits` paints those as Pending. When `/api/stats` height advances, `confirmRound` settles that round into Spendable. Demo `_findBlock` is not the live path.
3. Mac DMG sha256 `ddd5dcd315d4459ea1d4e38a681a3b0b0d2d18fbce95fe0d5b4e98b81f70df71` **Notarized Developer ID**. `spctl --assess --type execute` = **Notarized Developer ID**.
4. Mac APK second-eyed OK (~51 MB, sha256 `0726846c2c17f7ae5ddf30c6844f068a548a86be54d6f49cb4d35c6b5de3bd03`, `AndroidManifest.xml` + `libapp.so`, versionName `0.0.9` / versionCode `9`).
5. Laptop leftover **already on tag**: `shear-wallet-0.0.9-windows.zip` / `-linux.zip` / `-archlinux.zip` (**no miner inside**, PKGBUILD `pkgver=0.0.9`).
6. Miner **0.1.7** stays on `v0.1.7`. Do **not** recut **0.0.8**. **No iOS / iPad zip** on GitHub until App Store review. Do **not** upload Shear to the App Store. **No mainnet zip.** `HASH_TX_LIVE` stays **0**.
7. Live consensus to keep: **9s** ASERT, **0.1 SHE** pot, **1e-11**/hash, sample prune **1000**.

### 2026-08-25 — Windows leftover (Shear miner 0.1.6 PE)

Read this file first (`git -C ~/handoff pull`). Pointer: `shear/WINDOWS_HANDOFF.md`. **No sibling tag.** Do **not** recut **0.1.5** / **0.1.4** / **0.1.3**. `HASH_TX_LIVE` stays **0**. Darwin leftover stays on Amelia’s Mac.

1. **Shear miner 0.1.6** (`9907ecc`, https://github.com/rgsneddon/shear/releases/tag/v0.1.6). Title **`[TESTNET] Shear miner 0.1.6`**. Mac `shear-miner-0.1.6-macos.zip` and Linux `shear-miner-0.1.6-linux.zip` (ELF `0755`) already on the tag. Attach `shear-miner-0.1.6-windows.zip` to **the same** `v0.1.6`. `--selftest` `selftest ok 6e95b9033c5d044d08bbf854fb2e5343ca3103b96ae37bde101258d43cfacc63`. Declared **5%** dual-login fee; `FEE_DEST` `she1qlrll6hhdakpcrlygumhq5a2xqhcj49ys7j2lzj` (`.fee`). Mainnet amends this dest. `--user she1` / `shp1`. No 256 clamp.

### 2026-08-25 — Windows leftover (Shear wallet 0.0.8) — **done on the laptop**

Read this file first (`git -C ~/handoff pull`). Mac-cut was **on tag**. Leftover zips attached to **the same** `v0.0.8`. No sibling. Keep the GitHub release title **`[TESTNET] Shear wallet 0.0.8`**. Do **not** recut **0.0.7**.

**Shear wallet 0.0.8** (1 SHE + 1e-11/hash, eight-digit public amounts, **no miner**, offer she1):

1. Built from `rgsneddon/shear` `74faa0b` / tag `v0.0.8`. Mac DMG sha256 `5b37b9b9192a93e1b9eef4084e62d97a84ac958e1572ca6fd49391054b40a1af` **Notarized Developer ID**.
2. Mac APK second-eyed OK (~51 MB, sha256 `dbd4d1ea5aed004c925b39d87cedcae2fceecc40b5e3cfb2dff76df36cf5e5f5`).
3. `shear-wallet-0.0.8-windows.zip` / `-linux.zip` / `-archlinux.zip` attached to **the same** `v0.0.8` (no sibling). **No miner inside.** Title Shear 0.0.8. PKGBUILD `pkgver=0.0.8`. `pack/build_linux.sh` and `pack/zip_linux.sh` already pin **0.0.8**.
4. Miner pin is **0.1.5** on `v0.1.5`. **0.1.4 is deprecated** (too slow). Do **not** recut **0.1.3** / **0.1.4** / **0.0.7**. **No iOS / iPad zip** on GitHub until App Store review. Do **not** upload Shear to the App Store. **No mainnet zip.** Do **not** drop the `[TESTNET]` prefix on the GitHub release title.

### 2026-08-24 — Windows leftover (Shear wallet 0.0.7 + GNFP wallet 0.2.3) — **done on the laptop**

Read this file first (`git -C ~/handoff pull`). Mac-cut was **on tag**. Leftover zips attached to **the same** tags. No sibling. Do **not** recut **0.0.6** / **0.2.2**.

**Shear wallet 0.0.7** (1 SHE + 1e-11/hash, eight-digit public amounts, **no miner**):

1. Built from `rgsneddon/shear` `1f3e91f` / tag `v0.0.7`. Mac DMG sha256 `c93af58d56eff3fe9c37026ace080c986cc88fb58a29ccac04eef98924b63759` **Notarized Developer ID**.
2. Mac APK second-eyed OK (~51 MB, sha256 `97bc084f022e74bdbb2527c552f0e59ded5f9041433474210c15e08e4bae668f`).
3. `shear-wallet-0.0.7-windows.zip` / `-linux.zip` / `-archlinux.zip` attached to **the same** `v0.0.7` (no sibling). **No miner inside.** Title Shear 0.0.7. PKGBUILD `pkgver=0.0.7`.
4. Miner **0.1.2** stays on `v0.1.2`. Do **not** recut **0.0.6**. **No iOS / iPad zip** on GitHub until App Store review. Do **not** upload Shear to the App Store. **No mainnet zip.**

**GNFP wallet 0.2.3** (eight-digit public amounts; 1e-11 book units):

1. Built from `rgsneddon/gnfp-wallet` `18eff2a` / tag `v0.2.3`. Mac DMG sha256 `28f740eaa878ee0354bcd950ae3ac03df284e28f517b87c1230a2f338ba998b5` **Notarized Developer ID**; zip `9a484bcd8510706ce611b5dfa4fcf8d43132ef77e4f2878c4d93dd972a8278ca`.
2. Mac APK second-eyed OK (~51 MB, sha256 `c6dd14bda451f83d871ba86b37034b0e20bb3d14add5720be6fe8e86571736dd`).
3. `gnfp-wallet-0.2.3-windows.zip` / `-linux.zip` / `-archlinux.zip` attached to **the same** `v0.2.3` (no sibling). CLI `pack\gnfp-cli.cmd --version` = `$GNFP core wallet v0.2.3 (cli)`. Bundled `gnfp-cminer.exe` / `gnfp-cminer` next to the GUI as on 0.2.2. In-zip `--selftest` printed `selftest ok 986437c40fee8a876e0ca3f1e58b14fa38785a179f57f98ebbb0fb03102bd4eb`. Title `$GNFP core wallet v0.2.3`. PKGBUILD `pkgver=0.2.3`.
4. Do **not** recut **0.2.2**. Do **not** rebuild gnfp-cminer **1.1.2**. `HASH_TX_LIVE` stays **0**. Live DE already pays 1e-11/hash; this pin is display + Join units.

### 2026-08-24 — Windows leftover (Shear wallet 0.0.6 + GNFP wallet 0.2.2) — **done on the laptop; do not recut**

Leftover zips for **0.0.6 / 0.2.2** are already on those tags. Current pin is **0.0.7 / 0.2.3**. Do **not** attach more files to `v0.0.6` / `v0.2.2`.

### 2026-08-24 — Windows leftover (Shear wallet 0.0.5, no miner) — **done on the laptop**

Read this file first (`git -C ~/handoff pull`). Pointer: `shear/WINDOWS_HANDOFF.md`. Repo is **private**. Pin **0.0.5**. **Does not mine.**

**Miner 0.1.2 is already on `v0.1.2`. Do not recut it. Do not put `shear-miner` / `shear-miner.exe` in any wallet zip.**

**Laptop attach (done 2026-08-24 from this Windows box):**

1. Built from `rgsneddon/shear` `main` `bc7c565` / tag `v0.0.5`.
2. Mac APK second-eyed OK (~51 MB, `AndroidManifest.xml` + `libapp.so`).
3. `shear-wallet-0.0.5-windows.zip` / `-linux.zip` / `-archlinux.zip` attached to **the same** `v0.0.5` (no sibling). **No miner inside.** Title Shear 0.0.5. PKGBUILD `pkgver=0.0.5`.
4. Do **not** recut wallet **0.0.4**. Do **not** rebuild miner **0.1.2** / **0.1.1**. Do **not** cut a mainnet genesis zip. Do **not** invent a sibling tag. Do **not** upload Shear to the App Store.

### 2026-08-24 — Windows leftover (Shear miner 0.1.2 / wallet 0.0.4) — **done on the laptop** (superseded; do not recut 0.0.4)

Read this file first (`git -C ~/handoff pull`). Pointer: `shear/WINDOWS_HANDOFF.md`. Repo is **private**.

**Laptop attach (done 2026-08-24 from this Windows box):**

1. **Miner 0.1.2** `shear-miner-0.1.2-windows.zip` attached to **the same** `v0.1.2` (no sibling; Mac `shear-miner-0.1.2-macos.zip` already on tag). `--selftest` printed `selftest ok 6e95b9033c5d044d08bbf854fb2e5343ca3103b96ae37bde101258d43cfacc63`. `--user shp1…`. Default `pool.shear.digital:1111`. No 256 thread clamp.
2. **Wallet 0.0.4** Windows/Linux/Arch attached to **the same** `v0.0.4` (no sibling). Miner **0.1.2** is **inside** those zips next to the GUI. Title Shear 0.0.4. she is private. shp1 dests. Testnet `shear-testnet-v1`. **No mainnet zip.**
3. Do **not** attach Shear binaries to any other project’s GitHub tags. Do **not** invent a sibling tag. Do **not** cut a mainnet genesis zip. Do **not** rebuild miner **0.1.1** or wallet **0.0.3**.

### Inherit from GNFP pool — session thread inventory (2026-08-24)

Live GNFP (`~/gnfp`, book `gnfp/src/miner_stats.js`) had miner-b58b69b4 worker **EP01** flipping **32 claimed / 32 device** and **230 claimed / 256 device** every few seconds, H/s stuck ~56 MH/s, tile **HONEST**. Two stratum clients shared `wallet.EP01`. Last submit overwrote inventory; accepts from both still summed. Honesty is `claimed <= device` on the **banner**, so both snapshots looked honest.

**Rule Shear must keep when it inherits the GNFP miner book:**

| Do | Do not |
|----|--------|
| One inventory per **TCP session** (socket id). Remote IP is not unique (two processes on one box). | Last-write `threads` / `cpuCores` / `cpuThreads` onto the login name |
| Worker row = **sum** utilised + **sum** each session’s device | `max` device across sessions and last claimed |
| Honesty **per TCP session** (`claimed <= that socket’s cpuThreads`). Table may still **sum** sessions | Honesty (or **ban / TCP-kick**) on the **folded** sum — that locked out 240-thread farms |
| Key by **full login** `wallet.worker` | Key by wallet only (`parseLogin` today strips `.worker`) |
| Drop only that session on disconnect | `connected=false` on the whole worker when one socket dies |
| Keep the miner-fee dual-login out of the 1-thread H/s baseline | Let fee `threads=1` + farm H/s poison inferred “work N” |
| **No `--threads` 256 clamp** in Shear miner (same as gnfp-cminer **1.1.1**: device logical CPUs only, no hardcoded farm-size lid) | Reintroduce `MAX_THREADS 256` / `min(..., 256)` on `--threads` |

Small copy already in Shear: `foldConnectionInventory` (`pool/src/pool.js`), spec `specs/pool.md`, tests in `pool/tests/test_pool.js`. When the full GNFP miner table / honesty / hashed tags land, copy `gnfp/src/miner_stats.js` session fold + **per-session** honesty + `banMiner` no-op, not folded-row `thread_cheat` kicks, not the pre-2026-08-24 last-write book.

Incident tag: public miner `miner-b58b69b4` worker EP01 (flicker). Follow-up 2026-08-24: same class of large farms kicked — see **GNFP pool — large-farm kick/ban** below. Miner pin **gnfp-cminer 1.1.1** has **no `--threads` 256 clamp** — Shear miner must keep that (device logical CPUs only; do not put `MAX_THREADS 256` back). Not a sibling tag. Do **not** invent a sibling tag.

### Inherit from GNFP miner — no 256 thread clamp (2026-08-24)

GNFP official CPU miner **1.1.1** (`rgsneddon/gnfp-cminer` `v1.1.1`): `--threads N` is **not** `min`'d with 256. `honor_threads(requested, device_logical)` is the only cap. SHA-256 bit width and `PRE_CAP 256` buffers are **not** thread clamps.

**Shear miner inherit:**

| Do | Do not |
|----|--------|
| Honor `--threads` up to this machine’s logical CPUs | `#define MAX_THREADS 256` or `min(n, 256)` on worker count |
| Ship a new Shear miner pin if you copy this (do not rewrite an old tag) | Rebuild GNFP **1.1.0** or invent `vX.Y.Z-windows` siblings |
| Keep pool honesty as `claimed <= device` (unlist inflate, **no ban**) | TCP-kick large farms for high `--threads` |

`HASH_TX_LIVE` stays **0**. Testnet only on Shear.

### Inherit from GNFP pool — difficulty ceiling 256 bits (2026-08-24)

Live GNFP (`~/gnfp` → DE `/opt/restore-privacy/perc_chain`, `rpt-gnfp-pool`) froze at **`difficultyBits=32` / `difficulty=4294967296`**. Explorer showed **4.2 billion**. Large CPU farms (~0.2–2 GH/s) kept producing **~6–16s** blocks against a 90s target. `2^32` is not a SHA-256 limit — it was `MAX_DIFFICULTY_BITS=32` in book law plus vardiff `VARDIFF_MAX_BITS=24`.

**Live fix (DE `rpt-gnfp-pool` restarted 2026-08-24 16:48 UTC).** Deployed `src/book_law.js` `src/gnfp_vardiff.js` `src/chronoflux_chain.js` `src/gnfp_nodes.js` `src/gnfp_pool_credit.js` `src/gnfp_pool.js`:

| Do | Do not |
|----|--------|
| Block + share ceiling **256 bits** (hash width) | Keep `MAX_DIFFICULTY_BITS=32` / vardiff max **24** |
| Per-session vardiff still **never exceeds** current block bits; CPU sessions stay ~16–18 | Issue 256-bit share jobs to a 1-thread miner |
| GPU/ASIC refuse at client / nonce / solution (sequential 8-round hash) | Treat a higher PoW ceiling as permission to mint from lolminer / 208-hex blobs |
| Climb from this-uptime block intervals (restart warmup still ignores a 0.5s disk interval) | Apply a pre-restart 20ms interval before this process has formed a block |
| Next **gnfp-node** pin copies `MAX_DIFFICULTY_BITS=256` (source already has it) | Recut public **1.2.7** / invent `v1.2.7-…` siblings |

After restart: height kept climbing (`gnfp-germany-book-v1`); **bits 32 → 33** (`2^33` work) on the first uptime retarget. Miners reconnect TLS default. `HASH_TX_LIVE` stays **0**. Pool fee stays **1%**. Do **not** retarget on the miner.

**Shear must copy this before testnet hashrate outruns 32 bits:**

| Do | Do not |
|----|--------|
| `crypto/asert.js` `MAX_BITS = 256`; `clampBits` / `nextBits` use it | `MAX_BITS = 32` or “legacy 1..32” as a live lid |
| `pool/src/share_vardiff.js` default `maxBits` = `MAX_BITS`; share bits never exceed header `bits` | Hardcode vardiff max **24** or **32** |
| Specs: `specs/consensus.md`, `specs/pool.md` Resistance ceiling **256** | Leave “ceiling 32 bits” in Shear docs |
| GPU/ASIC stay out at the ShearHash share gate | Weaken client / nonce / solution refusals to “fix” block time |

Shear source on this Mac already has that cap. Testnet only. Do **not** cut a mainnet genesis zip. Do **not** invent a sibling tag.

### Inherit from GNFP pool — mint bonus 1e-10 / 10-digit frame (2026-08-24)

Live GNFP (`~/gnfp` → DE `/opt/restore-privacy/perc_chain`, `rpt-gnfp-pool` restarted **2026-08-24 17:42 UTC**) pays **0.0000000001 GNFP per proven hash** plus **1 GNFP per formed block** (split by in-window work). Public amounts use a **10-digit** frame so one hash prints as `0.0000000001`, not a 9-digit zero. Integer book unit moved **1e9 → 1e10** (`NANOS_PER_GNFP`; the name is not SI nano). Fingerprint now includes that scale: `gnfp-book-law-1:90000:14:21:14:1:10000000000:1:100:16384:10:1:1:1:1:1`. `/api/network` publishes `hashBonusGnfp=1e-10` `blockRewardGnfp=1` `nanosPerGnfp=10000000000`. Pool fee stays **1% of the 1-coin pot**.

**`HASH_TX_LIVE` stays 0.** That flag is **lean collate**: do **not** persist one open-window object per hash. Block-found pot + per-hash bonus are **still sealed** (`hashBonusGnfp` on the block, miner credits). Do **not** treat `HASH_TX_LIVE=0` as “bonus off”. Flip to 1 only at a later coordinated hard fork.

**Shear inherit (acknowledge; do not cut a live Shear mint, do not cut a mainnet genesis zip):**

| Do | Do not |
|----|--------|
| **1 SHE** pot per formed block, split by in-window work | 1 coin per miner, or a 50-coin pot |
| **0.0000000001 SHE per proven hash** (`HASH_BONUS` = 1 unit of 10^{-10}) | Keep a 1e-9 / 9-digit bonus that rounds one hash to zero |
| Public amount frame **10 fractional digits** (`0.0000000000`) | `toFixed(9)` / 10^{-9} display |
| Keep `HASH_TX_LIVE=0` as lean collate | Confuse that pin with the bonus rate, or enact `HASH_TX_LIVE=1` |
| Next Shear pin copies this law when you ship it | Deploy a Shear mint-law change to a live pool from this note, recut GNFP **1.2.7** / wallet **0.2.1** / miner **1.1.1**, or invent a sibling tag |

Do **not** rewrite historical sealed amounts. Do **not** recut public **gnfp-node 1.2.7**. Testnet only on Shear.

### 2026-08-23 — Windows leftover (Shear miner 0.1.1 / wallet 0.0.3) — **done on the laptop**

Read this file first (`git -C ~/handoff pull`). Pointer: `shear/WINDOWS_HANDOFF.md`. Repo is **private**.

**Laptop attach (done 2026-08-23 from this Windows box):**

1. **Miner 0.1.1** `shear-miner-0.1.1-windows.zip` attached to **the same** `v0.1.1` (no sibling). `--selftest` printed `selftest ok 6e95b9033c5d044d08bbf854fb2e5343ca3103b96ae37bde101258d43cfacc63`. `--user sdcard1…` or `she1…`. Default `--pool pool.shear.digital:1111`.
2. **Wallet 0.0.3** Windows/Linux/Arch attached to **the same** `v0.0.3` (no sibling). Miner **0.1.1** is **inside** those zips next to the GUI. Title Shear 0.0.3. Testnet `shear-testnet-v1`. sdcard1 and she1 dests. **No mainnet zip.**
3. Do **not** attach Shear binaries to any other project’s GitHub tags. Do **not** invent a sibling tag. Do **not** cut a mainnet genesis zip.

### 2026-08-23 — Windows leftover (Shear miner 0.1.0 / wallet 0.0.1) — **done on the laptop**

Read this file first (`git -C ~/handoff pull`). Pointer: `shear/WINDOWS_HANDOFF.md`. Repo is **private**.

**Laptop attach (done 2026-08-23 from this Windows box):**

1. **Miner 0.1.0** `shear-miner-0.1.0-windows.zip` attached to **the same** `v0.1.0` (no sibling). `--selftest` printed `selftest ok 6e95b9033c5d044d08bbf854fb2e5343ca3103b96ae37bde101258d43cfacc63`. `client=ShearHash`. Default `--pool pool.shear.digital:1111`.
2. **Wallet 0.0.1** Windows/Linux/Arch attached to **the same** `v0.0.1` (no sibling). Miner is **inside** those zips next to the GUI. Title Shear 0.0.1. Testnet `shear-testnet-v1`. `shear1` addresses. **No mainnet zip.**
3. Do **not** attach Shear binaries to any other project’s GitHub tags. Do **not** invent a sibling tag. Do **not** cut a mainnet genesis zip.

## GNFP client releases (one table)

Current public pins. No sibling tags. Admit floor **GNFPHash 1.0.4+**; **1.0.3 and lower earn nothing**. Prefer **gnfp-cminer 0.5**. Honor: running workers within **logical SMT threads** (`--threads 10` on 6-core/12-thread is honest). **No `--threads` 256 clamp.**

| Client | Pin | GitHub | Shipped on this Mac | Laptop leftover |
|--------|-----|--------|---------------------|-----------------|
| **Wallet** | **0.2.6** | https://github.com/rgsneddon/gnfp-wallet/releases/tag/v0.2.6 | Paint 0 after `join_clear`. Unique join1 per gnfp1. **Does not mine.** No Mine tab. No bundled `gnfp-cminer`. Title `$GNFP core wallet v0.2.6`. Do **not** recut **0.2.5**. | Mac-cut + Windows/Linux/Arch **on tag**: `gnfp-wallet-0.2.6-macos.dmg` sha256 `8743bc329f5a4d0718f1b626712b9b2323d7356f4d031e5a2c6e945bb4336354`, `-macos.zip` sha256 `5aab9f401ba24c7c6ee1750b808cb62030ddf2c2b9339b839746bcb593e1ad76`, `-android.apk` sha256 `86d7725d353f3b89212173af917d319174618307cf8402da0512a11f8e68ed5c`, `-windows.zip` sha256 `aae4ccce07080cc7ce51403726a18e40248bd7c0dbfa638df6efe07c86b9eef3` (zip-root Flutter `gnfp_wallet.exe`, **no cminer inside**), `-linux.zip` sha256 `202b77325ec3975c933a0ddf33c38ee90987a74eead14adfaff14fc850188598` (ELF `7f454c46`), `-archlinux.zip` sha256 `a8f9207f3e3357377d476202f456bddbdb578d33922d25cf3f956e49dda463e4` (`pkgver=0.2.6`). CLI `$GNFP core wallet v0.2.6 (cli)`. Historical **0.2.5** Mac/Android **on tag** — do **not** recut leftover **0.2.5**. Do **not** invent a sibling tag. |
| **Miner** | **gnfp-cminer 0.5 public** | https://github.com/rgsneddon/gnfp-cminer/releases/tag/v0.5 | Same hasher as 0.4. Fee offset + lazy fee connect. Darwin arm64 **DMG** + Linux ELF (`0755`, `avx2-x8`) + Windows **`gnfp-cminer.exe` + `example.bat`**. `--selftest` **ok** `986437c4…`. Do **not** recut **0.4**. | **on tag.** Zip root `gnfp-cminer.exe` + `example.bat` (static PE). `gnfp-cminer-0.5-macos.dmg` signed. Do **not** ship leftover `1.0.6-max-autotune`. |
| **Node miner (deprecated)** | **GNFPHash 1.0.6** | https://github.com/rgsneddon/GNFPHash/releases/tag/v1.0.6 (`dbc222c`) | Deprecated as the miner everyone should pull. Still earns at **1.0.4+**. | Do **not** rebuild 1.0.5. Prefer gnfp-cminer. |
| **Node** | **1.2.7** | https://github.com/rgsneddon/gnfp-node/releases/tag/v1.2.7 | `gnfp-node-1.2.7-{macos,linux}.tar.gz` + windows **source** zip. Equal daemon default. Admit floor **1.0.4+**. `HASH_TX_LIVE=0`. | Optional PE-style zip. `--print-config` `version=1.2.7` `equalNode=true` `hashTxLive=0`. Do **not** rebuild 1.2.6. |

How-to for each node pack: README on `v1.2.7`. Pool https://gnfp.restoreprivacy.online · Explorer https://explorer.restoreprivacy.online · Germany `de.restoreprivacy.online:1474` · Singapore `sg.restoreprivacy.online:1474` (peers, not masters).

### 2026-08-25 — Windows leftover (gnfp-cminer 0.5 PE) — **done**

Read this file first (`git -C ~/handoff pull`). Pointer: `gnfp-cminer/WINDOWS_HANDOFF.md`. Repo is **public**. Pin **0.5**. **No sibling tags.** Do **not** recut **0.4**. `HASH_TX_LIVE` stays **0**.

`--clobber` onto **the same** `v0.5` (https://github.com/rgsneddon/gnfp-cminer/releases/tag/v0.5): Windows PE + `example.bat` at zip root, Linux ELF tar.gz, macOS DMG. Source-only windows zip is gone.

1. Built from `rgsneddon/gnfp-cminer` **`v0.5`** / `9c99cc7`. Same hasher as 0.4; fee clock is offset + lazy connect. Static PE (no extra DLLs).
2. `gnfp-cminer.exe --selftest` vector `986437c40fee8a876e0ca3f1e58b14fa38785a179f57f98ebbb0fb03102bd4eb`.
3. Startup prints `offset=N/20`. Fee login does **not** happen until the first fee share.
4. `gnfp-cminer-0.5-windows.zip` has `gnfp-cminer.exe` + `example.bat` at zip root. `gnfp-cminer-0.5-linux.tar.gz` ELF `0755`. `gnfp-cminer-0.5-macos.dmg` Developer ID signed.
5. Do **not** recut **0.4**. Do **not** ship leftover `1.0.6-max-autotune`.

### 2026-08-25 — gnfp-cminer 0.4 (Desktop miner as shipped) — **done on this Mac** (superseded by 0.5; do not recut)

Read this file first (`git -C ~/handoff pull`). Pointer: `gnfp-cminer/WINDOWS_HANDOFF.md`. **No sibling tags.** Do **not** recut **0.4** / **1.1.6**. `HASH_TX_LIVE` stays **0**. No miner source edits.

1. **gnfp-cminer 0.4** (`de719c5`, https://github.com/rgsneddon/gnfp-cminer/releases/tag/v0.4). Title **`gnfp-cminer 0.4`**. Latest. Windows `gnfp-cminer-0.4-windows.zip` is the Desktop `gnfp` folder **byte-identical** (`gnfp_cminer_v0.4.exe` sha256 `b9f0328748c4a88e62b384d32b5078eb52b04355cc311a17a64132eb95e70528` + the five OpenSSL/MinGW DLLs). Darwin `gnfp-cminer-0.4-macos.tar.gz` `--selftest` `986437c4…` `backend=scalar-x8`. Linux `gnfp-cminer-0.4-linux.tar.gz` ELF `0755` `--selftest` `986437c4…` `backend=avx2-x8`. **1.1.6 is not the pin.**
2. Do **not** rebuild the Windows PE. Do **not** ship leftover `1.0.6-max-autotune`.

### 2026-08-25 — Windows leftover (gnfp-cminer 1.1.6 PE/ELF + shear-miner 0.1.4 Windows) — **done on the laptop**

Read this file first (`git -C ~/handoff pull`). Pointers: `gnfp-cminer/WINDOWS_HANDOFF.md`, `shear/WINDOWS_HANDOFF.md`. **No sibling tags.** Do **not** recut **1.1.5** / **0.1.3**. `HASH_TX_LIVE` stays **0**. Darwin leftover for both miners stays on Amelia’s Mac. Do not overvolt or enable AVX in BIOS.

1. **gnfp-cminer 1.1.6** (`eda2602`, https://github.com/rgsneddon/gnfp-cminer/releases/tag/v1.1.6). Runtime SHA-NI/AVX2 dispatch; auto times legal kernels and keeps the fastest; `--backend scalar` hatch. Default CFLAGS have no `-mavx2`/`-msha`. Fee still 5% dual-login `"login"` + `fTAIL_worker`. Laptop attached `gnfp-cminer-1.1.6-windows.zip` + `gnfp-cminer-1.1.6-linux.tar.gz`. Linux ELF `-rwxr-xr-x`; extract-run `--selftest` **without chmod** `986437c4…`. This-host `--bench` 2-thread auto **~824 kH/s** `avx2-x8` vs `--backend scalar` **~207 kH/s** vs 1.1.5 **~221 kH/s**.
2. **Shear miner 0.1.4** (`2b04af7`, https://github.com/rgsneddon/shear/releases/tag/v0.1.4). Laptop `shear-miner-0.1.4-windows.zip`. `--selftest` `6e95b903…` `x8-independent ok`. **1 hash = 1 tx**. **No miner fee**. `--user she1` / `shp1`. No 256 clamp.

### 2026-08-25 — Windows leftover (gnfp-cminer 1.1.5 PE/ELF + shear-miner 0.1.3 Windows) — **done on the laptop**

Read this file first (`git -C ~/handoff pull`). Pointers: `gnfp-cminer/WINDOWS_HANDOFF.md`, `shear/WINDOWS_HANDOFF.md`. **No sibling tags.** Do **not** recut **1.1.4** / **0.1.2**. `HASH_TX_LIVE` stays **0**. Darwin leftover for both miners stays on Amelia’s Mac.

1. **gnfp-cminer 1.1.5** (`fe9ad28`, https://github.com/rgsneddon/gnfp-cminer/releases/tag/v1.1.5). Scalar-x8 + first-block midstate on long `preWork`. Fee still 5% dual-login `"login"` + `fTAIL_worker`. Laptop attached `gnfp-cminer-1.1.5-windows.zip` + `gnfp-cminer-1.1.5-linux.tar.gz`. Linux ELF listing `-rwxr-xr-x`; extract-run `--selftest` **without chmod** `selftest ok 986437c40fee8a876e0ca3f1e58b14fa38785a179f57f98ebbb0fb03102bd4eb backend=scalar-x8`. `--bench` 2-thread 10s **210.79 kH/s** vs 1.1.4 **187.15 kH/s**. DE probe shares accepted. Do **not** ship leftover `1.0.6-max-autotune`.
2. **Shear miner 0.1.3** (`7220ecc`, https://github.com/rgsneddon/shear/releases/tag/v0.1.3). Laptop `shear-miner-0.1.3-windows.zip`. `--selftest` `selftest ok 6e95b9033c5d044d08bbf854fb2e5343ca3103b96ae37bde101258d43cfacc63` `x8-independent ok`. **1 hash = 1 tx** (each meeting nonce is its own share). **No miner fee** / no `FEE_ADDR` / `clientLogin=single`. `--user she1` / `shp1`. No 256 clamp.

### 2026-08-24 — Windows leftover (gnfp-cminer 1.1.4 PE / ELF + wallet 0.2.4) — **done on the laptop**

Read this file first (`git -C ~/handoff pull`). Pointer: `gnfp-cminer/WINDOWS_HANDOFF.md`. Repo is **public**. Pin **1.1.4**. **No `--threads` 256 clamp.** Fee worker is `fTAIL_worker`.

Mac already cut the pin (`b56ede9`, https://github.com/rgsneddon/gnfp-cminer/releases/tag/v1.1.4). Darwin **arm64** is on the tag. Laptop `--clobber` PE + ELF onto **the same** `v1.1.4`. **No sibling tag.** Do **not** recut **1.1.3**.

**What Mac already did (do not redo):**

1. Pulled rvp-design GitHub UI uploads (`gnfp_cminer_win.c`, `gnfp_cminer_lin`, `gnfp_win.exe`, `VERSION 1.0.6-max-autotune`). Safety review. **Stashed** under `leftover/rvp-1.0.6-max/` — **not the pin**.
2. Official `src/` bumped to **1.1.4**. Fee login is now `FEE_ADDR.f<last6>_<first8 of worker>` so the book shows who paid. Example: `--user gnfp18ff7e8b2f0ef3e96f598231638aafd5a5abc490c.testc` → fee `gnfp19381c4b1d7a9cbae64120f24b16d248ae07c6ff1.fbc490c_testc`. Fee socket still `"login"` + `threads=1`. Local stratum test: 20 main / 1 fee share.
3. Darwin `--selftest` printed `selftest ok 986437c40fee8a876e0ca3f1e58b14fa38785a179f57f98ebbb0fb03102bd4eb backend=scalar-x8`. `make test` ok (admit / local stratum / readme / scalar ISA / public host).
4. Attached to `v1.1.4`: `gnfp-cminer-1.1.4-macos.tar.gz` (sha256 `d7dd0a3787c130d98a1bad480dcff0d4f4a381a3bbe9cdbb38bbdf371154a486`) + source linux tar + source windows zip. `--clobber` PE/ELF onto **those same names**.

**Do not ship leftover `1.0.6-max-autotune` (laptop or Germany):**

| File | Why not |
|------|---------|
| `leftover/rvp-1.0.6-max/gnfp_cminer_lin` | No `"login"` field — pool takes `msg.login` then `msg.user`; `"user"` is the miner gnfp1; submit overwrites `"id"` with jobId, so fee shares credit the **miner**, not `FEE_ADDR`. SHA-NI `sha256_fast_ni` is one 64-byte block (stack overflow on short pre / `--selftest` / `--bench`). `--threads` 256 clamp is back. |
| `leftover/rvp-1.0.6-max/gnfp_win.exe` | Same source. Same bugs. |
| `leftover/rvp-1.0.6-max/gnfp_cminer_win.c` | Source for the two binaries. Fee-worker idea was kept in official 1.1.4; this file is not the pin. |

Strings check on a bad binary: `1.0.6-max-autotune` and `"id":"%s","user":"%s","worker":"%s"` without `"login"`. Official 1.1.4 must have `"login":"%s"` and `VERSION "1.1.4"`.

**Laptop attach (done 2026-08-24 from this Windows box):**

1. Built official `src/` at `v1.1.4` (`b56ede9`). **No** `-mavx2` / `-msha`. PE static OpenSSL 3 (system DLLs only: ADVAPI32, CRYPT32, KERNEL32, msvcrt, USER32, WS2_32). WSL ELF `ymm_lines=0`.
2. `--selftest` printed `selftest ok 986437c40fee8a876e0ca3f1e58b14fa38785a179f57f98ebbb0fb03102bd4eb backend=scalar-x8`. Help `GNFPHash C miner 1.1.4` + `fTAIL_worker`. **Not** `1.0.6-max-autotune`. Strings have `"login":"%s"` and `VERSION "1.1.4"`.
3. `--clobber` `gnfp-cminer-1.1.4-windows.zip` (zip root `example.bat` + `gnfp-cminer.exe`) and `gnfp-cminer-1.1.4-linux.tar.gz` (ELF) onto **the same** `v1.1.4`. Darwin macos tar not recut.
4. Wallet **0.2.4** (`8fe9adb`): `gnfp-wallet-0.2.4-{windows,linux,archlinux}.zip` + CLI on **the same** `v0.2.4`. Title `$GNFP core wallet v0.2.4`. CLI `--version` = `$GNFP core wallet v0.2.4 (cli)`. **No cminer inside.** PKGBUILD `pkgver=0.2.4`. Mac APK not on the tag (dmg/zip already); did not invent Android here.
5. Do **not** recut **1.1.3**. Do **not** rebuild **1.1.2**. Do **not** recut wallet **0.2.3**. Do **not** bundle the PE into the wallet zip. `HASH_TX_LIVE` stays **0**.

**Who is paying:** after miners pull 1.1.4, fee address `gnfp19381c4b1d7a9cbae64120f24b16d248ae07c6ff1` shows workers `f<last6>_<worker>`. Blob `.fee` (1.1.3 and older) or no fee login at all = not this pin. RVP max ELF looks unpaid because fee submits never used `"login"=FEE_ADDR`.

### 2026-08-24 — gnfp-cminer 1.1.2 (v0.4 Windows + example.bat) — **done**

Read this file first (`git -C ~/handoff pull`). Pointer: `gnfp-cminer/WINDOWS_HANDOFF.md`. Repo is **public**. Pin **1.1.2**. **No `--threads` 256 clamp.**

1. Windows PE is Desktop `gnfp4/gnfp_cminer_v0.4.exe` with login version patched **1.0.5 → 1.1.2** (same length). OpenSSL DLLs from that folder sit next to `gnfp-cminer.exe`. Zip root has **`example.bat`** (`gnfp1YOURADDRESS.worker`, `--threads 8`).
2. Darwin **arm64** and Linux **x86_64 ELF** (`avx2-x8` on DE gcc) built from `~/gnfp-cminer` `de719c5`. `--selftest` `selftest ok 986437c40fee8a876e0ca3f1e58b14fa38785a179f57f98ebbb0fb03102bd4eb`.
3. Attached to **the same** `v1.1.2` (no sibling): `gnfp-cminer-1.1.2-macos.tar.gz` / `-linux.tar.gz` / `-windows.zip`.
4. Do **not** recut **1.1.1**. Do **not** invent a sibling tag. Wallet **0.2.1** still bundles **1.1.0** inside the zip — do **not** upload a standalone miner installer onto `v0.2.1`. Do **not** recut wallet **0.2.1** or node **1.2.7** for the 1e-10 bonus / 10-digit frame (those are live on the DE book).

### 2026-08-24 — Windows leftover (gnfp-cminer 1.1.1 PE / ELF) — **done on the laptop** (superseded; do not recut 1.1.1)

Read this file first (`git -C ~/handoff pull`). Pointer: `gnfp-cminer/WINDOWS_HANDOFF.md`. Repo is **public**. Pin **1.1.1**. **No `--threads` 256 clamp.**

**Laptop attach (done 2026-08-24 from this Windows box):**

1. Built Linux **x86_64 ELF** and Windows **PE** (`gnfp-cminer.exe`, static OpenSSL) from `v1.1.1` source `1fe25b5`. Attached into **the same** `gnfp-cminer-1.1.1-linux.tar.gz` / `-windows.zip` (no sibling).
2. In-zip `--selftest` printed `selftest ok 986437c40fee8a876e0ca3f1e58b14fa38785a179f57f98ebbb0fb03102bd4eb`. Help prints `GNFPHash C miner 1.1.1`. `VERSION` **1.1.1**, not 1.1.0.
3. Do **not** rebuild **1.1.0**. Do **not** invent a sibling tag. Wallet **0.2.1** still bundles **1.1.0** inside the zip — do **not** upload a standalone miner installer onto `v0.2.1`.

### 2026-08-24 — GNFP pool: large farms kicked/banned (live DE)

Read this file first (`git -C ~/handoff pull`). Book: `~/gnfp` → live `/opt/restore-privacy/perc_chain` on `germany` (`rpt-gnfp-pool`).

**Symptom:** miner was hashing, then could not connect. Example:

```
./gnfp-cminer --pool de.restoreprivacy.online:1474 --user gnfp1….rom16t --threads 240
```

Other large farms dropped the same way. DE TLS `:1474` stayed up; four small honest miners remained.

**Cause (after the EP01 session-sum deploy ~12:42 UTC):**

1. Two+ TCP sessions on one `wallet.worker` **sum** claimed threads **and** device inventory for the table. Honesty was then run on that **folded** row. A 240-thread farm + another socket looked like `claimed > cpuThreads` → `inflate` → `thread_cheat`.
2. `applyThreadHonesty` **banned** the login in an in-memory map. The **accepted** share reply set `kick: true` and destroyed the socket.
3. Next `login` hit `isMinerBanned` and was kicked immediately. Ban lasted until process restart. Valid PoW never got a second chance.
4. Hard **256** thread clamp in cminer / gnfp-mine / node rollup / flood budget was a separate farm-size lid (240 is under 256; the kick was the ban, not the clamp).

**Live fix (DE `rpt-gnfp-pool` restarted 2026-08-24 14:07 UTC).** Deployed `src/miner_stats.js` `src/gnfp_pool.js` `src/gnfp_share_guard.js`:

| Do | Do not |
|----|--------|
| `banMiner` is a **no-op**; `isMinerBanned` always false | Persist `thread_cheat` / GPU / old-miner bans on the username |
| Honesty **per TCP session**; inflate/underreport only **unlist** the public row | TCP-kick or ban after a valid share |
| Credit every valid GNFPHash share | Treat a fast 240-thread CPU as fake |
| GPU / GNFPHash 1.0.3-and-lower refuse **this socket only** | Lock the gnfp1 out after one bad client |
| No hardcoded 256 farm cap (device logical CPUs only) | Clamp claimed/cpuThreads to 256 on the book |

After restart: height kept climbing (`gnfp-germany-book-v1`); **~15 miners / ~608 threads / 0 rejected**; large worker back on the board. Tell `.rom16t` to reconnect the same line (TLS default). Unique `.worker` name **per box** keeps the table honest.

**Source trees:** live book is DE `perc_chain`. Miner pin **1.1.1** is on GitHub (`rgsneddon/gnfp-cminer` `v1.1.1`). Pool/node 256 book clamp already removed on DE.

**Do not:** rebuild public **gnfp-cminer 1.1.0** (leave that tag). Use **1.1.1** for no `--threads` 256 clamp. Do **not** invent a sibling tag. Do **not** enact `HASH_TX_LIVE=1`. Pool fee stays **1%**.

### 2026-08-22 — Windows leftover (wallet 0.2.1) — **done on the laptop**

Read this file first (`git -C ~/handoff pull`). Pointer: `gnfp-wallet/WINDOWS_HANDOFF.md`.

**Laptop 0.2.1 attach (done 2026-08-22 from this Windows box):**

1. **Wallet 0.2.1 Windows/Linux/Arch + CLI** attached to **the same** `v0.2.1` (no sibling). Built from `4fb735f` (GUI pin **0.2.1**, `FileVersion=0.2.1+21`). `pack\gnfp-cli.cmd --version` prints `$GNFP core wallet v0.2.1 (cli)`. Zips include `cli/gnfp_cli.dart` + `cli/gnfp-cli.cmd`. Title `$GNFP core wallet v0.2.1`.
2. **Mine tab C miner is inside the wallet zip**, not a second GitHub asset. Windows zip has `gnfp-cminer.exe` next to `gnfp_wallet.exe`. Linux/Arch have `gnfp-cminer` next to `gnfp_wallet`. From **inside the Windows zip** `gnfp-cminer.exe --selftest` printed `selftest ok 986437c40fee8a876e0ca3f1e58b14fa38785a179f57f98ebbb0fb03102bd4eb`. WSL Linux zip same hash. Do **not** upload a standalone miner installer onto `v0.2.1`.
3. Mac APK second-eyed OK (~51 MB, `AndroidManifest.xml` + `libapp.so`, not debug cert). Do **not** rebuild **0.2.0**. Do **not** rebuild public C-miner PE on `gnfp-cminer` `v1.1.0`. Do **not** invent a sibling tag.
4. `HASH_TX_LIVE` stays **0**. Pool fee stays **1%**. The 5% is a miner dual-login fee only.

### 2026-08-22 — Windows leftover (wallet 0.2.0 — **done**, do not rebuild)

0.2.0 Darwin/Android/iOS **and** the 0.2.0 leftover row are superseded by **0.2.1**. Do **not** attach more files to `v0.2.0`.

### 2026-08-22 — Windows leftover (gnfp-cminer 1.1.0 PE verify) — **done on the laptop**

Read this file first (`git -C ~/handoff pull`). Pointer: `gnfp-cminer/WINDOWS_HANDOFF.md`. Repo is **public**.

**Laptop PE verify (done 2026-08-22 from this Windows box):**

1. Downloaded `gnfp-cminer-1.1.0-windows.zip` from public `rgsneddon/gnfp-cminer` `v1.1.0`. Unpacked. Ran:

```
gnfp-cminer.exe --selftest
```

Printed `selftest ok 986437c40fee8a876e0ca3f1e58b14fa38785a179f57f98ebbb0fb03102bd4eb`. PE is MinGW x86_64, static OpenSSL, no extra DLL. `pack\win\gnfp-cminer.cmd` launches it. Do **not** rebuild the PE.

2. Optional live: `gnfp-cminer.exe --user gnfp1YOURADDRESS.worker --threads 1` TLS to `de.restoreprivacy.online:1474`. Pool vardiffs per TCP session (start 16). Do **not** retarget on the miner.
3. Do **not** rebuild 1.1.0 as a new pin. Do **not** invent a sibling tag. Haswell leftover is Air-only (`leftover/macos-x86_64-haswell-bigsur/`).

### 2026-08-21 — Windows leftover (node 1.2.7 equal daemon) — **do this on the laptop**

Read this file first (`git -C ~/handoff pull`). Pointer: `gnfp-node/WINDOWS_HANDOFF.md`.

1. **Node 1.2.7 source zip** — already the Mac pack (`gnfp-node-1.2.7-windows.zip` with `pack\win\gnfp-node.cmd`). Optional native PE on **the same** `v1.2.7`. `--print-config` must print `version=1.2.7` `equalNode=true` `join=false` `hashTxLive=0` `book=gnfp-germany-book-v1`.
2. Do **not** rebuild 1.2.6. Do **not** enact `HASH_TX_LIVE=1`. Do **not** invent a sibling tag.
3. Default `pack\win\gnfp-node.cmd` is an equal daemon (local stratum is the book). `--join` relays into a seed if you still want that.

4. Wallet **0.2.1** Windows/Linux/Arch + CLI is **on tag** `v0.2.1` (section above). 0.2.0 / 0.1.9 leftovers are **done**. Optional leftover is native PE for node **1.2.7**.

### 2026-08-21 — Windows leftover (0.1.9 / 1.0.6) — **do this on the laptop**

Read this file first (`git -C ~/handoff pull`). Per-repo `WINDOWS_HANDOFF.md` files are pointers here.

**Laptop 0.1.9 attach (done 2026-08-21 from this Windows box):**

1. **Wallet 0.1.9 Windows/Linux/Arch + CLI** attached to **the same** `v0.1.9` (no sibling). Built from `master` `eee8640` (CLI `--version` stamp; GUI pin **0.1.9**). `pack\gnfp-cli.cmd --version` prints `$GNFP core wallet v0.1.9 (cli)`. Zips include `cli/gnfp_cli.dart` + `cli/gnfp-cli.cmd`. Title `$GNFP core wallet v0.1.9` (`FileVersion=0.1.9+19`). Mac APK second-eyed OK. `curl` `/api/tip` returns `ticker=GNFP` live height. Do **not** rebuild 0.1.8.
2. **Official miner is now public gnfp-cminer 1.1.0** — PE already on that tag. `--selftest` **ok** 2026-08-22. Do **not** rebuild the PE. Node **GNFPHash 1.0.6** is **deprecated** (still earns at 1.0.4+). Do **not** rebuild 1.0.5.
3. **Windows sync** — proved on this box: `curl` `https://gnfp.restoreprivacy.online/api/tip` JSON `ok=true` `coin=GNFP` live `height`.


This Mac attached Darwin/Android/iOS **0.1.9** on `v0.1.9`. That Windows leftover is **done**. Wallet **0.2.1** Windows/Linux/Arch + CLI is **on tag** `v0.2.1`. Optional leftover is native PE for node **1.2.7**.

Do **not** rebuild 0.1.9 / 0.1.8 / miner 1.0.5 / node 1.2.6. Do **not** invent sibling tags. Do **not** enact `HASH_TX_LIVE=1`. Do **not** rebuild C-miner PE.

### 2026-08-21 — Windows leftover (0.1.8 / 1.2.6) + wallet sync report

**Laptop 0.1.8 attach (done 2026-08-21 from this Windows box):**

1. **Windows sync report.** `curl` from cmd to `https://gnfp.restoreprivacy.online/api/network` and `/api/tip` returns JSON `ticker=GNFP` and a live `height` (~37265). Session store exists at `%APPDATA%\GNFP\session.json`. Default Dart `HttpClient` had **no** `connectionTimeout` (hung TLS looked like **Network Tip: …** forever). Patched on **0.1.8** (`3dac5ea`, same tag, no sibling): 8s `connectionTimeout` and Network Tip surfaces `timeout`. Do **not** rebuild 0.1.7.
2. **Windows/Linux/Arch 0.1.8 attached** to **the same** `v0.1.8`. Title `$GNFP core wallet v0.1.8`. Mac APK second-eyed OK (~51 MB). Wrong-pin `0.0.2-*` zips deleted from this tag.
3. Optional leftover: native PE for node 1.2.6. Source zip is already on `v1.2.6`. Pointer: `gnfp-node/WINDOWS_HANDOFF.md`.

### CLI wallet (laptop wrote the source; Mac packages Darwin later)

Laptop 2026-08-21: `rgsneddon/gnfp-wallet` `master` has `bin/gnfp_cli.dart` + `lib/gnfp_cli.dart` (same seed/`gnfp1`/pool/mine-command units as the GUI). README **CLI wallet how-to** covers Windows / Linux / macOS. Verbs: **new**, **restore**, **show**, **balance**, **history**, **tip**, **send**, **mine-cmd**. Session: `%APPDATA%\GNFP\session.json` (Windows), `~/.gnfp/session.json` (Linux), `~/Library/Application Support/GNFP/session.json` (macOS).


CLI help/`--version` stamps **the same pin as the GUI** (`kGnfpPackageVersion` **0.2.1**). Shipped inside the 0.2.1 Windows/Linux/Arch zips (`cli/gnfp-cli.cmd`). No `vX.Y.Z-cli` sibling. Do **not** rebuild 0.2.0 GUI zips. Do **not** rebuild C-miner PE.

Do **not** rebuild 0.1.7 / 0.1.6 / miner 1.0.5 / node 1.2.5. Do **not** invent sibling tags. Do **not** enact `HASH_TX_LIVE=1`.

| Product | Tag | This Mac shipped | Laptop leftover |
|---------|-----|------------------|-----------------|
| Miner 1.0.6 | https://github.com/rgsneddon/GNFPHash/releases/tag/v1.0.6 | macos/linux tar.gz + windows **source** zip (`pack\win\gnfp-mine.cmd`, Node 18+ message) | Optional `gnfphash.exe` + `libcrypto-3-x64.dll` on **the same** `v1.0.6`. 1.0.5 native PE still usable. Do **not** rebuild 1.0.5. |
| Miner 1.0.5 | https://github.com/rgsneddon/GNFPHash/releases/tag/v1.0.5 | macos/linux tar.gz + windows **source** zip | **on tag** — `gnfphash.exe` + `libcrypto-3-x64.dll`. Do **not** rebuild. |
| Node 1.2.6 | https://github.com/rgsneddon/gnfp-node/releases/tag/v1.2.6 | macos/linux tar.gz + windows **source** zip | Optional PE-style zip (source pack on the tag is enough). `--print-config` `version=1.2.6` `hashTxLive=0`. |
| Wallet 0.1.9 | https://github.com/rgsneddon/gnfp-wallet/releases/tag/v0.1.9 (`db038e3`, CLI `eee8640`) | Darwin/Android/iOS on the tag (notarized DMG+zip, APK, unsigned IPAs). | **on tag** 2026-08-21 — windows/linux/arch + CLI on **the same** `v0.1.9`. `--version` = `$GNFP core wallet v0.1.9 (cli)`. Do **not** rebuild. |
| Wallet 0.1.8 | https://github.com/rgsneddon/gnfp-wallet/releases/tag/v0.1.8 (`35671ad`, timeout `3dac5ea`) | Darwin/Android/iOS (notarized DMG+zip, APK, unsigned IPAs) | **on tag** 2026-08-21 — windows/linux/arch on **the same** `v0.1.8`. Title `$GNFP core wallet v0.1.8`. Do **not** rebuild. |
| Wallet 0.1.7 | https://github.com/rgsneddon/gnfp-wallet/releases/tag/v0.1.7 | Darwin/Android/iOS | **on tag** — windows/linux/arch. Do **not** rebuild. |
| Wallet 0.2.1 | https://github.com/rgsneddon/gnfp-wallet/releases/tag/v0.2.1 (`4fb735f`) | Darwin/Android/iOS on the tag (notarized DMG+zip, APK, unsigned IPAs). Desktop Mine tab runs bundled gnfp-cminer 1.1.0. | **on tag** 2026-08-22 — windows/linux/arch + CLI on **the same** `v0.2.1`. `--version` = `$GNFP core wallet v0.2.1 (cli)`. In-zip cminer `--selftest` **ok**. Do **not** rebuild. |
| Official C miner 1.1.0 | **public** https://github.com/rgsneddon/gnfp-cminer/releases/tag/v1.1.0 | Darwin **arm64** + Linux **ELF** + Windows **PE** on the tag. Haswell leftover in git. | **on tag** 2026-08-22 — `gnfp-cminer.exe --selftest` printed `selftest ok 986437c40fee8a876e0ca3f1e58b14fa38785a179f57f98ebbb0fb03102bd4eb`. Do **not** rebuild the PE. |

### 2026-08-20 — Windows leftover (0.1.7 pins, historical)

| Product | Tag | This Mac shipped | Laptop leftover |
|---------|-----|------------------|-----------------|
| Miner | https://github.com/rgsneddon/GNFPHash/releases/tag/v1.0.5 | macos/linux tar.gz + windows **source** zip | **built** — `gnfphash.exe` + `libcrypto-3-x64.dll` on the tag (OpenSSL / `GNFP_NATIVE=1`). JS path still starts. |
| Node | https://github.com/rgsneddon/gnfp-node/releases/tag/v1.2.5 | macos/linux tar.gz + windows **source** zip | Optional PE-style zip (source pack on the tag is enough) |
| Wallet 0.1.6 | https://github.com/rgsneddon/gnfp-wallet/releases/tag/v0.1.6 | Darwin/Android/iOS. In-wallet miner **is 1.0.5**. | **built** — windows/linux/arch zips on `v0.1.6`. Mac APK second-eyed OK. Do **not** rebuild. |
| Wallet 0.1.7 | https://github.com/rgsneddon/gnfp-wallet/releases/tag/v0.1.7 | Darwin/Android/iOS on the tag (`92a94df`). Optional pin; 0.1.6 stays usable. | **on tag** 2026-08-20 — windows/linux/arch zips on `v0.1.7`. Title `$GNFP core wallet v0.1.7`. Mac APK second-eyed OK. Do **not** rebuild. |

Laptop wallet **0.1.7** Windows/Linux/Arch already attached on `v0.1.7` 2026-08-20 from this laptop (`92a94df`). Do not rebuild 0.1.7. Do not rebuild 0.1.6. Wrong-pin `gnfp-wallet-0.0.2-{windows,linux,archlinux}.zip` deleted from `v0.1.7`.

- `gnfp-wallet-0.1.7-windows.zip` sha256 `FF6F92408788A52CD8B17DA87A0A4A1A27EE9AF6A44E3799215D2A95B0C2FEC6`
- `gnfp-wallet-0.1.7-linux.zip` sha256 `359FD0A2DF367D7843FB892B48F9257F43F92A584D6E1C84DE576903BC5D13BA`
- `gnfp-wallet-0.1.7-archlinux.zip` sha256 `3C3B0BFBCA1FED9F308E7B67F2845213C5630DA51DA43F18B57B5F4454C0A1B1`

### 2026-08-17 — Windows box, read this first


- **Wallet pin is 0.2.1** — https://github.com/rgsneddon/gnfp-wallet/releases/tag/v0.2.1. Darwin/Android/iOS from this Mac; Windows/Linux/Arch + CLI **on tag** 2026-08-22 from this laptop (`4fb735f`). Desktop Mine tab runs **gnfp-cminer 1.1.0 inside the wallet zip**. Phones keep the Dart hasher. Node **GNFPHash** is deprecated. Window title `$GNFP core wallet v0.2.1`. CLI `--version` `$GNFP core wallet v0.2.1 (cli)`. Node **1.2.7**. `HASH_TX_LIVE=0`. Do **not** rebuild 0.2.0.
- **Windows / Linux / Arch 0.1.0** already attached on `v0.1.0` 2026-08-18 from the Windows laptop (`067e76f`). Do not rebuild 0.1.0.
  - `gnfp-wallet-0.1.0-windows.zip` sha256 `CAD57CEAA083FFDDB6EB1A856664F9B4D65FC8FE320C60D1AA5994944DC8D77D`
  - `gnfp-wallet-0.1.0-linux.zip` sha256 `D23F7369FCF55E00301435FACEBED26D22D937587A668FF871BDE0A48BD3DD99`
  - `gnfp-wallet-0.1.0-archlinux.zip` sha256 `BAE77B8A3D50BC98B2E331D8CFA97A9A1975CAC7BA133068D6A5CBDB1A13F27E`
- **Windows / Linux / Arch 0.0.9** already attached on `v0.0.9` 2026-08-17 from the Windows laptop (`057c9c1`). Do not rebuild 0.0.9.
  - `gnfp-wallet-0.0.9-windows.zip` sha256 `8a0b8fa12e409a0731d10e820afe9bc41cceddaa84843f97bd54638d2fa5c9c7`
  - `gnfp-wallet-0.0.9-linux.zip` sha256 `74912536fc74d4b5c3051458909aaa0d4780f12f8a5ba0d681056b4d2083714f`
  - `gnfp-wallet-0.0.9-archlinux.zip` (PKGBUILD, same pin)
- Mine checks on the 0.0.9 Windows miner (live Germany `:1474` TLS): 1-thread stayed **running** ≥ 65s (~15.1k H/s, empty error); 4-thread ~30.5k H/s (higher hashes + rate); STOP left `running=false`. Widget tests also cover persist-off-tab, reconnect, and dispose-stop.
- **Windows / Linux / Arch 0.0.8** already attached on `v0.0.8` 2026-08-17 from the Windows laptop. Do not rebuild 0.0.8.
- **Windows / Linux / Arch 0.0.7** already attached on `v0.0.7`. Do not rebuild 0.0.7.
- **Wallet 0.1.2** macOS (DMG+zip) / Android APK / iOS+iPad IPA / Windows / Linux / Arch already on `v0.1.2`. In-wallet miner is **GNFPHash 1.0.1**. VPN still coming soon.
- **Windows / Linux / Arch 0.1.6** already attached on `v0.1.6` 2026-08-20 from this laptop. Do not rebuild 0.1.6.
  - `gnfp-wallet-0.1.6-windows.zip` sha256 `B583B769B320309D630543E26DC11CE149F7EB379005B91A3995A4391DDCBEF3`
  - `gnfp-wallet-0.1.6-linux.zip` sha256 `C5AB57C52659AD2B994B1E1DB77FFB98F40E34E35F43F469CE3B7EFD463EA065`
  - `gnfp-wallet-0.1.6-archlinux.zip` sha256 `41D82CA3B7BDA49BA318AAD863169D1E2D2A6BD4C5CA4625C341821B3A7A4F19`
- **Windows / Linux / Arch 0.1.7** already attached on `v0.1.7` 2026-08-20 from this laptop. Do not rebuild 0.1.7.
  - `gnfp-wallet-0.1.7-windows.zip` sha256 `FF6F92408788A52CD8B17DA87A0A4A1A27EE9AF6A44E3799215D2A95B0C2FEC6`
  - `gnfp-wallet-0.1.7-linux.zip` sha256 `359FD0A2DF367D7843FB892B48F9257F43F92A584D6E1C84DE576903BC5D13BA`
  - `gnfp-wallet-0.1.7-archlinux.zip` sha256 `3C3B0BFBCA1FED9F308E7B67F2845213C5630DA51DA43F18B57B5F4454C0A1B1`
- **Windows / Linux / Arch 0.1.8** already attached on `v0.1.8` 2026-08-21 from this laptop (`35671ad` + timeout `3dac5ea`). Do not rebuild 0.1.8 as a sibling tag.
  - `gnfp-wallet-0.1.8-windows.zip` sha256 `4388CA6B20C2D493D56756A315CB7A2EDC8CF639AD6DAAEED7163EFF55D0A549`
  - `gnfp-wallet-0.1.8-linux.zip` sha256 `5ACE18C82733F77C4E9B25F2156B9B5B77F5AC2CBD9CA553E593CDD0BA32494A`
  - `gnfp-wallet-0.1.8-archlinux.zip` sha256 `13F4C62E7A145D81A20DC1E2E99D4364A2DECF63C73DD1A834763E764AF326D8`
- **Windows / Linux / Arch 0.1.9 + CLI** already attached on `v0.1.9` 2026-08-21 from this laptop (`eee8640`). Do not invent a sibling tag.
  - `gnfp-wallet-0.1.9-windows.zip` sha256 `AAB3948F208E2B1A8EF7824EC9DB117D64AD11D6DF0B2D0D1285F22B347A4BEE`
  - `gnfp-wallet-0.1.9-linux.zip` sha256 `DC28B59790C8631002E9B057779132DD4789A9CD79CD43B2EF68B49C7E638079`
  - `gnfp-wallet-0.1.9-archlinux.zip` sha256 `481B42A272CD1BB86E627840D54CE933E1F76BDE180C62CFAA764CD62A6CB294`
- **Windows / Linux / Arch 0.2.0 + CLI** already attached on `v0.2.0` 2026-08-22 from this laptop (`7b3c69c`). Do not invent a sibling tag.
  - `gnfp-wallet-0.2.0-windows.zip` sha256 `36FAEFD73ABF7898C7A39C021F2E4DA2E0D9B640B04AFD6F48A0917419EE5BA6`
  - `gnfp-wallet-0.2.0-linux.zip` sha256 `4E72F90D92FF0A348E7CE686B05E8ECE352FFEDF79CFAABB3AF522D15D4CF215`
  - `gnfp-wallet-0.2.0-archlinux.zip` sha256 `AF17B3ED2465D006ACF15647F1BCCF3E41D5B86BD8B0A6A8CA13BADBC1340458`
- **Windows / Linux / Arch 0.2.1 + CLI** already attached on `v0.2.1` 2026-08-22 from this laptop (`4fb735f`). Bundled gnfp-cminer inside the zip. Do not invent a sibling tag.
  - `gnfp-wallet-0.2.1-windows.zip` sha256 `C686FB41D1A52819B67EFE61C54B266101D8D791491730D7622B6C9A268BF64D`
  - `gnfp-wallet-0.2.1-linux.zip` sha256 `85041C3B8A52FA475E5867377BF9107EFCDC07893A7DF4898F0CE6AB07EC83CD`
  - `gnfp-wallet-0.2.1-archlinux.zip` sha256 `A9C5BC42F83B0AB8627E372BC8193F08D66879A7AAD58B9A0A74D08484F48A2D`

**Windows / Linux build tracker** (update this table when the laptop ships or skips a pin):

| Pin | Windows zip | Linux zip | Note |
|-----|-------------|-----------|------|
| 0.0.2 | built | built | first public pin; attached on `v0.0.2` 2026-08-17 |
| 0.0.3 | skipped | skipped | laptop had not built yet; **do not go back** |
| 0.0.4 | skipped | skipped | Mac-only draft; laptop never attached 0.0.4 zips |
| 0.0.5 | built | built | previous; attached on `v0.0.5` 2026-08-17 |
| **0.0.6** | **built** | **built** | previous; attached on `v0.0.6` 2026-08-17. Darwin/Android from Amelia’s Mac. |
| **0.0.7** | **built** | **built** | previous; Windows/Linux/Arch attached on `v0.0.7` 2026-08-17. Darwin/Android from Amelia’s Mac. |
| **0.0.8** | **built** | **built** | previous; Windows/Linux/Arch attached on `v0.0.8` 2026-08-17. Do not rebuild. |
| **0.0.9** | **built** | **built** | previous; Windows/Linux/Arch attached on **the same** `v0.0.9` 2026-08-17. Do not rebuild. |
| **0.1.0** | **built** | **built** | previous cut; attached on `v0.1.0` 2026-08-18. Do not rebuild. |
| **0.1.1** | **on tag** | **on tag** | previous; attached on `v0.1.1`. Do not rebuild. |
| **0.1.2** | **on tag** | **on tag** | previous. Mac cut `49b95c2`. Do not rebuild as current. |
| **0.1.6** | **on tag** | **on tag** | last tagged public set. Darwin/Android/iOS from Amelia’s Mac. Windows/Linux/Arch attached 2026-08-20 from this laptop. Mac APK second-eyed OK. Do **not** rebuild. |
| **0.1.7** | **on tag** | **on tag** | previous optional pin. Darwin/Android/iOS + Windows/Linux/Arch on `v0.1.7` (`92a94df`). Do **not** rebuild. |
| **0.1.8** | **on tag** | **on tag** | previous. Darwin/Android/iOS + Windows/Linux/Arch on `v0.1.8` (`35671ad`, timeout `3dac5ea`). Title `$GNFP core wallet v0.1.8`. Do **not** rebuild. |
| **0.1.9** | **on tag** | **on tag** | previous pin. Darwin/Android/iOS + Windows/Linux/Arch + CLI on `v0.1.9`. `--version` = `$GNFP core wallet v0.1.9 (cli)`. Do **not** rebuild. |

| **0.2.0** | **on tag** | **on tag** | previous. Darwin/Android/iOS on `v0.2.0`. Do **not** rebuild. |
| **0.2.1** | **on tag** | **on tag** | **current pin.** Darwin/Android/iOS + Windows/Linux/Arch + CLI on `v0.2.1` (`4fb735f`). `--version` = `$GNFP core wallet v0.2.1 (cli)`. Bundled gnfp-cminer `--selftest` **ok**. Do **not** rebuild 0.2.0. |
- **Books are DE + SG only.** Germany `rpt-gnfp-pool` is the live emission book (hash-window seals, `HASH_TX_LIVE=0`). Singapore join is **gnfp-node 1.2.7** (`:1474` TLS + `:8014`, peer DE, same tip). **Helsinki is empty** (SSH only) — replica and DE→HEL tunnels are **off**. Do **not** restore 50-GNFP live blocks. DE `rpt-gnfp-join` stays **off**.
- **Miner pin is gnfp-cminer 1.1.0 public** — https://github.com/rgsneddon/gnfp-cminer/releases/tag/v1.1.0 (Darwin/Linux/Windows PE already on the tag). Declared **5% miner** dual-login fee; pool fee stays **1%**. Node **GNFPHash 1.0.6** is **deprecated** (still earns at 1.0.4+). Live book refuses **1.0.3 and lower**. Node pin **gnfp-node 1.2.7**. Do **not** rebuild C-miner PE.
- **`GNFP_PRIVACY_SALT` is required on the book** (systemd drop-in, not in git). Public stats throw if it is unset.
- Operator miners: **2026-08-22** DE `rpt-gnfp-cminer` `--threads 1` cedar (JS `rpt-gnfp-mine` stopped). SG `rpt-gnfp-cminer` `--threads 12` monsoon (JS `perc-mine` stopped). Public miners should pull **gnfp-cminer v1.1.0**. GNFPHash **1.0.5 still earns**. Node `gnfp-mine` is superseded.

The original outgoing Mac **has no USB ports**. Keys travel as an **encrypted** archive (see [No-USB operator bundle](#no-usb-operator-bundle)). The passphrase is **not** in this file — it is in the Grok chat on the outgoing Mac.

---

## Leaving the MacBook Air → Amelia’s MacBook (2026-08-16)

This 2013 Air (`MacBookAir6,1`, 4 GB RAM, Big Sur **11.7.11**) cannot run a current Xcode or ship most pins. **Stop using it as the Darwin builder.** Pick up on Amelia’s MacBook (modern Xcode).

On Amelia’s Mac, first:

```bash
gh auth login   # if needed
cd ~/handoff && git pull
# then pull the repos you will touch
git -C ~/restore-privacy pull
git -C ~/gnfp pull --tags
git -C ~/evolve pull
git -C ~/git pull          # perccent-wallet
```

Then type `/handoff`.

**Product work done on the Air and already on GitHub** (nothing important is only on the Air disk):

| Repo | Tip / pin | What changed on the Air |
|------|-----------|-------------------------|
| `restore-privacy` | **1.2.7** `d2d2d44` (on `origin/main`) | Settings cog + App menu Settings fix (`83af1e1`). iOS 1.2.7 still **WAITING_FOR_REVIEW** (build **134 VALID**). Catalog macOS zip **not** Air-G2 resealed (sha256 `d3b75e13…`). |
| `gnfp` / `gnfp-wallet` | **wallet v0.1.2** (2026-08-18). Air-era tag was v0.1.13 | Current installers are on **`rgsneddon/gnfp-wallet` v0.1.2**. Treat 0.1.13 as 0.0.1-era. |
| `evolve` | **4.2.1** `adf51dc` | Tag `v4.2.1` is **published** with Android, macOS, iOS, **Windows**, **Linux**, and **Arch** assets (not a draft). |
| `perccent-wallet` (`~/git`) | `d4b27ee` | `:9477` skip on `main`. Darwin rebuilds attached to **v1.1.8**: macOS (DevID + notarized), iOS IPA, Android APK. Windows PE still laptop. |
| `rpOffice` | `9f4a242` | **v0.5.0** release has pens desktop zips (macos / win / linux / all-platforms). |
| `handoff` | this file | |

**Still running on the Air when this note was written — do not need them on Amelia’s Mac:**

- `~/Downloads/Xcode_13.2.1.xip` download (~10 GB, last compatible Xcode for Big Sur). Leave it; 13.2.1 cannot ship current Flutter/iOS pins.
- A second Grok session (`01a00a22-e075-…`) is watching GNFP Actions run `31944141564` (GitHub API was rate-limited from the Air). Check the release / Actions on Amelia’s Mac instead.

**Do not copy off the Air:** `~/Downloads/AuthKey_7P26KXH7HW.p8`, the new DevID `.cer` / CSR, or keychain items — keep them off git. Amelia’s Mac should keep using its **original outgoing-Mac Developer ID** for residual Packet Tunnel profiles (this Air’s new G2 DevID reseal of 1.2.7 launched AMFI 137 because profiles bind the outgoing identity). ASC API key `7P26KXH7HW` + notary profiles already live under `~/Library/Developer/perccent-codesign/` on the Air if you later AirDrop that folder.

**`gh` on the Air is logged out.** GitHub **SSH** as `rgsneddon` works (`git@github.com`).

**VPS SSH from the Air now works** (rescue rebuild 2026-08-16). Same hosts belong in Amelia’s `~/.ssh/config` (keys from the operator bundle, not this file):

| Alias | Host | User |
|-------|------|------|
| `germany` / `de` | `178.105.187.178` | `root` |
| `helsinki` / `hel` | `135.181.152.10` | `root` |
| `singapore` / `sg` | `5.223.48.8` | `root` |
| `iceland` / `restore-privacy-iceland` | `82.221.101.241` | `raskul` |

---

## First 10 minutes on the new Mac

```bash
# 1. Install Grok + Homebrew + Flutter (if missing)
curl -fsSL https://x.ai/cli/install.sh | bash
# then: brew, Xcode CLT, Flutter stable, gh, git

# 2. Sign in (browser — no USB, no old SSH keys required)
gh auth login          # GitHub.com, account rgsneddon, repo + gist scopes
grok                   # grok.com auth

# 3. Read this note + fetch the encrypted key bundle
gh repo clone rgsneddon/handoff ~/handoff
# decrypt: see "No-USB operator bundle" below (passphrase is in the old-Mac Grok chat)
```

Then tell Grok, in any directory:

```
/handoff
```

or, without installing the skill:

```
Read https://github.com/rgsneddon/handoff/blob/main/HANDOFF.md
and tell me where every repo and every platform is up to.
```

Install the skill so `/handoff` works:

```bash
mkdir -p ~/.grok/skills/handoff
gh api repos/rgsneddon/handoff/contents/skill/handoff/SKILL.md \
  --jq '.content' | base64 -d > ~/.grok/skills/handoff/SKILL.md
# Restore Privacy full-ship skill:
mkdir -p ~/.grok/skills/kyrusfables/references
gh api repos/rgsneddon/handoff/contents/skills/kyrusfables/SKILL.md \
  --jq '.content' | base64 -d > ~/.grok/skills/kyrusfables/SKILL.md
gh api repos/rgsneddon/handoff/contents/skills/kyrusfables/references/pipeline.md \
  --jq '.content' | base64 -d > ~/.grok/skills/kyrusfables/references/pipeline.md
```

Suggested clone layout on the new Mac (match this if you want old paths to keep working):

| Clone here | Remote |
|------------|--------|
| `~/restore-privacy` | `rgsneddon/restore-privacy` |
| `~/evolve` | `rgsneddon/evolve` |
| `~/git` | `rgsneddon/perccent-wallet` |
| `~/perc-mine` | `rgsneddon/perc-mine` |
| `~/perc-stratum-pool` | `rgsneddon/perc-stratum-pool` |
| `~/mishi` | `rgsneddon/mishi` **(private)** |
| `~/basic` | `rgsneddon/basic` |
| `~/rpOffice` | `rgsneddon/rpOffice` |
| `~/rpMail` | `rgsneddon/rpMail` |
| `~/handoff` | `rgsneddon/handoff` **(this repo, private)** |
| `~/666Stitches-production` | `rgsneddon/666Stitches-production` **(private, manifests only)** |
| `~/evolve-ios` | `rgsneddon/evolve-ios` **(private archive)** |

This Mac now has every product repo cloned (including the “not cloned on outgoing Mac” list).

---

## This Air (MacBookAir6,1 / Big Sur 11.7.11) — Apple signing (retired builder)

| Item | State |
|------|--------|
| Team | `SFCBP95595` (`export DEVELOPMENT_TEAM=SFCBP95595` in `~/.zshrc`) |
| Identity | `Developer ID Application: Russell Sneddon (SFCBP95595)` G2, expires **2031-08-16** (new CSR issued 2026-08-16; old outgoing-Mac DevID private key not imported) |
| CLT | **13.2** (`xcode-select` → Command Line Tools). Full **Xcode.app is not installed** (4 GB RAM). `notarytool` + `stapler` work. |
| Notary | App Store Connect API `.p8` + key-id + issuer live in `~/Library/Developer/perccent-codesign/` (not in git) and keychain profiles `evolve-notary` / `perccent-notary`. Probe + Evolve + MY PERC submits **Accepted**. |
| Flutter | **3.29.3 / Dart 3.7.2** at `~/flutter` (pinned — current stable 3.47 Dart 3.13 **aborts** on Big Sur). `flutter test` honesty suite **passes**. Full iOS/macOS `.app` rebuild still needs **Xcode.app** (not installed). |
| Apple Development | **not** on this keychain — cannot re-sign IPAs. Existing GH IPAs already carry `Apple Distribution` / `Apple Development` Team `SFCBP95595`. |

**Re-sealed on this Mac (DevID + notarized + stapled, `source=Notarized Developer ID`):**

| Artifact | sha256 | local path |
|----------|--------|------------|
| `evolve-v4.2.1-macos-x64.zip` | `949d640c4965fef855136739cf33dccc4df66073fe388331fcbd343b21785507` | `~/sealed/` |
| `perccent-wallet-v1.1.8-macos-setup.zip` | `6c74f7801a40303f5ba8fb8edcf5527e51aa6dbe61ad236440399005620ecdf0` | `~/sealed/` |

Evolve `v4.2.1` is on GitHub Releases (do not invent a sibling tag). Restore Privacy **1.2.7** Apple zips are **not** on GitHub (latest GH tag 1.2.5 is Windows-only); fetched from Helsinki `free_direct` and verified locally:

| Artifact | sha256 |
|----------|--------|
| `restore-privacy-client-1.2.7-macos.zip` | `d3b75e13f2f9d732fba4869911a73c2fb3eb7d807eb8b831cffb9f91ed011d4a` |
| `restore-privacy-client-1.2.7-ios.zip` | `1bbd9daac060364955ccdc20ef4073252a9f8bcbeeafccd414bb2c812f3255e4` |

Incoming 1.2.7 macOS is already **Notarized Developer ID** + stapled, host NE is `packet-tunnel-provider-systemextension` (not bare `packet-tunnel-provider`) with MAC_APP_DIRECT profiles. Official `sign_and_notarize_macos.py` re-sign with this Mac’s new G2 DevID **Accepted** + staple, but launch probe is AMFI 137 (profiles bind the outgoing-Mac DevID). Catalog zip kept as the incoming Helsinki file.

iOS any-user path (2026-08-16, this Mac):

- Keychain now has **Apple Development** (`Created via API (7P26KXH7HW)`) and **Apple Distribution: Russell Sneddon (SFCBP95595)** plus App Store profiles for `com.restoreprivacy.restorePrivacyClient` / `.PacketTunnel` and `vpn.restoreprivacy.online` / `.PacketTunnel`.
- Catalog 1.2.7 IPA was re-signed **Apple Distribution** (verify OK). Enterprise In-House is not available on this team (standard App Store account).
- App Store app **Restore Privacy VPN** (`vpn.restoreprivacy.online`, ASC `6798729178`) iOS 1.2.0 is **WAITING_FOR_REVIEW**. TestFlight external group **Public Testers** is live: https://testflight.apple.com/join/tT2C8UFe (beta review WAITING_FOR_REVIEW). iPhone/iPad storefront Install page prefers that TestFlight link.
- Helsinki store now accepts this Mac. Uploaded 1.2.7 **macos** + **ios** (Distribution-signed zip) to `/opt/restore-privacy/paid_assets/1.2.7/` on 2026-08-16.

GNFP/perc-mine/beam-mine macOS packs have **no `.app`**. Mishi **0.1.4** private `Mishi.app` fetched via authenticated GitHub release page, re-sealed on this Mac (DevID + notarized + stapled). sha256 `d487cdd6b29b2d353bf9225667d30b1a0ce9ddbc531766967e15270e5eb7869f` (`~/sealed/mishi-v0.1.4-macos.zip`). `macos_packaging/build_macos_app.sh` still cannot produce a new `.app` here (no Xcode.app). Live notary prove 2026-08-16: `NotaryProve.app` **Accepted** `ff09de76-1cce-4100-84d4-9ff55a957148`, stapled twice, `spctl` `source=Notarized Developer ID`.

Amelia’s Mac `~/restore-privacy` is on `origin/main` (`d2d2d44`). Catalog 1.2.7 macOS zip sha256 remains Helsinki `d3b75e13f2f9d732fba4869911a73c2fb3eb7d807eb8b831cffb9f91ed011d4a` (not the Air G2 reseal).

---

## What to work next (priority)

**Windows box — formatted 2026-09-11, no local repo.** Live Shear work is **[WINDOWS-ADMITv2.md](WINDOWS-ADMITv2.md)** (`https://github.com/rgsneddon/handoff/blob/main/WINDOWS-ADMITv2.md`). **Next (in order):** (1) pack wallet **0.34** Windows + Linux + Arch GUI zips **and** Windows/Linux CLI, upload onto existing tag `0.34` on `rgsneddon/shear-wallet` **and** `rgsneddon/shear-testnet`; (2) pack `ShearK-Miner-2.2-windows.zip` onto existing tag `2.2`. Do **not** recut **0.33** / **2.1**. Mac already attached 0.34 Android APK + macOS CLI. v3 leftover start remains [WINDOWS.md](WINDOWS.md).

**Windows laptop / Germany — leftover done:** gnfp-cminer **1.1.6** PE + Linux ELF on **the same** `v1.1.6`; Shear miner **0.1.4** Windows zip on **the same** `v0.1.4`; wallet **0.2.4** Windows/Linux/Arch on **the same** `v0.2.4` (no cminer). Runtime dispatch pin. Do **not** recut **1.1.5** / **0.1.3**. Do **not** ship leftover `1.0.6-max-autotune`. Do **not** invent a sibling tag. Optional leftover is native PE for node **1.2.7** — only after a **fresh clone** of `gnfp-node`. Darwin 1.1.6 / 0.1.4 leftover on the Mac.

Do this on **Amelia’s MacBook** or **Helsinki/de**, not as a ship from this Air (except the leftover row above).

1. **Restore Privacy 1.2.7 App Store / TestFlight — waiting on Apple.** Build **134** VALID. iOS version 1.2.7 **WAITING_FOR_REVIEW**. Public Testers: https://testflight.apple.com/join/tT2C8UFe. macOS App Store version 1.2.0 is **PREPARE_FOR_SUBMISSION** (not submitted). Do **not** re-sign the catalog macOS zip with the Air’s new G2 DevID (AMFI 137). Tip is `d2d2d44`.

2. **GNFP — wallet v0.2.4 (does not mine), node v1.2.7, miner gnfp-cminer 1.1.6 standalone.** See **GNFP client releases**. Book Germany `:1474`. **Laptop leftover done:** 1.1.6 PE + ELF on **the same** `v1.1.6`; wallet 0.2.4 Windows/Linux/Arch + CLI on **the same** `v0.2.4` (**no cminer inside**). Optional leftover is native PE for node **1.2.7**. Do **not** rebuild 0.2.3 / 0.2.1 / C-miner **1.1.5**. Node GNFPHash is deprecated.
3. **GNFP pool mint bonus — live 2026-08-24 17:42 UTC on Germany `rpt-gnfp-pool`.** **0.0000000001 GNFP/hash** + **1 GNFP/block**. 10-digit amount frame. `HASH_TX_LIVE` stays **0** (lean collate, **not** bonus-off). Shear inherit: 1 SHE pot, **0.0000000001**/hash, 10-digit frame — acknowledge only; **no mainnet zip**. Difficulty ceiling (256 bits) is already live (16:48 UTC); Shear ASERT/`MAX_BITS` must stay **256**.
4. **Evolve 4.2.1 — published, all six platforms on the tag.** No laptop rebuild required unless those assets need a new pin.
5. **MY PERC `:9477` Darwin — done on v1.1.8.** macOS + iOS + Android on that tag include `d4b27ee`. **Windows PE on tag is 1.1.6** (`perccent-wallet-v1.1.6-windows-x64-setup.exe` sha256 `5458e133…`). 1.1.8 Windows was **never** attached. The formatted disk cannot pack it. Download 1.1.6; do **not** recut.
6. **rpOffice 0.5.0 — packaged.** https://github.com/rgsneddon/rpOffice/releases/tag/v0.5.0
7. **rpOS 0.3.3** is a live ISO only.

---

## Machine split (still in force)

| Machine | Builds |
|---------|--------|
| **Amelia’s MacBook (Darwin + current Xcode)** | Android, macOS (Developer ID + notary), iOS/iPad IPA — **first** |
| **Windows laptop (formatted 2026-09-11)** | **No local trees.** `gh repo clone` from GitHub first ([WINDOWS.md](WINDOWS.md)). Current Shear leftover **done** (0.30 windows zip + ShearK 1.6 on tag). MY PERC Windows leftover is **1.1.6 on tag** (1.1.8 Windows never attached). Restore Privacy GitHub Windows is **1.2.5** (1.2.7 PE gone with the disk). Future pins: Windows PE/zip — **only after** Amelia cuts a new pin. Do **not** pack privacy-class v3. |
| **MacBook Air 6,1 Big Sur** | **Retired.** Last Xcode it can run is 13.2.1. Do not ship current pins from it. |

### GNFP wallet installer order (do not invert)

1. Mac cuts the pin, attaches **macOS / Android APK / iOS**, then updates **this file** (not a new `WINDOWS_HANDOFF_<pin>.md`).
2. This laptop, in the **same attach turn** (the handover is the start signal, not the full checklist):
   - **Second-eye the Mac Android APK** on that tag: must be a real `.apk` (~50 MB), not `android.zip` source; `AndroidManifest.xml` + `libapp.so`; not the Android Debug cert (0.0.8-class). Script: `~/.grok/skills/gnfp-wallet-attach/scripts/verify_mac_apk.py`. If it fails, still attach Windows/Linux/Arch and say so — never upload a source zip as the APK.
   - Then attach **Windows / Linux / Arch** to **that same tag**.
3. Every installer must contain the real executable — never a source/CMake/Gradle stub.
   - Windows: `gnfp_wallet.exe` (~13 MB zip)
   - Linux: `gnfp_wallet` (~10 MB zip)
   - Arch: `PKGBUILD` + that Linux bundle (~10 MB zip)
   - Android (Mac): `gnfp-wallet-<pin>-android.apk` (~50 MB)
4. List the zip (`tar -tf`) before `gh release upload`. Refuse to upload if the exe is missing or the zip is under ~1 MB.
5. One pin → one tag. Do not attach another pin’s files (e.g. `0.0.2-*`) onto this tag.

Never invent a `vX.Y.Z-macos-ios-android` sibling tag. Attach Mac assets and laptop assets to the **same** tag.

Apple team for signing: **`SFCBP95595`** (Russell Sneddon). Put in `~/.zshrc`:

```bash
export DEVELOPMENT_TEAM=SFCBP95595
export PATH="$HOME/flutter/bin:$PATH"
export PATH="$HOME/.grok/bin:$PATH"
eval "$(/opt/homebrew/bin/brew shellenv)"
alias rpt='grok --cwd "$HOME/restore-privacy"'
alias rptc='grok --cwd "$HOME/restore-privacy" -c'
```

---

## Per-repository status

### 1. restore-privacy — residual VPN + storefront

| | |
|--|--|
| URL | https://github.com/rgsneddon/restore-privacy |
| Pin | **1.2.7** (`client/VERSION`) |
| Tip | `d2d2d44` *downloads-map: refresh GitHub release inventory* (Settings fix `83af1e1`) |
| Public site | https://restoreprivacy.online |
| Pages export | https://rgsneddon.github.io/restore-privacy-suite/ |
| Full ship | type `kyrusfables` / `/kyrusfables` (skill copied in this repo) |
| Build script | `scripts/build_suite_1.2.7.py` |

**Platforms (monopin 1.2.7) — files on the outgoing Mac `releases/1.2.7/`:**

| Platform | File | State |
|----------|------|--------|
| Windows | `restore-privacy-client-1.2.7-windows-x64-setup.exe` | **Gone with the formatted laptop.** GitHub Releases Windows installer is **1.2.5** (`restore-privacy-client-1.2.5-windows-x64-setup.exe` sha256 `492632b5ba80c3b7114f877a2952d7f997dec5b55ef23be8f2402fc1669225d6`). Do **not** recut 1.2.5. Do **not** invent a 1.2.7 Windows GitHub tag from that box. |
| Android | `restore-privacy-client-1.2.7-android.apk` | Present (this Mac). |
| macOS | `restore-privacy-client-1.2.7-macos.zip` | Present — notarized Developer ID + residual Packet Tunnel **systemextension** host NE. |
| iOS | `restore-privacy-client-1.2.7-ios.zip` | Present — IPA `Payload/Runner.app`, Team-signed sideload (rename to `.ipa`). |
| Linux | `restore-privacy-client-1.2.7-linux-x64.tar.gz` | Present (carry-forward / laptop). |

Suite twins (`restore-privacy-suite-1.2.7-*`) sit next to the client names.

**Honesty notes**

- `client/windows/WINDOWS_HANDOFF_1.2.7.md` still says “Apple / Android stay 1.2.6 until the Mac ships 1.2.7” — that sentence is **stale**. The Mac *did* ship 1.2.7 packages locally.
- Local `releases/1.2.7/manifest.json` lists android / ios / linux / windows only (no macos row) even though the macos zip is on disk. Fix when next touching catalog.
- GitHub Releases latest tag is still **1.2.5** (storefront/Helsinki is the live catalog, not the GitHub Releases tab).
- Amelia’s Mac is **on `origin/main`** at `d2d2d44` (pulled 2026-08-16).
- `kyrusfables` skill on the old Mac still *says* pin 1.1.7 in its header — **ignore that**; live pin is `client/VERSION` → 1.2.7.
- App Store Connect: delivery `24700208-…` (build **133**) **FAILED** ITMS-90683 (missing `NSCameraUsageDescription`). Build **134** is **VALID**, attached to public TestFlight group and to App Store version **1.2.7**; both reviews waiting. Join link: https://testflight.apple.com/join/tT2C8UFe
- Catalog macOS zip sha256 on the Air after the Applications-wrapper fix: `31a73442ee4b4478acfa4bfc3bad23415fc9db2b392299f51007687f43c3ec60`. Incoming Helsinki zip sha256 was `d3b75e13f2f9d732fba4869911a73c2fb3eb7d807eb8b831cffb9f91ed011d4a`.

**Related private repos**

- `rgsneddon/restore-privacy-suite` — public website snapshot, last commit 2026-08-04 (v1.1.9 storefront). Live site is generated from the monorepo (`scripts/build_public_pages.py`).
- `rgsneddon/rpWEBSITE` — DR archive of restoreprivacy.online (2026-08-02).

---

### 2. evolve — Chronoflux / % chance / Perccent in-app

| | |
|--|--|
| URL | https://github.com/rgsneddon/evolve |
| Pin | **4.2.1+181** (`pubspec.yaml`) |
| Tip | `adf51dc` *ship(4.2.1): Mac Android/iOS/macOS hashes and Darwin packager host* |
| Pages | https://rgsneddon.github.io/evolve/ |
| Machine split | `docs/MACHINE_SPLIT.md` |
| Mac runbook | `docs/MAC_BUILDS.md`, `docs/HANDOVER_4.2.1_APPLE.md` |
| Linux/Arch | `docs/HANDOVER_4.2.1_LINUX_ARCH.md` |
| Bundle ID | `com.evolve.chronoflux` |

**Tag `v4.2.1` is published** (not a draft). Assets on it today:

| Platform | Asset | On `v4.2.1`? |
|----------|--------|----------------|
| Android | `evolve-v4.2.1-android-setup.apk` | **Yes** (~80 MB) |
| iOS + iPad | `evolve-v4.2.1-ios-setup.ipa` (universal, family 1,2) | **Yes** (~23 MB) |
| macOS | `evolve-v4.2.1-macos-x64.zip` (DevID + notarized) | **Yes** (~22 MB) |
| Windows | `evolve-v4.2.1-windows-x64-setup.exe` | **Yes** (~14 MB) |
| Linux | `evolve-v4.2.1-linux-x64.tar.gz` | **Yes** (~12 MB) |
| Arch | `evolve-v4.2.1-archlinux-x86_64.pkg.tar.zst` | **Yes** (~9 MB) |

Outgoing Mac also has leftover untracked `downloads/v4.1.9/` and `downloads/v4.1.10/` (safe to ignore). Stale clone `~/evolve-apple` is an old 4.1.8 tree with dirty perc_network files — **do not use it**; `~/evolve` is the real repo.

---

### 3. perccent-wallet — MY PERC standalone

| | |
|--|--|
| URL | https://github.com/rgsneddon/perccent-wallet |
| Local clone | **`~/git`** (not `~/perccent-wallet`) |
| Pin in source | **1.1.8+13** |
| Tip (pushed) | `d4b27ee` *fix(wallet): skip dead public :9477 hops; prefer HTTPS rendezvous* |
| Pages | https://rgsneddon.github.io/perccent-wallet/downloads/ |

**Shipped artifacts (2026-08-16 Amelia’s Mac Darwin rebuild of `d4b27ee` onto tag v1.1.8):**

| Platform | Shipped pin | Asset |
|----------|-------------|--------|
| macOS | **1.1.8** | `perccent-wallet-v1.1.8-macos-setup.zip` (`MY PERC.app`, DevID + notarized `623fa1a6…`, stapled) |
| iOS | **1.1.8** | `perccent-wallet-v1.1.8-ios-setup.ipa` (Payload + `App.framework`, unsigned sideload) |
| Android | **1.1.8** | `perccent-wallet-v1.1.8-android-setup.apk` (real `libapp.so`) |
| Windows | **1.1.6** | `perccent-wallet-v1.1.6-windows-x64-setup.exe` sha256 `5458e1338a3d07caa461c5939e3d69837ed3f3694b390ef285751032ad8fb41c` — **on tag `v1.1.6`**. 1.1.8 Windows was never attached. Formatted disk cannot pack it. Download; do **not** recut. |

`:9477` skip is in the Darwin/Android v1.1.8 packages (tests + AOT strings). WIP patch in `patches/` is already on `main` — do not re-apply.

---

### 4. gnfp — God's Coin book + $GNFP privacy wallet

| | |
|--|--|
| Book repo | https://github.com/rgsneddon/gnfp (`master`) |
| **Wallet repo (installers)** | https://github.com/rgsneddon/gnfp-wallet |
| **Latest wallet pin** | **v0.2.1** — https://github.com/rgsneddon/gnfp-wallet/releases/tag/v0.2.1 |
| Older wallet tags | `v0.1.13` etc. on `rgsneddon/gnfp` — treat as **0.0.1** era. `v0.1.0` / `v0.1.1` stay on their own tags. |
| Pool book | **DE emission book** + **SG join 1.2.5** (same chain). HEL replica/front **deprecated** (box emptied 2026-08-25). |
| Explorer | https://explorer.restoreprivacy.online |
| Pool page | https://gnfp.restoreprivacy.online |
| Live (2026-08-18) | height **~30395**, circulating **~7.67M GNFP**, holders hashed (`shear-…`) **with amounts**, **blockRewardGnfp=1**. Coins **sealed not reset**. |
| Miner pin | **GNFPHash v1.0.5** — https://github.com/rgsneddon/GNFPHash/releases/tag/v1.0.5 |
| Node pin | **gnfp-node v1.2.5** — https://github.com/rgsneddon/gnfp-node/releases/tag/v1.2.5 (live SG join). HEL is not a node. |
| Book repo tip | `8f85fd1` explorer restored to last Mac page (circulation + hashed top-ten) on `b112860` incremental-pull book |
| Clone | `~/gnfp` (book) and `~/gnfp-wallet` (public client) |
| Mac pool note | 15-block watch done 2026-08-16; holdings restore + slim persist done 2026-08-17. Stale `HANDOVER_MAC_20260816.md` in `gnfp` was removed. |

**Historical (2026-08-21):** v0.1.8 was then the current pin. **Current pin is 0.2.1** — see **GNFP client releases**. Do **not** rebuild 0.2.0 / 0.1.9.

Tabs: Wallet (SOCIAL CHANNELS titles only, no pending-credit) — Explorer (newest-first ledger + `.xls` export) — Backup (12 English BIP-39 boxes, cream-on-dark warning) — Mine (persist + real thread workers + typed pool/payout; GNFPHash **1.0.5**) — VPN. No Mix. No Analysis. Native window / launcher title: `$GNFP core wallet v0.1.8`.

| Platform | Asset | Honesty |
|----------|--------|---------|
| macOS DMG | `gnfp-wallet-0.1.2-macos.dmg` | Drag GNFP Wallet onto Applications. DevID + notarized. |
| macOS zip | `gnfp-wallet-0.1.2-macos.zip` | Same app for the in-app update feed. |
| iPhone | `gnfp-wallet-0.1.2-ios.ipa` | Unsigned Release IPA. Sideload. |
| iPad | `gnfp-wallet-0.1.2-ipad.ipa` | Same IPA, iPad-named. |
| Android | `gnfp-wallet-0.1.2-android.apk` | Release-signed v2+v3 as GNFP Wallet (~51 MB). |
| Arch | `gnfp-wallet-0.1.2-archlinux.zip` | On `v0.1.2`. Real `gnfp_wallet` + `libapp.so`. |
| Windows | `gnfp-wallet-0.1.2-windows.zip` | On `v0.1.2`. Real `gnfp_wallet.exe`. |
| Linux | `gnfp-wallet-0.1.2-linux.zip` | On `v0.1.2`. Real `gnfp_wallet`. |

**Book / emission (do not regress)**

- Live reward is **1 GNFP + share bonus**. Do **not** restore 50-GNFP blocks or the 3000 ms interval.
- HEL 50-era coins are spendable on DE as each miner’s Helsinki holding (~7.65M mined + DE post-move). Explorer circulating/emitted/top-ten read that book. Cutover **did not wipe** `/var/lib/gnfp/wallet.json`.
- DE `rpt-gnfp-join` must stay **off** (it bound the book ports after reboot).
- Cutover order is **book → fronts → miners**. Book and **GNFPHash 1.0.5** must move together. `GNFP_PRIVACY_SALT` stays on the DE pool drop-in.
- Operator miners: public miners pull **GNFPHash v1.0.5**. Move DE cedar / SG monsoon to 1.0.5 if they are still on 1.0.4. HEL PERC stays `--threads 1`.

Current installers: https://github.com/rgsneddon/gnfp-wallet/releases/tag/v0.1.8 (Darwin/Android/iOS/Windows/Linux/Arch). **0.1.7** and **0.1.6** remain usable (Windows/Linux/Arch zips stay on those tags). Native miner PE is on `v1.0.5`. Do **not** rebuild 0.1.8 / 0.1.7 / 0.1.6. Do **not** invent a sibling tag. GOD https://god.restoreprivacy.online refreshes installer links itself. VPN still tracks the suite catalog, not GitHub.

Live stratum used from this Air is **`de.restoreprivacy.online:1474`** (TLS). Haswell leftover is in public `rgsneddon/gnfp-cminer` `leftover/macos-x86_64-haswell-bigsur/` (see next section). Official public miner pin is **gnfp-cminer 1.1.0**.

---

## GNFPHash CPU miner on this Air (2026-08-21)

Session on **MacBookAir6,1** (Haswell i5-4250U, 2c/4t, Big Sur 11.7.11). Miner is **stopped**. Air still heats hard at 2 threads; next run use `--threads 1`.

### What was built (Air leftover — this Air only, not a second pin)

`rvp-design/gnfp_cminer` is a **stripped Linux ELF**, not source. Native macOS x86_64 rebuild, **not** a second pin and **not** a multi-platform ship. 1.1.0 OpenSSL packs for arm64/Linux/Windows shipped 2026-08-22 from Amelia’s Mac.

| | |
|--|--|
| Repo | https://github.com/rgsneddon/gnfp-cminer (**public** official pin; Haswell leftover is Air-only) |
| Leftover path | `leftover/macos-x86_64-haswell-bigsur/` on `main` |
| Local | `~/gnfp_cminer` on this Air (same tree) |
| Binary | `gnfp_cminer` Mach-O x86_64, AVX2 8-way, Apple TLS (no brew OpenSSL) |
| Wire | `client=GNFPHash` `version=1.0.5` (admit floor 1.0.4+) |
| Pool | `tls://de.restoreprivacy.online:1474` |
| Fee | 5% dual-login to `gnfp19381c4b1d7a9cbae64120f24b16d248ae07c6ff1.fee` |
| Last worker | `gnfp1b9aa65404d97a6e589888cd3ec9c0c4d32fd71de.minidumf` |
| Selftest | official vector `986437c4…d4eb` `backend=avx2-x8` |

Also on this Air: `~/gnfp-cpu-miner` (2% fee, AVX2, same pool). Downloads `gnfp-cminer-1.1.0` is the **arm64** community tarball (will not run here).

**Still to build elsewhere (this Air cannot):** proven-stats / in-flight queue merge into the 1.1.0 OpenSSL packs if those should match the Air board. **2026-08-22 Amelia’s Mac shipped** Darwin arm64 + Linux ELF + Windows PE on the same **public** `v1.1.0`. Do **not** rebuild that PE.

### Observed on live pool (diff **14**, fixed)

- 1 thread ~**140 kH/s call**. Finds ~8–10 shares/s. **0 rejects** when shares arrive.
- After ~9s of that flood: **`main socket closed — peer aborted TLS (osstatus=-9806)`**. Then handshake `-50` on the first address, reconnect 3–24s later. Not a miner crash.
- Miner **call** hashrate (all hashes) was higher than **pool proven** (accepted × 2^14 / time) because an early in-flight cap of 4 **dropped** ~40% of meets before they left the box. Latest binary reports **proven** on the `stats` JSON (`hashrate` field) and shows both `proven=` and `call=` on the STATS line; in-flight cap is **24** and finds **queue** instead of dropping at 4.
- Pool UI (`recordMinerStats`) stores the miner’s `hashrate` field. Send proven if you want the board to match share math.

### Pool share vardiff (live 2026-08-22; ceiling raised 2026-08-24)

Do **not** throttle difficulty on the miner. Hooked in `attachMiner` (`~/gnfp/src/gnfp_vardiff.js` + `gnfp_pool.js`). Live on Germany `rpt-gnfp-pool` (same perc_chain tree).

- One difficulty **per TCP session**, not per wallet. Fee login is a second session.
- Start **16**. Every 8 shares or 20s: bits step by `round(log2(target/actual))`, floor **14**, ceiling **256** (hash width; was 24 until 2026-08-24), never above block bits.
- Target **~1 share / 5–10s** (`VARDIFF_TARGET_MS=7500`). New `job` on change. Credit old shares at the issued job’s bits.
- Book law `SHARE_DIFFICULTY_BITS=14` is unchanged (HTTP/fallback). Block `MAX_DIFFICULTY_BITS=256` (was 32). `HASH_TX_LIVE` stays **0**.
- Shear: copy `MAX_BITS=256` / vardiff `maxBits=MAX_BITS`. Do **not** keep a 32-bit header lid.

At first deploy, cedar 1-thread sat near **diff 21**; monsoon 12-thread hunted **19–22**. Fixed-14 flood (~20 shares/s) was the TLS abort.

**2026-08-22 SG board was erratic / ~1-thread:** OpenSSL `SHA256()` serialized 12 workers; TLS `WANT_WRITE` dropped dequeued shares; a new vardiff job wiped the queue; pool H/s was `accepts × last bits`. Fixed in miner (lock-free SHA, keep queue, re-queue on would-block) and pool (per-accept work, 4096 jobs). Any number of named workers on one payout address still roll up. Private `v1.1.0` packs replaced.

### Run again on this Air (after cool-down)

```bash
~/gnfp_cminer/gnfp_cminer \
  --user gnfp1b9aa65404d97a6e589888cd3ec9c0c4d32fd71de.minidumf \
  --threads 1
```

Ctrl-C in that Terminal stops it. Do not use 2 threads on this chassis for long.

---

### 5. rpOS — Restore Privacy OS

| | |
|--|--|
| URL | https://github.com/rgsneddon/rpOS |
| Latest GitHub release | **v0.3.3** — `rpos-0.3.3-live.iso` only |
| Tip | `e24e8bc` NED/FRED/PEDRO credit-free loop; El Torito+EFI ISO |
| In monorepo | `restore-privacy/rpos` (older in-tree copy, README still talks 0.2.1 RxShell / 0.1.0 desktop zips) |
| Standalone clone on outgoing Mac | **none** |

| Platform | State |
|----------|--------|
| Live ISO (EFI) | **0.3.3 shipped** |
| Windows / macOS / Linux desktop zips | README still names `0.1.0` paths — not the current 0.3.x line |
| iOS / Android | Not installable (by design) |

---

### 6. perc-mine + perc-stratum-pool — PERC pool / CPU miner

| | perc-mine | perc-stratum-pool |
|--|-----------|-------------------|
| URL | https://github.com/rgsneddon/perc-mine | https://github.com/rgsneddon/perc-stratum-pool |
| Pin | **1.0.2** | **1.0.0** |
| Tip | `25f63a5` 1-thread Helsinki/Germany/Singapore worker tests | `b4fcf98` initial 1.0.0 |
| Live pool | https://mineperc.restoreprivacy.online/ | ports **1466** (normal) / **3334** (high) |

**perc-mine v1.0.2 desktop packs:**

| Platform | Asset |
|----------|--------|
| Windows | `perc-mine-1.0.2-windows.zip` |
| macOS | `perc-mine-1.0.2-macos.tar.gz` |
| Linux | `perc-mine-1.0.2-linux.tar.gz` |

Outgoing `~/perc-mine` is clean except untracked `package-lock.json`.

---

### 7. beam-mine + beam-stratum-pool — BEAM pool / miner

| | beam-mine | beam-stratum-pool |
|--|-----------|-------------------|
| URL | https://github.com/rgsneddon/beam-mine | https://github.com/rgsneddon/beam-stratum-pool |
| Branch | `master` | `master` |
| Latest | **v1.0.1** | tip `3433703` (no release tag) |
| Host | `beam.restoreprivacy.online` ports **1690** / **1974** | |

**beam-mine v1.0.1:**

| Platform | Asset |
|----------|--------|
| Windows | `beam-mine-1.0.1-windows-x64.zip` |
| macOS | `beam-mine-1.0.1-macos-universal.tar.gz` |
| Linux | `beam-mine-1.0.1-linux-x64.tar.gz` |

Payouts: `rgsneddon/basic` (BASiC), last real change `7850f0e` (2026-08-14 pool path). No GitHub release.

---

### 8. mishi — FCG ward moderator (PRIVATE)

| | |
|--|--|
| URL | https://github.com/rgsneddon/mishi **private** |
| Pin | **0.1.4** |
| Tip | `7f9e5fd` one `mishi_credentials.txt` only |
| Local | `~/mishi` clean |

| Platform | State |
|----------|--------|
| macOS | `releases/mishi-v0.1.4-macos.zip` (+ sha256/sha512) **private, do not publish** |
| Windows | Evolve looks for `%LOCALAPPDATA%\Evolve\mishi\mishi.exe` after moderator sign-in |
| iOS / Android / Linux | No public packages. CLI is `dart run mishi …` |

Never put Mishi on gh-pages.

---

### 9. rpOffice — Pens · Tables · Slides

| | |
|--|--|
| URL | https://github.com/rgsneddon/rpOffice |
| Pushed pin | **0.5.0** (`9f4a242` *feat: Pens/Tables/Slides 0.5.0 desktop GUI*) |

GitHub release **v0.5.0**: `pens-0.5.0-macos.zip`, `pens-0.5.0-windows-x64.zip`, `pens-0.5.0-linux-x86_64.zip`, `pens-0.5.0-linux-aarch64.zip`, `pens-0.5.0-all-platforms.zip`. Python 3.10+ / tkinter. Not iOS/Android. WIP patch in `patches/` is the 0.5.0 GUI already on `main` — do not re-apply.

---

### 10. rpMail — Restore Privacy Mail

| | |
|--|--|
| URL | https://github.com/rgsneddon/rpMail |
| Pin | **0.1.0** |
| Tip | `79f7fdd` Outlook-class PIM variant (2026-08-01) |
| Local | `~/rpMail` clean |

Python library + tests. No packaged installers for any OS yet.

---

### 11. CERBERUS — residual fleet oracle

https://github.com/rgsneddon/CERBERUS — initial source `a161b47` / cleanup `8054f86` (2026-08-02). No releases. Not cloned on the outgoing Mac.

---

### 12. Rx-Privacy-Browser

https://github.com/rgsneddon/Rx-Privacy-Browser — `7c83353` from-scratch Rx + bundled Restore Privacy VPN 3.3.3 (2026-07-24). No releases. Not cloned.

---

### 13. restore-privacy-beam-dapp

https://github.com/rgsneddon/restore-privacy-beam-dapp — scaffold only (`4ad5ab6`, 2026-08-01).

---

### 14. 666Stitches.mov — feature film

| | |
|--|--|
| Public repo | https://github.com/rgsneddon/666Stitches.mov |
| Release | **v1.0.0** `666Stitches_Feature.mov` |
| Production state (no media) | https://github.com/rgsneddon/666Stitches-production **private** |
| Local production media | `~/666Stitches_Anime_Film/` (~16 GB — **not** on GitHub; outgoing Mac has no USB) |
| Local clone of public repo | `~/666Stitches.mov_repo` |

**Production honesty**

- Public picture-lock exists (v1.0.0).
- Local `feature_manifest.json`: **259** unique paragraph scenes, **6216 s** (~103 min), build `unique_one_scene_per_paragraph_v4`.
- Local `exports/666Stitches_Feature.mov` ~671 MB (14 Aug).
- Newer paragraph-queue track: 29 segments in `segment_manifest.json`, next index **30**, block `lasting_reams_block_p027plus` (3/27 done). Book is 259 paragraphs / 660 planned shots / 110 min target.
- To continue generation: leave the outgoing Mac on the same Wi‑Fi and `scp -r` / AirDrop `~/666Stitches_Anime_Film/` (no USB on that machine). Manifests/scripts/refs are already in `rgsneddon/666Stitches-production`.

---

### 15. Scratch / ignore

- `rgsneddon/evolve-410-windows-ci` — temporary Windows CI for 4.1.10. Safe to delete.
- `~/evolve-410-build`, `~/evolve-ios`, `~/evolve_ghpages`, `~/perccent_wallet_ghpages` — old working trees / Pages mirrors, not source of truth.
- `~/flutter` is a Flutter SDK clone (stable), not a product.

---

## No-USB operator bundle

The outgoing Mac **has no USB ports**. Keys and local operator files are in an AES-256 archive. **Plaintext keys are not in git.** The passphrase is only in the outgoing-Mac Grok chat.

**File:** `operator/operator-bundle-2026-08-16.tar.enc`

| Copy | How the new Mac gets it |
|------|-------------------------|
| **GitHub (this repo)** | `gh repo clone rgsneddon/handoff` then decrypt `operator/operator-bundle-2026-08-16.tar.enc` |
| **iCloud Drive** | `~/Library/Mobile Documents/com~apple~CloudDocs/TAKE-TO-NEW-MAC/` (same Apple ID) |
| **Iceland VPS** | `restore-privacy-iceland:~/operator-handoff/` — only after SSH keys are installed (chicken-and-egg: use GitHub or iCloud first) |
| **AirDrop** | Desktop folder `TAKE-TO-NEW-MAC` on the outgoing Mac (if both machines are together) |

```bash
# after gh clone ~/handoff
openssl enc -d -aes-256-cbc -pbkdf2 -iter 200000 \
  -in ~/handoff/operator/operator-bundle-2026-08-16.tar.enc \
  -out /tmp/operator-bundle-2026-08-16.tar
mkdir -p ~/handoff-unpack
tar -xf /tmp/operator-bundle-2026-08-16.tar -C ~/handoff-unpack
# follow ~/handoff-unpack/README.txt
shred -u /tmp/operator-bundle-2026-08-16.tar   # if shred exists
```

Inside the archive: SSH keys + `config`, Android `upload-keystore.jks`, Apple notary notes + CSR, `mishi_credentials.txt`, `~/.restore-privacy` / `~/.restore_privacy` / `~/.rpos`, Grok skills (`handoff`, `kyrusfables`), `.zshrc`. **Not** included: `~/.grok/auth.json` (sign in with the browser), 16 GB film media.

Also sign in again: `gh auth login` and `grok` (browser). No old tokens required.

**SSH hosts (Air, 2026-08-16 after rescue):** `germany` `178.105.187.178` root; `helsinki` `135.181.152.10` root (this used to time out from the original outgoing Mac); `singapore` `5.223.48.8` root; `iceland` / `restore-privacy-iceland` `82.221.101.241` user `raskul` (hostname there `restore-privacy-vps`). Hop `185.146.232.107` denied the hop key. Put the same `~/.ssh/config` block on Amelia’s Mac; keys stay in the operator bundle.

Paid/free store is Germany (`178.105.187.178`) via `scripts/host_paid_assets_vps.py`. Public HTTPS store: **https://178.105.187.178.sslip.io/paid-assets**. Public hostname: **restoreprivacy.online** (shop still Render). Namecheap: point `god` / `mineperc` / `evolve` / `beam` / `hel` A records at `178.105.187.178`.

### Extra trees saved this session

| What | Where |
|------|--------|
| MY PERC `:9477` filter | `rgsneddon/perccent-wallet` `main` `d4b27ee` |
| rpOffice 0.5.0 GUI | `rgsneddon/rpOffice` `main` `9f4a242` |
| Ned VPN/wallet learner | `rgsneddon/restore-privacy` `main` `314f94d` |
| Stale `~/evolve-apple` WIP | branch `wip/outgoing-mac-evolve-apple-2026-08-16` on `rgsneddon/evolve` — **do not merge into 4.2.1 main** |
| Swift `~/evolve-ios` archive | `rgsneddon/evolve-ios` (private; superseded by Flutter iOS) |
| 666 production manifests | `rgsneddon/666Stitches-production` (private) |

---

## Grok commands on the new Mac

| You type | What Grok should do |
|----------|---------------------|
| **`/handoff`** | Fetch this file from GitHub and summarise every repo/platform. |
| `Read the handoff from github.com/rgsneddon/handoff` | Same, no skill required. |
| **`kyrusfables`** / `/kyrusfables` | Full Restore Privacy ship (build all Darwin platforms, sign/notarize, git, Helsinki). Pin = `client/VERSION`. |
| `rpt` (zsh alias) | New Grok session rooted in `~/restore-privacy`. |
| `rptc` | Continue last restore-privacy session. |

After `/handoff`, name the product you want (`evolve`, `restore-privacy`, `MY PERC`, …) and Grok should clone/pull that repo and continue from the row in this file — not from a stale Windows/Apple handoff inside an old pin.

---

## How to refresh this note

When a pin or platform changes, update **this file** on `rgsneddon/handoff` `main` and push. If the Windows leftover changes, also update **[WINDOWS.md](WINDOWS.md)**. Keep one date stamp at the top. **GNFP wallet / miner / node pins live in the table at the top** — do not start a second GNFP handoff. Per-repo `WINDOWS_HANDOFF.md` is a pointer only (no pin in the filename). The formatted Windows box has **no** local repo until it clones this one.

```bash
cd ~/handoff
# edit HANDOFF.md and WINDOWS.md
git add HANDOFF.md WINDOWS.md && git commit -m "handoff: <what changed>" && git push
```
