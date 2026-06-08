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

GhostlyShare makes local development apps public for a short time.

Use the desktop app for an interactive workflow, or use the `ghs` command-line tool for terminal, server, and script workflows. Both create temporary Cloudflare-powered public URLs for local apps.

GhostlyShare is a private, proprietary application. This repository is only the public release, download, issue, support, and user documentation home for GhostlyShare. The application source code is private and is not included here.

## Quick Start

1. Download and install GhostlyShare.
2. Start your local app.
3. Open GhostlyShare.
4. Select the app and click `Go Public`.
5. Copy the link or scan the QR code.
6. Keep GhostlyShare and the local app running while the public link should work.

## Features

- Auto-detect local web apps, APIs, dashboards, docs, and common development servers.
- Create random public links without an account, domain, DNS setup, or API token.
- Use your own Cloudflare-managed custom domain with your own API token.
- Add optional password protection before sharing or while a link is live.
- Set an optional public-link lifetime so temporary links can go offline automatically.
- Copy links, open links, scan QR codes, and view simple live traffic statistics.
- Use `ghs` from a terminal for scan, share, Cloudflare, doctor, and JSON workflows.

## Downloads, Installation, Update and Uninstall

Use the [Installation wiki page](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Installation) to choose, verify, install, and update the right package for your system.

The installation guide covers:

- Windows Microsoft Store, desktop setup ZIP, and CLI ZIP.
- Ubuntu, Debian, Kali, Linux Mint, Pop!_OS, and other `.deb` based systems.
- Arch Linux `.pkg.tar.zst` packages.
- Fedora, openSUSE, RHEL, Rocky Linux, AlmaLinux, and other RPM based systems.
- RPM signing key import, RPM signature checks, and SHA256 checksum verification.

For uninstall commands and cleanup notes, see [Cleanup and Uninstall](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Cleanup-and-Uninstall).

## Command Line Interface

The `ghs` CLI is a power-user, server, and script tool. It is not a background daemon and does not replace the desktop app.

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

`ghs share` keeps running while the public link is active. Press `Ctrl+C` to stop sharing. If you use a custom domain, GhostlyShare creates a temporary Cloudflare DNS record while sharing and removes it again when the command stops.

The CLI has no background daemon and no separate `ghs stop` or `ghs list` command. The running `ghs share` process is the sharing session.

See the [Command Line Interface wiki page](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Command-Line-Interface) for full CLI documentation.

## Important Usage and Security Notes

GhostlyShare is intended for lawful development, testing, demos, temporary reviews, and quick sharing of local apps from your own device.

Public links expose the selected local app to the internet. Only share apps you own, trust, and are allowed to make public. Optional password protection protects the GhostlyShare public link, but sensitive or internal services should still not be exposed.

Do not use GhostlyShare for illegal content, malware, phishing, spam, copyright infringement, privacy violations, unauthorized access, or any other harmful or abusive activity.

Never post Cloudflare tokens, passwords, private URLs, full logs with secrets, or other sensitive information in public issues.

See [Responsible Use](RESPONSIBLE_USE.md) and [Security and Privacy](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Security-and-Privacy) for details.

## Documentation

The full user guide is available in the [GhostlyShare Wiki](https://github.com/Nix1983/GhostlyShare-Releases/wiki).

Good starting points:

- [Installation](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Installation)
- [Getting Started](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Getting-Started)
- [Command Line Interface](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Command-Line-Interface)
- [Security and Privacy](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Security-and-Privacy)
- [Going Public and Link Readiness](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Going-Public)
- [Password Protection](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Password-Protection)
- [Link Lifetime](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Link-Lifetime)
- [Traffic Statistics](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Traffic-Statistics)
- [Custom Domains](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Custom-Domains)
- [Troubleshooting](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Troubleshooting)

## Bugs and Feature Requests

Use GitHub Issues to report bugs or request user-facing improvements:

- [Report a bug](https://github.com/Nix1983/GhostlyShare-Releases/issues/new?template=bug_report.yml)
- [Request a feature](https://github.com/Nix1983/GhostlyShare-Releases/issues/new?template=feature_request.yml)

Please do not post Cloudflare API tokens, passwords, private URLs, or other secrets in public issues.

## Known Limitations

- The selected local app must keep running while the public link should work.
- Your computer must stay online.
- Sleep, network changes, VPN changes, or interrupted connectivity can make an existing public link unreachable.
- Cloudflare Quick Tunnel and custom-domain readiness can take a moment.
- Random public links can be temporarily paused if Cloudflare rate-limits quick tunnel creation.
- At most 3 public apps can be active at the same time.
- Optional link lifetimes can be set up to 40 days, 23 hours, and 59 minutes.
- Linux desktop behavior can differ between GNOME, KDE Plasma, XFCE, Wayland, and X11.

See [Known Limitations](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Known-Limitations), [Windows and Linux Differences](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Windows-and-Linux), and [Troubleshooting](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Troubleshooting) for details.

## License

GhostlyShare is proprietary software by Ghostly Inc. This release repository is not an open-source source-code repository, and no open-source license is granted for the application source or binaries unless a separate license agreement says otherwise.
