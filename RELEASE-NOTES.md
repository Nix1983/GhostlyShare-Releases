# Release Notes

## 1.3.1.0 — October 21, 2026

### Refreshed design

- Added the new GhostlyShare icon across the desktop app, taskbar, tray, and Linux packages.
- Simplified the app cards and made the **Public** and **LAN** sections easier to distinguish.
- Improved status placement, active markers, empty states, and first-start feedback.
- Redesigned the About page and added easier access to documentation, feedback, ratings, and project support.

### More reliable app detection

- Improved detection when the same protected app is available through both IPv4 and IPv6.
- Prevented duplicate entries for these endpoints while keeping genuinely different apps separate.
- Made one-time CLI scans more reliable on busy computers.
- An incomplete CLI scan now reports a clear error instead of returning a partial app list as a successful result.

## 1.3.0.0 — October 19, 2026

### Local network sharing

- Share a detected app with phones, tablets, and other computers on the same private IPv4 network.
- LAN sharing does not require Cloudflare and can run at the same time as a public link.
- The desktop app shows a LAN URL and QR code.
- The CLI adds `ghs lan <port|url>` with `--interface`, `--json`, and `--url-only`.
- LAN sharing stops automatically when the local app changes or closes, the selected network changes, or GhostlyShare exits.

### Better app detection

- Added discovery diagnostics in the desktop settings and through `ghs scan --diagnostics`.
- Diagnostics explain whether endpoints were detected, hidden, blocked, skipped, timed out, or failed.
- Added verified discovery for local Docker and WSL workloads.
- Added support for standard web ports `80` and `443`.
- Improved IPv4/IPv6 handling, redirect handling, duplicate detection, and stale app cleanup.
- GhostlyShare now opens the useful discovered start route, such as Swagger UI, instead of always opening `/`.
- App cards can show whether a service runs on Windows, Linux, WSL, or Docker.

### Desktop improvements

- Added a browser preference for the operating system default browser, Firefox, Chrome, or Edge.
- Improved status feedback while discovery or LAN sharing is still being prepared.
- Refined LAN sharing controls and QR-code presentation.

### Reliability and safety

- Public and LAN shares remain bound to the verified local app identity, reducing the risk of forwarding a reused port to a different process.
- Managed tunnel and custom-domain state is recorded so interrupted sessions can be cleaned up safely.
- Improved cleanup of stale Cloudflare connections, tunnels, and temporary DNS records.
- Improved recovery when local apps, networks, or tunnel processes change unexpectedly.

### Packaging

- Desktop and CLI packages now use .NET 10 internally.
- Release packages remain self-contained. End users do not need to install a separate .NET runtime.

## 1.2.9.3 — September 30, 2026

- Improved detection of local websites that redirect to a page with substantial inline CSS before the HTML title.
- These sites could previously be missing from the desktop app or `ghs scan` even though they were running correctly.
- The fix applies to the desktop app and CLI on Windows and Linux. No command or configuration changes are required.

See the [published releases](https://github.com/Nix1983/GhostlyShare-Releases/releases) for downloads and [Troubleshooting](wiki/Troubleshooting.md) when a local app or link does not behave as expected.
