# Changelog

## 0.4.1

**Fix: Light theme regression from 0.4.0.** The regrade script that ported the new palette
onto every theme key mechanically forced a handful of Light/Black-specific "off-palette"
colors (custom one-off choices that never matched any of that variant's own theme colors to
begin with) onto the new tier colors, breaking them:
- **Light**: `editor.active_line.background` had become the new near-black text color at 80%
  opacity — the current-cursor line rendered as a solid dark bar. Reverted to its original,
  correct value (a light gray tint).
- **Light**: `terminal.ansi.black` had become almost the same lightness as the background,
  making default-black terminal text nearly invisible. Reverted to its original value.
- **Light**: `element.hover` had become noticeably darker/heavier than intended for a hover
  background. Reverted to its original value.
- **Black**: `element.active`/`ghost_element.active` had become nearly indistinguishable from
  the near-black background, making the "active" UI state effectively invisible. Reverted to
  their original values.

None of these five keys are part of `color-palette.md`'s documented grade (elevation ramp,
text ramp, or the 5 accent roles) — they were bespoke per-variant choices the regrade
shouldn't have touched. Everything the grade *does* cover (accent hue, elevation/text ramps,
the Black/Light contrast fixes from 0.4.0) is unaffected by this patch.

## 0.4.0

**Accent color changed (placeholder):** the signature lime-green accent (`#D2FF3A`) is
replaced with a violet hue (`#B7A2FF` dark/black, `#5F3BBB` light) across all three variants.
This hue is **not final** — it stands in for the retired lime while a permanent replacement is
chosen, and will change again in a future release. Everything else about the new grade is
stable regardless of which hue eventually lands there.

**Contrast fixes**, per `color-palette.md`'s OKLCH-derived grade:
- Introduced a 4-step elevation ramp (chrome / surface / content / frame) and 4-step text
  ramp (text / muted / subtle / disabled) to all three variants.
- **Black**: `title_bar`/`tab_bar`/`status_bar` no longer sit at the exact same `#000000` as
  the editor — they're now distinguishable from editor content while the editor itself keeps
  its true-black background.
- **Light**: `surface.background` and `elevated_surface.background` were identical
  (`#EFF1F3`) — popovers/menus now have real separation from the panel behind them.
  `text.disabled` and `text.placeholder` were also identical (`#767B82`) — now distinct.
- Fixed a latent bug where Light's `accents[0]` held a stray copy of Dark's lime accent
  instead of its own brand color.

**Secondary accent retired too:** the second lime-olive tone (`#B8E625`, used for
`border.selected`, `vim.visual_block`, and the terminal's ANSI magenta slot) is replaced with
a hue-shifted tint from the same violet family (`#ED8EF3` dark/black, `#8C2293` light).

Red Dark/Black/Light variants that existed only as unpublished local exploration are dropped
in this release — the palette going forward is Dark/Black/Light only.
