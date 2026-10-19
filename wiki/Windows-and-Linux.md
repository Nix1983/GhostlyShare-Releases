# Windows and Linux

GhostlyShare provides the desktop app and `ghs` CLI for Windows and x86_64 Linux.

## Feature Availability

| Feature | Windows | Linux |
| --- | --- | --- |
| Desktop app | Yes | Yes |
| `ghs` CLI | Yes | Yes |
| LAN sharing | Yes | Yes |
| Random public links | Yes | Yes |
| Custom Cloudflare domains | Yes | Yes |
| Password and lifetime settings | Yes | Yes |
| Discovery diagnostics | Yes | Yes |
| Docker workload detection | Yes | Yes, when host-accessible |
| WSL workload detection | Yes | Not applicable |
| System-default browser option | Yes | Yes |

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

## Secure Token Storage

Custom-domain API tokens use platform secure credential storage. Use GhostlyShare settings or `ghs cloudflare logout` to remove the saved token.

## Desktop Differences

Windows provides the most consistent tray and window behavior.

On Linux, tray placement, focus, startup integration, and window positioning can differ between GNOME, KDE Plasma, XFCE, Wayland, X11, and distribution packaging choices. These differences do not change the core LAN and public sharing workflow.

## Local Data

Typical app-state locations:

- Windows: `%LOCALAPPDATA%\GhostlyShare`
- Linux: `${XDG_STATE_HOME:-$HOME/.local/state}/GhostlyShare`

Use **Settings → Settings folder** to open the exact folder used on the current device.
