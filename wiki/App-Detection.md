# App Detection and Diagnostics

GhostlyShare looks for local TCP listeners and safely checks whether they are shareable HTTP or HTTPS apps.

It can recognize common development websites, API documentation, OpenAPI or Swagger surfaces, health pages, dashboards, static sites, redirects, and many framework development servers.

## Supported Local Environments

GhostlyShare can identify apps running in:

- Windows
- Linux
- WSL
- Docker

The app card can show the detected execution environment next to the port.

GhostlyShare scans local endpoints. It does not scan other computers on your LAN.

## Ports and Addresses

- Common development ports are supported.
- Standard web ports `80` and `443` are supported.
- IPv4 and IPv6 endpoints are checked separately.
- Equivalent endpoints are combined only when GhostlyShare can safely identify them as the same app.
- If several different local apps use the same port through different local addresses, the CLI can accept the exact URL.

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

The diagnostics window shows apps and inspected endpoints, including entries that were:

- Detected and shown.
- Hidden because the app signal was too weak.
- Blocked by a safety rule.
- Skipped until a retry.
- Timed out.
- Failed because the endpoint was not HTTP or could not be reached.

Diagnostic records are intentionally limited. Response bodies, response headers, full URLs, and process details are not retained by this feature.

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
