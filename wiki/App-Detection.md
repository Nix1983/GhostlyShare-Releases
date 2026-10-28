# App Detection and Diagnostics

GhostlyShare looks for local HTTP and HTTPS apps that can be opened in a browser and shared without asking you to configure every port manually.

It commonly finds development websites, APIs, Swagger pages, dashboards, static sites, redirects, and apps running through WSL or Docker. Detection is helpful, but it is not a promise that every open port or every network service will be shown.

## What You Can Expect

- GhostlyShare scans the current computer, not other computers on your LAN.
- Standard web ports such as 80 and 443 are supported.
- IPv4 and IPv6 addresses for the same app are normally combined.
- Genuinely different endpoints can appear separately even when they use the same port.
- A useful page such as Swagger UI can be kept as the start address instead of always opening `/`.
- Docker and WSL apps need a local address that the host computer can reach.

The desktop app refreshes over time. `ghs scan` is a single snapshot, so a short-lived app or an app that started during a refresh can appear at a different moment. Both use the same user-facing detection rules.

## Choose an Exact Address

When a port has more than one distinct endpoint, CLI users can select the intended one with its full local URL:

```bash
ghs share http://localhost:5173
ghs share http://[::1]:5173
```

Always verify the local page before sharing it.

## Port Discovery Preferences

Open **Settings → Port Discovery → Manage** to add a preference:

- **Always Detect** asks GhostlyShare to include a web app on one exact port when possible.
- **Never Show** hides a port or port range from the app list.
- Ports without a custom rule remain automatic.

You can also open **Manage port rules** from an app card. A rule applies to every app using that port. These preferences influence what is shown; they do not turn an unsafe or unreachable service into a shareable app.

## Understand a Missing App

Open:

**Settings → Discovery diagnostics → Open**

The diagnostics window shows a short result for endpoints GhostlyShare checked, such as detected, hidden, blocked for safety, temporarily skipped, timed out, or unreachable.

Diagnostics are designed for troubleshooting and do not retain page bodies, response headers, full URLs, or detailed process information.

CLI users can run:

```bash
ghs scan --diagnostics
ghs scan --diagnostics --json
```

## What to Try

1. Confirm the exact local URL still opens in a browser.
2. Wait for the next desktop refresh or run `ghs scan` again.
3. Read the short diagnostic reason.
4. Check whether a container or VM exposes the app to the host.
5. Check local HTTPS certificate errors and redirect loops.
6. Review custom Port Discovery rules.
7. Restart the local app after changing its listening address.

Include only the safe diagnostic reason and minimal reproduction steps in a bug report. See [Troubleshooting](Troubleshooting.md) for more help.
