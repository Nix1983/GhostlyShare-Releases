# Password Protection

Password protection is available for both public and LAN sharing. It adds a small sign-in page before GhostlyShare forwards requests to the local app.

## When to Use It

- Add a password to a public preview when the random URL alone is not enough.
- Add a password to a LAN test when other trusted users share the network.
- Use a unique temporary password and stop the link when the test ends.

Password protection is a lightweight access gate. It does not add user accounts, roles, or application-level authorization.

## Important LAN Difference

Public links use HTTPS for the visitor-facing connection. LAN links use plain HTTP.

On LAN, the password, session cookie, and app traffic are not encrypted in transit. Use LAN password protection only on a trusted network; it does not make an untrusted Wi-Fi network safe.

## Desktop App

Open the key-shaped password action for the selected Public or LAN share. Enter a password and choose the visitor-session rules.

You can set or change protection before starting the link and while the link is active. Test the link in a private browser window to confirm that the prompt appears.

## CLI

Prompt securely for a public password:

```bash
ghs share 5173 --password
```

The same option works for LAN:

```bash
ghs lan 5173 --password
```

Change the attempt and session limits:

```bash
ghs share 5173 --password --password-attempts 5 --password-session-minutes 60
ghs lan 5173 --password --password-attempts 5 --password-session-minutes 60
```

For scripts, read the password from an environment variable:

```bash
ghs share 5173 --password-env GHS_SHARE_PASSWORD
ghs lan 5173 --password-env GHS_LAN_PASSWORD
```

Passwords must contain 8 to 32 characters. The wrong-attempt limit can be 3 to 10; the default is 3 and the lockout lasts five minutes. An unlocked visitor session can last 5 to 1440 minutes; the default is 30 minutes.

Avoid putting passwords directly in command history, scripts, screenshots, or logs.

## What It Does Not Replace

GhostlyShare password protection is not:

- Multi-user identity management.
- Role-based access control.
- A replacement for the local app's own authentication.
- A security audit of the local app.
- Protection after someone shares the password with another person.
