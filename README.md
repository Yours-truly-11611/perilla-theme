# Perilla Theme

A Hugo theme inspired by the [Surrealist WordPress theme](https://wordpress.org/themes/surrealist/) by Automattic. Features a full-viewport tinted hero landing page, a full-screen navigation overlay, image lightbox with captions, and a clean, responsive blog layout built around warm earthy tones and elegant serif typography.

---

## Setup

1. **Clone or copy** this theme folder into your Hugo site's `themes/` directory:
   ```
   your-hugo-site/
   └── themes/
       └── perilla/      ← this folder
   ```

2. **Set the theme** in your site's `config.toml`:
   ```toml
   theme = "perilla"
   ```

3. **Add your hero image.** Place a high-resolution landscape image at:
   ```
   your-hugo-site/static/images/hero.jpg
   ```
   Then point to it in `config.toml`:
   ```toml
   [params]
     heroImage = "images/hero.jpg"
   ```

4. **Copy and customize** `config.example.toml` — it contains all available parameters with comments.

5. Run `hugo server` and visit `http://localhost:1313`.

---

## Configuration Reference

All options live under `[params]` in your site `config.toml`:

| Key | Default | Description |
|---|---|---|
| `heroTitle` | Site title | Large display text on the homepage hero |
| `heroSubtitle` | *(none)* | Small uppercase text below the title. Remove the key to hide. |
| `heroImage` | `images/hero.jpg` | Path to the hero background image (relative to `static/`) |
| `heroTintColor` | `rgba(30,20,40,0.55)` | CSS color value overlaid on the hero image. Adjust the last number (opacity) to lighten or darken. |
| `menuButtonLabel` | `Explore` | Text on the menu button |
| `footerNote` | `All rights reserved.` | HTML-safe string shown in the footer |

---

## Page Frontmatter

These fields are available in page frontmatter for hero images and content cards:

| Key | Description |
|---|---|
| `heroImage` | Path to the hero image for this page |
| `heroImageDesc` | Description text displayed beneath the image in the lightbox |
| `heroTintColor` | CSS color overlay for full-width heroes (default: `rgba(30,20,40,0.55)`) |
| `heroFull` | Set to `true` for a full-viewport hero instead of the split layout |
| `heroSubtitle` | Subtitle text displayed in the hero section |
| `image` | Thumbnail image used on post cards in list views |
| `summary` | Short description shown on post cards |
| `popular` | Set to `true` to feature a blog post in the popular tab |

---

## Archetypes

The theme includes leaf bundle archetypes for creating new content:

```bash
# Create a new blog post
hugo new blog/my-post

# Create a new portfolio piece
hugo new portfolio/my-project
```

Both create a directory with an `index.md` file, ready for page-scoped images and resources.

---

## Image Lightbox

Pages with a split hero image include a click-to-expand lightbox. Clicking the hero image opens a full-screen overlay. Add a description beneath the image using the `heroImageDesc` frontmatter field:

```yaml
heroImage: "/images/my-photo.jpg"
heroImageDesc: "Oil on canvas, 1931 — Salvador Dalí"
```

---

## Navigation

Populate the overlay menu by adding `[[menu.main]]` entries in your `config.toml`:

```toml
[[menu.main]]
  name   = "About"
  url    = "/about/"
  weight = 1
```

---

## Customization

- **Colors & fonts:** Edit the CSS custom properties at the top of `static/css/style.css` (under the `:root` block).
- **Custom CSS:** Drop a file at `your-hugo-site/assets/css/custom.css` — it will be picked up automatically without editing theme files.
- **Swap the display font:** Replace the `--font-display` variable with your preferred font. If you self-host a font like Kame, add a `@font-face` rule in `custom.css` pointing to files in `static/fonts/`.

---

## Theme Structure

```
perilla/
├── archetypes/
│   ├── default/
│   │   └── index.md                  # Default leaf bundle archetype
│   ├── blog/
│   │   └── index.md                  # Blog post archetype
│   └── portfolio/
│       └── index.md                  # Portfolio piece archetype
├── layouts/
│   ├── baseof.html                   # Root HTML shell
│   ├── index.html                    # Homepage (hero landing page)
│   ├── _default/
│   │   ├── single.html               # Single post/page
│   │   ├── list.html                 # Section list
│   │   ├── taxonomy.html             # Taxonomy list (e.g. /categories/)
│   │   ├── term.html                 # Taxonomy term (e.g. /categories/design/)
│   │   ├── search.html               # Search page
│   │   └── index.json                # JSON index for search
│   ├── portfolio/
│   │   └── list.html                 # Portfolio section list
│   └── partials/
│       ├── blog-tabs.html            # Blog section tab bar
│       ├── nav-overlay.html          # Full-screen nav + JS
│       ├── footer.html
│       └── head-extras.html          # OG tags, canonical, favicon
├── static/
│   └── css/
│       └── style.css                 # Main stylesheet
├── theme.toml                        # Theme metadata
├── config.example.toml               # Example site config
└── LICENSE
```

---

## License

Released into the public domain under [The Unlicense](https://unlicense.org).
