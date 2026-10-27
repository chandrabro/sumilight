# Changes from beyondsumi 1.0.1

## Skills: 4 -> 1
- Merged `sumi-svg` -> `skills/sumi/references/svg/`, `assets/svg/`, `scripts/check_svg.py`.
- Merged `sumi-voicebox` -> `references/voicebox-setup.md`, `scripts/probe_voicebox.py`.
- Removed `sumi-elevenlabs` (paid) and every code path/doc for ElevenLabs: voice helper, SFX generator (`generate_sfx.py`), `import-sfx`, provider block in `catalog.json`, `--elevenlabs-available`, `elevenlabs` narration choice/memory value.
- Installer (`install.py`) now installs one folder.

## Files: 333 -> ~170, 222 MB -> ~3 MB
- Removed: GitHub-Pages showcase (`docs/`), marketing/compat docs, 9 legacy style guides, research/case-study notes, other-host install guides, director-lab, motion-lab, unused style atlases.
- Removed the 219 MB prebuilt WAV music bank. It is deterministic Python output: it renders on demand per cue, or run `library.py build-music --root <dir>`.

## Locks and gates removed (none were licence/DRM/telemetry checks; all were workflow gates)
- `npm run render` no longer runs `preflight` first. `npm run check` runs the validators as advice.
- `validate_shot_plan.py` / `validate_physics.py` exit 0 unless `--strict`.
- `new_remotion_project.py` no longer requires `--motion-approval`; final message no longer says render is gated.
- Audio: unreviewed music/SFX/contact anchors/loops render by default (`--strict-review` restores refusal).
- `SKILL.md` has a "Production mode" section making approval/stop language in the references advisory.
- Kept (technical, not locks): valid even H.264 dimensions, existing media, caption timing sanity checks in `project.ts`.

## Tests
Suites adjusted where they asserted the removed locks/providers. All pass.
