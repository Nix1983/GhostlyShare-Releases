# LAN Sharing

LAN sharing gives another device a temporary address for an app running on your computer. It stays inside the selected private IPv4 network: no Cloudflare account, domain, or internet connection is required.

Use it to test a responsive site on a phone, open a dashboard on a tablet, or show a development build on another computer or TV.

## Desktop App

1. Start the local app and find its card in GhostlyShare.
2. Select **LAN**.
3. Optionally set a password or link lifetime.
4. Switch **LAN On**.
5. Open the displayed address or scan its QR code from the other device.
6. Use the activity button when you want to see simple session counters.
7. Switch **LAN Off** when finished.

LAN and Public are independent. You can use either one or both for the same local app.

## Optional Password and Expiry

A LAN password can prevent casual access by other devices on the same network. It does **not** encrypt the password, cookie, or app traffic because LAN links use plain HTTP.

Use the password only as an additional gate on a trusted network. Do not use LAN sharing for sensitive data on guest Wi-Fi, hotels, public hotspots, or networks containing unknown devices.

An expiry can turn the LAN link off automatically after a chosen duration or at the end of the day. You can also stop it immediately at any time.

See [Password Protection](Password-Protection.md) and [Link Lifetime](Link-Lifetime.md).

## CLI

Basic examples:

```bash
ghs lan 5173
ghs lan http://localhost:3000
```

Add a password without putting it in shell history, or add an expiry:

```bash
ghs lan 5173 --password
ghs lan 5173 --expires-after 30m
```

Choose a specific adapter on a computer with several networks:

```bash
ghs lan 5173 --interface Wi-Fi
ghs lan 5173 --interface 192.168.1.20
```

The interface value can be an adapter name, adapter ID, or local IPv4 address. Use `--url-only` for only the ready URL or `--json` for machine-readable events. Press `Ctrl+C` to stop.

## When GhostlyShare Shows Limited

A **Limited** warning means GhostlyShare can start the link but cannot confirm that the intended device will reach it.

A common example is a virtual machine using VirtualBox NAT. The link can work inside the VM while phones and computers on the physical LAN cannot reach the VM address. Change the VM network adapter to **Bridged Adapter**, reconnect it to the intended network, and start the LAN share again.

The warning does not weaken or bypass a safety check. It tells you that the selected network may not provide the reachability you expect.

## When Sharing Stops Automatically

A LAN share stops when:

- You switch it off, press `Ctrl+C`, or its expiry is reached.
- The local app closes or is replaced by a different app.
- The selected network changes or disappears.
- GhostlyShare or the owning `ghs` process exits.
- The computer shuts down.

While the computer is asleep or suspended, the link is unreachable. After waking, check the displayed state before relying on the link again. LAN sessions are not restored after GhostlyShare restarts.

## A Device Cannot Open the Link

Check these points:

- Both devices are on the same trusted network and subnet.
- The client is not on isolated guest Wi-Fi.
- Wireless client or access-point isolation is disabled.
- The operating-system firewall allows GhostlyShare on the private network.
- A VPN is not sending the two devices through different routes.
- The displayed address belongs to the intended adapter.
- A virtual machine uses bridged networking rather than NAT when physical devices need access.
- The local app, GhostlyShare, and computer are still running and awake.

See [Troubleshooting](Troubleshooting.md) for more help.
