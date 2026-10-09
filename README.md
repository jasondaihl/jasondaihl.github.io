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

Styling is driven by the [quoin](https://github.com/jasondaihl/quoin) design
system's tokens (`--quoin-*`). The site's own CSS in `src/styles/global.css`
references quoin's semantic tokens only — there is no site-local token layer.

- `src/styles/quoin-tokens.css` — the token layer, **vendored** from
  `@jasondaihl/quoin-tokens` v0.5.0. This is a temporary copy; once that package
  is published, delete this file and import `@jasondaihl/quoin-tokens/tokens.css`.
- `src/styles/global.css` — component styling, referencing `--quoin-*` tokens.

Dark mode and multi-brand theming are owned by quoin via `data-theme` /
`data-brand` attributes. Because quoin themes by attribute rather than
`prefers-color-scheme`, a small inlined script in `Base.astro` mirrors the OS
preference onto `<html data-theme>` so dark mode still follows the system.

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
