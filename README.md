# GhostlyShare

[![Ubuntu desktop .deb](https://img.shields.io/github/v/release/Nix1983/GhostlyShare-Releases?label=Ubuntu%20%2F%20Debian%20desktop&logo=ubuntu&logoColor=white&color=%23e95420)](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest)
[![Linux CLI .deb](https://img.shields.io/github/v/release/Nix1983/GhostlyShare-Releases?label=Linux%20CLI%20.deb&logo=linux&logoColor=white&color=%23e95420)](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest)
[![Arch Linux packages](https://img.shields.io/github/v/release/Nix1983/GhostlyShare-Releases?label=Arch%20Linux%20packages&logo=archlinux&logoColor=white&color=%231793d1)](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest)
[![RPM packages](https://img.shields.io/github/v/release/Nix1983/GhostlyShare-Releases?label=RPM%20packages&logo=fedora&logoColor=white&color=%23294172)](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest)
[![Windows setup](https://img.shields.io/github/v/release/Nix1983/GhostlyShare-Releases?label=Windows%20setup%20ZIP&logo=windows&logoColor=white&color=%230078d4)](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest)
[![Windows CLI](https://img.shields.io/github/v/release/Nix1983/GhostlyShare-Releases?label=Windows%20CLI%20ZIP&logo=windows&logoColor=white&color=%230078d4)](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest)
[![Windows Store](https://img.shields.io/badge/Windows-Microsoft%20Store-0078d4?logo=microsoftstore&logoColor=white)](https://apps.microsoft.com/detail/9PJ6DBC342GR)
[![User Wiki](https://img.shields.io/badge/docs-user%20wiki-2ea44f)](https://github.com/Nix1983/GhostlyShare-Releases/wiki)
[![License](https://img.shields.io/badge/license-proprietary-6f42c1)](#license)

GhostlyShare is an app for making local development apps public for a short time.
Use the desktop app for an interactive workflow, or use the `ghs` command-line tool
for terminal, server, and script workflows. Both create temporary Cloudflare-powered
public URLs for local apps.

GhostlyShare is a private, proprietary application. This repository is only the public
release, download, issue, support, and user documentation home for GhostlyShare. The
application source code is private and is not included here.

## Quick Start

1. Download and install GhostlyShare.
2. Start your local app.
3. Open GhostlyShare.
4. Select the app and click `Go Public`.
5. Copy the link or scan the QR code.
6. Keep GhostlyShare and the local app running while the public link should work.

## Responsible Use

GhostlyShare is intended for lawful development, testing, demos and quick sharing of local apps from your own device.

Do not use GhostlyShare for illegal content, malware, phishing, spam, copyright infringement, privacy violations, unauthorized access, or any other harmful or abusive activity.

Public links can be reached by anyone who has the link. You are responsible for your local app, its content, access protection and legal use.

See [Responsible Use](RESPONSIBLE_USE.md) for the full policy.

## Feature Overview

- Auto-detect local web apps and APIs.
- Create random public links without an account, domain, or DNS setup.
- Use your own custom domain with your Cloudflare domain and API token.
- Enable, change, or remove optional password protection before sharing or while a link is live.
- Set or adjust an optional public-link lifetime so a link goes offline automatically.
- Copy or open public links from the app when you are ready to share.
- View simple live statistics for a public link, including requests, visitors, and active users.
- Automatically return a public link to local-only mode if it becomes unreachable.
- Choose the tray window corner and screen-edge distance manually from App Settings.
- Use `ghs` from a terminal for scan, share, Cloudflare, doctor, and JSON workflows.
- See link readiness and offline states while your local app or tunnel changes.

## App Settings

Open GhostlyShare and click the Settings button to change app preferences. Use
`Window position` and select `Change` to choose where the tray window opens. You can
choose top left, top right, bottom left, or bottom right, and adjust the distance from
the screen edge.

## Which Package Should I Choose?

- Windows users should prefer the Microsoft Store for the easiest desktop install.
- Windows ZIP downloads are for users who want a direct download outside the Store.
- Ubuntu / Debian desktop `.deb` is for the graphical GhostlyShare app.
- Ubuntu / Debian CLI `.deb` is only for terminal, server, and script workflows.
- Arch Linux desktop `.pkg.tar.zst` is for the graphical GhostlyShare app.
- Arch Linux CLI `.pkg.tar.zst` is only for terminal, server, and script workflows.
- RPM desktop `.rpm` is for the graphical app on Fedora, openSUSE, RHEL, Rocky Linux, and AlmaLinux.
- RPM CLI `.rpm` is only for terminal, server, and script workflows on RPM-based distributions.
- Desktop and CLI packages are separate and can be installed independently.

## Download

Choose the package that matches the app or CLI workflow you want to install.

| Package | Download | Installs |
|:--|:--|:--|
| Windows desktop setup ZIP | [GhostlyShareSetup_win-x64.zip](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/GhostlyShareSetup_win-x64.zip) | Desktop app setup |
| Windows CLI ZIP | [GhostlyShareCLI_win-x64.zip](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/GhostlyShareCLI_win-x64.zip) | Single-file `ghs.exe` |
| Windows Microsoft Store | [Install from Microsoft Store](https://apps.microsoft.com/detail/9PJ6DBC342GR) | Desktop app |
| Ubuntu / Debian desktop `.deb` | [ghostlyshare-x86_64.deb](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.deb) | `ghostlyshare` desktop app |
| Ubuntu / Debian CLI `.deb` | [ghostlyshare-cli-x86_64.deb](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.deb) | `ghs` command |
| Arch Linux desktop `.pkg.tar.zst` | [ghostlyshare-x86_64.pkg.tar.zst](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.pkg.tar.zst) | `ghostlyshare` desktop app |
| Arch Linux CLI `.pkg.tar.zst` | [ghostlyshare-cli-x86_64.pkg.tar.zst](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.pkg.tar.zst) | `ghs` command |
| RPM desktop `.rpm` | [ghostlyshare-x86_64.rpm](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.rpm) | `ghostlyshare` desktop app |
| RPM CLI `.rpm` | [ghostlyshare-cli-x86_64.rpm](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.rpm) | `ghs` command |
| RPM signing key | [RPM-GPG-KEY-GhostlyShare](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/RPM-GPG-KEY-GhostlyShare) | Signature verification for RPM packages |

### Windows Download Note

The Windows setup ZIP and Windows CLI ZIP are provided for users who prefer a direct
download outside the Microsoft Store.

The Windows CLI ZIP contains a single self-contained `ghs.exe`. Because it is a
direct unsigned executable download, Windows may show a SmartScreen or Microsoft
Defender warning when you run it. Only run it after verifying that you downloaded it
from the official GhostlyShare release page.

If you prefer a signed Microsoft install flow, use the Microsoft Store package
instead. The Store/MSIX package is delivered through Microsoft and avoids the
unsigned direct-download warning for the desktop app.

## Linux Installation

The desktop app and CLI are packaged separately. Install both when you want the GUI
and the `ghs` terminal command on the same system.

RPM-based distributions require the GhostlyShare RPM signing key before installing
the RPM packages. Debian/Ubuntu `.deb` packages and Arch `.pkg.tar.zst` packages do
not use this RPM key.

### Ubuntu / Debian

Install the desktop app and CLI:

```bash
mkdir -p ~/Downloads/ghostlyshare
cd ~/Downloads/ghostlyshare

wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.deb
wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.deb

sudo apt install ./ghostlyshare-x86_64.deb ./ghostlyshare-cli-x86_64.deb

ghostlyshare
ghs --help
```

Install only the desktop app:

```bash
sudo apt install ./ghostlyshare-x86_64.deb
```

Install only the CLI:

```bash
sudo apt install ./ghostlyshare-cli-x86_64.deb
```

### Fedora

Install the desktop app and CLI:

```bash
mkdir -p ~/Downloads/ghostlyshare
cd ~/Downloads/ghostlyshare

wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/RPM-GPG-KEY-GhostlyShare
wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.rpm
wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.rpm

sudo rpm --import RPM-GPG-KEY-GhostlyShare
sudo dnf install ./ghostlyshare-x86_64.rpm ./ghostlyshare-cli-x86_64.rpm

ghostlyshare
ghs --help
```

Install only the desktop app:

```bash
sudo dnf install ./ghostlyshare-x86_64.rpm
```

Install only the CLI:

```bash
sudo dnf install ./ghostlyshare-cli-x86_64.rpm
```

### openSUSE

Install the desktop app and CLI:

```bash
mkdir -p ~/Downloads/ghostlyshare
cd ~/Downloads/ghostlyshare

wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/RPM-GPG-KEY-GhostlyShare
wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.rpm
wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.rpm

sudo rpm --import RPM-GPG-KEY-GhostlyShare
sudo zypper install ./ghostlyshare-x86_64.rpm ./ghostlyshare-cli-x86_64.rpm

ghostlyshare
ghs --help
```

Install only the desktop app:

```bash
sudo zypper install ./ghostlyshare-x86_64.rpm
```

Install only the CLI:

```bash
sudo zypper install ./ghostlyshare-cli-x86_64.rpm
```

### RHEL / Rocky Linux / AlmaLinux

Install the desktop app and CLI:

```bash
mkdir -p ~/Downloads/ghostlyshare
cd ~/Downloads/ghostlyshare

wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/RPM-GPG-KEY-GhostlyShare
wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.rpm
wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.rpm

sudo rpm --import RPM-GPG-KEY-GhostlyShare
sudo dnf install ./ghostlyshare-x86_64.rpm ./ghostlyshare-cli-x86_64.rpm

ghostlyshare
ghs --help
```

### Arch Linux

Install the desktop app and CLI:

```bash
mkdir -p ~/Downloads/ghostlyshare
cd ~/Downloads/ghostlyshare

curl -LO https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.pkg.tar.zst
curl -LO https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.pkg.tar.zst

sudo pacman -U ./ghostlyshare-x86_64.pkg.tar.zst ./ghostlyshare-cli-x86_64.pkg.tar.zst

ghostlyshare
ghs --help
```

Install only the desktop app:

```bash
sudo pacman -U ./ghostlyshare-x86_64.pkg.tar.zst
```

Install only the CLI:

```bash
sudo pacman -U ./ghostlyshare-cli-x86_64.pkg.tar.zst
```

## Command Line Interface

The `ghs` CLI is a power-user, server, and script tool. It is not a background daemon
and does not replace the desktop app.

Useful commands:

```bash
ghs --help
ghs version
ghs scan
ghs scan --json
ghs share 5173
ghs share http://localhost:3000
ghs share 5173 --json
ghs share 5173 --url-only
ghs share 5173 --expires-after 15m
ghs share 5173 --password --password-attempts 5 --password-session-minutes 60
ghs cloudflare login
ghs cloudflare status
ghs doctor
ghs doctor --json
```

`ghs share` keeps running while the public link is active. Press `Ctrl+C` to stop
sharing. If you use a custom domain, GhostlyShare creates a temporary Cloudflare DNS
record while sharing and removes it again when the command stops.

If a public link becomes unreachable while sharing is active, the CLI stops the
sharing session cleanly and prints a short message before cleanup finishes.

The CLI has no background daemon and no separate `ghs stop` or `ghs list` command.
The running `ghs share` process is the sharing session.

## Public Link Options

- Random public links work without a GhostlyShare account, Cloudflare account,
  custom domain, DNS setup, or API token.
- Custom domains require your own Cloudflare-managed domain and your own Cloudflare API token.
- Optional password protection and link lifetime work with random links and custom domains.
- In the desktop app, password protection can be enabled before sharing or enabled, changed, or
  removed while the link is live.
  Live changes apply immediately without restarting the tunnel. Existing visitor password
  sessions are invalidated when the password settings change.
- Passwords must be 8 to 32 characters. By default, a visitor is locked for 5
  minutes after 3 wrong password attempts from the same visitor.
- A successful password login creates a temporary browser session. The default
  password session is 30 minutes, and the CLI can set 5 to 1440 minutes with
  `--password-session-minutes`.
- Public links can have an optional lifetime. In the desktop app, choose or change a
  preset such as 15 minutes, 30 minutes, 1 hour, 3 hours, 1 day, Today, or Custom
  before sharing or while the link is live. In the CLI, use
  `--expires-after <duration|today>`, for example
  `--expires-after 15m`, `--expires-after 1h`, `--expires-after 1d4h15m`, or
  `--expires-after today`. Custom durations must be between 1 minute and
  40 days, 23 hours, 59 minutes.
- GhostlyShare allows up to 3 public apps at the same time. This keeps tunnel
  usage conservative and helps avoid Cloudflare quick-tunnel rate limits.
- GhostlyShare checks active public links and automatically stops sharing if a link
  is no longer reachable. With Random mode, the next start usually creates a new
  public URL. With Custom mode, GhostlyShare reconnects the same configured hostname.
- If Cloudflare returns a quick-tunnel rate limit, GhostlyShare waits before
  trying random public links again. Consecutive cooldowns are 1 hour, then 3
  hours, then up to 6 hours, and the cooldown is cleared after a successful start.
- Password protection is useful for private demos, temporary reviews, and quick tests.
- Password protection is not a replacement for careful sharing and basic security habits.
- Never post tokens, secrets, passwords, private URLs, or sensitive logs in public issues.

## Verify Download

Download GhostlyShare only from the Microsoft Store or the latest GitHub release linked
above.

When SHA256 checksums are available, they are shown in the release notes. Compare the
published checksum with the file you downloaded before installing. If a release does not
show a checksum, no checksum file is currently published for that release.

Linux example:

```bash
sha256sum /tmp/ghostlyshare-x86_64.deb
```

Windows example:

```powershell
Get-FileHash .\downloaded-file -Algorithm SHA256
```

## Documentation

The full user guide is available in the [GhostlyShare Wiki](https://github.com/Nix1983/GhostlyShare-Releases/wiki).

Good starting points:

- [Responsible Use](RESPONSIBLE_USE.md)
- [Getting Started](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Getting-Started)
- [Command Line Interface](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Command-Line-Interface)
- [Security and Privacy](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Security-and-Privacy)
- [How App Detection Works](https://github.com/Nix1983/GhostlyShare-Releases/wiki/App-Detection)
- [Why Apps Are Merged](https://github.com/Nix1983/GhostlyShare-Releases/wiki/App-Merging)
- [Going Public and Link Readiness](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Going-Public)
- [Traffic Statistics](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Traffic-Statistics)
- [Link Lifetime](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Link-Lifetime)
- [Password Protection](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Password-Protection)
- [Rate Limits and Sessions](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Rate-Limits-and-Sessions)
- [Custom Domains](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Custom-Domains)
- [Cleanup and Uninstall](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Cleanup-and-Uninstall)
- [Known Limitations](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Known-Limitations)
- [Windows and Linux Differences](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Windows-and-Linux)
- [Troubleshooting](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Troubleshooting)

## Bugs and Feature Requests

Use GitHub Issues to report bugs or request user-facing improvements:

- [Report a bug](https://github.com/Nix1983/GhostlyShare-Releases/issues/new?template=bug_report.yml)
- [Request a feature](https://github.com/Nix1983/GhostlyShare-Releases/issues/new?template=feature_request.yml)

Please do not post Cloudflare API tokens, passwords, private URLs, or other secrets
in public issues.

## Linux Tray Window Behavior

If the tray window opens in an inconvenient place, open GhostlyShare App Settings,
choose `Window position`, and select `Change`. You can choose top left, top right,
bottom left, or bottom right, and adjust the distance from the screen edge.

Linux desktops can handle tray windows, focus, and positioning differently. The Linux
tray window behavior has been tested with:

| System | Desktop | Session |
|:--|:--|:--|
| Arch Linux | KDE Plasma | Wayland |
| Kali Linux | XFCE | X11 |
| Ubuntu | GNOME | Wayland |

Other Linux desktops and sessions may work too, but they are not explicitly tested.
If the tray window, focus behavior, or window position does not work correctly on your
desktop, please open a bug report and include your desktop/session details.

Useful Linux GUI details for bug reports:

```bash
cat /etc/os-release
uname -a
echo "$XDG_CURRENT_DESKTOP"
echo "$DESKTOP_SESSION"
echo "$XDG_SESSION_TYPE"
loginctl show-session "$XDG_SESSION_ID" -p Type -p Desktop -p Name
ghostlyshare
```

## Update

Download the newest package from the latest release and install it over the existing
version. For RPM packages, import the RPM signing key before installing or updating.

Update Ubuntu / Debian desktop and CLI:

```bash
mkdir -p ~/Downloads/ghostlyshare
cd ~/Downloads/ghostlyshare

wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.deb
wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.deb

sudo apt install ./ghostlyshare-x86_64.deb ./ghostlyshare-cli-x86_64.deb
```

Update Arch Linux desktop and CLI:

```bash
mkdir -p ~/Downloads/ghostlyshare
cd ~/Downloads/ghostlyshare

curl -LO https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.pkg.tar.zst
curl -LO https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.pkg.tar.zst

sudo pacman -U ./ghostlyshare-x86_64.pkg.tar.zst ./ghostlyshare-cli-x86_64.pkg.tar.zst
```

Update Fedora / RHEL / Rocky Linux / AlmaLinux desktop and CLI:

```bash
mkdir -p ~/Downloads/ghostlyshare
cd ~/Downloads/ghostlyshare

wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/RPM-GPG-KEY-GhostlyShare
wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.rpm
wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.rpm

sudo rpm --import RPM-GPG-KEY-GhostlyShare
sudo dnf install ./ghostlyshare-x86_64.rpm ./ghostlyshare-cli-x86_64.rpm
```

Update openSUSE desktop and CLI:

```bash
mkdir -p ~/Downloads/ghostlyshare
cd ~/Downloads/ghostlyshare

wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/RPM-GPG-KEY-GhostlyShare
wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-x86_64.rpm
wget https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/ghostlyshare-cli-x86_64.rpm

sudo rpm --import RPM-GPG-KEY-GhostlyShare
sudo zypper install ./ghostlyshare-x86_64.rpm ./ghostlyshare-cli-x86_64.rpm
```

## Linux Remove / Uninstall

Use this section when you want to remove an existing GhostlyShare installation before
a clean reinstall, or when you want to uninstall GhostlyShare completely.

Remove the Ubuntu / Debian desktop app and CLI:

```bash
sudo apt remove ghostlyshare ghostlyshare-cli
```

Remove the Fedora, RHEL, Rocky Linux, or AlmaLinux desktop app and CLI:

```bash
sudo dnf remove ghostlyshare ghostlyshare-cli
```

Remove the openSUSE desktop app and CLI:

```bash
sudo zypper remove ghostlyshare ghostlyshare-cli
```

Remove the Arch Linux desktop app and CLI:

```bash
sudo pacman -Rns ghostlyshare ghostlyshare-cli
```

Remove only the desktop app:

```bash
sudo apt remove ghostlyshare
sudo dnf remove ghostlyshare
sudo zypper remove ghostlyshare
sudo pacman -R ghostlyshare
```

Remove only the CLI:

```bash
sudo apt remove ghostlyshare-cli
sudo dnf remove ghostlyshare-cli
sudo zypper remove ghostlyshare-cli
sudo pacman -R ghostlyshare-cli
```

Uninstalling a package removes that installed Linux package, but local user data may remain
in your profile. See [Cleanup and Uninstall](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Cleanup-and-Uninstall)
for notes about app data, logs, cached `cloudflared` files, and stored custom-domain
tokens.

## What GhostlyShare Expects

GhostlyShare is designed for local development apps: web servers, APIs, dashboards,
frontend dev servers, local docs, and similar tools that listen on localhost or all
local interfaces.

The most reliable apps are:

- HTTP or HTTPS apps on ports above `1024`.
- Apps started by common development runtimes such as `dotnet`, `node`, `python`,
  `python3`, versioned Python commands like `python3.12`, `vite`, `npm`, `php`,
  `ruby`, `rails`, `java`, `uvicorn`, `streamlit`, and similar tools.
- HTML apps with a meaningful `<title>`.
- APIs with JSON, OpenAPI, Swagger, FastAPI, or similar API signals.
- Framework apps such as Vite, React, Vue, Angular, Next.js, Blazor, ASP.NET Core,
  IIS Express, and other common local development stacks.

Apps may be hidden when they look like system services, infrastructure, printers,
VPN services, Docker proxy helpers, or generic HTTP endpoints without enough evidence
that they are user-facing development apps.

## Security and Privacy Basics

Public links expose the selected local app to the internet. Only share apps you own,
trust, and are allowed to make public.

Do not expose private admin panels, company systems, database tools, operating system
services, or anything that should stay internal. Optional password protection protects
the GhostlyShare public link, but the local app should still be treated carefully.

Never post Cloudflare tokens, passwords, private URLs, full logs with secrets, or other
sensitive information in public issues.

Traffic statistics are simple local counters for the current public link session.
They are meant as quick user feedback, not as full analytics or security auditing.

## Known Limitations

- The selected local app must keep running while the public link should work.
- Your computer must stay online.
- Sleep, network changes, VPN changes, or interrupted connectivity can make an
  existing public link unreachable. GhostlyShare may then stop the link automatically.
- VPNs, firewalls, proxies, DNS, and corporate networks can affect public links.
- Cloudflare Quick Tunnel and custom-domain readiness can take a moment.
- Random public links can be temporarily paused if Cloudflare rate-limits quick
  tunnel creation.
- At most 3 public apps can be active at the same time.
- Optional link lifetimes can be set up to 40 days, 23 hours, and 59 minutes.
- Password protection protects the public GhostlyShare link, but sensitive or internal
  services should still not be exposed.
- Some system, infrastructure, and low-confidence ports are intentionally hidden.
- Linux app detection can differ from Windows because process and desktop metadata differ.

## Cleanup / Uninstall Notes

On Linux, removing the installed `ghostlyshare` or `ghostlyshare-cli` package does not
guarantee that user settings, logs, cached Cloudflare tunnel files, saved custom-domain
tokens, or other local app data are removed automatically.

GhostlyShare manages its own downloaded `cloudflared` files, cache, settings, logs, and
stored custom-domain token data. It does not remove system-wide `cloudflared`
installations that you installed separately.

## Linux Notes

The Ubuntu/Debian, Arch Linux, and RPM desktop packages install:

- The `ghostlyshare` command.
- A desktop launcher.
- The self-contained application under `/usr/lib/ghostlyshare`.
- Required desktop dependencies such as `xdg-utils`, `libsecret-tools`, and core X11
  libraries.

The Ubuntu/Debian, Arch Linux, and RPM CLI packages install:

- The `ghs` command.
- The self-contained CLI under `/usr/lib/ghostlyshare-cli`.
- CLI-oriented dependencies such as `libsecret-tools` and `ca-certificates`.

GhostlyShare downloads and verifies the matching `cloudflared` binary on first use.
Custom-domain token storage uses the Linux desktop Secret Service through
`secret-tool`.

## License

GhostlyShare is proprietary software by Ghostly Inc. This release repository is not
an open-source source-code repository, and no open-source license is granted for the
application source or binaries unless a separate license agreement says otherwise.
