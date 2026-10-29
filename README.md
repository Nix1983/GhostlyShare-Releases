# GhostlyShare

[![Latest release](https://img.shields.io/github/v/release/Nix1983/GhostlyShare-Releases?sort=semver&label=latest%20release&color=2ea44f)](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest)
[![Downloads](https://img.shields.io/badge/download-Windows%20%7C%20Linux-0078d4)](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest)
[![Microsoft Store](https://img.shields.io/badge/Windows-Microsoft%20Store-0078d4?logo=microsoftstore&logoColor=white)](https://apps.microsoft.com/detail/9PJ6DBC342GR)
[![User guide](https://img.shields.io/badge/docs-user%20guide-2ea44f)](wiki/Home.md)
[![Website](https://img.shields.io/badge/web-GhostlyShare-6f42c1)](https://ghostlyinc.com/en-us/tools/ghostly-share/)

GhostlyShare finds websites, APIs, dashboards, and other browser-based apps running on your computer. It gives you a link for testing on another device or sharing a temporary preview over the internet.

- **Public:** create a temporary internet link for a demo, webhook, client review, or remote teammate.
- **LAN:** open your app on a phone, tablet, TV, or another computer on the same trusted network.

The desktop app is the easiest way to start. The optional `ghs` command-line tool provides the same main workflows for terminals, servers, and scripts. Windows and Linux downloads are self-contained; no separate .NET installation is required.

## Start in Five Steps

1. [Install GhostlyShare](wiki/Installation.md).
2. Start your local website, API, dashboard, or development server and confirm it opens in your browser.
3. Open GhostlyShare and select the detected app.
4. Choose **Public** for an internet link or **LAN** for nearby devices.
5. Copy the link or show its QR code, then stop sharing when you are finished.

Keep the local app, GhostlyShare, and the computer awake while the link is needed. The [Getting Started guide](wiki/Getting-Started.md) walks through a complete first test.

## Choose Public or LAN

| | Public | LAN |
| --- | --- | --- |
| Who can open it? | Anyone who receives the link | Devices that can reach your computer on the selected local network |
| Internet needed? | Yes | No |
| Password and automatic expiry | Optional | Optional |
| Encryption | HTTPS to the public link | Plain HTTP; use only on a trusted network |
| Best for | Demos, webhooks, and remote reviews | Testing on your own devices |

Public and LAN can be active for the same app. Both show a QR code and simple activity counters for the current session.

## Downloads

- **Windows desktop:** use the signed [Microsoft Store version](https://apps.microsoft.com/detail/9PJ6DBC342GR) or the direct setup ZIP from GitHub.
- **Linux desktop:** packages are available for Debian/Ubuntu, Arch Linux, Fedora, openSUSE, RHEL, Rocky Linux, AlmaLinux, and compatible distributions.
- **Command line:** install the separate `ghs` package for Windows or Linux if you prefer a terminal.

[Download the latest release](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest) · [Choose the correct package](wiki/Installation.md#choose-your-download) · [Read the release notes](RELEASE-NOTES.md)

## What You Can Do

- Automatically find many local websites, APIs, dashboards, redirects, and development servers.
- Create a temporary public link without an account, domain, or API token.
- Test an app from another device without changing the app's listening address.
- Add a password and automatic expiry to public or LAN shares.
- See a QR code, connection status, and simple live activity counters.
- Use your own Cloudflare-managed hostname when a random URL is not suitable.
- Diagnose why a local app or link is unavailable without exposing page contents in the report.

GhostlyShare does not publish an app merely because it was detected. A share starts only when you choose to start it.

## Command Line

```bash
ghs scan
ghs share 5173
ghs lan 5173
```

`ghs share` and `ghs lan` stay active until you press `Ctrl+C` or the configured expiry is reached. See the [CLI guide](wiki/Command-Line-Interface.md) for useful examples.

## Share Safely

- Anyone who receives a public URL may try to open it. Add a password when appropriate.
- Use LAN sharing only on a trusted network. Its optional password is an access gate, but LAN traffic remains unencrypted.
- Do not expose private admin panels, databases, secrets, customer data, or services you are not authorized to share.
- Stop sharing as soon as the test or review is finished.

Read [Security and Privacy](wiki/Security-and-Privacy.md) before sharing a sensitive development service.

## Help

- [Getting Started](wiki/Getting-Started.md)
- [Installation and Updates](wiki/Installation.md)
- [Public Sharing](wiki/Going-Public.md)
- [LAN Sharing](wiki/LAN-Sharing.md)
- [Command Line](wiki/Command-Line-Interface.md)
- [Troubleshooting](wiki/Troubleshooting.md)
- [Complete User Guide](wiki/Home.md)

## Feedback

- [Report a bug](https://github.com/Nix1983/GhostlyShare-Releases/issues/new?template=bug_report.yml)
- [Request a feature](https://github.com/Nix1983/GhostlyShare-Releases/issues/new?template=feature_request.yml)

Before posting, remove passwords, API tokens, private URLs, customer data, and other secrets.

## About This Repository

This repository contains public releases, downloads, issue forms, release notes, and user documentation. The GhostlyShare application source code is private and is not included here.

GhostlyShare is proprietary software by Ghostly Inc. No open-source license is granted for the application source or binaries unless a separate license agreement explicitly says otherwise.
