# keskos-core-meta

`keskos-core-meta` is the base user-space bundle for a typical KeskOS system.

## What this is

This repository builds a pacman meta package. The package itself is empty at runtime and exists only to pull in a curated group of packages through dependencies.

## Role in KeskOS

Meta package for the core system toolset.

## Package name

```txt
Package: keskos-core-meta
Repo: [keskos]
Architecture: any
```

## What it installs or provides

- Installs no runtime files beyond pacman metadata.
- Pulls in its software set entirely through `depends` (and optional `optdepends` where present).

## Commands and launchers

- This package does not install commands, GUI launchers, config files, logs, or systemd units directly.

## Config, logs, and state

- Configuration and logs belong to the packages pulled in by this meta package, not to the meta package itself.

## Dependencies

- Current hard dependencies: `base-devel`, `bluez`, `bluez-utils`, `btop`, `cups`, `fastfetch`, `git`, `gparted`, `htop`, `kdeconnect`, `keskos-keyring`, `keskos-mirrorlist`, `keskos-release`, `keskos-tools`, `networkmanager`, `print-manager`, and `timeshift`.
- Build with `makepkg -s --noconfirm`.

## Build

```bash
makepkg -s --noconfirm
```

## Packaging notes

- This meta package defines the baseline user-space utility layer for many KeskOS installs.
- It intentionally stays separate from desktop, browser, and optional workload bundles.

## Troubleshooting

- If installation fails, the problem is usually in one of the dependency packages or in repository availability, not in the empty meta package itself.

## Docs website export notes

- Docs site usage: package-group overview plus the dependency list from this README.
