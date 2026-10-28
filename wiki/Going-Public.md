# Public Sharing

Public sharing creates a temporary internet address for a local app. The visitor opens an HTTPS link while GhostlyShare remains in control of whether the local app is reachable.

Nothing becomes public merely because GhostlyShare detected it. You must explicitly start each public share.

## Random Public Link

A random link is the quickest option:

1. Start the local app.
2. Select **Public** on its card.
3. Keep **Random** selected.
4. Optionally set a password or automatic expiry.
5. Select **Go Public** and wait for **Live**.
6. Copy the URL or show its QR code.
7. Select **Stop** when finished.

Random links do not require a GhostlyShare account, your own domain, DNS setup, or Cloudflare API token.

CLI:

```bash
ghs share 5173
ghs share http://localhost:3000
```

## What Stop and Restart Do

**Stop** makes the route unavailable immediately. It does not publish itself again when the local app restarts.

While the desktop app keeps running, selecting **Go Public** again for the same app normally reuses the same random URL. GhostlyShare can release an old inactive URL when it needs room for another random link. Fully quitting and restarting GhostlyShare ends the old random-URL session, so the next share receives a new URL.

A custom hostname remains the same by definition. GhostlyShare can reuse its temporary setup while the desktop app stays open and removes its managed temporary resources when GhostlyShare fully exits. A CLI share ends and cleans up when its command exits.

See [Rate Limits and Sessions](Rate-Limits-and-Sessions.md) for the three-random-link limit.

## Custom Domain

A custom domain uses a hostname from a Cloudflare-managed zone, such as `demo.example.com`.

It requires a scoped Cloudflare API token that can read the zone and edit its DNS records. See [Custom Domains](Custom-Domains.md).

CLI:

```bash
ghs cloudflare login
ghs share 5173 --custom demo.example.com
```

## Password, Expiry, and Activity

A public share can include:

- A visitor password with failed-attempt lockout.
- A temporary unlocked visitor session.
- An automatic link lifetime.
- Simple activity counters for the current session.

See [Password Protection](Password-Protection.md), [Link Lifetime](Link-Lifetime.md), and [Traffic Statistics](Traffic-Statistics.md).

## Link Is Not Ready Yet

A new public hostname can need a short time before it works everywhere. GhostlyShare keeps checking and shows the current state.

If the link works from another device but the originating computer still reports a warning, that computer's DNS, VPN, proxy, or security software may be affecting only its local check.

GhostlyShare manages the helper needed for public sharing. You do not need to install `cloudflared` separately.

## When the Computer Sleeps

A public link is not usable while the computer is shut down, asleep, suspended, or disconnected from the internet. After waking or reconnecting, wait for GhostlyShare to show a healthy state and test the link again.

Public sharing is intended for temporary development, testing, demos, and reviews—not unattended hosting.
