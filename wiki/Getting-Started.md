# Getting Started

## First Desktop Test

1. Start a local website, API, dashboard, or development server.
2. Confirm that its local URL opens in your browser.
3. Open GhostlyShare.
4. Wait for the app card to appear.
5. Choose **LAN** or **Public** at the bottom of the card.
6. For LAN, switch **LAN On**. For Public, select **Go Public**.
7. Copy the link or open its QR code and test it from the intended device.
8. Stop sharing when your test is finished.

Keep both GhostlyShare and the local app running. Closing either one stops the route.

## Local Network Example

Use this for a phone or tablet connected to the same Wi-Fi:

1. Open **LAN** on the app card and switch **LAN On**.
2. Open the displayed LAN URL or scan the QR code.
3. Turn the switch off when finished.

LAN sharing does not use Cloudflare and has no built-in password. Use it only on a trusted network.

## Public Link Example

Use this for a remote teammate or webhook:

1. Open **Public** on the app card and select **Go Public**.
2. Wait until the card shows that the link is live.
3. Optionally add a password or expiration time before sharing.
4. Copy the public URL.
5. Select **Stop** when the review is over.

## Prefer the Command Line?

```bash
ghs scan
ghs lan 5173
```

Or create a public link:

```bash
ghs share 5173
```

The command remains active while the link is running. Press `Ctrl+C` to stop it.

## App Not Listed?

Open **Settings → Discovery diagnostics → Open**. The window explains why an app was detected, hidden, blocked, skipped, timed out, or could not be reached.

CLI users can run:

```bash
ghs scan --diagnostics
```

Continue with [App Detection and Diagnostics](App-Detection.md) or [Troubleshooting](Troubleshooting.md).
