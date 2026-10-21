# Known Limitations

- GhostlyShare is intended for temporary development sharing, not permanent production hosting.
- The local app, GhostlyShare, and the computer must remain running.
- LAN sharing currently uses a private IPv4 network and does not add password protection.
- LAN sessions are not restored after GhostlyShare restarts.
- Up to three public apps can be active at the same time.
- Cloudflare can temporarily rate-limit new random Quick Tunnels.
- New public hostnames can need a short readiness delay.
- Random public URLs are temporary and can change between sessions.
- Public link lifetime is limited to `40d23h59m`.
- Custom domains require a Cloudflare-managed zone and a suitable API token.
- One public publication is managed per local port. When several distinct endpoints share a port, use the exact URL in the CLI.
- The CLI has no background daemon and no separate `stop` or `list` command.
- Current public packages target x64 Windows and x86_64 Linux.
- There is no public macOS package.
- Linux tray, focus, and window positioning can differ between desktop environments, Wayland, and X11.
- Docker and WSL discovery requires a local endpoint that the host can reach.
- Traffic statistics are approximate session counters, not full analytics or audit logs.
- Password protection is a lightweight gate and does not replace application authentication.
