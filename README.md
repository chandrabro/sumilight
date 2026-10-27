# Beyondsumi (lite)

Cinematic Sumi-style animated storytelling driven by an AI agent: script → direction → artwork → animation → narration → local music/SFX → HD MP4.
This is a slimmed, no-paywall, no-lock edition of Beyondsumi 1.0.1 (MIT). See `CHANGES.md` for exactly what changed.

## What you get

- **One skill**: `skills/sumi/` (SVG art route and Voicebox narration route are folded into it as references).
- **Three styles**: Sumi Original, Sumi Light, Sumi Dark. Images preferred; SVG as a no-API route.
- **Free narration options**: Voicebox (local, free), your own recording, or none. No paid provider is included.
- **Local sound**: 12 original Python music themes + SFX synthesizer, rendered on demand (no bundled WAVs, no API).
- **No render locks**: `npm run render` renders directly. Validators are optional (`npm run check`).

## Install

Requirements: Python 3.9+, Node 20+, FFmpeg (rendering only).

```sh
python3 install.py --skills-root "$HOME/.claude/skills"      # Claude Code
# Windows PowerShell: py -3 install.py --skills-root "$env:USERPROFILE\.claude\skills"
```

For any other agent that reads Agent Skills folders, pass that app's skills directory instead. More detail: `skills/sumi/references/install/claude.md` and `shared.md`.
Then start a fresh session and say:

```text
Use Sumi. Make a 30-second story about [my idea]. No narration. Go straight to the MP4.
```

Claude web/Cowork need the `skills/sumi` folder uploaded as a skill and a code-execution environment with Node + FFmpeg to render.

## Pre-render the music bank (optional)

```sh
python3 skills/sumi/assets/sound-library/library.py build-music --root ~/sumi-bank   # ~2 min, offline, deterministic
```

## Tests

```sh
python3 -m unittest discover -s tests
for t in skills/sumi/scripts/test_*.py; do python3 "$t"; done
```

## License

MIT (see `LICENSE`). Third-party notes: `THIRD-PARTY.md`. Original author: Muhammad Tahir Ashraf (Beyond Tahir), https://github.com/beyondtahir/beyondsumi.
