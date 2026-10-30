# Noctalia template for Seanime

Writes the active Noctalia palette to a file the
[Noctalia Theme plugin](https://github.com/Below-Z3R0/seanime-noctalia-theme) reads, so Seanime
follows the desktop theme.

The template exports Noctalia's Material **roles**. The plugin derives the two Tailwind colour
scales Seanime's UI is built from (`--color-brand-*` and `--color-gray-*`) — Noctalia exposes
roles, not ramps, and its filters cannot express a channel-separated scale.

## Setup

1. Install the Noctalia Theme plugin in Seanime (Settings → Extensions → Marketplace).
2. Enable **Seanime** in **Noctalia Settings → Templates**.
3. Change the Noctalia theme. The palette file is rewritten and Seanime repaints within a couple
   of seconds — no reload needed.

The template writes to:

```
~/.local/state/noctalia/seanime/palette.css
```

## Output

```css
--nt-mode: light;
--nt-primary: #d7827e;
--nt-primary-container: #e5cdcc;
--nt-secondary: #56949f;
--nt-tertiary: #286983;
--nt-error: #b4637a;
--nt-surface: #fffaf3;
--nt-on-surface: #575279;
--nt-surface-variant: #f2e9e1;
--nt-on-surface-variant: #797593;
--nt-surface-container: #f2e9e1;
--nt-surface-container-low: #f8f1ea;
--nt-surface-container-high: #ecdfd3;
--nt-outline: #959190;
--nt-outline-variant: #dfdad9;
```

`--nt-mode` carries the resolved theme mode (`light` or `dark`) so the plugin can keep Seanime's
colour scheme in step with it.

The file is a plain list of custom properties: it is safe to read, safe to diff, and safe to
delete — the plugin goes inert until it comes back.

## Files

```
seanime/
├── template.toml   the template manifest
├── palette.css     the input, rendered with Noctalia's colour tokens
└── README.md
```

## License

MIT
