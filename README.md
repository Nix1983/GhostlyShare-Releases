# GhostlyShare

[![Ubuntu .deb](https://img.shields.io/github/v/release/Nix1983/GhostlyShare-Releases?label=Ubuntu%20%2F%20Debian%20.deb&logo=ubuntu&logoColor=white&color=e95420)](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest)
[![Windows Store](https://img.shields.io/badge/Windows-Microsoft%20Store-0078d4?logo=microsoftstore&logoColor=white)](https://apps.microsoft.com/detail/9PJ6DBC342GR)
[![User Wiki](https://img.shields.io/badge/docs-user%20wiki-2ea44f)](https://github.com/Nix1983/GhostlyShare-Releases/wiki)
[![License](https://img.shields.io/badge/license-proprietary-6f42c1)](#license)

GhostlyShare is a desktop app for making local development apps public for a short time.
Start a local web app, open GhostlyShare, choose the app, and share it through a public
Cloudflare-powered URL.

This repository is the public release home for GhostlyShare. It contains Linux release
downloads, release notes, and user documentation. The application source code is private.

## Download

| Platform | Download |
|:--|:--|
| Ubuntu / Debian Linux | [Download the latest `.deb` package](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest) |
| Windows | [Install from Microsoft Store](https://apps.microsoft.com/detail/9PJ6DBC342GR) |

## Documentation

The full user guide is available in the [GhostlyShare Wiki](https://github.com/Nix1983/GhostlyShare-Releases/wiki).

Good starting points:

- [Getting Started](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Getting-Started)
- [How App Detection Works](https://github.com/Nix1983/GhostlyShare-Releases/wiki/App-Detection)
- [Why Apps Are Merged](https://github.com/Nix1983/GhostlyShare-Releases/wiki/App-Merging)
- [Going Public and Link Readiness](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Going-Public)
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
