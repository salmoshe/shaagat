# Shaagat HaAri — שאגת הארי

## Project Overview
Family chore chart web app for a family of 7 + grandma + עדי. Single-page app with no frameworks or build tools.
Page heading: "חלוקת אחריות ומשימות - מבצע ״שאגת הארי״"

## Tech Stack
- Plain HTML + CSS + JS in a single `index.html`
- No frameworks, no build tools, no dependencies
- Hosted on GitHub Pages: https://salmoshe.github.io/shaagat/

## Files
- `index.html` — entire app (HTML + embedded CSS + JS)
- `IMG_6949.JPG` — logo image (lion + Star of David + "שאגת הארי")

## Architecture
- **Splash screen**: user selection (9 family members), logo, heading
- **Dashboard**: heading, fixed tasks + 4 weekly schedule tables with highlighting
- **Theme**: dark/light toggle button (on splash + header), system preference as default, saved to localStorage
- **Persistence**: localStorage for selected user (`shaagat-user`) + theme (`shaagat-theme`)

## Family Members
| ID | Name | Emoji | Color | Fixed Task |
|----|------|-------|-------|------------|
| abba | אבא | 👨 | #4A90D9 | הכנסת מדיח |
| ima | אמא | 👩 | #E91E8C | נקיונות לפסח (shared with סבתא) |
| erez | ארז | 🦁 | #E8A838 | פריקת מדיח |
| alon | אלון | 🌳 | #5CB85C | פחים |
| maayan | מעיין | 💧 | #9B59B6 | כביסות |
| chai | חי | ⚡ | #E74C3C | סידורים + נסיעות |
| mudi | מודי | 🎮 | #00BCD4 | (viewer only) |
| savta | סבתא | 👵 | #F39C12 | נקיונות לפסח (shared with אמא) |
| adi | עדי | 🎶 | #FF6B9D | הווי ובידור |

## Fixed Tasks
- `ownerId` can be a string (single owner) or array (multiple owners, e.g. `['ima','savta']`)

## Weekly Schedule (Sun→Thu)
1. **אחראי ארוחת צהריים** — סבתא, ארז, —, חי, מעיין
2. **אחראי ארוחת ערב** — אמא every day
3. **עוזר לאמא בארוחת ערב** — אלון, מעיין, אבא, ארז, חי
4. **אחראי סדר קומת כניסה ואמבטיות + עריכת שולחן צהריים וערב** — ארז, אלון, מעיין, אלון, ארז

## Key Design Decisions
- RTL throughout — punctuation must go at logical end of Hebrew strings (e.g., `מי את/ה?` not `?מי את/ה`)
- Logo white background removed via `mix-blend-mode: multiply` (light) / `filter: invert + mix-blend-mode: screen` (dark)
- Dark mode uses `html.dark` class, not media query, to support manual toggle button
- Theme toggle: `toggleTheme()` function called via `onclick`, updates all `.theme-toggle` buttons
- Today's column auto-highlighted Sun–Thu; Fri/Sat show no highlight
- Mobile responsive with breakpoints at 600px and 360px

## Deployment
```bash
git add index.html IMG_6949.JPG CLAUDE.md && git commit -m "description" && git push
```
GitHub Pages auto-deploys from `main` branch root.
