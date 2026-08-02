# RPM Repository for DrHelius Emulators

This is the official RPM repository for [DrHelius](https://github.com/drhelius) emulators, served via GitHub Pages.

## Available Emulators

| Emulator | System | Install Command |
|----------|--------|-----------------|
| [Gearboy](https://github.com/drhelius/Gearboy) | Game Boy / Game Boy Color / Super Game Boy | `sudo dnf install gearboy` |
| [Gearsystem](https://github.com/drhelius/Gearsystem) | Sega Master System / Game Gear / SG-1000 | `sudo dnf install gearsystem` |
| [Gearcoleco](https://github.com/drhelius/Gearcoleco) | ColecoVision | `sudo dnf install gearcoleco` |
| [Geargrafx](https://github.com/drhelius/Geargrafx) | TurboGrafx-16 / PC Engine / SuperGrafx / CD-ROM² | `sudo dnf install geargrafx` |
| [Gearlynx](https://github.com/drhelius/Gearlynx) | Atari Lynx | `sudo dnf install gearlynx` |
| [Geartowns](https://github.com/drhelius/Geartowns) | FM Towns | `sudo dnf install geartowns` |

## Installation

First, import the GPG key and add the repository:

```bash
sudo rpm --import https://drhelius.github.io/rpm-geardome/geardome-rpm.asc

sudo tee /etc/yum.repos.d/geardome.repo << 'EOF'
[geardome]
name=GearDome Emulators
baseurl=https://drhelius.github.io/rpm-geardome/packages/fedora/$releasever/$basearch/
enabled=1
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://drhelius.github.io/rpm-geardome/geardome-rpm.asc
EOF
```

Then install any emulator:

```bash
sudo dnf install gearboy
sudo dnf install gearsystem
sudo dnf install gearcoleco
sudo dnf install geargrafx
sudo dnf install gearlynx
sudo dnf install geartowns
```

## Updating

To update all emulators to their latest versions:

```bash
sudo dnf upgrade
```

Or update a specific emulator:

```bash
sudo dnf upgrade geargrafx
```

## Uninstallation

```bash
sudo dnf remove geargrafx
```

To remove the repository:

```bash
sudo rm /etc/yum.repos.d/geardome.repo
sudo rpm -e gpg-pubkey-<KEY_ID>
```

## Supported Platforms

- Fedora 44, 43, 42
- Architectures: x86_64, aarch64

## License

This repository is provided under the GNU GPL v3 license.
