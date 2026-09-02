# PINWHEELS site

Static one-page site for Pinwheels. No build step, no framework, no dependencies.
Edit the files, push, and GitHub Pages redeploys in about a minute.

```
index.html      the whole page
style.css       all the styling (colors are variables at the top)
assets/         font, images, favicon
```

## Editing

**Links (Spotify / Apple / SoundCloud / Instagram)**: in `index.html`, find the
`LINKS` section and change the `href="..."` on each line.

**Adding a track**: in the `RECORDINGS` section, copy one whole `<li class="track"> ... </li>`
block and paste it above the others. Change:

1. the number (`001`), title, and date
2. the `href` of the `SC →` link
3. the track id in the iframe `src` (`api.soundcloud.com%2Ftracks%2F**2393258067**`)

To get a track id, open this in a browser and copy the number after `tracks/`:

```
https://soundcloud.com/oembed?format=json&url=https://soundcloud.com/pinwheelsmusic/TRACK-SLUG
```

Also bump the `3 ITEMS · UPDATED ...` line if you care.

**Colors**: top of `style.css`, the `:root { ... }` block. `--violet` is the link color.

**Images**: drop replacements into `assets/` with the same file names
(`irithyll.jpg` 1920×1080, `irithyll-960.jpg` 960×540, `portrait.jpg` 800×800).

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
