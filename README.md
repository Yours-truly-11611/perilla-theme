# Perilla Theme

A Hugo theme inspired by the [Surrealist WordPress theme](https://wordpress.org/themes/surrealist/) by Automattic. Features a full-viewport tinted hero landing page, a full-screen navigation overlay, and a clean, responsive blog layout built around warm earthy tones and elegant serif typography.

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
- **Custom CSS:** Drop a file at `your-hugo-site/static/css/custom.css` — it will be picked up automatically without editing theme files.
- **Swap the display font:** Replace the `--font-display` variable with your preferred font. If you self-host a font like Kame, add a `@font-face` rule in `custom.css` pointing to files in `static/fonts/`.

---

## Theme Structure

```
perilla/
├── layouts/
│   ├── baseof.html                  # Root HTML shell
│   ├── index.html                   # Homepage (hero landing page)
│   ├── _default/
│   │   ├── single.html              # Single post/page
│   │   └── list.html                # Section/taxonomy list
│   └── partials/
│       ├── nav-overlay.html         # Full-screen nav + JS
│       ├── footer.html
│       └── head-extras.html         # OG tags, canonical, favicon
├── static/
│   └── css/
│       └── style.css                # Main stylesheet
├── theme.toml                       # Theme metadata
└── config.example.toml              # Example site config
```
