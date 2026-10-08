# jasondaihl.github.io

Personal site for Jason Daihl — Staff Frontend Engineer, UI Platforms & Design Systems.

Served at [jasondaihl.github.io](https://jasondaihl.github.io) via GitHub Pages.

## Structure

- `index.html` — the single page.
- `styles.css` — styling, built on a design-token layer.

## Design tokens

Styles are driven by a two-tier token system in `styles.css`:

- **Primitives** (`--ds-*`) — the raw palette, spacing, type, and radii scales.
- **Semantic tokens** (`--color-*`) — intent-based variables that map to primitives.

Components only reference semantic tokens, so theming is a matter of remapping
that layer. Dark mode is implemented exactly this way: a
`@media (prefers-color-scheme: dark)` block repoints the semantic tokens at
different primitives, leaving the component CSS untouched.

## Development

No build step. Open `index.html` directly, or serve the folder:

```sh
python3 -m http.server
```
