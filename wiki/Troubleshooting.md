# Troubleshooting

Start with these three checks:

1. Make sure the local app still opens directly in your browser.
2. Keep GhostlyShare and the local app running.
3. Open **Settings → Discovery diagnostics → Open** for a clear reason when an app is missing.

## A Local App Is Missing

1. Open the local URL in a browser.
2. Confirm the app is listening on the host, not only inside a container or virtual machine.
3. Wait for the next GhostlyShare refresh.
4. Open **Settings → Discovery diagnostics**.
5. CLI users can run:

```bash
ghs scan --diagnostics
```

Look for a reason such as not a web app, not enough information to identify it, blocked for safety, timed out, or unavailable.

Ports `80` and `443` are supported. Docker and WSL apps still need a host-accessible local endpoint.

## The Wrong Page Opens

GhostlyShare keeps useful discovered routes, such as Swagger UI. Restart the local app and refresh GhostlyShare when the app changed its routes or redirect behavior.

In the CLI, use an exact local URL when several distinct endpoints share a port:

```bash
ghs share http://localhost:5173
```

## A LAN Link Does Not Open

- Put both devices on the same private network and subnet.
- Avoid guest Wi-Fi or enable communication between wireless clients.
- Allow GhostlyShare through the private-network firewall.
- Disconnect or reconfigure a VPN that changes local routing.
- Confirm the displayed LAN address belongs to the intended adapter.
- With the CLI, choose an adapter explicitly:

```bash
ghs lan 5173 --interface Wi-Fi
```

A network change automatically stops the LAN session.

## A Public Link Is Pending or Offline

- Keep the local app and GhostlyShare running.
- Confirm the computer has internet access.
- Wait briefly for a new hostname and tunnel to become ready.
- Check VPN, proxy, DNS-filtering, and security software.
- Run:

```bash
ghs doctor
```

- Make sure fewer than three public apps are active.
- A Cloudflare Quick Tunnel cooldown may temporarily block new random links.

A link can work from another device while the originating computer's local readiness check is affected by its own DNS or VPN settings.

## A Custom Domain Fails

- Run `ghs cloudflare status`.
- Verify zone-read and DNS-edit permissions.
- Confirm the token can access the correct account and zone.
- Check for a conflicting DNS record.
- Stop old sessions and restart GhostlyShare so recorded cleanup can run.

## A Link Opens in the Wrong Browser

Open **Settings → Browser** and choose **Default**, Firefox, Chrome, or Edge.

**Default** uses the browser configured by the operating system. GhostlyShare does not change the system default.

## Linux Tray or Window Problems

Linux desktop behavior can vary between GNOME, KDE Plasma, XFCE, Wayland, and X11.

Start GhostlyShare from a terminal to see immediate launch errors. Make sure the desktop package matches the distribution and that a system tray implementation is available.

## Current Limits

- GhostlyShare is designed for temporary development sharing, not permanent hosting.
- The local app, GhostlyShare, and the computer must remain running.
- LAN links do not have GhostlyShare password protection.
- Up to three apps can be public at the same time.
- There is currently no macOS package.

See [Known Limitations](Known-Limitations.md) for the complete list.

## Reporting a Bug

Include:

- GhostlyShare version.
- Operating system and desktop environment.
- Desktop app or CLI.
- Local URL and framework.
- Safe discovery diagnostic reason.
- Exact error text.
- Minimal reproduction steps.

Remove API tokens, passwords, private URLs, customer data, and other secrets before posting.
