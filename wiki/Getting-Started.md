# Getting Started

## First Desktop Test

1. Start a local app, for example Vite, ASP.NET Core, a dashboard, or an API with Swagger.
2. Confirm that its local URL opens in your browser.
3. Open GhostlyShare.
4. Wait for the app card to appear.
5. Choose one sharing mode:
   - Turn on **Share on local network** for devices on the same trusted network.
   - Select **Go Public** for a temporary internet URL.
6. Copy the generated link or open its QR code.
7. Test the link from the intended device.
8. Stop sharing when finished.

Keep both GhostlyShare and the local app running. Closing either one stops the route.

## Local Network Example

Use this for a phone or tablet connected to the same Wi-Fi:

1. Turn on **Share on local network**.
2. Open the displayed LAN URL or scan the QR code.
3. Turn the switch off when finished.

LAN sharing does not use Cloudflare and has no built-in password. Use it only on a trusted network.

## Public Link Example

Use this for a remote teammate or webhook:

1. Select **Go Public**.
2. Wait until the card shows that the link is live.
3. Optionally add a password or expiration time.
4. Copy the public URL.
5. Select **Stop** when the review is over.

## First CLI Test

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

Open **Settings → Discovery diagnostics**. It explains which local endpoints were found and why each endpoint is visible, hidden, blocked, skipped, timed out, or failed.

CLI users can run:

```bash
ghs scan --diagnostics
```

Continue with [App Detection and Diagnostics](App-Detection.md) or [Troubleshooting](Troubleshooting.md).
