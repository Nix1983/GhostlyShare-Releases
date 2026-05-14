# GhostlyShare Releases

[![Ubuntu .deb](https://img.shields.io/github/v/release/Nix1983/GhostlyShare-Releases?label=Ubuntu%20%2F%20Debian%20.deb&logo=ubuntu&logoColor=white&color=e95420)](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest)
[![Windows Store](https://img.shields.io/badge/Windows-Microsoft%20Store-0078d4?logo=microsoftstore&logoColor=white)](https://apps.microsoft.com/detail/9PJ6DBC342GR)
[![License](https://img.shields.io/badge/license-proprietary-6f42c1)](#license)

Public Linux downloads for GhostlyShare, a desktop app for sharing local
development services through public links.

GhostlyShare helps you expose a local development app through a public
Cloudflare-powered URL without deploying the app first.

## Get GhostlyShare

| Platform | Download |
|:--|:--|
| Ubuntu / Debian Linux | [Download the latest `.deb` package](https://github.com/Nix1983/GhostlyShare-Releases/releases/latest) |
| Windows | [Install from Microsoft Store](https://apps.microsoft.com/detail/9PJ6DBC342GR) |

Windows MSIX release assets are published privately from the source repository.
Linux builds are published here as public release artifacts.

## Ubuntu / Debian Installation

Download and install the latest `GhostlyShare-linux-x64.deb` package:

```bash
wget -O /tmp/GhostlyShare-linux-x64.deb https://github.com/Nix1983/GhostlyShare-Releases/releases/latest/download/GhostlyShare-linux-x64.deb
```

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
```

```bash
sudo apt install /tmp/GhostlyShare-linux-x64.deb
```

## Uninstall

```bash
sudo apt remove ghostlyshare
```

## Linux Notes

The package installs a desktop launcher, the `ghostlyshare` command, and the
bundled self-contained .NET application under `/usr/lib/ghostlyshare`.

GhostlyShare downloads and verifies the matching `cloudflared` binary on first
use. Custom-domain token storage uses the desktop Secret Service through
`secret-tool`.

## About This Repository

This repository intentionally contains only public release notes and downloadable
Linux release artifacts. The application source code lives in a private
repository.

## License

GhostlyShare is proprietary software by Ghostly Inc. This release repository is
not an open-source source-code repository, and no open-source license is granted
for the application source or binaries unless a separate license agreement says
otherwise.
