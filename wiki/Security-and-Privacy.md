# Security and Privacy

GhostlyShare is a development-sharing tool. The safest workflow is to expose only the specific temporary app needed for a test and to stop sharing immediately afterward.

## LAN Sharing

- The link is reachable from the selected private IPv4 network.
- GhostlyShare does not add password protection to LAN links.
- Use LAN sharing only on a trusted network.
- Guest Wi-Fi and access-point isolation can block the link.
- A network change stops the LAN session.

## Public Sharing

- Anyone who obtains the URL may try to open it.
- Random URLs are not a substitute for authentication.
- Password protection is a lightweight visitor gate, not a full security system.
- Link lifetime limits duration but does not control who can use the link.
- Public traffic passes through Cloudflare's tunnel infrastructure.

## Local App Identity

GhostlyShare verifies the selected local endpoint and its owning workload. Active shares are tied to that identity so a later process reusing the same port is not silently treated as the original app.

A share stops or is reconciled when the local app disappears, changes identity, or moves to a different endpoint.

## Cloudflare Token

A token used for custom domains is stored through secure credential storage provided by the operating system.

Use a scoped token with only the required zone-read and DNS-edit permissions. Remove it from GhostlyShare when it is no longer needed.

## Diagnostics and Logs

Discovery diagnostics keep limited status information and safe reasons. They do not retain response bodies, response headers, full URLs, or process details.

Support logs can still contain environment or endpoint information. Review and redact them before sharing.

## What Not to Expose

Do not share:

- Databases or database administration tools.
- Secret stores or configuration dashboards.
- Unprotected admin panels.
- Customer or personal data.
- Internal infrastructure.
- Services you do not own or have permission to expose.

Read [Responsible Use](../RESPONSIBLE_USE.md) for prohibited uses.
