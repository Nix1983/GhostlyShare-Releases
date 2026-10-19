# Link Lifetime

A public link can stop automatically after a selected amount of online time.

Link lifetime applies to public random links and public custom domains. LAN sharing continues until it is stopped or interrupted.

## Desktop App

Open the lifetime settings for the app and choose a preset, **Today**, or a custom duration. The public link stops when the configured lifetime is reached even if the local app is still running.

## CLI

```bash
ghs share 5173 --expires-after 15m
ghs share 5173 --expires-after 3h
ghs share 5173 --expires-after 1d
ghs share 5173 --expires-after 1d4h15m
ghs share 5173 --expires-after today
```

Allowed duration: `1m` to `40d23h59m`.

## Important Details

- The countdown applies to the active public session.
- Expiration stops the public route; it does not close the local app.
- GhostlyShare and the computer must remain running until expiration.
- Stopping manually ends the link immediately.
- A new sharing session receives its own lifetime.
- Link lifetime is not authentication. Add a password when access also needs a visitor gate.
