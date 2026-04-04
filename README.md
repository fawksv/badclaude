# badclaude

Tiny Electron tray app that spawns a fake physics whip overlay and fires a terminal macro when the whip "cracks".

## Install + run (global CLI)

```bash
npm install -g badclaude
badclaude
```

## Local dev

```bash
npm install
npm run dev
```

## Controls

- Click tray icon: show overlay + spawn whip.
- Click tray icon again: drop/despawn whip (falls off-screen, overlay hides).
- Fast whip motion triggers crack detection and macro send.
- Mouse click while overlay is open also drops the whip.

## Macro on crack

On each crack event, the app immediately:

1. Sends interrupt (`Ctrl+C` on Windows, `Cmd+C` on macOS)
2. Types a fast phrase
3. Presses `Enter`

## Tweak physics

All whip tuning lives in `overlay.html` under the `P` settings object (`segments`, `constraintIters`, `crackSpeed`, gravity, arc, etc).

## Notes

- Windows macro path uses `koffi` + Win32 key events.
- macOS macro path uses `osascript` (`System Events`) and requires Accessibility permission for the app/terminal running `badclaude`.
- MVP/hacky by design.
