# Transparent — theme for OpenCode

A dark-first OpenCode TUI theme with a true transparent background and a semi-transparent alpha ladder (70/75/90%) on panels, elements and diff surfaces; all text and syntax colors stay opaque for readability.

## Install

```sh
mkdir -p ~/.config/opencode/themes
curl -o ~/.config/opencode/themes/transparent.json https://raw.githubusercontent.com/log0u7/opencode-transparent-theme/main/.opencode/themes/transparent.json
```

Then restart OpenCode, run `/themes` and select `transparent`.

## Terminal compatibility

Transparency is rendered by your terminal, not by the theme. The result depends on whether the terminal supports per-cell alpha blending.

| Support | Terminals | What you get |
| --- | --- | --- |
| Per-cell alpha blending | kitty, ghostty, wezterm, foot | Full effect: true transparency, every alpha rung visible |
| No per-cell alpha | VTE-based terminals (GNOME Terminal, Guake), Windows Terminal | Alpha rungs render as their opaque RGB: readable, but panels are solid; the base zone still shows through when the terminal window itself has transparency enabled |

### How the theme is built

- The base `background` is the string `"none"`: the theme paints no background at all, so whatever sits behind the terminal window becomes the canvas.
- All panel, element and menu colors are `#RRGGBBAA` values at 70%, 75% and 90% alpha.
- Diff backgrounds are semi-transparent tints.
- Every text, border and syntax color is opaque, so readability never depends on what is behind the window.

## Requirements

Truecolor (24-bit) is required for full color accuracy. Check with:

```sh
echo $COLORTERM
```

`truecolor` (or `24bit`) means you are set.

## License

MIT. See [LICENSE](LICENSE).
