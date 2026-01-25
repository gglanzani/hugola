# Hugola Theme

## Setup

- Move `assets/og_standard.png` into `assets/og_base.png` or create an `assets/og_base.png` file in your hugo root. Otherwise, a standard will be used.
- Create an `author` key in your `hugo.toml`

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
