# dark-shorts-skill

Portable Cursor / Agent skills for **Shadow Protocol** dark-psychology shorts:

| Skill | Call names | Language |
|-------|------------|----------|
| **English** (this folder’s `SKILL.md`) | `dark_shorts_skill` · `dark_sumi_skill` · `faceless combo` / `fd combo` | English |
| **Urdu** (`dark-urdu-skill/`) | `dark_urdu_skill` | Urdu / Urdish |

Do **not** mix English and Urdu pipelines in one short.

## Install (Cursor)

1. Clone:

```bash
git clone https://github.com/raffay22/dark-shorts-skill.git
cd dark-shorts-skill
```

2. Install **both** skill folders (Cursor only loads a skill if `SKILL.md` is at that skill’s root):

```powershell
# English
Copy-Item -Recurse . "$env:USERPROFILE\.cursor\skills\dark-shorts-skill"

# Urdu (nested folder → its own skill name)
Copy-Item -Recurse .\dark-urdu-skill "$env:USERPROFILE\.cursor\skills\dark-urdu-skill"
```

macOS / Linux:

```bash
cp -R . ~/.cursor/skills/dark-shorts-skill
cp -R ./dark-urdu-skill ~/.cursor/skills/dark-urdu-skill
```

3. New agent chat. Call:

- English: `dark_shorts_skill` / `dark_sumi_skill` / `faceless combo`
- Tech / product guides: **`tech style`** / `cyber-sumi` (see `tech-style.md`)
- Urdu: `dark_urdu_skill`
- Either language + faceless engine: `faceless skill` / `2d skill`

## Repo layout

```text
dark-shorts-skill/           ← English skill root
  SKILL.md
  locked-settings.md
  visual-themes.md
  sumi-dark-faceless.md
  tech-style.md              ← Cyber-Sumi knowledge-guide lock
  faceless-route.md
  themes.json
  english_shorts_voice.json
  dark-urdu-skill/           ← Urdu skill (copy out as its own skills folder)
    SKILL.md
    locked-settings.md
    visual-themes.md
    faceless-route.md
    themes.json
    urdu_shorts_voice.json
```

## Project requirements

| English | Urdu |
|---------|------|
| `data/english_topics.json` | `data/urdu_topics.json` |
| `output/topic-*` | `output/urdu-topic-*` |
| Voice lock in `english_shorts_voice.json` | Voice lock in `urdu_shorts_voice.json` |

Shared: `music-laybary/`, Shadow Protocol brand, ElevenLabs via `ELEVENLABS_API_KEY` (never commit keys).

## License / sharing

Channel locks (voice IDs, brand, loudness caps) are in this public repo. Make the GitHub repo **private** if you don’t want those visible.
