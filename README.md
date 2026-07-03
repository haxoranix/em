# Elementor Hero Library MVP

A static SPA demo with 10 modern hero sections.

## What it does

- Shows responsive previews of 10 hero sections
- Filters and searches sections
- Copies an Elementor-style clipboard payload for **Paste from other site**
- Downloads a normal Elementor JSON template as fallback

## Important Elementor copy note

The **Copy to Elementor** button copies a plain text payload shaped like Elementor's native clipboard format:

```json
{
  "type": "elementor",
  "siteurl": "https://example.com/index.php?rest_route=/",
  "elements": []
}
```

This matches the payload style copied by real Elementor sites. The app writes only `text/plain` to the clipboard because Elementor's paste handler expects raw clipboard text.

For the most reliable cross-site paste, set `window.ELEMENTOR_SOURCE_SITEURL` to a real WordPress REST route from a WordPress site you control, for example:

```html
<script>
  window.ELEMENTOR_SOURCE_SITEURL = 'https://your-wp-test-site.com/index.php?rest_route=/';
</script>
```

Place that script before `app.js` in `index.html`.

Static hosting on GitHub Pages or Vercel can copy the payload, but it is not a real WordPress REST endpoint. If your Elementor install validates the source URL or tries to import media from the source site, use a real WordPress source URL.

## GitHub Pages

Keep these files in the repository root:

```txt
index.html
styles.css
app.js
data/
README.md
vercel.json
```

Then enable:

```txt
Settings → Pages → Deploy from a branch → main → /root
```

## Vercel

Use static settings:

```txt
Framework: Other
Build command: empty
Output directory: empty
Install command: empty
```

## Elementor test flow

1. Open the hosted library page.
2. Click **Copy to Elementor**.
3. Open a page in Elementor.
4. Right-click inside the canvas.
5. Choose **Paste from other site**.
6. Press Ctrl/Cmd + V.

If paste fails, test with:

- Elementor Free updated
- Flexbox Containers enabled
- Hello Elementor theme
- No third-party Elementor addons

The **Download JSON** button remains available for template import fallback.
