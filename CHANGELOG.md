# Changelog

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
