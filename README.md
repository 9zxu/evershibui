# Evershibui
A minimal, quiet [Hugo](https://gohugo.io/) blog theme combining Everforest color palettes with Shibui-inspired simplicity.

Please visit https://9zxu.github.io/posts/evershibui/ for a detailed theme introduction.

![Evershibui screenshot](https://raw.githubusercontent.com/9zxu/evershibui/main/images/screenshot.png)

|         |                                                        Light                                                        |                                                        Dark                                                        |
| :-----: | :------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------: |
|  Home   | ![home-light](https://raw.githubusercontent.com/9zxu/evershibui/main/images/light-home.png) | ![home-dark](https://raw.githubusercontent.com/9zxu/evershibui/main/images/dark-home.png) |
| Content | ![content-light](https://raw.githubusercontent.com/9zxu/evershibui/main/images/light-content.png) | ![content-dark](https://raw.githubusercontent.com/9zxu/evershibui/main/images/dark-content.png) |
|  Post   | ![post-light](https://raw.githubusercontent.com/9zxu/evershibui/main/images/light-post.png) | ![post-dark](https://raw.githubusercontent.com/9zxu/evershibui/main/images/dark-post.png) |

## Features

- Responsive layout that adapts cleanly to desktop, tablet, and mobile screens.
- Toggleable dark/light mode built on the Everforest color palette.
- Syntax highlighting for code blocks with Chroma.
- Tag-based taxonomy for organizing and browsing posts.
- Math typesetting support via KaTeX.
- Sidebar outline for quick navigation through post headings.

## Usage

Add the theme as a git submodule in your Hugo site:

```bash
git submodule add https://github.com/9zxu/evershibui.git themes/evershibui
```

Then set the theme in your site's config (e.g. `hugo.toml`):

```toml
theme = 'evershibui'
```

This theme requires Hugo `0.146.0` or later.

## Customization

### Colorscheme

All raw hex colors live in a single file: `assets/css/_palette.css`. It defines the "Shibui" palette (dark "Sumi" / light "Washi") as `--ef-*` CSS variables — this is the only file allowed to contain hex codes.

Every other stylesheet references semantic tokens from `assets/css/_tokens.css` instead, which map abstract names (e.g. `--color-bg`, `--color-text`) to the `--ef-*` variables. To customize the colorscheme, edit the hex values in `_palette.css`; to change what a token *means*, remap it in `_tokens.css`. Layout and component CSS should never reference `--ef-*` or hex values directly.

A previous Everforest palette is kept, unused, in `assets/css/_palette-everforest.css` as a reference/rollback option — swap the `@import` in `assets/css/main.css` to switch palettes.

### Layout

Layouts live under `layouts/`, built around `layouts/baseof.html` as the base template, with reusable pieces in `layouts/_partials/` (header, footer, sidebar, menu, post list, etc.) and content-type templates at the top level (`home.html`, `page.html`, `section.html`, `taxonomy.html`, `term.html`). Override any of these by copying the file into your site's own `layouts/` directory with the same relative path — Hugo will prefer the site's version over the theme's.
