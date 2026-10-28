# Release Notes

These notes summarize changes that affect people using the published GhostlyShare downloads. Internal refactoring and test-only changes are intentionally omitted.

## 1.3.8.0 — October 28, 2026

### Linux window recovery

- GhostlyShare can be reopened reliably from the application launcher after its window was minimized or hidden.
- Desktops without a usable tray, including a standard GNOME setup without AppIndicator support, no longer leave the running app effectively unreachable.
- Reopening uses the existing GhostlyShare instance, so active work is not replaced by a second permanent process.
- Native minimize behavior remains available on Linux.
- Tray and launcher recovery remain supported on KDE Plasma, XFCE, MATE, Wayland, and X11 where the desktop provides the relevant behavior.

### Tested upgrades

- The Windows, Debian/Ubuntu, Fedora/RPM, Arch Linux, CLI, discovery, LAN, public-link, WSL, Docker, IPv6, and custom-domain paths were exercised for this release.
- Updating the Linux package keeps desktop and CLI installations compatible.
- A separately installed system `cloudflared` remains untouched; GhostlyShare uses its own managed helper.

## 1.3.7.0 — October 27, 2026

### Clearer LAN behavior in virtual machines

- LAN sharing now shows **Limited** for a recognized VM NAT setup that may work inside the VM but remain unreachable from physical devices.
- Sharing is still allowed, and the message points users toward a bridged network when physical LAN access is required.

### Safer public-sharing helper

- GhostlyShare requires a current supported `cloudflared` version for public links.
- Verified managed copies can be reused when offline; an outdated or unverified fallback is rejected instead of being used silently.
- Old GhostlyShare-managed helper versions are cleaned up without changing a separately installed system copy.
- Concurrent support-log writes no longer interfere with one another.

## 1.3.5.0 — October 26, 2026

### More useful LAN sharing

- Added optional password protection to LAN links.
- Added automatic expiry to LAN links.
- Added separate LAN activity counters.
- Added compatibility messages before sharing and clearer **Limited**, **Unverified**, and **Unavailable** states.
- LAN sharing stays active across unrelated network changes but stops when its selected network actually changes.

LAN links still use plain HTTP. Their password is an access gate for a trusted network, not transport encryption.

### Control which ports appear

- Added **Port Discovery** preferences in Settings.
- A single exact port can be marked **Always Detect** when it hosts a local web app.
- A port or range can be marked **Never Show**.
- App cards provide quick access to the rules for their port.

### Desktop and reliability improvements

- Reorganized Settings and simplified the Public/LAN card controls.
- Improved Linux window placement and opening of the Settings folder.
- Improved Linux discovery for dual-stack listeners and common master/worker web servers.
- Improved public-link continuity when a development app restarts. The link stays offline until the user explicitly starts sharing again.
- Improved safe updates to active password settings and public/LAN session cleanup.

## 1.3.3.0 — October 22, 2026

### Stable and safer sharing sessions

- A stopped random URL can normally be reused during the same running desktop session.
- A restarted local app is never made public automatically; the user must select **Go Public** again.
- Custom-domain setup avoids replacing unrelated DNS records and cleans up only resources GhostlyShare can identify as its own.
- Custom-domain sharing works with the DNS-comment limits of Cloudflare's Free plan.
- Improved public sharing for IPv6-only local apps.

### Consistent discovery

- Discovery results are published as one coherent refresh, reducing temporary duplicates and partial lists.
- Improved handling of local apps that restart or briefly change between addresses.

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
- LAN sharing stops when the local app changes or closes, the selected network changes, or GhostlyShare exits.

### Better app detection

- Added discovery diagnostics in desktop Settings and through `ghs scan --diagnostics`.
- Added discovery for host-accessible Docker and WSL workloads.
- Added support for standard web ports 80 and 443.
- Improved IPv4/IPv6, redirect, duplicate, and stale-app handling.
- GhostlyShare can open a useful discovered route such as Swagger UI instead of always opening `/`.
- App cards can show whether a service runs on Windows, Linux, WSL, or Docker.

### Desktop, packaging, and safety

- Added a browser preference for the operating-system default, Firefox, Chrome, or Edge.
- Active shares stay tied to the selected local app instead of silently following an unrelated process that later reuses its port.
- Improved cleanup after interrupted public and custom-domain sessions.
- Desktop and CLI packages use .NET 10 internally and remain self-contained for end users.

## 1.2.9.3 — September 30, 2026

- Improved detection of local websites that redirect to a page with substantial inline CSS before the HTML title.
- These sites could previously be missing from the desktop app or `ghs scan` even though they were running correctly.
- The fix applies to the desktop app and CLI on Windows and Linux. No command or configuration changes are required.

See the [published releases](https://github.com/Nix1983/GhostlyShare-Releases/releases) for downloads and [Troubleshooting](wiki/Troubleshooting.md) when a local app or link does not behave as expected.
