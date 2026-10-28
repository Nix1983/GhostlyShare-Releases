# Command Line Interface

The GhostlyShare command is `ghs`. Install the separate Windows or Linux CLI package when you want to scan and share from a terminal, server, script, or CI job.

There is no background daemon. A LAN or public link remains active only while its `ghs` process is running or until its expiry is reached.

## Help and Version

```bash
ghs --help
ghs help scan
ghs help lan
ghs help share
ghs version
```

## Find Local Apps

```bash
ghs scan
ghs scan --json
```

When an app is missing, ask for safe diagnostic reasons:

```bash
ghs scan --diagnostics
ghs scan --diagnostics --json
```

## Share on the LAN

```bash
ghs lan <port|url> [options]
```

Useful examples:

```bash
ghs lan 5173
ghs lan http://localhost:3000
ghs lan 5173 --interface Wi-Fi
ghs lan 5173 --password
ghs lan 5173 --expires-after 30m
ghs lan 5173 --url-only
ghs lan 5173 --json
```

LAN options:

- `--interface <name|id|ipv4>` selects a network adapter.
- `--password` asks for a password securely.
- `--password-env <name>` reads the password from an environment variable.
- `--password-attempts <3-10>` sets wrong attempts before a five-minute lockout.
- `--password-session-minutes <5-1440>` sets how long an unlocked browser remains valid.
- `--expires-after <duration|today>` stops the link automatically.
- `--url-only` prints only the ready LAN URL.
- `--json` prints machine-readable events.

LAN uses plain HTTP. Its password is an access gate, not transport encryption. Use it only on a trusted network.

## Share Publicly

```bash
ghs share <port|url> [options]
```

Useful examples:

```bash
ghs share 5173
ghs share http://localhost:3000
ghs share 5173 --password
ghs share 5173 --expires-after 15m
ghs share 5173 --custom demo.example.com
ghs share 5173 --url-only
ghs share 5173 --json
```

Public options:

- `--custom <hostname>` uses a hostname in your Cloudflare-managed domain.
- `--password` asks for a password securely.
- `--password-env <name>` reads the password from an environment variable.
- `--password-attempts <3-10>` sets wrong attempts before a five-minute lockout.
- `--password-session-minutes <5-1440>` sets how long an unlocked browser remains valid.
- `--expires-after <duration|today>` stops the link automatically.
- `--url-only` prints only the ready public URL.
- `--json` prints machine-readable events.

Password length is 8 to 32 characters.

Expiry examples for either `lan` or `share`:

```bash
ghs share 5173 --expires-after 30m
ghs share 5173 --expires-after 3h
ghs share 5173 --expires-after 1d4h15m
ghs share 5173 --expires-after today
```

The allowed range is `1m` to `40d23h59m`.

## Custom-Domain Login

```bash
ghs cloudflare login
ghs cloudflare status
ghs cloudflare logout
```

`login` stores the token in the operating system's secure credential storage. Do not pass a Cloudflare token as a command-line option or place it in logs.

## Check Public-Sharing Readiness

```bash
ghs doctor
ghs doctor --json
```

Doctor checks common network, proxy, DNS, credential-storage, and public-connection problems.

## Stop and Script Safely

Press `Ctrl+C` to stop the owning LAN or public session. Custom-domain resources created by that command are cleaned up as the command exits.

Use `--json` for newline-delimited machine-readable events. Use `--url-only` when a script needs only the ready URL. Do not combine the two options.

A non-zero exit code means startup, the active share, or cleanup failed. Read standard error or the JSON failure event for the reason. Avoid printing passwords, tokens, and private URLs in CI logs.
