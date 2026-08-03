# Version 14 Theme for Zed

A clean dark and light theme for [Zed](https://zed.dev), built around the **Version 14** brand palette — high-contrast accents on deep neutrals.

## Variants

| Variant | Description |
|---|---|
| **Version 14 Dark** | Deep dark backgrounds with a violet accent (`#B7A2FF`) — see note on the accent color below |
| **Version 14 Black** | Pure black backgrounds (`#000000`) with the same violet accent — ideal for OLED displays |
| **Version 14 Light** | Bright neutral surfaces with a violet accent (`#5F3BBB`) |

> **v0.4.0 note:** this release replaces the previous signature lime-green accent (`#D2FF3A`) with a violet hue and adds a 4-step elevation/text contrast grade to all three variants (see `color-palette.md` in [`version14-themes`](https://github.com/version14) for the full rationale). **The violet accent hue is a placeholder**, not final — it will change again in a future release once a permanent replacement hue is chosen. Everything else about the grade (lightness/chroma, contrast ratios) is stable regardless of which hue eventually lands there.

## Installation

1. Open Zed and go to **Extensions** (`Cmd+Shift+X`)
2. Search for **Version 14**
3. Click **Install**
4. Open the Command Palette (`Cmd+Shift+P`) → **theme selector: Toggle**
5. Select **Version 14 Dark**, **Version 14 Black**, or **Version 14 Light**

## Color Palette

### Dark

| Role | Color |
|---|---|
| Background | `#1A1E23` |
| Editor | `#14171B` |
| Accent (placeholder) | `#B7A2FF` |
| Functions | `#B7A2FF` |
| Keywords | `#ED8EF3` |
| Strings | `#4BDE7F` |
| Types | `#78AFFF` |
| Constants | `#FFA85E` |
| Errors | `#FF5C59` |
| Comments | `#6E737A` |

### Black

| Role | Color |
|---|---|
| Background | `#0C0D0E` |
| Editor | `#000000` |
| Accent (placeholder) | `#B7A2FF` |
| Functions | `#B7A2FF` |
| Keywords | `#ED8EF3` |
| Strings | `#4BDE7F` |
| Types | `#78AFFF` |
| Constants | `#FFA85E` |
| Errors | `#FF5C59` |
| Comments | `#6E737A` |

### Light

| Role | Color |
|---|---|
| Background | `#F4F5F6` |
| Editor | `#EBEDEF` |
| Accent (placeholder) | `#5F3BBB` |
| Functions | `#5F3BBB` |
| Keywords | `#8C2293` |
| Strings | `#166534` |
| Types | `#0054CB` |
| Constants | `#8F4400` |
| Errors | `#B91A25` |
| Comments | `#636870` |

## Also available for VS Code and Neovim

- [VS Code extension](https://github.com/version14/vscode-theme)
- [Neovim/Vim plugin](https://github.com/version14/version14.vim)

## License

[MIT](./LICENSE) © [Mathieu Souflis](https://mathieusouflis.fr)
