# Frequently Asked Questions

## Does GhostlyShare deploy my app?

No. Your app continues running on your computer. GhostlyShare gives it a temporary LAN or public route, and the route works only while the required app and computer remain available.

## Does detection make an app public?

No. GhostlyShare starts a LAN or public share only after you explicitly turn it on.

## Can I protect a LAN link with a password?

Yes, but LAN links use plain HTTP. The password is an access gate on a trusted network; it does not encrypt the password or app traffic.

## Why does a LAN link work in a VM but not on my phone?

The VM probably uses NAT. Change the VM network adapter to bridged networking when physical devices need to reach the guest directly.

## Why do two apps use the same port?

They may listen on different local addresses or be genuinely different endpoints. Verify each local URL. The CLI can select one exact URL.

## Why is there no tray icon on GNOME?

A standard GNOME session often does not provide AppIndicator tray support. Restore GhostlyShare from the dock, Overview, or application launcher. Missing tray support does not prevent sharing.

## What happens when the computer sleeps?

LAN and public links are unreachable while the computer sleeps or is suspended. After waking, wait for the network to return, check GhostlyShare's state, and test the link again.

## Will an update remove my settings or Cloudflare token?

Normally no. Install the newer package over the old version. Fully stop shares and quit GhostlyShare before updating. See [Installation and Updates](Installation.md).

## Do I need to install cloudflared?

No. GhostlyShare manages its own supported helper for public sharing. A separately installed system copy is not required and is not removed by a GhostlyShare update.

## How long does a CLI share last?

Only while the owning `ghs lan` or `ghs share` command is running, or until its expiry is reached. Press `Ctrl+C` to stop it.

## Why does a new public link take a moment to work?

A new hostname and public connection can need a short readiness delay. If it remains offline, check internet access, VPN, proxy, DNS filtering, and `ghs doctor`.

## Is GhostlyShare suitable for production hosting?

No. It is intended for temporary development tests, demos, webhooks, and reviews.

## Where can I get more help?

Start with [Troubleshooting](Troubleshooting.md). If the problem remains, [report a bug](https://github.com/Nix1983/GhostlyShare-Releases/issues/new?template=bug_report.yml) without including passwords, tokens, private URLs, or customer data.
