# Mood

A palette-driven theme for [Obsidian](https://obsidian.md/). One small set of colour tokens
drives every Obsidian variable, so switching the whole look is a single choice in
[Style Settings](https://github.com/mgmeyers/obsidian-style-settings).

Supports dark and light mode.

## Palettes

Each palette defines seven tokens: a four-step dark-to-light ramp (`--pal-1` … `--pal-4`),
a primary accent (`--pal-a1`), a darker counterpart accent (`--pal-a2`) and a lightest tone
(`--pal-light`).

| Palette | Feel |
| --- | --- |
| **Bardon** (default) | Deep green with a slate-blue mid tone and a warm gold accent |
| **Ember** | Warm browns and terracotta with a muted sage accent |
| **Tide** | Cool teals with a soft brass accent |
| **Dusk** | Muted plum and mauve with a warm apricot accent |

## Settings

Install the **Style Settings** community plugin to get:

- **Colour scheme** — pick one of the four palettes.
- **Use the darker accent** — swap the primary accent for its darker counterpart.
- **Base font size** — 12–22px.
- **Editor line width** — 500–1100px.

Without Style Settings the theme still renders: a fallback rule applies the Bardon palette
and the default typography values.

## Install

### From the community themes list

Settings → Appearance → Themes → Manage, then search for **Mood**.

### Manually

Copy `theme.css` and `manifest.json` into `<vault>/.obsidian/themes/Mood/`, then select
**Mood** under Settings → Appearance → Themes.

## Adding a palette

1. Add a `body.pal-<name>` block in section 2 of `theme.css` defining all seven tokens.
2. Add a matching option to the `palette` `class-select` in the `@settings` block at the top.

Nothing else needs to change — sections 3 and 4 read from the tokens only.

## Development

```bash
npm install
npm run lint    # stylelint with stylelint-config-obsidianmd
```

Linting also runs on every pull request via [the lint workflow](.github/workflows/lint.yml).

### Releasing

Update `manifest.json` and add the version to `versions.json` (the key is the theme version,
the value is the minimum compatible Obsidian version), then push a tag matching the manifest
version. [The release workflow](.github/workflows/release.yml) creates a draft release with
`manifest.json` and `theme.css` attached.

## License

[MIT](LICENSE)
