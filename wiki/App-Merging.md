# App Cards and Duplicate Entries

GhostlyShare tries to keep the app list useful. Addresses that clearly lead to the same local app can appear as one card, while genuinely different endpoints can remain separate even when they share a port.

## Common Examples

- An HTTP address redirects to the HTTPS address for the same app: normally one useful card is enough.
- The same app is reachable through IPv4 and IPv6: GhostlyShare normally combines the addresses.
- A frontend and API run separately: both can appear when they are distinct apps.
- Two servers listen on different local addresses but use the same port: both can be valid entries.

## If the List Looks Wrong

1. Wait until every development server has finished starting.
2. Open each local address in a browser and check what it actually serves.
3. Wait for the next GhostlyShare refresh.
4. Open **Settings → Discovery diagnostics → Open**.
5. Review **Settings → Port Discovery → Manage** for custom rules.

CLI users can choose an exact endpoint instead of only a port:

```bash
ghs share http://localhost:5173
```

Always verify the displayed local address before starting LAN or public sharing. See [App Detection and Diagnostics](App-Detection.md) for more help.
