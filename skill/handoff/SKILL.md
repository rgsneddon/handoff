---
name: handoff
description: >
  Fetch and report the Mac-to-Mac operator handoff from GitHub
  (rgsneddon/handoff HANDOFF.md): every repository, every platform,
  current pin, what is shipped vs still to build, and uncommitted WIP
  patches. Use when the user types /handoff, "read the handoff",
  "handoff note", "where are we up to", "status of all repos",
  "status of all platforms", or starts work on a new Mac.
user-invocable: true
---

# /handoff — read the GitHub operator note

## Source of truth

Private repo: **https://github.com/rgsneddon/handoff**  
File: **`HANDOFF.md` on `main`**  
Formatted Windows box (no local repo): **`WINDOWS.md` on `main`** — https://github.com/rgsneddon/handoff/blob/main/WINDOWS.md

Do not invent status from memory or from stale `WINDOWS_HANDOFF_*.md` / `APPLE_HANDOFF_*.md` files until you have read the GitHub note. The Windows disk was formatted 2026-09-11; there is no leftover tree until after `git clone`.

## Steps

1. Fetch the live file (needs `gh` auth as `rgsneddon`):

```bash
gh api repos/rgsneddon/handoff/contents/HANDOFF.md --jq .content | base64 -d
```

If `gh` fails, try:

```bash
gh repo clone rgsneddon/handoff /tmp/rgsneddon-handoff -- --depth 1
```

then read `/tmp/rgsneddon-handoff/HANDOFF.md`.

2. Read the **entire** `HANDOFF.md`. Also list `patches/` if the user is applying WIP.

3. Reply with a compact card first:

- date stamp from the note
- **next work** (the numbered priority list)
- one row per product: pin, which platforms are shipped, which are missing
- uncommitted patches that must be applied (`perccent-wallet`, `rpOffice`)
- remind: `restore-privacy` on the outgoing Mac was behind `origin/main` — pull before committing

4. If the user named a product, `cd` to that clone (create it if missing), `git fetch && git pull`, then continue from that product’s section. Suggested paths are in the note (`~/restore-privacy`, `~/evolve`, `~/git` for perccent-wallet, …).

5. Do not commit secrets. Do not publish Mishi. Do not create sibling GitHub tags like `vX.Y.Z-macos-ios-android`.

## After the card

Stop and wait unless the user already named the next build. Do not start `kyrusfables` or an Evolve ship until they say so.
