# Installation, Updates, and Removal

Download GhostlyShare only from the [latest GitHub release](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest) or the official [Microsoft Store listing](https://apps.microsoft.com/detail/9PJ6DBC342GR).

The public packages support x64 Windows and x86_64 Linux. They include everything required to run GhostlyShare; a separate .NET installation is not needed.

## Choose Your Download

| Your system | Desktop app | Optional CLI |
| --- | --- | --- |
| Windows | Microsoft Store or [`GhostlyShareSetup_win-x64.zip`](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/GhostlyShareSetup_win-x64.zip) | [`GhostlyShareCLI_win-x64.zip`](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/GhostlyShareCLI_win-x64.zip) |
| Ubuntu, Debian, Mint, Kali, Pop!_OS | [`ghostlyshare-x86_64.deb`](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.deb) | [`ghostlyshare-cli-x86_64.deb`](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.deb) |
| Arch Linux | [`ghostlyshare-x86_64.pkg.tar.zst`](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.pkg.tar.zst) | [`ghostlyshare-cli-x86_64.pkg.tar.zst`](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.pkg.tar.zst) |
| Fedora, RHEL, Rocky, AlmaLinux | [`ghostlyshare-x86_64.rpm`](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.rpm) | [`ghostlyshare-cli-x86_64.rpm`](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.rpm) |
| openSUSE | [`ghostlyshare-x86_64.rpm`](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.rpm) | [`ghostlyshare-cli-x86_64.rpm`](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.rpm) |

Install the desktop app for the visual interface. Install the CLI only when you want the `ghs` command. Desktop and CLI can be installed together.

Use one Windows desktop installation method—Microsoft Store or direct setup—not both.

Every download link and command on this page uses GitHub's `latest` address and therefore follows the newest published release. If `curl` is unavailable on Linux, use the download links in the table and run the installation command from the download folder.

## Updating an Existing Installation

You normally do not need to uninstall the old version.

1. Stop active LAN and public shares.
2. End running `ghs lan` and `ghs share` commands with `Ctrl+C`.
3. Fully quit the GhostlyShare desktop app.
4. Download and install the latest package using the same method as before.
5. Start GhostlyShare and check **About**, or run `ghs version`.

Settings and the saved Cloudflare token normally remain in place. A separately installed system `cloudflared` is neither required nor removed by a GhostlyShare update.

## Windows Desktop

### Microsoft Store

The Store is the simplest signed installation and update path. A new Store version can appear later than the GitHub release because Microsoft certification is separate.

1. Open the [GhostlyShare Store listing](https://apps.microsoft.com/detail/9PJ6DBC342GR).
2. Select **Install**.
3. Start GhostlyShare from the Start menu.

Updates are installed through Microsoft Store updates.

To remove the Store version, open Windows **Settings → Apps → Installed apps**, find GhostlyShare, and select **Uninstall**.

### Direct GitHub Setup

Download the latest setup ZIP in a browser using the table above, or run this in PowerShell:

```powershell
Invoke-WebRequest `
  -Uri "https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/GhostlyShareSetup_win-x64.zip" `
  -OutFile "GhostlyShareSetup_win-x64.zip"
```

Then:

1. Extract `GhostlyShareSetup_win-x64.zip`.
2. Run the only setup program inside it. Its filename includes the release version: `GhostlyShareSetup_<version>_win-x64.exe`.
3. Follow the setup wizard.
4. Start GhostlyShare from the Start menu.

Windows can show a SmartScreen or publisher warning for a direct GitHub download. Confirm that the file came from the official release repository before continuing.

To update, download the latest ZIP again and run the newer setup program. Do not uninstall the existing version first.

To remove the direct setup version, open Windows **Settings → Apps → Installed apps**, find GhostlyShare, and select **Uninstall**.

## Windows CLI

Download and extract the latest portable CLI with PowerShell:

```powershell
Invoke-WebRequest `
  -Uri "https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/GhostlyShareCLI_win-x64.zip" `
  -OutFile "GhostlyShareCLI_win-x64.zip"

Expand-Archive `
  -LiteralPath ".\GhostlyShareCLI_win-x64.zip" `
  -DestinationPath ".\GhostlyShareCLI" `
  -Force

.\GhostlyShareCLI\ghs.exe version
```

Move the extracted `GhostlyShareCLI` folder to a permanent location if required. You can add that folder to your user `PATH` so `ghs` works from any terminal.

To update:

1. Stop every running `ghs` command.
2. Download the latest ZIP again.
3. Extract it over the existing CLI folder with `-Force`.
4. Run `ghs version` or `.\GhostlyShareCLI\ghs.exe version`.

To remove the CLI, delete its extracted folder and remove that folder from `PATH` if you added it. The CLI does not install a background service.

## Ubuntu, Debian, Mint, Kali, Pop!_OS

Open a terminal in the folder where you want to save the packages. For example, use `cd ~/Downloads`.

Download and install the desktop app:

```bash
curl -fL "https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.deb" -o ghostlyshare-x86_64.deb
sudo apt install ./ghostlyshare-x86_64.deb
```

Optionally download and install the CLI:

```bash
curl -fL "https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.deb" -o ghostlyshare-cli-x86_64.deb
sudo apt install ./ghostlyshare-cli-x86_64.deb
ghs version
```

To update, fully quit GhostlyShare and repeat the download and `apt install` commands. The package manager upgrades the existing installation.

Remove the desktop app and/or CLI with:

```bash
sudo apt remove ghostlyshare
sudo apt remove ghostlyshare-cli
```

## Arch Linux

Download and install the desktop app:

```bash
curl -fL "https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.pkg.tar.zst" -o ghostlyshare-x86_64.pkg.tar.zst
sudo pacman -U ./ghostlyshare-x86_64.pkg.tar.zst
```

Optionally download and install the CLI:

```bash
curl -fL "https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.pkg.tar.zst" -o ghostlyshare-cli-x86_64.pkg.tar.zst
sudo pacman -U ./ghostlyshare-cli-x86_64.pkg.tar.zst
ghs version
```

To update, fully quit GhostlyShare and repeat the download and `pacman -U` commands.

Remove the desktop app and/or CLI with:

```bash
sudo pacman -R ghostlyshare
sudo pacman -R ghostlyshare-cli
```

## Fedora, RHEL, Rocky Linux, AlmaLinux

Download the signing key and import it once:

```bash
curl -fL "https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/RPM-GPG-KEY-GhostlyShare" -o RPM-GPG-KEY-GhostlyShare
sudo rpm --import ./RPM-GPG-KEY-GhostlyShare
```

Download and install the desktop app:

```bash
curl -fL "https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.rpm" -o ghostlyshare-x86_64.rpm
sudo dnf install ./ghostlyshare-x86_64.rpm
```

Optionally download and install the CLI:

```bash
curl -fL "https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.rpm" -o ghostlyshare-cli-x86_64.rpm
sudo dnf install ./ghostlyshare-cli-x86_64.rpm
ghs version
```

To update, fully quit GhostlyShare and repeat the package download and `dnf install` commands.

Remove the desktop app and/or CLI with:

```bash
sudo dnf remove ghostlyshare
sudo dnf remove ghostlyshare-cli
```

## openSUSE

Download the signing key and import it once:

```bash
curl -fL "https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/RPM-GPG-KEY-GhostlyShare" -o RPM-GPG-KEY-GhostlyShare
sudo rpm --import ./RPM-GPG-KEY-GhostlyShare
```

Download and install the desktop app:

```bash
curl -fL "https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.rpm" -o ghostlyshare-x86_64.rpm
sudo zypper install ./ghostlyshare-x86_64.rpm
```

Optionally download and install the CLI:

```bash
curl -fL "https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.rpm" -o ghostlyshare-cli-x86_64.rpm
sudo zypper install ./ghostlyshare-cli-x86_64.rpm
ghs version
```

To update, fully quit GhostlyShare and repeat the package download and `zypper install` commands.

Remove the desktop app and/or CLI with:

```bash
sudo zypper remove ghostlyshare
sudo zypper remove ghostlyshare-cli
```

## Verify the Installation

- Start the desktop app from the normal application launcher.
- Open **About** and check the displayed version.
- If the CLI is installed, run `ghs version` and `ghs --help`.
- Continue with [Getting Started](Getting-Started.md) for a first LAN or public share.

## Verify a Download

GitHub records a SHA-256 digest for every release asset. Calculate the local digest and compare it with the value shown for the same asset on the release page.

Windows PowerShell:

```powershell
Get-FileHash ".\GhostlyShareSetup_win-x64.zip" -Algorithm SHA256
```

Linux:

```bash
sha256sum ghostlyshare-x86_64.deb
```

For RPM packages, importing `RPM-GPG-KEY-GhostlyShare` lets the package manager verify the release signature during installation.

Package removal normally keeps preferences and support data. See [Cleanup and Uninstall](Cleanup-and-Uninstall.md) when you also want to remove the saved token or optional local data.
