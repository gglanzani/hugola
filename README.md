# Hugola Theme

## Setup

- Move `assets/og_standard.png` into `assets/og_base.png` or create an `assets/og_base.png` file in your hugo root. Otherwise, a standard will be used.
- Create an `author` key in your `hugo.toml`

## Open Source Projects

A card-grid section for showcasing open source projects. Each card shows an
icon, the title, a short description, and links directly to the project repo.

### Usage

1. Create `content/projects/_index.md` for the section page:

   ```markdown
   ---
   title: "Open source"
   lede: "Tools and libraries I maintain."
   ---
   ```

2. Add one markdown file per project under `content/projects/`:

   ```markdown
   ---
   title: "Hugola"
   description: "A minimal Hugo theme for long-form writing."
   icon: "/images/projects/hugola.png"
   repo: "https://github.com/gglanzani/hugola"
   tags: ["hugo", "css"]
   weight: 1
   ---
   ```

3. Visit `/projects/` to see the grid.

### Front matter

- `title` — project name (required)
- `description` — one-line summary shown on the card
- `icon` — absolute path (`/images/...`), full URL, or an emoji/short string;
  falls back to the first letter of the title when omitted
- `repo` — URL the card links to (opens in a new tab)
- `tags` — optional, up to three shown as chips on the card
- `weight` — controls card order (lower first)

### GitHub stars & forks

When `repo` points to a `github.com/<owner>/<name>` URL, the card fetches
the repo's star and fork counts client-side from the public GitHub API and
displays them in the card footer. Counts are cached in the visitor's
`localStorage` for one hour to stay well under the 60-req/hour
unauthenticated rate limit. Non-GitHub repos render without stats.

## Image Carousel

Display multiple images in a carousel/slideshow format using the `carousel` shortcode.

### Usage

```markdown
{{</* carousel */>}}
![Alt text for image 1](image1.jpg "Optional caption")
![Alt text for image 2](image2.jpg)
![Alt text for image 3](path/to/image3.png "Another caption")
{{</* /carousel */>}}
```

### Features

- **Responsive images**: Automatically generates srcset for optimal loading
- **Navigation**: Previous/next buttons and dot indicators
- **Touch support**: Swipe left/right on mobile devices
- **Keyboard support**: Use arrow keys to navigate when carousel is focused
- **Lazy loading**: Only the first image loads immediately; others load as needed
- **Captions**: Add optional captions using the title syntax `"caption text"`

### Notes

- Each image should be on its own line
- Images can be page resources or site assets
- WebP images are supported (served as-is without resizing)
- Single images will display without navigation controls
