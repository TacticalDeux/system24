# system24 for Yapfast

A port of [refact0r/system24](https://github.com/refact0r/system24) — a
customizable, TUI-style theme — to the Yapfast theme format (`theme_api` 1).

Square corners, 2px solid borders around every pane, DM Mono throughout,
Loader art and panel labels. The dark palette is
system24's own; the light palette is system24's light variant over a
`catppuccin-latte` base.

## Install

Point Yapfast at this folder from its theme picker, or validate the package
first:

```
yapfast theme check <folder>
```

`theme check` reads `theme.json` and every file it names (`fonts/`, `icons/`,
`assets/`) and reports anything Yapfast would ignore.

## Variants and light mode

Both variants ship:

- **dark** — `base: "yap"` with system24's 63-token palette.
- **light** — `base: "catppuccin-latte"` with system24's own light overrides.

Yapfast follows the app's appearance automatically and picks the matching
variant, so no separate "auto" theme is needed.

## Flavour

The Flavour option offers system24's palette plus seven ported flavours:

System24, Nord, Tokyo Night, Catppuccin Mocha, Catppuccin Macchiato,
Everforest, Rosé Pine, Rosé Pine Moon.

A Yapfast option holds at most eight choices, so system24's **vencord**
flavour is not offered; its palette is otherwise identical to the system24
base. Every flavour rewrites only the dark palette (`variants.dark.colours.*`),
so light mode keeps the Catppuccin Latte palette.

## Other options

| Option                    | Default | What it does                                                       |
| ------------------------- | ------- | ------------------------------------------------------------------ |
| Screen art                | None    | Scanlines, grain, CRT (both), or the system24 / cats loaders       |
| Panel labels              | on      | `NAV`, `MEMBERS`, `INPUT #channel` titles over the panes           |
| Square corners            | on      | system24's unrounding; off restores rounded corners                |
| Compact user panel        | off     | hides the account avatar                                           |
| Remove avatar decorations | on      | square, undecorated avatars                                        |
| Animations                | on      | blinking block caret and the channel-change fade                   |

## What the port leaves out

- **Spotify bar** — system24's now-playing bar is a custom plugin surface
  Yapfast has no counterpart for, so it is not drawn.
- **Custom cursors** — retired in Yapfast; the system cursor is used.
- **Hidden tokens** — `chrome.hide` is empty in the theme itself. The
  compact-panel option hides only `account-avatar`; system24's
  `channel-icons` token has no verified Yapfast equivalent and is not used.
- **CSS-only tokens** — system24 variables that paint things Yapfast does not
  expose (window-level CSS details, plugin hooks) were dropped rather than
  mapped onto unrelated tokens.

## Fonts

DM Mono ships in `fonts/DMMono-Regular.ttf` and `fonts/DMMono-Medium.ttf`
under the SIL Open Font License 1.1; the full text is `fonts/OFL.txt`.

## Licence

MIT, as upstream — see `LICENSE`. Fonts are OFL, as noted above.
