# Changelog

## 0.4.2

**Terminal ANSI slots 0 and 8 corrected.** Both held elevation-ramp colours — `border` and `border.variant` — so anything the integrated terminal painted through them sat between 1.07:1 and 1.44:1 against the background and was effectively invisible. Shells lean on exactly these two slots: zsh-autosuggestions defaults to `fg=8`, and zsh-syntax-highlighting puts comments on slot 0.

Both now take the text ramp, in all three variants:

| Slot | Role | Dark | Black | Light |
|---|---|---|---|---|
| 0 `black` | `text.disabled` | `#4E5660` | `#4E5660` | `#999FA7` |
| 8 `bright black` | `text.subtle` | `#6E737A` | `#6E737A` | `#636870` |

`dim_black` follows slot 0. The other fourteen slots were already correct and are untouched. Light's slot 8 is `#636870` rather than the ramp's `#787E86`, matching the value the rest of the Version 14 suite already uses for light secondary text.

**Light `players[0..5].selection` repaired.** A player's selection is meant to be its own cursor colour with an alpha — the rule Dark already followed, and which `[6]` and `[7]` followed in Light. The other six had kept pre-0.4.0 values, including two lime greens (`#4D6B00`, `#5C6C00`) left over from the retired accent, so light-mode editor selection rendered olive beneath a violet cursor. `players[7].selection` in Dark and Black also picked up its own cursor colour, retiring an off-ramp `#5B6068`.

No editor UI colours changed in this release.

## 0.4.1

Fixed a regression from 0.4.0 in five keys that were never part of the documented palette grade and should not have changed:

- **Light**: `editor.active_line.background` is restored to its original light gray tint (0.4.0 had turned the active line into a solid dark bar).
- **Light**: `terminal.ansi.black` is restored to its original value (0.4.0 made default black terminal text nearly invisible against the background).
- **Light**: `element.hover` is restored to its original value.
- **Black**: `element.active` and `ghost_element.active` are restored to their original values (0.4.0 made the active UI state nearly indistinguishable from the background).

Everything the grade does cover (accent hue, elevation and text ramps, the Black/Light contrast fixes from 0.4.0) is unchanged by this patch.

## 0.4.0

**Accent color changed (placeholder).** The lime green accent (`#D2FF3A`) is replaced with a violet hue (`#B7A2FF` dark/black, `#5F3BBB` light) across all three variants. This hue is not final: it stands in for the retired lime accent while a permanent replacement is chosen.

**Contrast fixes:**
- Added a 4-step elevation ramp (chrome, surface, content, frame) and a 4-step text ramp (text, muted, subtle, disabled) to all three variants.
- **Black**: `title_bar`, `tab_bar`, and `status_bar` no longer sit at the same `#000000` as the editor. They are now distinguishable from editor content while the editor keeps its true black background.
- **Light**: `surface.background` and `elevated_surface.background` were identical (`#EFF1F3`). Popovers and menus now have real separation from the panel behind them. `text.disabled` and `text.placeholder` were also identical (`#767B82`) and are now distinct.
- Fixed `accents[0]` in Light, which held a stray copy of Dark's old lime accent instead of its own brand color.

**Secondary accent retired.** The secondary lime olive tone (`#B8E625`, used for `border.selected`, `vim.visual_block`, and the terminal's ANSI magenta slot) is replaced with a violet family tint (`#ED8EF3` dark/black, `#8C2293` light).

The palette going forward covers Dark, Black, and Light only.
