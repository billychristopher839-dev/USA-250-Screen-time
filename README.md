# The Republic of Discipline — USA Prosperity Game

A patriotic, USA-themed screen-time habit tracker. You play the Government of the
United States: log your daily screen time, and the less you scroll, the more the
nation prospers. Journey from 1776 to 2026 across 250 days, relive a real piece of
American history each year, and unlock all 50 states.

================================================================
EASIEST WAY TO PUBLISH (recommended) — ONE FILE, NOTHING BREAKS
================================================================

If your images or sounds ever show up broken on GitHub Pages, use the
**single self-contained file** instead. Every picture, sound, and the map is
baked directly into it, so there are no asset paths that can break.

1. Take the file named **index.html** that was provided alongside this folder
   (the ~5 MB self-contained one).
2. In your repository, DELETE the old `index.html` and the `assets/` folder.
3. Upload that single **index.html** to the repository root.
4. Settings -> Pages -> Source: "Deploy from a branch", Branch: main, Folder: / (root).
5. Wait ~1 minute. Done. It will work at the root OR in a project subfolder.

That's the foolproof option. The multi-file version below is optional.

================================================================
MULTI-FILE VERSION (separate images & sounds)
================================================================

Upload **everything in this folder**, keeping the structure EXACTLY:

```
.nojekyll            <- IMPORTANT: keep this empty file (stops GitHub from hiding assets)
index.html
assets/
  eagle.png
  flag.png
  america.mp3
  stars.mp3
  scenery/
    01_sf.jpg ... 14_nasa.jpg
```

Then: Settings -> Pages -> Deploy from a branch -> main -> / (root).

### If pictures/sounds are MISSING (broken icons), check these — in order:

1. **Folder nesting.** `index.html` and the `assets` folder must be at the SAME
   level (the repo root), NOT inside an extra `usa-prosperity/` folder. If you
   dragged the whole folder in, your repo may have `usa-prosperity/index.html`
   and `usa-prosperity/assets/...` — move them up to the root, or just point
   GitHub Pages at that subfolder.

2. **The `assets/scenery/` files didn't upload.** GitHub's web uploader
   sometimes drops nested folders. Open your repo on github.com and confirm you
   can actually see `assets/scenery/01_sf.jpg`. If not, upload that folder again.

3. **Capitalization.** GitHub's servers are case-sensitive. The folder must be
   `assets` (lowercase) and files must match exactly (`01_sf.jpg`, not
   `01_SF.JPG`).

4. **Keep `.nojekyll`.** This empty file tells GitHub Pages to serve your assets
   as-is. Without it, GitHub may skip some files.

5. **Right URL for a project repo.** If your repo is named, say,
   `USA-250th-Edition-Screen-Time-Tracker`, the live site is at
   `https://<username>.github.io/USA-250th-Edition-Screen-Time-Tracker/`
   (with the trailing slash), not the bare `…github.io` root.

Tip: open your browser's developer console (right-click -> Inspect -> Network) and
reload. Red 404 lines show the EXACT path the page is asking for vs. where your
files actually are — that tells you which of the above it is.

## Run it locally

Open it through a tiny local server (double-clicking the multi-file version can
block assets in some browsers; the single-file index.html opens fine directly):

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Editing the game

- **Nation name, victory length, indicator values:** use the in-app
  "Amendments / Edit" button — no code needed.
- **Swap photos:** replace any file in `assets/scenery/` (keep the same name).
- **Anthems:** replace `assets/america.mp3` / `assets/stars.mp3`.
- **History events:** edit the `EVENTS` object in `index.html`.
- **States:** edit the `STATES` array in `index.html`.

(Editing the multi-file version's files is simplest; the single-file index.html
has the same code but with assets embedded as data URIs.)
