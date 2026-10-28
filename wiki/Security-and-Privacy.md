# Security and Privacy

GhostlyShare is a temporary development-sharing tool. Share only the specific app needed for a test, verify the displayed address, and stop the link as soon as the work is finished.

Detection alone never makes an app public. LAN and public routes start only after you choose to start them.

## LAN Sharing

- Devices that can reach the selected private IPv4 network may be able to open the link.
- An optional password adds an access gate, but LAN traffic remains plain HTTP and is not encrypted.
- Use LAN sharing only on a trusted network.
- Guest Wi-Fi, client isolation, firewalls, VPNs, and VM NAT can block intended access.
- A network change can stop the session rather than silently move it to a different network.

## Public Sharing

- Anyone who obtains the URL can try to open it.
- Random URLs are not a substitute for authentication.
- Password protection is useful for temporary reviews but is not a complete security system.
- Expiry limits how long a route runs; it does not control who receives the link.
- Visitor-facing traffic uses a Cloudflare-hosted HTTPS link.
- The local app, GhostlyShare, and computer must remain running and awake.

## Protecting the Selected App

GhostlyShare ties an active route to the local app you selected. If that app closes, changes, or is replaced by another app on the same port, GhostlyShare does not silently continue forwarding to the replacement.

This protection can make a share stop when a development server restarts in an unexpected way. Verify the app and explicitly start sharing again.

## Cloudflare Token

A token for custom domains is stored through secure credential storage provided by the operating system.

Use a scoped token with only the required zone-read and DNS-edit permissions. Remove it from GhostlyShare when it is no longer needed.

## Diagnostics and Logs

Discovery diagnostics keep short status reasons rather than page bodies, headers, full URLs, or detailed process information.

Support logs can still contain environment or endpoint information. Review and redact them before sharing.

## Never Expose

Do not share:

- Databases or database administration tools.
- Secret stores or configuration dashboards.
- Unprotected admin panels.
- Customer, personal, or confidential data.
- Internal infrastructure you are not authorized to expose.
- Any service you do not own or have permission to share.

Read [Responsible Use](../RESPONSIBLE_USE.md) for prohibited uses.
