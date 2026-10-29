# Link Lifetime

Public and LAN links can stop automatically after a chosen amount of active time or at the end of the current day.

Use an expiry when you do not want a forgotten test or review link to remain available.

## Desktop App

Open the clock-shaped lifetime action for the selected Public or LAN share. Choose a preset, **Today**, or a custom duration.

The link stops when the lifetime is reached even if the local app and GhostlyShare are still running. You can always stop it earlier.

## CLI

The same option works for public and LAN sharing:

```bash
ghs share 5173 --expires-after 15m
ghs share 5173 --expires-after 3h
ghs share 5173 --expires-after 1d
ghs share 5173 --expires-after 1d4h15m
ghs share 5173 --expires-after today
ghs lan 5173 --expires-after 30m
```

Allowed duration: `1m` to `40d23h59m`.

## What to Expect

- The countdown belongs to the current sharing session.
- Expiry turns off the GhostlyShare route; it does not close the local app.
- Stopping manually ends access immediately.
- A new sharing session receives its own lifetime.
- The computer and GhostlyShare must remain running and awake until expiry.
- Link lifetime controls duration, not who can use the link. Add a password when access also needs a visitor gate.
