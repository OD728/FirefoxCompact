# CLAUDE.md

`chrome/userChrome.css` for Firefox: compact Darkly-style tab pills and an auto-hide address bar. GPL-2.0 because it is based on Bali10050/darkly-firefox; keep the credit.

## The repo copy is not the live file

The user edits the live copy in their Firefox profile's `chrome\` folder (`about:profiles` → Root Directory). Workflow:
1. Edit the profile copy; the user restarts Firefox to test (userChrome.css has no live reload).
2. Copy it into `chrome/userChrome.css` here, **removing the "Previous version: userChrome.backup…" header line** (it's private).
3. Commit, push, refresh the Drive bundle.

## Design decisions (keep unless asked)

- Variables at the top: `--dk-tab-height` 30px, `--dk-pill-height` 24px, `--dk-strip-radius` 4px, `--dk-pill-radius` 3px, `--dk-tab-gap` 10px. The strip stays at least 4px taller than the pill.
- Pill brightness: `currentColor 11%` inactive, `22%` selected; inactive hover tints with the system accent colour.
- Address bar folds away with `max-height` and shows after **1s** hover (2s was too slow) or instantly on keyboard focus (`Ctrl+L`, `F6`, `Alt+D`) or an open menu; hides 0.3s after leaving. A floating-overlay version was tried and rejected.
- Firefox's window buttons are hidden; the "OS style Close/Maximize/Minimize Window Button" add-ons replace them.
- README feature list and variable table must match the CSS. Screenshots are in `screenshots/`.
