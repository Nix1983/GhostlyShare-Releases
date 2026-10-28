# Custom Domains

GhostlyShare can temporarily publish a local app through a hostname in a Cloudflare-managed zone, for example `demo.example.com`.

Use this when a familiar hostname is better than a random public URL for a client review, demo, or integration test.

## Before You Start

You need:

- A domain whose DNS is managed by Cloudflare.
- A scoped Cloudflare API token that can read the required zone and edit its DNS records.
- An available hostname that does not conflict with an unrelated existing record.

Use the smallest practical token scope. Do not use your global Cloudflare API key.

## Desktop App

1. Select **Public** and choose the custom-domain option.
2. Enter and validate the Cloudflare API token when asked.
3. Select the zone and hostname.
4. Start sharing and wait for **Live**.
5. Stop the route when the demo is finished.
6. Fully quit GhostlyShare when you want its temporary custom-domain resources cleaned up.

GhostlyShare stores the token in the operating system's secure credential storage rather than the normal settings file.

## CLI

Save and check the token:

```bash
ghs cloudflare login
ghs cloudflare status
```

Start a share:

```bash
ghs share 5173 --custom demo.example.com
```

Remove the saved token:

```bash
ghs cloudflare logout
```

## What to Expect

- GhostlyShare creates the temporary connection and DNS record needed for the selected hostname.
- Pressing **Stop** or taking the local app offline makes the route unusable immediately.
- Starting it again while the desktop app remains open reuses the hostname and normally avoids rebuilding the setup.
- No share is reactivated automatically after the local app or GhostlyShare restarts.
- Fully quitting GhostlyShare removes its managed temporary custom-domain resources.
- After a crash or forced shutdown, the next start attempts to clean up resources that GhostlyShare can safely identify as its own.
- Existing unrelated DNS records and tunnels are not deliberately replaced or deleted.

The Cloudflare zone and domain remain yours. GhostlyShare removes only temporary resources it created for its own sharing session.

## Common Problems

- **Token rejected:** check zone-read and DNS-edit permissions.
- **Zone missing:** make sure the token includes the correct Cloudflare account and zone.
- **Hostname unavailable:** choose another hostname or inspect the conflicting DNS record in Cloudflare.
- **Link not ready:** allow a short time for DNS and the public connection to become ready.
- **Cleanup warning:** restart the current GhostlyShare version so it can retry safe cleanup, then inspect the Cloudflare dashboard if the warning remains.

Never post the token or unredacted custom-domain logs in a public issue.
