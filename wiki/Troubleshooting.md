# Troubleshooting

Start with these checks:

1. Confirm that the local app still opens directly in a browser on the GhostlyShare computer.
2. Keep the local app, GhostlyShare, and the computer running and awake.
3. Check the selected LAN/Public mode and the status shown on the app card.
4. Open **Settings → Discovery diagnostics → Open** when the app itself is missing.

## A Local App Is Missing

- Wait for the next desktop refresh.
- Make sure the app is reachable from the host computer, not only inside a container or VM.
- Review **Settings → Port Discovery → Manage** for a **Never Show** rule.
- Check for local HTTPS certificate errors or redirect loops.
- Run this from the CLI:

```bash
ghs scan --diagnostics
```

Ports 80 and 443 are supported. Docker and WSL apps still need a host-accessible local endpoint.

## Desktop and CLI Show Different Results

The desktop refreshes repeatedly, while `ghs scan` captures one moment. Wait for the desktop refresh and run the CLI command again after the local app has fully started.

Also confirm that both installations report the same current version and run as the same user:

```bash
ghs version
```

If two distinct servers genuinely share a port through different local addresses, both can be valid entries.

## The Wrong Page or App Opens

GhostlyShare can keep a useful discovered route such as Swagger UI. Restart the local app and refresh GhostlyShare after changing routes or redirect behavior.

Use an exact URL in the CLI when several distinct endpoints share a port:

```bash
ghs share http://localhost:5173
```

## A LAN Link Does Not Open

- Put both devices on the same private network and subnet.
- Avoid guest Wi-Fi or enable communication between wireless clients.
- Allow GhostlyShare through the private-network firewall.
- Disconnect or reconfigure a VPN that changes local routing.
- Confirm the displayed address belongs to the intended adapter.
- Select an adapter explicitly when needed:

```bash
ghs lan 5173 --interface Wi-Fi
```

If GhostlyShare shows **Limited** inside a virtual machine, NAT is a likely cause. Switch the VM adapter to bridged networking when devices on the physical LAN need to reach it.

A network change can stop the LAN session. Start it again after reconnecting.

## A Public Link Is Pending or Offline

- Confirm that the computer has internet access.
- Wait briefly for a new hostname to become ready.
- Check VPN, proxy, DNS filtering, and security software.
- Make sure fewer than three random public links are active.
- Run:

```bash
ghs doctor
```

Cloudflare can temporarily limit new random links. Existing links can continue while a new one needs to wait.

GhostlyShare downloads and uses its own supported public-sharing helper. A separately installed `cloudflared` is not required. If a helper update cannot be verified while offline, connect to the internet and try again.

## A Link Stopped During Sleep

LAN and public links cannot be reached while the computer is sleeping, suspended, shut down, or disconnected from the required network.

After waking:

1. Wait for the network to reconnect.
2. Open GhostlyShare and check the current state.
3. Confirm the local app still opens directly.
4. Start or test the share again rather than assuming it recovered.

## A Custom Domain Fails

- Run `ghs cloudflare status`.
- Verify zone-read and DNS-edit permissions.
- Confirm the token can access the correct account and zone.
- Check for an unrelated DNS record already using the hostname.
- Fully quit and restart GhostlyShare so it can retry safe cleanup of its own interrupted resources.

## A Link Opens in the Wrong Browser

Open **Settings → Browser** and choose **Default**, Firefox, Chrome, or Edge.

**Default** uses the browser configured by the operating system. GhostlyShare does not change the system default.

## Linux Window or Tray Behavior

Tray support depends on the desktop environment.

- **GNOME without an AppIndicator extension:** a small tray icon may not appear. Minimize GhostlyShare and restore the existing window from the dock, Overview, or application launcher.
- **KDE Plasma, XFCE, MATE, and other desktops:** a tray icon can appear when the panel provides compatible tray support.
- Starting GhostlyShare again from the launcher should reactivate the existing instance rather than leave a second permanent instance.

If the window appears briefly and disappears, start GhostlyShare again from the application launcher. If it still does not return, run `ghostlyshare` from a terminal and include the visible error in a bug report.

## GhostlyShare Does Not Start

1. Fully quit any old GhostlyShare instance if the desktop still shows one.
2. Start it again from the normal application launcher.
3. On Linux, run `ghostlyshare` in a terminal to see an immediate error.
4. Confirm that the installed desktop package matches your distribution and x86_64 architecture.
5. Reinstall the latest package over the existing installation; removing settings first is normally unnecessary.

## Reporting a Bug

Include:

- GhostlyShare version.
- Operating system and, on Linux, desktop environment and Wayland/X11.
- Desktop app or CLI.
- The local URL and framework.
- The safe discovery diagnostic reason.
- Exact error text and minimal reproduction steps.

Remove API tokens, passwords, private URLs, customer data, and other secrets before posting.
