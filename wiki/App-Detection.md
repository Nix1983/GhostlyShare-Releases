# App Detection and Diagnostics

GhostlyShare checks apps running on your computer and shows the ones that can be opened in a browser or shared safely.

It can recognize development websites, APIs, Swagger pages, dashboards, static sites, redirects, and many common development servers.

## Supported Local Environments

GhostlyShare can identify apps running in:

- Windows
- Linux
- WSL
- Docker

The app card can show the detected execution environment next to the port.

GhostlyShare scans local endpoints. It does not scan other computers on your LAN.

## What GhostlyShare Checks

- Common development ports are supported.
- Standard web ports `80` and `443` are supported.
- Apps available through IPv4 and IPv6 are combined when GhostlyShare can confirm that they are the same app.
- If several different apps use the same port, CLI users can select one with its exact local URL.

Example:

```bash
ghs share http://[::1]:5173
```

## Useful Start Pages

When an API exposes a useful browser page away from `/`, GhostlyShare can keep that route. For example, an API may open its Swagger UI instead of a metadata or empty root page.

HTTP-to-HTTPS redirects are followed only when the local target can be checked safely.

## Desktop Diagnostics

Open:

**Settings → Discovery diagnostics → Open**

The diagnostics window shows detected apps and anything GhostlyShare checked but did not display. It gives a short reason such as:

- Detected and shown.
- Hidden because the app signal was too weak.
- Blocked by a safety rule.
- Skipped until a retry.
- Timed out.
- Failed because the endpoint was not HTTP or could not be reached.

Diagnostics intentionally avoid storing page contents, headers, full URLs, and process details.

## CLI Diagnostics

```bash
ghs scan --diagnostics
ghs scan --diagnostics --json
```

Normal scanning remains available:

```bash
ghs scan
ghs scan --json
```

## When an App Is Missing

1. Confirm its local URL opens in a browser.
2. Wait for the next automatic refresh.
3. Open Discovery diagnostics or run `ghs scan --diagnostics`.
4. Check whether the app listens only inside a container or VM without a host-accessible local endpoint.
5. Check redirects, local HTTPS errors, and whether the endpoint returns an actual app or API signal.
6. Restart the local app if its listening address or owning process changed.
7. Include the safe diagnostic reason in a bug report.

See [Troubleshooting](Troubleshooting.md) for common fixes.
