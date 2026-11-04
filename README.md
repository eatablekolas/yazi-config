# Yazi config

My personal configuration for the [Yazi](https://github.com/sxyazi/yazi) terminal file manager, used on Windows (`%AppData%\yazi\config`).

## Files

| File | Purpose |
| --- | --- |
| `yazi.toml` | Main settings: layout, sorting, and openers |
| `keymap.toml` | Key binding overrides |
| `theme.toml` | Selects the active flavor |
| `package.toml` | Packages managed by `ya pkg` (pinned flavors) |
| `flavors/` | Installed flavors (themes), fetched by `ya pkg` |

## Highlights

### File manager (`yazi.toml`)

- Pane ratio `1:3:4` (parent : current : preview)
- Alphabetical, case-sensitive sorting with directories first
- Hidden files shown; line mode shows modification time
- Openers:
  - Text files, JSON and empty files open in **Neovim** (`nvim`)
  - Directories open in **Windows Explorer** when opened with `o`

### Keymap (`keymap.toml`)

- `<Enter>` is remapped to `enter`, so it only navigates into directories and no longer opens files. Use `o` to open files.

### Theme (`theme.toml`)

- Active dark flavor: **claude-inspired**

## Flavors

Installed and pinned in `package.toml`:

| Flavor | Source |
| --- | --- |
| claude-inspired (active) | [rapidrabbit76/claude-inspired](https://github.com/rapidrabbit76/claude-inspired.yazi) |
| kanagawa | [dangooddd/kanagawa](https://github.com/dangooddd/kanagawa.yazi) |
| kanagawa-paper | [melindachang/kanagawa-paper](https://github.com/melindachang/kanagawa-paper.yazi) |

To switch flavors, change `dark` in `theme.toml`:

```toml
[flavor]
dark = "kanagawa"
```

## Setup

1. Clone this repo into Yazi's config directory:
   - Windows: `%AppData%\yazi\config`
   - Linux/macOS: `~/.config/yazi`
2. Install the pinned packages:

   ```sh
   ya pkg install
   ```

3. Optional requirements:
   - [Neovim](https://neovim.io/) for the `edit` opener
   - A [Nerd Font](https://www.nerdfonts.com/) for icons used by the flavors

Each flavor keeps its own license in its folder under `flavors/`.
