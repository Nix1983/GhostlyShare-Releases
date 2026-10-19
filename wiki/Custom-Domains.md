# Custom Domains

GhostlyShare can temporarily publish a local app through a hostname in a Cloudflare-managed zone, for example `demo.example.com`.

Use a custom domain when a random public URL is not suitable for a client review, demo, or integration test.

## Requirements

- The domain is managed in Cloudflare.
- You can create a scoped Cloudflare API token.
- The token can read the required zone and edit DNS records for it.
- The chosen hostname is available or is already managed by GhostlyShare for the same workflow.

Use the smallest practical token scope. Do not use your global Cloudflare API key.

## Desktop App

1. Open the custom-domain workflow for the detected app.
2. Enter and validate the Cloudflare API token when asked.
3. Select the zone.
4. Choose the hostname.
5. Start sharing.
6. Stop the session when the demo is finished.

GhostlyShare stores the token in secure platform credential storage, not as plain text in the settings file.

## CLI

Save the token:

```bash
ghs cloudflare login
```

Check access:

```bash
ghs cloudflare status
```

Start the custom hostname:

```bash
ghs share 5173 --custom demo.example.com
```

Remove the saved token:

```bash
ghs cloudflare logout
```

## What GhostlyShare Manages

For an active custom-domain session, GhostlyShare can:

- Find the matching Cloudflare zone.
- Create the managed tunnel configuration.
- Create or update the temporary DNS record.
- Route the hostname to the selected verified local app.
- Remove temporary DNS and tunnel resources when sharing stops.
- Recover and clean up recorded resources after an interrupted session.

The hostname is temporary by design. Keep GhostlyShare and the local app running while it should work.

## Common Problems

- **Token rejected:** check zone-read and DNS-edit permissions.
- **Zone missing:** make sure the token includes the correct Cloudflare account and zone.
- **Hostname unavailable:** choose another hostname or remove a conflicting DNS record you own.
- **Link not ready:** allow a short time for DNS and tunnel readiness.
- **Old resources remain:** restart the current GhostlyShare version so recorded cleanup can run, then check the Cloudflare dashboard if needed.

Never post the token or unredacted custom-domain logs in a public issue.
