# Mac → Mac (and Windows) operator handoff

**This is the note the other machine should read first.**

Full inventory (every GitHub repo, every platform): **[HANDOFF.md](HANDOFF.md)**

**URL:** https://github.com/rgsneddon/handoff/blob/main/HANDOFF.md

**Formatted Windows box (no local repo):** **[WINDOWS.md](WINDOWS.md)** — https://github.com/rgsneddon/handoff/blob/main/WINDOWS.md

**ADMITv2 Windows cut (new work, not the v3 leftover):** **[WINDOWS-ADMITv2.md](WINDOWS-ADMITv2.md)** — https://github.com/rgsneddon/handoff/blob/main/WINDOWS-ADMITv2.md — this box cuts wallet **Windows + Linux + Arch** (pin **0.34**) and ShearK **1.7** Windows + Linux. Do not mix into WINDOWS.md.

Repo: https://github.com/rgsneddon/handoff (private, account `rgsneddon`).

The Windows box was **formatted** (2026-09-11) to recover from an error. There is **no local repo** on that disk. Open **WINDOWS.md** (clone this repo, or the URL above after `gh auth login`). Do **not** `git -C` a path until after `git clone`. Do **not** recut wallet **0.30** or ShearK **1.6**.

---

## Command to type in Grok on the other Mac

The outgoing Mac **has no USB ports**. After `gh auth login` and `grok` sign-in, say exactly:

```
Read the handoff from github.com/rgsneddon/handoff and tell me where every repo and every platform is up to.
```

Or, after installing the skill (below):

```
/handoff
```

That is the only command you need. Grok will fetch `HANDOFF.md` from this repo with `gh` and report status. Then name the product you want to continue (`evolve`, `restore-privacy`, `MY PERC`, …).

## Windows (formatted box)

There is no leftover tree on that disk. Full recipe: **[WINDOWS.md](WINDOWS.md)** (`https://github.com/rgsneddon/handoff/blob/main/WINDOWS.md`). `gh repo clone`, then download — do not recut.

```
gh auth login
gh repo clone rgsneddon/handoff %USERPROFILE%\handoff
notepad %USERPROFILE%\handoff\WINDOWS.md
```

Shear wallet **0.30** Windows zip (`shear-wallet-0.30-windows.zip` sha256 `8bc28d5255e14935e2ec7afc5cd43d89a217c84247eff40edfe25da667bc29a8`) and ShearK **1.6** Windows zip (`879a0024297962cd9a97bf544dcd1fe1656a546d82ea37cfa6f6a2615befb5fb`) are **already on tag** — download, do not recut, do not pack a second zip. Miner login is `YOUR_SSA1.worker`. Privacy-class v3 is not a Windows leftover. Other leftover hashes (GNFP, Evolve, MY PERC 1.1.6, rpOffice, …) are in WINDOWS.md.

---

## Install `/handoff` on the new Mac (once)

```bash
mkdir -p ~/.grok/skills/handoff
gh api repos/rgsneddon/handoff/contents/skill/handoff/SKILL.md \
  --jq '.content' | base64 -d > ~/.grok/skills/handoff/SKILL.md
```

Optional Restore Privacy full-ship skill:

```bash
mkdir -p ~/.grok/skills/kyrusfables/references
gh api repos/rgsneddon/handoff/contents/skills/kyrusfables/SKILL.md \
  --jq '.content' | base64 -d > ~/.grok/skills/kyrusfables/SKILL.md
gh api repos/rgsneddon/handoff/contents/skills/kyrusfables/references/pipeline.md \
  --jq '.content' | base64 -d > ~/.grok/skills/kyrusfables/references/pipeline.md
```

---

## Also in this repo

| Path | What |
|------|------|
| [HANDOFF.md](HANDOFF.md) | Status of every repository and platform |
| [WINDOWS.md](WINDOWS.md) | Formatted Windows box — leftover v3: clone, then download 0.30 + ShearK 1.6 |
| [WINDOWS-ADMITv2.md](WINDOWS-ADMITv2.md) | **New** Windows work: wallet 0.34 + ShearK **2.2** Windows zip onto existing tag `2.2` |
| [patches/](patches/) | Historical WIP patches (already applied on `main` of those repos) |
| [operator/](operator/) | Encrypted key bundle (`*.tar.enc`) — passphrase is **not** in git |
| [skill/handoff/SKILL.md](skill/handoff/SKILL.md) | The `/handoff` skill source |
| [skills/kyrusfables/](skills/kyrusfables/) | Restore Privacy ship pipeline skill |

Plaintext secrets are not in this repo. Decrypt the operator bundle (see HANDOFF.md). The outgoing Mac has no USB — use GitHub, iCloud, or AirDrop.
