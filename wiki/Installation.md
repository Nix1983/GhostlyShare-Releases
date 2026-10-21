# Installation

Download GhostlyShare only from the [latest GitHub release](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest) or the official [Microsoft Store listing](https://apps.microsoft.com/detail/9PJ6DBC342GR).

All public packages are self-contained. You do not need to install .NET separately.

## Windows Desktop

### Microsoft Store

The Microsoft Store is the simplest signed install and update path. A new Store version can appear later than the GitHub release because Microsoft certification is a separate process.

1. Open the [GhostlyShare Store listing](https://apps.microsoft.com/detail/9PJ6DBC342GR).
2. Select **Install**.
3. Start GhostlyShare from the Start menu.

### Direct Setup Package

1. Download `GhostlyShareSetup_win-x64.zip` from the latest release.
2. Extract the ZIP.
3. Run `GhostlyShareSetup_win-x64.exe`.
4. Follow the setup wizard.

Windows may show its normal download or publisher checks. Confirm that the file came from the official release repository before continuing.

## Windows CLI

1. Download `GhostlyShareCLI_win-x64.zip`.
2. Extract it to a permanent folder.
3. Run `ghs.exe --help`.
4. Optionally add that folder to your user `PATH`.

The CLI is portable and has no background service.

## Ubuntu, Debian, Linux Mint, Kali, Pop!_OS

Desktop app:

```bash
sudo apt install ./ghostlyshare-x86_64.deb
ghostlyshare
```

CLI:

```bash
sudo apt install ./ghostlyshare-cli-x86_64.deb
ghs --help
```

The desktop and CLI packages can be installed together.

## Arch Linux

Desktop app:

```bash
sudo pacman -U ./ghostlyshare-x86_64.pkg.tar.zst
ghostlyshare
```

CLI:

```bash
sudo pacman -U ./ghostlyshare-cli-x86_64.pkg.tar.zst
ghs --help
```

## Fedora, RHEL, Rocky Linux, AlmaLinux

Import the release signing key once:

```bash
sudo rpm --import ./RPM-GPG-KEY-GhostlyShare
```

Install the desktop app and/or CLI:

```bash
sudo dnf install ./ghostlyshare-x86_64.rpm
sudo dnf install ./ghostlyshare-cli-x86_64.rpm
```

## openSUSE

Import the same release key, then install with `zypper`:

```bash
sudo rpm --import ./RPM-GPG-KEY-GhostlyShare
sudo zypper install ./ghostlyshare-x86_64.rpm
sudo zypper install ./ghostlyshare-cli-x86_64.rpm
```

## Verify a Download

Each GitHub release asset has a recorded SHA-256 digest. You can calculate the local file digest before installing it.

Windows PowerShell:

```powershell
Get-FileHash .\GhostlyShareSetup_win-x64.zip -Algorithm SHA256
```

Linux:

```bash
sha256sum ghostlyshare-x86_64.deb
```

Compare the result with the digest shown for the same asset in the GitHub release.

## Updating

- **Microsoft Store:** use Store updates.
- **Windows setup:** download and run the newer setup package.
- **Linux:** install the newer package with the same package manager command.
- **Windows CLI ZIP:** replace the extracted files with the newer ZIP contents.

Settings normally remain in place during an update.

See [Cleanup and Uninstall](Cleanup-and-Uninstall.md) to remove packages and optional local data.
