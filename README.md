# umu-shortcut

[![GitHub Release](https://img.shields.io/github/v/release/NubiaMeow/umu-shortcut)](https://github.com/NubiaMeow/umu-shortcut/releases/latest)
[![GitHub Downloads (all assets, all releases)](https://img.shields.io/github/downloads/NubiaMeow/umu-shortcut/total?color=blue)](https://github.com/NubiaMeow/umu-shortcut/releases/)
[![GitHub License](https://img.shields.io/github/license/NubiaMeow/umu-shortcut?color=blue)](https://github.com/NubiaMeow/umu-shortcut/blob/main/LICENSE)
[![Static Badge](https://img.shields.io/badge/umu--launcher_repo-blue?logo=github)](https://github.com/Open-Wine-Components/umu-launcher)

**umu-shortcut is now on the AUR ([link](https://aur.archlinux.org/packages/umu-shortcut))**

## Requirements

umu-shortcut requires Python 3 with the os, shutil and argparse libraries\
\
Though it is not required to run umu-shortcut, this tool is designed to be used with [UMU Launcher](https://github.com/Open-Wine-Components/umu-launcher)

## Description

### What is this?

This is a command-line tool for creating application menu shortcuts for Windows games installed in an UMU prefix.

### What does it do?

When used by itself, UMU Launcher doesn't create shortcuts in the application menu. `umu-shortcut` generates a wrapper around `umu-run` and creates a desktop entry in `~/.local/share/applications/`.

### How do I use it?
```
umu-shortcut -n "Game Name" /path/to/executable.exe
```

### Required Arguments

#### `-n, --name "Game Name"`

Sets the title for the desktop entry\
*This argument has no default value*

### Optional Arguments

#### `-i, --icon /path/to/icon.png`

Supply a path to an image file to use as an icon for the desktop entry\
*This argument has no default value*

### UMU Launcher Specific Arguments

For more information, please see the '[How Do I Use It?](https://github.com/Open-Wine-Components/umu-launcher#how-do-i-use-it)' section of the UMU Launcher readme.

#### `-p, --prefix /path/to/prefix`

Sets the `WINEPREFIX` environment variable for `umu-run`. Defaults to `umu-default`.

#### `-g, --gameid umu-gameid`

Sets the `GAMEID` environment variable for `umu-run`. Defaults to `umu-default`.

#### `-r, --proton /path/to/proton/directory`

Sets the `PROTONPATH` environment variable for `umu-run`. Defaults to `UMU-Proton`.

#### `-s, --store store-id`

Sets the `STORE` environment variable for `umu-run`. Defaults to `none`.

### Configuration Specific Switches

#### `--systemd-inhibit`

Use `systemd-inhibit` to prevent the system from entering an idle state while the game is running.\
This switch adds `systemd-inhibit --what=idle --why='Gaming via UMU'` to the wrapper.

#### `--kde-inhibit`
Use `kde-inhibit` to prevent the system from entering an idle state or showing the screensaver while the game is running.\
This switch adds `kde-inhibit --screenSaver --power` to the wrapper.

**Note:** Only one of these switches may be used at a time.

### Important Locations

Wrappers are stored in `~/.local/share/umu-shortcut/`\
Desktop entries are stored in `~/.local/share/applications/`

### Icon Storage

It is best practice to store icons in `~/.local/share/icons/hicolor/<icon size>/apps` as a PNG file.
