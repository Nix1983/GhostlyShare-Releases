# LAN Sharing

LAN sharing makes a detected local app reachable from devices on the same private IPv4 network. It does not create a Cloudflare tunnel and does not require an account, token, domain, or internet connection.

Typical uses:

- Test a responsive website on your phone.
- Open a dashboard on a tablet.
- Test a local app from another computer.
- Show a development build on a TV or other browser device.

## Desktop App

1. Start the local app.
2. Find it in GhostlyShare.
3. Select **LAN** at the bottom of its card.
4. Switch **LAN On**.
5. Copy the LAN URL or open the QR code.
6. Open the link from a device on the same network.
7. Switch **LAN Off** when finished.

LAN and public sharing are independent. You can use either one or both for the same app.

## CLI

```bash
ghs lan 5173
ghs lan http://localhost:3000
```

Print only the URL:

```bash
ghs lan 5173 --url-only
```

Use JSON events:

```bash
ghs lan 5173 --json
```

Choose a specific network adapter when the computer has multiple adapters:

```bash
ghs lan 5173 --interface Wi-Fi
ghs lan 5173 --interface 192.168.1.20
```

The interface value can be an adapter name, adapter ID, or local IPv4 address. Press `Ctrl+C` to stop.

## Security

A GhostlyShare LAN link has no built-in password protection. Anyone on the selected network may be able to open it.

Use LAN sharing only on a trusted home or development network. Avoid public hotspots, hotels, guest Wi-Fi, and shared networks containing unknown devices.

## Automatic Stop Conditions

LAN sharing stops when:

- You turn it off or press `Ctrl+C`.
- The local app closes.
- The local endpoint or owning process changes.
- The selected network changes or disappears.
- GhostlyShare exits.

LAN sessions are not restored after a restart.

## A Device Cannot Open the Link

Check these points:

- Both devices are on the same network and subnet.
- The client is not on isolated guest Wi-Fi.
- Access-point isolation is disabled.
- The operating system firewall allows GhostlyShare on the private network.
- A VPN is not sending the devices through different routes.
- The displayed IP address belongs to the intended adapter.
- The local app and GhostlyShare are still running.

When several adapters exist, use the CLI `--interface` option to test a specific one.

See [Troubleshooting](Troubleshooting.md) for more help.
