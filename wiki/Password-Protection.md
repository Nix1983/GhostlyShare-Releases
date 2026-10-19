# Password Protection

Password protection is available for public random links and public custom domains. It is not available for LAN sharing.

## What It Does

Visitors must enter the configured password before GhostlyShare forwards requests to the local app.

You can configure:

- Password length: 8 to 32 characters.
- Wrong attempts before lockout: 3 to 10.
- Default wrong-attempt limit: 3.
- Lockout duration: 5 minutes.
- Unlocked visitor session: 5 to 1440 minutes.
- Default visitor session: 30 minutes.

## Desktop App

Open the password settings for the app before sharing or while its public link is active. Save the password and visitor-session rules for that public session.

## CLI

Prompt securely:

```bash
ghs share 5173 --password
```

Change attempt and session limits:

```bash
ghs share 5173 --password --password-attempts 5 --password-session-minutes 60
```

Read a password from an environment variable:

```bash
export GHS_SHARE_PASSWORD='replace-this'
ghs share 5173 --password-env GHS_SHARE_PASSWORD
```

Avoid putting a password directly in command history, scripts, screenshots, or logs.

## Security Limits

GhostlyShare password protection is a lightweight gate for temporary development sharing. It is not:

- Multi-user identity management.
- Role-based access control.
- A replacement for the local app's authentication.
- A security audit of the local app.
- Protection against a password shared with the wrong person.

Use a unique temporary password and stop the public link when the review ends.
