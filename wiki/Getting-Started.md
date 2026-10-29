# Getting Started

Start with a harmless local test app. Keep the local app, GhostlyShare, and your computer running and awake until the test is finished.

## Before You Share

1. Start your website, API, dashboard, or development server.
2. Open its local address in a browser on the same computer.
3. Start GhostlyShare and wait for the app card to appear.

GhostlyShare may show more than one app on the same port when they are genuinely different local endpoints. Check the displayed address and app name before sharing.

## Create a Temporary Internet Link

Use Public sharing for a remote teammate, client review, or webhook.

1. Select **Public** on the app card.
2. Keep **Random** selected for the quickest setup.
3. Optionally set a password or an automatic expiry.
4. Select **Go Public** and wait for **Live**.
5. Copy the URL or show its QR code.
6. Select **Stop** when the review is over.

Stopping makes the route unavailable immediately. GhostlyShare never makes an app public again without another explicit **Go Public** action.

## Test on a Phone or Tablet over LAN

Use LAN sharing when both devices are on the same trusted home or development network.

1. Select **LAN** on the app card.
2. Optionally set a password or an automatic expiry.
3. Switch **LAN On**.
4. Scan the QR code or open the displayed address on the other device.
5. Switch **LAN Off** when finished.

LAN traffic uses plain HTTP. A password limits access but does not encrypt the traffic, so avoid guest Wi-Fi, hotels, and public hotspots.

## Prefer the Command Line?

Find local apps:

```bash
ghs scan
```

Share port 5173 over the internet or on the LAN:

```bash
ghs share 5173
ghs lan 5173
```

The command remains active while the link is running. Press `Ctrl+C` to stop it.

## App Not Listed?

First confirm that the local URL still opens in a browser. Then open:

**Settings → Discovery diagnostics → Open**

CLI users can run:

```bash
ghs scan --diagnostics
```

The result gives a short, safe explanation without storing the page contents. Continue with [App Detection and Diagnostics](App-Detection.md) or [Troubleshooting](Troubleshooting.md).
