# GhostlyShare

[![Latest release](https://img.shields.io/github/v/release/Nix1983/GhostlyShare-Releases?sort=semver&label=latest%20release&color=2ea44f)](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest)
[![Downloads](https://img.shields.io/badge/download-Windows%20%7C%20Linux-0078d4)](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest)
[![Microsoft Store](https://img.shields.io/badge/Windows-Microsoft%20Store-0078d4?logo=microsoftstore&logoColor=white)](https://apps.microsoft.com/detail/9PJ6DBC342GR)
[![User guide](https://img.shields.io/badge/docs-user%20guide-2ea44f)](wiki/Home.md)
[![Website](https://img.shields.io/badge/web-GhostlyShare-6f42c1)](https://ghostlyinc.com/en-us/tools/ghostly-share/)
[![License](https://img.shields.io/badge/license-proprietary-6f42c1)](#license)

GhostlyShare finds local web apps and lets you share them in two simple ways:

- **Local network:** open the app from another phone, tablet, or computer on the same trusted network.
- **Public link:** create a temporary Cloudflare-powered URL that works over the internet.

Use the desktop app for the visual workflow or the `ghs` command-line tool for terminals, servers, and scripts. Release packages are self-contained; users do not need to install .NET.

> **Current release:** `1.3.0.0` — see the [release notes](RELEASE-NOTES.md).

## Quick Start

1. [Download the latest release](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest) or install the Windows app from the [Microsoft Store](https://apps.microsoft.com/detail/9PJ6DBC342GR).
2. Start your local website, API, dashboard, or development server.
3. Open GhostlyShare and wait for the app to appear.
4. Choose **Share on local network** or **Go Public**.
5. Copy the link or show its QR code.
6. Keep GhostlyShare and the local app running while the link should work.

See [Getting Started](wiki/Getting-Started.md) for a guided first test.

## Choose the Right Sharing Mode

| | Local network | Public link |
| --- | --- | --- |
| Who can reach it? | Devices on the selected private IPv4 network | Anyone who has the public URL |
| Internet required? | No | Yes |
| Cloudflare required? | No | Yes |
| Password protection | No | Optional |
| Link lifetime | Runs until stopped or interrupted | Optional automatic expiration |
| Best for | Testing on your own phone, tablet, TV, or another local computer | Demos, webhook tests, client reviews, and remote teammates |

LAN and public sharing are independent. Both can be active for the same app.

## Main Features

- Automatically detects local websites, APIs, dashboards, documentation pages, and common development servers.
- Recognizes local apps running directly on Windows or Linux and can identify WSL and Docker workloads.
- Supports standard web ports `80` and `443` as well as common development ports.
- Opens useful start pages such as Swagger UI when GhostlyShare discovers them.
- Shows whether an app comes from Windows, Linux, WSL, or Docker.
- Shares an app on the local network without creating a Cloudflare tunnel.
- Creates random public links without an account, domain, DNS change, or API token.
- Supports temporary custom domains for Cloudflare-managed zones.
- Adds optional password protection and automatic expiration to public links.
- Shows QR codes and simple live traffic counters.
- Explains why a local endpoint was shown, hidden, blocked, skipped, or timed out.
- Lets the desktop app use the operating system's default browser or Firefox, Chrome, or Edge.
- Cleans up managed tunnel and custom-domain resources after normal stops and interrupted sessions.
- Provides CLI table output, JSON output, diagnostics, LAN sharing, public sharing, and readiness checks.

## Downloads

The latest release contains separate desktop and CLI packages:

| Platform | Desktop app | CLI |
| --- | --- | --- |
| Windows | Microsoft Store or `GhostlyShareSetup_win-x64.zip` | `GhostlyShareCLI_win-x64.zip` |
| Ubuntu / Debian | `ghostlyshare-x86_64.deb` | `ghostlyshare-cli-x86_64.deb` |
| Arch Linux | `ghostlyshare-x86_64.pkg.tar.zst` | `ghostlyshare-cli-x86_64.pkg.tar.zst` |
| Fedora / openSUSE / RHEL-compatible | `ghostlyshare-x86_64.rpm` | `ghostlyshare-cli-x86_64.rpm` |

Use the [Installation](wiki/Installation.md) guide for package-specific commands, updates, and verification notes.

## CLI Quick Reference

```bash
ghs --help
ghs version

ghs scan
ghs scan --diagnostics
ghs scan --diagnostics --json

ghs lan 5173
ghs lan http://localhost:3000
ghs lan 5173 --interface Wi-Fi
ghs lan 5173 --url-only

ghs share 5173
ghs share http://localhost:3000
ghs share 5173 --url-only
ghs share 5173 --expires-after 15m
ghs share 5173 --password
ghs share 5173 --custom demo.example.com

ghs cloudflare login
ghs cloudflare status
ghs cloudflare logout

ghs doctor
ghs doctor --json
```

`ghs lan` and `ghs share` keep running while the link is active. Press `Ctrl+C` to stop. The CLI has no background daemon and no separate `stop` or `list` command.

See [Command Line Interface](wiki/Command-Line-Interface.md) for all supported options.

## Security in One Minute

- A LAN link has no built-in password. Use it only on a trusted network.
- A public link is reachable by anyone who obtains the URL.
- Password protection reduces accidental access but is not a security audit or a replacement for the local app's own authentication.
- Do not expose private admin panels, databases, secrets, customer data, or systems you are not authorized to share.
- Never post Cloudflare tokens, passwords, private URLs, or unredacted logs in a public issue.

Read [Security and Privacy](wiki/Security-and-Privacy.md) and [Responsible Use](RESPONSIBLE_USE.md) before sharing sensitive development services.

## User Guide

- [Getting Started](wiki/Getting-Started.md)
- [Installation](wiki/Installation.md)
- [LAN Sharing](wiki/LAN-Sharing.md)
- [Going Public](wiki/Going-Public.md)
- [App Detection and Diagnostics](wiki/App-Detection.md)
- [Command Line Interface](wiki/Command-Line-Interface.md)
- [Custom Domains](wiki/Custom-Domains.md)
- [Password Protection](wiki/Password-Protection.md)
- [Link Lifetime](wiki/Link-Lifetime.md)
- [Traffic Statistics](wiki/Traffic-Statistics.md)
- [Troubleshooting](wiki/Troubleshooting.md)
- [Known Limitations](wiki/Known-Limitations.md)
- [Windows and Linux](wiki/Windows-and-Linux.md)
- [Cleanup and Uninstall](wiki/Cleanup-and-Uninstall.md)

The complete index is in the [GhostlyShare User Guide](wiki/Home.md).

## Bugs and Feature Requests

- [Report a bug](https://github.com/Nix1983/GhostlyShare-Releases/issues/new?template=bug_report.yml)
- [Request a feature](https://github.com/Nix1983/GhostlyShare-Releases/issues/new?template=feature_request.yml)

Please include the GhostlyShare version, operating system, local app details, and the exact error shown. Remove all secrets before posting.

## About This Repository

GhostlyShare is a private, proprietary application. This repository is the public home for releases, downloads, issue reports, release notes, and user documentation. The application source code is private and is not included here.

## License

GhostlyShare is proprietary software by Ghostly Inc. No open-source license is granted for the application source or binaries unless a separate license agreement explicitly says otherwise.
