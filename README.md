# Elementor Hero Library MVP

A static SPA prototype for a modern Elementor Free hero section library.

## What is included

- 10 hero section previews
- Desktop, tablet, and mobile preview modal
- Search and category filtering
- Copy Elementor JSON button
- Download JSON button
- Separate JSON files in `data/elementor-json/`
- No build step required

## How to run locally

Use any static server from the project folder:

```bash
python3 -m http.server 5173
```

Then open:

```txt
http://localhost:5173
```

## How to deploy

### GitHub Pages

Upload the folder contents to a GitHub repository and enable GitHub Pages for the branch.

### Vercel

Import the repository into Vercel. Since this is a static site, no framework preset is required.

## Elementor testing flow

1. Install Elementor Free on a clean WordPress site.
2. Use a compatible theme such as Hello Elementor, Astra, Kadence, GeneratePress, or Blocksy.
3. Make sure Elementor flexbox containers are enabled.
4. Click `Download JSON` for a hero.
5. Import the JSON through Elementor templates or test your preferred JSON import flow.
6. Use `Copy JSON` for clipboard-based workflows.

## Important implementation note

Elementor's official cross-site paste feature expects Elementor-created clipboard data and also depends on Elementor version plus matching enabled features. This MVP therefore ships both copy-to-clipboard and download fallback. The JSON files use Elementor's documented structure with `title`, `type`, `version`, `page_settings`, and `content`, then containers and widgets inside the content array.

## Widget whitelist used in this MVP

- Container
- Heading
- Text Editor
- Image
- Video
- Button
- Icon Box
- Icon List
- Image Carousel
- Counter
- Testimonial
- Social Icons
- Google Maps

## Next product step

After testing the first 10 templates in a clean Elementor Free install, expand the `HEROES` array to 50 sections and add a compatibility badge for each widget set.
