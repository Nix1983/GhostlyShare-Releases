# GhostlyShare

[![Latest release](https://img.shields.io/github/v/release/Nix1983/GhostlyShare-Releases?sort=semver&label=latest%20release&color=2ea44f)](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest)
[![Downloads](https://img.shields.io/badge/download-Windows%20%7C%20Linux-0078d4)](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest)
[![Microsoft Store](https://img.shields.io/badge/Windows-Microsoft%20Store-0078d4?logo=microsoftstore&logoColor=white)](https://apps.microsoft.com/detail/9PJ6DBC342GR)
[![User guide](https://img.shields.io/badge/docs-user%20guide-2ea44f)](wiki/Home.md)
[![Website](https://img.shields.io/badge/web-GhostlyShare-6f42c1)](https://ghostlyinc.com/en-us/tools/ghostly-share/)

GhostlyShare finds web apps running on your computer and gives you a link you can open on another device or share over the internet.

- **LAN:** test your app on a phone, tablet, TV, or another computer on the same trusted network.
- **Public:** create a temporary internet link for a demo, webhook, client review, or remote teammate.

The desktop app provides the easiest visual workflow. The optional `ghs` command-line tool is available for terminals, servers, and scripts. Everything required to run GhostlyShare is included in the download.

## Get Started

1. [Download the latest release](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest) or install GhostlyShare from the [Microsoft Store](https://apps.microsoft.com/detail/9PJ6DBC342GR).
2. Start your local website, API, dashboard, or development server.
3. Open GhostlyShare and wait for the app to appear.
4. Select **LAN** to share on your network or **Public** to create an internet link.
5. Copy the link or show its QR code.

Keep GhostlyShare and your local app running while the link is in use. Follow the [Getting Started guide](wiki/Getting-Started.md) for a complete first test.

## LAN or Public?

| | LAN | Public |
| --- | --- | --- |
| Who can open it? | Devices on the same trusted network | Anyone who has the link |
| Internet needed? | No | Yes |
| Password option | No | Yes |
| Best for | Testing on your own devices | Demos, webhooks, and remote reviews |

LAN and Public can both be active for the same app.

## Downloads

| Platform | Desktop app | CLI |
| --- | --- | --- |
| Windows | Microsoft Store or `GhostlyShareSetup_win-x64.zip` | `GhostlyShareCLI_win-x64.zip` |
| Ubuntu / Debian | `ghostlyshare-x86_64.deb` | `ghostlyshare-cli-x86_64.deb` |
| Arch Linux | `ghostlyshare-x86_64.pkg.tar.zst` | `ghostlyshare-cli-x86_64.pkg.tar.zst` |
| Fedora / openSUSE / RHEL-compatible | `ghostlyshare-x86_64.rpm` | `ghostlyshare-cli-x86_64.rpm` |

See [Installation](wiki/Installation.md) for install and update instructions. See [Release Notes](RELEASE-NOTES.md) for what changed.

## What GhostlyShare Includes

- Automatic detection of local websites, APIs, dashboards, and development servers.
- LAN links that work without Cloudflare or an internet connection.
- Temporary public links without an account, domain, or API token.
- Optional passwords and automatic expiration for public links.
- QR codes, simple live traffic counters, and clear connection status.
- Windows and Linux desktop apps plus a separate CLI.

Custom domains are also supported when your domain is managed by Cloudflare. See [Custom Domains](wiki/Custom-Domains.md).

## Command Line

```bash
ghs scan
ghs lan 5173
ghs share 5173
```

`ghs lan` and `ghs share` stay active until you press `Ctrl+C`. See the [CLI guide](wiki/Command-Line-Interface.md) for all commands and options.

## Share Safely

- Use LAN sharing only on a trusted network.
- Anyone who receives a public URL may try to open it.
- Do not expose private admin panels, databases, secrets, customer data, or services you are not authorized to share.
- Stop sharing when your test or demo is finished.

Read [Security and Privacy](wiki/Security-and-Privacy.md) before sharing sensitive development services.

## Help

- [Getting Started](wiki/Getting-Started.md)
- [Installation](wiki/Installation.md)
- [LAN Sharing](wiki/LAN-Sharing.md)
- [Public Sharing](wiki/Going-Public.md)
- [Troubleshooting](wiki/Troubleshooting.md)
- [Complete User Guide](wiki/Home.md)

## Feedback

- [Report a bug](https://github.com/Nix1983/GhostlyShare-Releases/issues/new?template=bug_report.yml)
- [Request a feature](https://github.com/Nix1983/GhostlyShare-Releases/issues/new?template=feature_request.yml)

Before posting, remove passwords, API tokens, private URLs, customer data, and other secrets.

## About This Repository

This repository contains public releases, downloads, issue forms, release notes, and user documentation. The GhostlyShare application source code is private and is not included here.

GhostlyShare is proprietary software by Ghostly Inc. No open-source license is granted for the application source or binaries unless a separate license agreement explicitly says otherwise.
