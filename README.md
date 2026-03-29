# cursor

Arch Linux package for [Cursor](https://www.cursor.com) — the AI code editor. Packages the official `.deb` release with its bundled Electron runtime.

Available on the [AUR](https://aur.archlinux.org/packages/cursor).

## Features

- Tracks the official **latest** release channel
- Uses Cursor's bundled Electron (no system electron dependency)
- Icon trimmed and resized to fit desktop environment conventions

## cursor vs cursor-bin

| | cursor | cursor-bin |
|---|---|---|
| Electron | Bundled (upstream) | System |
| Native module compatibility | Guaranteed | May break |
| Package size | Larger | Smaller |
| Upstream behaviour | Identical to official builds | Best-effort |

Use `cursor` if you want the exact behaviour of Cursor's official Linux builds. Use `cursor-bin` if you prefer sharing the system Electron and don't mind the occasional breakage with native extensions.

## Install

```bash
# With an AUR helper
paru -S cursor

# Or manually
git clone https://aur.archlinux.org/cursor.git
cd cursor
makepkg -si
```

## Update Script

A TypeScript update helper is included to check for and apply new upstream releases:

```bash
# Check for updates
npx tsx update.ts --check

# Update PKGBUILD and .SRCINFO
npx tsx update.ts --update
```
