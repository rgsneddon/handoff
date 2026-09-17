# Windows box — formatted, no local repo

**Wipe:** 2026-09-11 (recover from an error).  
**This file written:** 2026-09-12.  
**Updated:** 2026-09-14 — this box packs the missing **0.33** Windows wallet zip. Darwin does **not** `flutter build windows`. Do **not** wait on GitHub Actions from the Mac.

There is **no** leftover tree on that disk. There is **no** `C:\Users\rgsne\handoff`, **no** `C:\Users\rgsne\shear-testnet`, **no** leftover zip, **no** Flutter SDK, **no** Visual Studio, **no** WSL, **no** Git. Do **not** hunt old `C:\Users\rgsne\…` paths. Do **not** attach zips from the dead disk. Do **not** `git -C` a path until after clone.

**This file is the Windows start.** Full inventory of every repo and every platform is still [HANDOFF.md](HANDOFF.md).

| | |
|--|--|
| **This file (Windows start)** | https://github.com/rgsneddon/handoff/blob/main/WINDOWS.md |
| Full inventory | https://github.com/rgsneddon/handoff/blob/main/HANDOFF.md |
| Miner how-to | https://github.com/rgsneddon/ShearK/blob/main/README.md |

Repo `rgsneddon/handoff` is **private**. After `gh auth login` as **`rgsneddon`**, open the URLs above or read `%USERPROFILE%\handoff\WINDOWS.md`.

Use **Command Prompt** (`cmd.exe`) for every command in this file. `%USERPROFILE%` and `cd /d` are cmd syntax. Git Bash and PowerShell will not expand them the same way.

---

## Live Shear pins

Live book is **`shear-testnet-v3`**. Pool `pool.shear.digital:1111`. Seed `shear.digital:30303`. Wallet sync is a local node at `127.0.0.1:18332` (not flyclient). Miner pin **ShearK 1.6**. Soak through **2026-09-18**. Mainnet is **not** cut.

| Pin | What it is | GitHub | Windows zip |
|-----|------------|--------|-------------|
| **0.33** | Latest **client** (splash v3-sync, drop leftover v2). Pack this zip **on this box**. | tag **`0.33`** (`854ce9d`). macOS/Android/Linux/Arch already attached. | **missing — this box packs it** |
| **0.32** | Soak pin on default **`main`** (`c702ea4`). Clone of `rgsneddon/shear-testnet` is this tree. | tag **`0.32`**. macOS/Android/Linux/Arch attached. | none (same as 0.31). Do **not** recut 0.32. |
| **0.31** | Last flyclient wallet. History. | tag **`0.31`** | none. Do **not** recut. |
| **0.30** | History. | tag **`0.30`** | leftover zip on tag (table below). Do **not** recut. |

Privacy-class **v3** is the public testnet book (AdmitV1). Mainnet `shear-v1` starts **18 Sep 2026 21:00 UK**. Frozen flyclient `main` is `archive/main-flyclient-f1fc184`.

| Asset | Tag | sha256 | Zip root |
|-------|-----|--------|----------|
| `shear-wallet-0.30-windows.zip` | `rgsneddon/shear-testnet` **`0.30`** | `8bc28d5255e14935e2ec7afc5cd43d89a217c84247eff40edfe25da667bc29a8` | Flutter `shear_wallet.exe` (MZ), title **Shear 0.30**, **no miner inside** |
| `ShearK-Miner-1.6-windows.zip` | `rgsneddon/ShearK` **`1.6`** | `879a0024297962cd9a97bf544dcd1fe1656a546d82ea37cfa6f6a2615befb5fb` | `ShearK-Miner.exe` (MZ) + `example.bat` (`YOUR_SSA1.worker`) |

Do **not** recut tags **0.33** / **0.32** / **0.31** / **0.30** / **0.29** / ShearK **1.6**. Attaching the missing **0.33** Windows zip to tag **0.33** is not a recut. Do **not** attach Darwin as `*-linux.zip`. Do **not** put the miner inside the wallet zip.

