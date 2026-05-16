# GhostlyShare

[![Ubuntu .deb](https://img.shields.io/github/v/release/Nix1983/GhostlyShare-Releases?label=Ubuntu%20%2F%20Debian%20.deb&logo=ubuntu&logoColor=white&color=e95420)](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest)
[![Windows Store](https://img.shields.io/badge/Windows-Microsoft%20Store-0078d4?logo=microsoftstore&logoColor=white)](https://apps.microsoft.com/detail/9PJ6DBC342GR)
[![User Wiki](https://img.shields.io/badge/docs-user%20wiki-2ea44f)](https://github.com/Nix1983/GhostlyShare-Releases/wiki)
[![License](https://img.shields.io/badge/license-proprietary-6f42c1)](#license)

GhostlyShare is a desktop app for making local development apps public for a short time.
Start a local web app, open GhostlyShare, choose the app, and share it through a public
Cloudflare-powered URL.

GhostlyShare is a private, proprietary application. This repository is only the public
release, download, issue, support, and user documentation home for GhostlyShare. The
application source code is private and is not included here.

## Feature Overview

- Auto-detect local web apps and APIs.
- Create random public links without an account, domain, or DNS setup.
- Use your own custom domain with your Cloudflare domain and API token.
- Enable optional password protection per public link before sharing.
- Copy or open public links from the app when you are ready to share.
- See link readiness and offline states while your local app or tunnel changes.

## Download

| Platform | Download |
|:--|:--|
| Ubuntu / Debian Linux | [Download the latest `.deb` package](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest) |
| Windows | [Install from Microsoft Store](https://apps.microsoft.com/detail/9PJ6DBC342GR) |

## Public Link Options

- Random public links work without a GhostlyShare account, custom domain, or Cloudflare setup.
- Custom domains require your own Cloudflare-managed domain and your own Cloudflare API token.
- Optional password protection can be enabled before a selected app goes public.
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
sha256sum /tmp/GhostlyShare-linux-x64.deb
```

Windows example:

```powershell
Get-FileHash .\downloaded-file -Algorithm SHA256
```

## Documentation

The full user guide is available in the [GhostlyShare Wiki](https://github.com/Nix1983/GhostlyShare-Releases/wiki).

Good starting points:

- [Getting Started](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Getting-Started)
- [Security and Privacy](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Security-and-Privacy)
- [How App Detection Works](https://github.com/Nix1983/GhostlyShare-Releases/wiki/App-Detection)
- [Why Apps Are Merged](https://github.com/Nix1983/GhostlyShare-Releases/wiki/App-Merging)
- [Going Public and Link Readiness](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Going-Public)
- [Password Protection](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Password-Protection)
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

## Ubuntu / Debian Install

Download the latest package:

```bash
wget -O /tmp/GhostlyShare-linux-x64.deb https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/GhostlyShare-linux-x64.deb
```

Install it with dependencies:

```bash
sudo apt install /tmp/GhostlyShare-linux-x64.deb
```

Start GhostlyShare from your application launcher, or run:

```bash
ghostlyshare
```

## Update

Download the newest `.deb` package from the latest release and install it over
the existing version:

```bash
wget -O /tmp/GhostlyShare-linux-x64.deb https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/GhostlyShare-linux-x64.deb
sudo apt install /tmp/GhostlyShare-linux-x64.deb
```

## Uninstall

```bash
sudo apt remove ghostlyshare
```

Uninstalling the package removes the installed Linux app, but local user data may remain
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

## Known Limitations

- The selected local app must keep running while the public link should work.
- Your computer must stay online.
- VPNs, firewalls, proxies, DNS, and corporate networks can affect public links.
- Cloudflare Quick Tunnel and custom-domain readiness can take a moment.
- Password protection protects the public GhostlyShare link, but sensitive or internal
  services should still not be exposed.
- Some system, infrastructure, and low-confidence ports are intentionally hidden.
- Linux app detection can differ from Windows because process and desktop metadata differ.

## Cleanup / Uninstall Notes

On Linux, `sudo apt remove ghostlyshare` removes the installed app package. It does not
guarantee that user settings, logs, cached Cloudflare tunnel files, saved custom-domain
tokens, or other local app data are removed automatically.

GhostlyShare manages its own downloaded `cloudflared` files, cache, settings, logs, and
stored custom-domain token data. It does not remove system-wide `cloudflared`
installations that you installed separately.

## Linux Notes

The Ubuntu/Debian package installs:

- The `ghostlyshare` command.
- A desktop launcher.
- The self-contained application under `/usr/lib/ghostlyshare`.
- Required desktop dependencies such as `xdg-utils`, `libsecret-tools`, and core X11
  libraries.

GhostlyShare downloads and verifies the matching `cloudflared` binary on first use.
Custom-domain token storage uses the Linux desktop Secret Service through
`secret-tool`.

## License

GhostlyShare is proprietary software by Ghostly Inc. This release repository is not
an open-source source-code repository, and no open-source license is granted for the
application source or binaries unless a separate license agreement says otherwise.
