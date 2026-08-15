# tools

## Regenerating the social preview card (`/og.png`)

`og.html` is the source for the 1200x630 Open Graph image. It pulls fonts from
the site's own `style.css`, so it stays visually identical to the live pages.

Serve the site locally (the page needs `/fonts/*` over HTTP, not `file://`):

```
python3 -m http.server 8787
```

Then render with any Chromium browser in headless mode:

```
"/Applications/Brave Browser.app/Contents/MacOS/Brave Browser" \
  --headless --disable-gpu --hide-scrollbars \
  --force-device-scale-factor=1 --window-size=1200,630 \
  --virtual-time-budget=8000 \
  --screenshot=og.png \
  http://localhost:8787/tools/og.html
```

Move the result to the repo root as `og.png`. Keep it exactly 1200x630 — the
`og:image:width` / `og:image:height` tags on every page declare those dimensions.
