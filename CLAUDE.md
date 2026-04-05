# IC Gallery — Hugo Project

Photo gallery site using the Hugo Gallery theme (by Nico Kaiser). Requires Hugo Extended >= 0.123.0.

## Hugo Commands

```bash
# Start dev server (includes drafts)
hugo server -D

# Start dev server (includes future-dated posts)
hugo server --buildFuture

# Build site for production
hugo

# Create new content
hugo new content/<album-name>/index.md
```

## Project Structure

```
content/
├── _index.md                  # Homepage
├── main.jpg                   # Homepage hero image
├── about/
│   ├── index.md               # About page (layout: about)
│   └── main.jpg               # About page image
├── paris/
│   ├── index.md               # Album page
│   └── *.jpg                  # Photos
└── sao_paulo/
    ├── index.md               # Album page
    ├── index.pt.md            # Portuguese translation
    └── *.jpg                  # Photos
```

## Adding Albums

1. Create a folder under `content/` with an `index.md`
2. Drop `.jpg` photos in the same folder (avoid WebP — Hugo bug)
3. Albums without images won't appear on the site
4. Future-dated albums need `--buildFuture` flag to show

## Multilingual (EN / PT / SV)

- Default language: English
- Translations: create `index.pt.md` / `index.sv.md` alongside `index.md`
- UI strings: `i18n/` folder (theme provides en, pt; custom sv.yaml in project)

## Custom Layouts (overrides in `layouts/`)

- `partials/header.html` — adds About link + language switcher
- `partials/head-custom.html` — custom CSS
- `_default/home.html` — homepage with hero image
- `_default/about.html` — about page with image