Older hash `dcfd9df2…` for ShearK 1.6 was the pre-`example.bat` restamp. Ignore it. Live miner zip is `879a0024…`.

---

## 0) Tools on a blank disk

1. Install **Git for Windows** (https://git-scm.com/download/win). Default options are fine.
2. Install **GitHub CLI** (https://cli.github.com/).
3. Install **Visual Studio 2022** with workload **Desktop development with C++** (needed for `flutter build windows`).
4. Install **Flutter 3.44.6** stable (same as the Mac pack). Add `flutter` to PATH.
5. Open **Command Prompt**, then:

```
gh auth login
flutter doctor -v
```

Use account **`rgsneddon`**. Browser login is fine. When asked to authenticate Git with GitHub credentials, say **yes**. `flutter doctor` must show Windows desktop available before you pack.

---

## 1) Clone from GitHub (nothing exists until this)

`rgsneddon/handoff` is private. Use `gh repo clone` (not a bare `git clone` of the HTTPS URL).

```
gh repo clone rgsneddon/handoff %USERPROFILE%\handoff
gh repo clone rgsneddon/shear-testnet %USERPROFILE%\shear-testnet
gh repo clone rgsneddon/ShearK %USERPROFILE%\ShearK
cd /d %USERPROFILE%\shear-testnet
git checkout main
git pull
notepad %USERPROFILE%\handoff\WINDOWS.md
notepad %USERPROFILE%\handoff\HANDOFF.md
```

Optional later (only if you work those products on this box):

```
gh repo clone rgsneddon/gnfp-wallet %USERPROFILE%\gnfp-wallet
gh repo clone rgsneddon/gnfp-cminer %USERPROFILE%\gnfp-cminer
gh repo clone rgsneddon/gnfp-node %USERPROFILE%\gnfp-node
gh repo clone rgsneddon/perccent-wallet %USERPROFILE%\perccent-wallet
gh repo clone rgsneddon/evolve %USERPROFILE%\evolve
```

Do **not** `git -C` any of those paths until the clone above has created them.

---

## 1b) Pack wallet **0.33** Windows zip (this box's job)

Darwin cannot `flutter build windows`. Do **not** wait for the Mac. Attach the zip to **tag 0.33** (do **not** recut the tag, do **not** retarget 0.32).

```
cd /d %USERPROFILE%\shear-testnet
git fetch --tags origin
git checkout 0.33
cd wallet
flutter config --enable-windows-desktop
flutter pub get
flutter build windows --release --build-name=0.33 --build-number=49
cd /d %USERPROFILE%\shear-testnet
python wallet\pack\zip_windows.py
gh release upload 0.33 dist\shear-wallet-0.33-windows.zip --repo rgsneddon/shear-testnet
```

`wallet\pack\zip_windows.py` reads `kWalletVersion` and must write `dist\shear-wallet-0.33-windows.zip`. Zip root is `shear_wallet.exe`. **No miner inside.** Do **not** upload to tag **0.32**. Do **not** recut **0.31** / **0.30** / ShearK **1.6**. After the zip is on tag **0.33**, Amelia can restore the live site WALLET Windows menu.

---

## 2) Download Shear leftover (already on tag)

```
gh release download 1.6 --repo rgsneddon/ShearK --pattern ShearK-Miner-1.6-windows.zip --dir %USERPROFILE%\Downloads\sheark-1.6
gh release download 0.30 --repo rgsneddon/shear-testnet --pattern shear-wallet-0.30-windows.zip --dir %USERPROFILE%\Downloads\shear-0.30
```

Direct URLs (same files):

- https://github.com/rgsneddon/ShearK/releases/download/1.6/ShearK-Miner-1.6-windows.zip
- https://github.com/rgsneddon/shear-testnet/releases/download/0.30/shear-wallet-0.30-windows.zip

Verify:

```
certutil -hashfile %USERPROFILE%\Downloads\sheark-1.6\ShearK-Miner-1.6-windows.zip SHA256
certutil -hashfile %USERPROFILE%\Downloads\shear-0.30\shear-wallet-0.30-windows.zip SHA256
```

Must match `879a0024297962cd9a97bf544dcd1fe1656a546d82ea37cfa6f6a2615befb5fb` (miner) and `8bc28d5255e14935e2ec7afc5cd43d89a217c84247eff40edfe25da667bc29a8` (wallet). If they do not, stop. Do **not** recut. Re-download.

Unzip to the Desktop:

```
mkdir %USERPROFILE%\Desktop\sheark-1.6
tar -xf %USERPROFILE%\Downloads\sheark-1.6\ShearK-Miner-1.6-windows.zip -C %USERPROFILE%\Desktop\sheark-1.6
mkdir %USERPROFILE%\Desktop\shear-wallet-0.30
tar -xf %USERPROFILE%\Downloads\shear-0.30\shear-wallet-0.30-windows.zip -C %USERPROFILE%\Desktop\shear-wallet-0.30
```

---

## 3) Run Shear on this box

**Wallet (after 1b).** Run the **0.33** `shear_wallet.exe` you just packed (`wallet\build\windows\x64\runner\Release\shear_wallet.exe`, or unzip the zip). Title **Shear 0.33**. Node-sync local `127.0.0.1:18332`. Magic `shear-testnet-v3`. **Copy dest** (an `ssa1…` mailbox). `she1` is the silent ID — it is **not** a paid mining login by itself.

Leftover **0.30** Windows zip is history only (download in step 2). Do **not** treat 0.30 as the live v3 wallet.

**Miner.** Edit `%USERPROFILE%\Desktop\sheark-1.6\example.bat`: replace `YOUR_SSA1` with the dest you copied, change `.worker` to a unique name for this PC, set `--threads` to this machine’s logical CPUs (`echo %NUMBER_OF_PROCESSORS%`). Double-click `example.bat`.

Login is `ssa1….worker`. `she1` without `--dest` is unpaid. Never `shear1`. How-to: https://github.com/rgsneddon/ShearK/blob/main/README.md

Pool: `pool.shear.digital:1111`. Magic: `shear-testnet-v3`. Hash: ShearHash-v3 light.

SmartScreen may warn on the unsigned miner PE. **More info → Run anyway.** Do **not** recut a signed copy.

---

## 4) Other leftover already on tag (download — do not recut)

These Windows assets survived the wipe because they were already on GitHub. Clone the product repo only if you are working that product. Pins and Mac/Linux sha256s live in [HANDOFF.md](HANDOFF.md).

| Product | Tag | Asset | sha256 |
|---------|-----|-------|--------|
| GNFP wallet **0.2.6** | `rgsneddon/gnfp-wallet` **`v0.2.6`** | `gnfp-wallet-0.2.6-windows.zip` | `aae4ccce07080cc7ce51403726a18e40248bd7c0dbfa638df6efe07c86b9eef3` |
| gnfp-cminer **0.5** | `rgsneddon/gnfp-cminer` **`v0.5`** | `gnfp-cminer-0.5-windows.zip` | `31e41293151b6ed25a41d64d1e5544181535674a62c23be51a75b872cf15938a` |
| gnfp-node **1.2.7** (source zip) | `rgsneddon/gnfp-node` **`v1.2.7`** | `gnfp-node-1.2.7-windows.zip` | `2500cae3db7cfc7c0290dcbc58ae31263b357fc6a191acdd0d6b6c2254102d8d` |
| Evolve **4.2.1** | `rgsneddon/evolve` **`v4.2.1`** | `evolve-v4.2.1-windows-x64-setup.exe` | `04df924df2ecca70ba677a84c9a195f7876dd37c83dd0e0511645603ee768975` |
| rpOffice **0.5.0** | `rgsneddon/rpOffice` **`v0.5.0`** | `pens-0.5.0-windows-x64.zip` | `dbff56887d5b703f3af29c17fd180593fb6b47b8e859d1e6706a8eb764ad1f27` |
| MY PERC **1.1.6** | `rgsneddon/perccent-wallet` **`v1.1.6`** | `perccent-wallet-v1.1.6-windows-x64-setup.exe` | `5458e1338a3d07caa461c5939e3d69837ed3f3694b390ef285751032ad8fb41c` |
| perc-mine **1.0.2** | `rgsneddon/perc-mine` **`v1.0.2`** | `perc-mine-1.0.2-windows.zip` | `4b5e83a7e6c3a832a39991ead1a319137b8b9c75f98878a0a391301d326c7167` |
| beam-mine **1.0.1** | `rgsneddon/beam-mine` **`v1.0.1`** | `beam-mine-1.0.1-windows-x64.zip` | `4f6d80a50852101a29128c0c075363caccadc99a0b35bd32b10d7733fe32480e` |
| Restore Privacy **1.2.5** (GitHub) | `rgsneddon/restore-privacy` **`1.2.5`** | `restore-privacy-client-1.2.5-windows-x64-setup.exe` | `492632b5ba80c3b7114f877a2952d7f997dec5b55ef23be8f2402fc1669225d6` |

Download example (GNFP wallet):

```
gh release download v0.2.6 --repo rgsneddon/gnfp-wallet --pattern gnfp-wallet-0.2.6-windows.zip --dir %USERPROFILE%\Downloads\gnfp-0.2.6
certutil -hashfile %USERPROFILE%\Downloads\gnfp-0.2.6\gnfp-wallet-0.2.6-windows.zip SHA256
```

Prefer **gnfp-cminer 0.5**, not 1.1.6. Do **not** ship leftover `1.0.6-max-autotune`.

---

## 5) Lost with the formatted disk (do not invent a replacement)

These Windows bits lived only on the laptop, or were never attached to the current pin. They are **gone**. Do **not** recut them onto an older tag.

| What | Status after wipe |
|------|-------------------|
| MY PERC **1.1.8** Windows | Darwin/Android/iOS **1.1.8** are on tag `v1.1.8`. Windows PE was **never** attached to 1.1.8. Run **1.1.6** from the table above. Do **not** pack 1.1.8 Windows unless Amelia names that leftover. |
| Restore Privacy **1.2.7** Windows PE | Lived on the laptop (`releases/1.2.7/`). GitHub Releases latest Windows installer is **1.2.5**. Do **not** recut 1.2.5. Do **not** invent a 1.2.7 GitHub Windows tag from this box. |
| Flutter SDK / Visual Studio / WSL trees | Gone. Reinstall for the **0.33** Windows pack in section 1b. |
| Any zip that was sitting in `Downloads` / Desktop and not on a GitHub tag | Gone. |

---

## 6) What this box does **not** do

- Recut wallet **0.32** / **0.31** / **0.30** or miner **1.6**.
- Pack a second `shear-wallet-0.30-windows.zip`.
- Upload a Windows zip to tag **0.32** (soak pin stays as shipped; latest client zip goes on **0.33**).
- Re-upload Linux / Arch.
- `git -C` a path that was not cloned in step 1.
- Rsync anything onto Dedicated-de. Do **not** restart the live pool.
- Attach Darwin as `*-linux.zip`.
- Invent a sibling GitHub tag (`vX.Y.Z-windows` and similar).
- Hunt `C:\Users\rgsne\…` for a leftover zip.
- Wait for the Mac to dispatch GitHub Actions.

---

## 7) After 0.33 Windows is on the tag

1. Confirm `gh release view 0.33 --repo rgsneddon/shear-testnet` lists `shear-wallet-0.33-windows.zip`.
2. Record sha256 in [HANDOFF.md](HANDOFF.md).
3. Amelia can restore the live site WALLET Windows menu (`data-pack="wallet-windows"`).
4. Later pins: pack Windows on this box only; attach to **that same new tag**; never recut an older tag; never put the miner inside the wallet zip.
