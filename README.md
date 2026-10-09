# jasondaihl.github.io

Personal site for Jason Daihl — Staff Frontend Engineer, UI Platforms & Design Systems.

Served at [jasondaihl.github.io](https://jasondaihl.github.io) via GitHub Pages.

## Stack

Built with [Astro](https://astro.build) as a static site.

- `src/pages/index.astro` — the page content.
- `src/layouts/Base.astro` — document shell: `<head>`, metadata, fonts.
- `src/styles/global.css` — styling, built on a design-token layer.
- `public/` — static assets served as-is (e.g. `favicon.svg`).

## Design tokens

Styles are driven by a two-tier token system in `src/styles/global.css`:

- **Primitives** (`--ds-*`) — the raw palette, spacing, type, and radii scales.
- **Semantic tokens** (`--color-*`) — intent-based variables that map to primitives.

Components only reference semantic tokens, so theming is a matter of remapping
that layer. Dark mode is implemented exactly this way: a
`@media (prefers-color-scheme: dark)` block repoints the semantic tokens at
different primitives, leaving the component CSS untouched.

## Development

```sh
npm install
npm run dev      # dev server at localhost:4321
npm run build    # static build to dist/
npm run preview  # preview the production build
```

## Deployment

Pushing to `main` triggers the `Deploy to GitHub Pages` workflow
(`.github/workflows/deploy.yml`), which builds the site and publishes `dist/`.

This requires the Pages source to be set to **GitHub Actions**
(Settings → Pages → Build and deployment → Source).
