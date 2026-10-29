# Windows and Linux

GhostlyShare provides a desktop app and the optional `ghs` CLI for x64 Windows and x86_64 Linux.

## Available on Both Platforms

- Automatic local app discovery and diagnostics.
- Random public links and Cloudflare custom domains.
- Public password protection and expiry.
- LAN sharing with optional password and expiry.
- QR codes and simple Public/LAN activity counters.
- Windows-default, Firefox, Chrome, and Edge browser choices where installed.
- Docker discovery when the container exposes a host-accessible local endpoint.

Windows can also discover supported WSL web apps. WSL is not applicable on a Linux host.

## Packages

Windows:

- Microsoft Store desktop app.
- Direct desktop setup ZIP.
- Portable CLI ZIP.

Linux:

- Debian/Ubuntu desktop and CLI `.deb` packages.
- Arch desktop and CLI `.pkg.tar.zst` packages.
- RPM desktop and CLI packages for Fedora, openSUSE, RHEL, Rocky Linux, AlmaLinux, and compatible systems.

Desktop and CLI packages can be installed together. They are self-contained and do not require a separate .NET runtime.

## Linux Desktop Behavior

Linux desktops do not all provide the same tray support:

- GNOME without an AppIndicator extension normally has no GhostlyShare tray icon. Restore the existing window from the dock, Overview, or application launcher.
- KDE Plasma, XFCE, MATE, and similar desktops can show a tray icon when their panel supports it.
- Wayland and X11 can differ in focus and window placement.

Missing tray support does not prevent GhostlyShare from starting or sharing. Opening GhostlyShare from the launcher again should reactivate the existing instance.

## Secure Token Storage

The Cloudflare token for custom domains uses secure credential storage provided by the operating system. Remove it through GhostlyShare settings or `ghs cloudflare logout` when it is no longer needed.

## Settings and Support Data

Typical locations:

- Windows: `%LOCALAPPDATA%\GhostlyShare`
- Linux: `${XDG_STATE_HOME:-$HOME/.local/state}/GhostlyShare`

Use **Settings → Settings folder** to open the exact location used on the current device.
