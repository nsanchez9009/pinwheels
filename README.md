# PINWHEELS site

Static one-page site for Pinwheels. No build step, no framework, no dependencies.
Edit the files, push, and GitHub Pages redeploys in about a minute.

```
index.html      the whole page
style.css       all the styling
assets/         font, portrait, star SVGs, favicon
```

## Editing

**Links (Spotify / Apple / SoundCloud / IG)**: the `<p class="nav">` block in `index.html`.

**Adding a track**: copy one `<div class="track"> ... </div>` block and paste it above the
others. Change the title, the link, and the track id in the iframe `src`
(`api.soundcloud.com%2Ftracks%2F**2393258067**`).

To get a track id, open this in a browser and copy the number after `tracks/`:

```
https://soundcloud.com/oembed?format=json&url=https://soundcloud.com/pinwheelsmusic/TRACK-SLUG
```

**Colors**: `style.css`. Link color is `#9765d0`, search and replace it.

**Portrait**: replace `assets/portrait.jpg` (square, 800×800).

**Star dividers / frame**: `assets/stars-rule.svg` and `assets/stars-frame.svg`. The star
shapes are the ✵ ✶ ✷ glyphs from DejaVu Sans traced to paths, with a chrome gradient.

## Deploying (GitHub Pages)

`.github/workflows/pages.yml` deploys automatically on every push to `main`
(the first run also turns Pages on). Commit, push, wait a minute, refresh.
Live URL: `https://nsanchez9009.github.io/pinwheels/`

Custom domain later: buy one, add a `CNAME` file containing the domain to this folder,
and point the domain's DNS at GitHub Pages (Settings → Pages shows the exact records).

## Local preview

Open `index.html` in a browser. The font may not load over `file://` in some browsers;
if the wordmark looks like Times, run `python3 -m http.server` in this folder and
open `http://localhost:8000` instead.
