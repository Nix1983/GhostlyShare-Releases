# Public Sharing

Public sharing creates a temporary internet URL that forwards traffic to a verified local app.

## Random Public Link

A random link is the fastest option:

1. Start the local app.
2. Select **Public** at the bottom of its card.
3. Keep **Random** selected and choose **Go Public**.
4. Wait until the status shows **Live**.
5. Copy the URL or show its QR code.
6. Choose **Stop** when finished.

Random links do not require a GhostlyShare account, your own domain, DNS setup, or a Cloudflare API token.

CLI:

```bash
ghs share 5173
ghs share http://localhost:3000
```

## Custom Domain

A custom domain uses a hostname from a Cloudflare-managed zone, such as `demo.example.com`.

It requires a Cloudflare API token with zone-read and DNS-edit permission. See [Custom Domains](Custom-Domains.md).

CLI:

```bash
ghs cloudflare login
ghs share 5173 --custom demo.example.com
```

## Password, Expiration, and Activity

Public links can include:

- A visitor password.
- A failed-attempt limit and temporary lockout.
- An expiring visitor session.
- An automatic link lifetime.
- Simple live traffic counters for the current sharing session.

See [Password Protection](Password-Protection.md), [Link Lifetime](Link-Lifetime.md), and [Traffic Statistics](Traffic-Statistics.md).

## Link Readiness

A new public hostname may need a short time before DNS and the tunnel are ready everywhere. GhostlyShare shows the session status and continues checking readiness.

If the link works from another device but this computer still shows a warning, local DNS, VPN, proxy, or security software may be affecting only the local readiness check.

## Stopping and Cleanup

When sharing stops, GhostlyShare closes the public route. For a custom domain, it also removes the temporary DNS record and managed tunnel resources used by that session.

GhostlyShare records enough local session state to clean up interrupted managed sessions when it starts again.

## Good to Know

- Keep GhostlyShare, the local app, and the computer online.
- Up to three public apps can be active at the same time.
- Cloudflare may temporarily rate-limit creation of random quick tunnels.
- Random URLs are temporary and should not be treated as stable production addresses.
- Public sharing is intended for development, testing, demos, and short reviews.

More details are available under [Rate Limits and Sessions](Rate-Limits-and-Sessions.md), [Security and Privacy](Security-and-Privacy.md), and [Troubleshooting](Troubleshooting.md).
