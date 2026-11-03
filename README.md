# dark-shorts-skill

Personal Cursor / Agent skill for **English dark-psychology shorts** (Sumi Remotion + GSAP, Faceless, or **faceless combo** / `sumi-dark-faceless`).

**Not for Urdu** — use `dark_urdu_skill` separately.

## Install (Cursor)

1. Clone this repo somewhere durable, e.g.:

```bash
git clone https://github.com/OWNER/dark-shorts-skill.git
```

2. Copy or symlink into Cursor personal skills:

```text
~/.cursor/skills/dark-shorts-skill/
```

On Windows:

```powershell
Copy-Item -Recurse .\dark-shorts-skill "$env:USERPROFILE\.cursor\skills\dark-shorts-skill"
```

3. Restart Cursor (or start a new agent chat). Call the skill by name:

- `dark_shorts_skill` / `dark_sumi_skill`
- `faceless combo` / `fd combo` → Sumi Dark + faceless
- `faceless skill` / `2d skill` → faceless-shorts engine

## What’s inside

| File | Purpose |
|------|---------|
| `SKILL.md` | Entry point + routing |
| `locked-settings.md` | Voice, music loudness, brand, GSAP locks |
| `visual-themes.md` | Sumi styles / rotation rules |
| `sumi-dark-faceless.md` | Combo craft |
| `faceless-route.md` | Faceless routing notes |
| `themes.json` | Theme catalog |
| `english_shorts_voice.json` | Canonical English voice config |

## Requirements in the project you run it on

This skill expects a shorts project with assets such as:

- `data/english_topics.json`
- `music-laybary/`
- brand plate / `tools/mix_loudness_lock.py`
- ElevenLabs key in env (`ELEVENLABS_API_KEY`) — **never commit keys**

## License / sharing

Your channel locks (voice IDs, brand, loudness caps) travel with this skill. Treat the repo as private if you don’t want those public.
