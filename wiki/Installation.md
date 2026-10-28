# Installation and Updates

Download GhostlyShare only from the [latest GitHub release](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest) or the official [Microsoft Store listing](https://apps.microsoft.com/detail/9PJ6DBC342GR).

The current public packages support x64 Windows and x86_64 Linux. They are self-contained, so you do not need to install .NET separately.

## Choose Your Download

| Your system | Desktop app | Optional CLI |
| --- | --- | --- |
| Windows | Microsoft Store or `GhostlyShareSetup_win-x64.zip` | `GhostlyShareCLI_win-x64.zip` |
| Ubuntu, Debian, Mint, Kali, Pop!_OS | `ghostlyshare-x86_64.deb` | `ghostlyshare-cli-x86_64.deb` |
| Arch Linux | `ghostlyshare-x86_64.pkg.tar.zst` | `ghostlyshare-cli-x86_64.pkg.tar.zst` |
| Fedora, RHEL, Rocky, AlmaLinux | `ghostlyshare-x86_64.rpm` | `ghostlyshare-cli-x86_64.rpm` |
| openSUSE | `ghostlyshare-x86_64.rpm` | `ghostlyshare-cli-x86_64.rpm` |

Install the desktop app for the visual interface. Install the CLI package only when you want the `ghs` command. Both can be installed together.

## Windows Desktop

### Microsoft Store

The Store is the simplest signed installation and update path. A new Store version can appear later than the GitHub release because Microsoft certification is separate.

1. Open the [GhostlyShare Store listing](https://apps.microsoft.com/detail/9PJ6DBC342GR).
2. Select **Install**.
3. Start GhostlyShare from the Start menu.

### Direct Setup

1. Download `GhostlyShareSetup_win-x64.zip` from the latest release.
2. Extract the ZIP before running anything inside it.
3. Run the versioned setup program inside it, for example `GhostlyShareSetup_1.3.8.0_win-x64.exe` in the current release.
4. Follow the setup wizard, then start GhostlyShare from the Start menu.

Windows can show a SmartScreen or publisher warning for the direct GitHub package. Confirm that the file came from the official release repository. Use the Microsoft Store version if you prefer the signed Store installation flow.

## Windows CLI

1. Download `GhostlyShareCLI_win-x64.zip`.
2. Extract it to a permanent folder.
3. Open PowerShell in that folder and run:

```powershell
.\ghs.exe version
.\ghs.exe --help
```

Optionally add that folder to your user `PATH` so `ghs` works from any terminal. The CLI is portable and does not install a background service.

## Ubuntu, Debian, Mint, Kali, Pop!_OS

Download the required `.deb` file or files, open a terminal in the download folder, and install them with `apt`:

```bash
sudo apt install ./ghostlyshare-x86_64.deb
sudo apt install ./ghostlyshare-cli-x86_64.deb
```

Start the desktop app from the application menu or run `ghostlyshare`. Verify the optional CLI with `ghs version`.

## Arch Linux

Download the required package or packages and run:

```bash
sudo pacman -U ./ghostlyshare-x86_64.pkg.tar.zst
sudo pacman -U ./ghostlyshare-cli-x86_64.pkg.tar.zst
```

Start the desktop app from the application menu or run `ghostlyshare`. Verify the optional CLI with `ghs version`.

## Fedora, RHEL, Rocky Linux, AlmaLinux

Download the RPM package or packages and `RPM-GPG-KEY-GhostlyShare` into the same folder. Import the release signing key once:

```bash
sudo rpm --import ./RPM-GPG-KEY-GhostlyShare
```

Then install the desktop app, the CLI, or both:

```bash
sudo dnf install ./ghostlyshare-x86_64.rpm
sudo dnf install ./ghostlyshare-cli-x86_64.rpm
```

Start the desktop app from the application menu or run `ghostlyshare`. Verify the optional CLI with `ghs version`.

## openSUSE

Download the RPM package or packages and the release key into the same folder, then run:

```bash
sudo rpm --import ./RPM-GPG-KEY-GhostlyShare
sudo zypper install ./ghostlyshare-x86_64.rpm
sudo zypper install ./ghostlyshare-cli-x86_64.rpm
```

Start the desktop app from the application menu or run `ghostlyshare`. Verify the optional CLI with `ghs version`.

## Updating an Existing Installation

You normally do not need to uninstall the old version.

1. Stop active LAN and public shares, then fully quit GhostlyShare and running `ghs` commands.
2. Download the new package for the same installation method.
3. Install it with the same setup or package-manager command used above.
4. Start GhostlyShare and check **About**, or run `ghs version`.

- **Microsoft Store:** let the Store update the app.
- **Windows setup:** run the newer extracted setup program.
- **Linux:** install the newer package over the existing package.
- **Windows CLI ZIP:** replace all files in the old extracted CLI folder.

Settings and the saved Cloudflare token normally remain in place. GhostlyShare manages and updates its own public-sharing helper. A separately installed system `cloudflared` is neither required nor removed by a GhostlyShare update.

## Verify a Download

GitHub records a SHA-256 digest for every release asset. Calculate the local digest and compare it with the value shown for the same asset on the release page.

Windows PowerShell:

```powershell
Get-FileHash .\GhostlyShareSetup_win-x64.zip -Algorithm SHA256
```

Linux:

```bash
sha256sum ghostlyshare-x86_64.deb
```

For RPM packages, importing `RPM-GPG-KEY-GhostlyShare` lets the package manager verify the release signature during installation.

See [Getting Started](Getting-Started.md) for the first test or [Cleanup and Uninstall](Cleanup-and-Uninstall.md) to remove GhostlyShare.
