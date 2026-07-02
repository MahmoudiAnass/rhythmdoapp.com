# RhythmDo app screenshots

The landing page gallery loads five numbered images from this folder:

| Filename   | Source                                                    |
| ---------- | --------------------------------------------------------- |
| `01.jpg`   | Play Store marketing shot #1 (device frame + copy baked in) |
| `02.jpg`   | Play Store marketing shot #2                              |
| `03.jpg`   | Play Store marketing shot #3                              |
| `04.jpg`   | Play Store marketing shot #4                              |
| `05.jpg`   | Play Store marketing shot #5                              |

Current images are compressed to **800 px wide, JPEG q82** (~75–90 KB each) from the original 2–3 MB AppScreens PNGs.

## Replacing / adding images

- Overwrite `01.jpg` – `05.jpg` with new versions using the same filenames — no HTML changes needed.
- To add a 6th image, add `06.jpg` here and duplicate one `<figure>` block in `index.html` (search for `screenshots/05.jpg`).

## Recommended specs
- **Format**: JPG for photo-like marketing shots, PNG for pure UI screenshots with transparency
- **Aspect ratio**: portrait (9:19.5 works well; the current AppScreens output is portrait marketing frames)
- **Width**: 800 px is a good sweet spot (the site displays them at ~260–290 px wide, so 800 px covers retina without waste)
- **File size**: aim for under ~150 KB each. Use [tinypng.com](https://tinypng.com) or [squoosh.app](https://squoosh.app), or drop new PNGs into this folder and re-run `_compress.ps1` at the project root.

## Publishing

From the project root:

```powershell
git add screenshots
git commit -m "assets: update app screenshots"
git push
```

Vercel / Netlify / GitHub Pages auto-deploy on push; on cPanel, click **Deploy HEAD Commit**.
