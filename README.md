# Sakurazuki

Dark low-contrast Omarchy theme built around a sakura wallpaper — near-black plum base, muted rose accents, moonlit blue highlights.

Compatible with the current Omarchy Quattro release (Quickshell-based shell).

## Preview

![Sakurazuki preview](preview.png)

## Installation

```bash
omarchy-theme-install https://github.com/Deoxizn/omarchy-sakurazuki-theme.git
```

For the upstream original:

```bash
omarchy-theme-install https://github.com/ahmed-z0/omarchy-sakurazuki-theme.git
```

## What's Included

Built for Omarchy 4 (Quattro). `colors.toml` is the palette and does almost all the work: Omarchy renders Hyprland (`hyprland.lua`), Neovim, the Quickshell bar and lock screen, Alacritty, Foot, Ghostty, Kitty, btop, Chromium and VS Code from it through its own templates on install.

A theme installed from a git repo deliberately cannot ship `*.lua`, a terminal config or `vscode.json` — those name programs that get launched, so Omarchy generates them from the palette instead. That is why they are not in here.

That leaves:

| File | Consumer |
|------|----------|
| `colors.toml` | everything above |
| `shell.toml` | Quickshell bar, popups, notifications, launcher, menu, polkit, lock, image-picker (handcrafted, not generated) |
| `backgrounds/` | `omarchy theme bg next`, background switcher |
| `preview.png` / `preview-unlock.png` / `unlock.png` | theme switcher |
| `icons.theme` | `omarchy-theme-set-gnome` |

Quattro generates `hyprland.lua`, `neovim.lua`, and terminal configs from `colors.toml` when installed via `omarchy-theme-install` (see `INSTALLED_THEME_DENIED` in `omarchy-theme-set`).

## Palette

Near-black plum base, muted rose accents, moonlit blue highlights.

| Role   | Color     |
|--------|-----------|
| bg     | `#14111A` |
| fg     | `#D8D0DC` |
| accent | `#B6849D` |
| muted  | `#6B5E72` |
| red    | `#8D5F74` |
| green  | `#6F7B8F` |
| yellow | `#9A84A2` |
| blue   | `#A87692` |
| magenta| `#947598` |
| cyan   | `#7E95C1` |

`hyprland_active_border` is a rose → moonlit gradient (`rgba(b6849dee) rgba(a1809acc) 45deg`), `hyprland_inactive_border` is a muted plum (`rgba(655763aa)`).

## Notes

- `colors.toml` is the single source of truth — `hyprland.lua` (borders), `neovim.lua` (aether.nvim v3), and terminal configs are generated from it when installed via `omarchy-theme-install`. No `*.lua`, `alacritty.toml`, `foot.ini`, `ghostty.conf`, `kitty.conf`, or `vscode.json` is shipped, per `INSTALLED_THEME_DENIED`.
- `shell.toml` fully describes Quickshell surfaces (bar, popups, notifications, launcher, menu, polkit, lock, image-picker, controls, spacing, typography). `shell.lock.toml` is no longer needed — the `[lock]` section lives in `shell.toml`.
- Hyprland borders are defined in `colors.toml` as `hyprland_active_border = "rgba(b6849dee) rgba(a1809acc) 45deg"` etc and rendered via `default/themed/hyprland.lua.tpl`.

## Template

Structure templated from [OldJobobo/omarchy-dune-theme](https://github.com/OldJobobo/omarchy-dune-theme) but stripped to the strict minimal file list like newer themes (Tokyo-night, Dark Spiderman) — only `colors.toml`/`shell.toml` + assets, everything else generated.

## Preview

![Preview 1](preview/preview-1.png)
![Preview 2](preview/preview-2.png)
