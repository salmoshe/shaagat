# Shaagat HaAri — שאגת הארי

## Project Overview
Family chore chart web app for a family of 5 + grandma. Single-page app with no frameworks or build tools.

## Tech Stack
- Plain HTML + CSS + JS in a single `index.html`
- No frameworks, no build tools, no dependencies
- Hosted on GitHub Pages: https://salmoshe.github.io/shaagat/

## Files
- `index.html` — entire app (HTML + embedded CSS + JS)
- `IMG_6949.JPG` — logo image (lion + Star of David + "שאגת הארי")

## Architecture
- **Splash screen**: user selection (8 family members)
- **Dashboard**: fixed tasks + weekly schedule tables with highlighting
- **Theme**: dark/light toggle with system preference as default
- **Persistence**: localStorage for selected user + theme preference

## Family Members
| ID | Name | Role |
|----|------|------|
| abba | אבא | Fixed: הכנסת מדיח |
| ima | אמא | No fixed task (viewer) |
| erez | ארז | Fixed: פריקת מדיח |
| alon | אלון | Fixed: פחים |
| maayan | מעיין | Fixed: כביסות |
| chai | חי | Fixed: סידורים + נסיעות |
| mudi | מודי | No fixed task (viewer) |
| savta | סבתא | No fixed task (weekly schedule only) |

## Weekly Schedule
- **אחראי ארוחת צהריים** (lunch responsibility)
- **עוזר לאמא בארוחת ערב** (dinner helper)
- **אחראי סדר + עריכת שולחן** (table setting)

## Key Design Decisions
- RTL throughout — punctuation must go at logical end of Hebrew strings (e.g., `מי את/ה?` not `?מי את/ה`)
- Logo white background removed via `mix-blend-mode: multiply` (light) / `filter: invert + mix-blend-mode: screen` (dark)
- Dark mode uses `html.dark` class, not media query, to support manual toggle
- Today's column auto-highlighted Sun–Thu; Fri/Sat show no highlight

## Deployment
```bash
git add index.html IMG_6949.JPG && git commit -m "description" && git push
```
GitHub Pages auto-deploys from `main` branch root.
