# RhythmDo app screenshots

Drop your PNG screenshots into this folder using these exact filenames — the site auto-loads them:

| Filename            | Screen                                              |
| ------------------- | --------------------------------------------------- |
| `home.png`          | Home screen (greeting, streak, session chips)       |
| `timer.png`         | Focus timer running (Pomodoro ring)                 |
| `rescue.png`        | End-of-session Rescue Mode (extend / split / reschedule) |
| `badge-unlock.png`  | Badge unlocked celebration screen                   |
| `insights.png`      | Insights / Identity Progress / Rhythm Score         |
| `plan.png`          | Plan Ahead — Week / Month / Year view (Pro)         |
| `badges.png`        | Achievement badges grid                             |
| `new-task.png`      | New Task creation screen                            |

## Recommended specs
- **Format**: PNG (preferred) or JPG
- **Aspect ratio**: 9:19.5 (standard Android portrait)
- **Width**: ~1080 px is plenty (the site displays them at ~260 px wide)
- **File size**: keep under ~300 KB each — compress with [tinypng.com](https://tinypng.com) or [squoosh.app](https://squoosh.app)

## How to add them

1. Copy your PNGs into this folder with the filenames above.
2. From the project root, push to GitHub:
   ```powershell
   git add screenshots
   git commit -m "assets: add app screenshots"
   git push
   ```
3. Redeploy (Vercel / Netlify / GitHub Pages auto-deploy on push; on cPanel, click **Deploy HEAD Commit**).

Missing images are hidden automatically (via `onerror` fallback), so partial uploads won't break the layout.
