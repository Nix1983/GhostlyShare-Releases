# Command Line Interface

The GhostlyShare CLI command is `ghs`. It is available as a separate Windows or Linux package and is intended for terminals, servers, scripts, and machine-readable workflows.

The CLI has no background daemon. A LAN or public link remains active only while its `ghs` process is running.

## Help and Version

```bash
ghs --help
ghs help scan
ghs help lan
ghs help share
ghs version
```

## Scan

Find local apps:

```bash
ghs scan
ghs scan --json
```

Show inspected endpoints and safe reasons:

```bash
ghs scan --diagnostics
ghs scan --diagnostics --json
```

## Share on the LAN

```bash
ghs lan <port|url> [options]
```

Examples:

```bash
ghs lan 5173
ghs lan http://localhost:3000
ghs lan 5173 --interface Wi-Fi
ghs lan 5173 --url-only
ghs lan 5173 --json
```

Options:

- `--interface <name|id|ipv4>` selects a network adapter.
- `--url-only` prints the LAN URL to standard output when ready.
- `--json` prints machine-readable events.

LAN links have no built-in password. Press `Ctrl+C` to stop.

## Share Publicly

```bash
ghs share <port|url> [options]
```

Examples:

```bash
ghs share 5173
ghs share http://localhost:3000
ghs share 5173 --url-only
ghs share 5173 --json
ghs share 5173 --expires-after 15m
ghs share 5173 --password
ghs share 5173 --custom demo.example.com
```

Public options:

- `--custom <hostname>` uses a temporary custom hostname from a Cloudflare-managed zone.
- `--password` asks for a password without putting it in command history.
- `--password-env <name>` reads the password from an environment variable.
- `--password-attempts <3-10>` controls wrong attempts before a five-minute lockout. Default: `3`.
- `--password-session-minutes <5-1440>` controls how long an unlocked visitor session remains valid. Default: `30`.
- `--expires-after <duration|today>` stops the public link automatically.
- `--url-only` prints the public URL when ready.
- `--json` prints machine-readable events.

Password length: 8 to 32 characters.

Expiration examples:

```bash
ghs share 5173 --expires-after 30m
ghs share 5173 --expires-after 3h
ghs share 5173 --expires-after 1d4h15m
ghs share 5173 --expires-after today
```

Allowed expiration range: `1m` to `40d23h59m`.

Press `Ctrl+C` to stop. Custom-domain DNS and tunnel resources are cleaned up when the command stops.

## Cloudflare Token

```bash
ghs cloudflare login
ghs cloudflare status
ghs cloudflare logout
```

`login` stores the token in the platform's secure credential storage. Do not pass a token as a command-line option or place it in logs.

## Doctor

```bash
ghs doctor
ghs doctor --json
```

Doctor checks common network, proxy, DNS, and tunnel-readiness problems.

## JSON and Scripts

Use `--json` for newline-delimited machine-readable events. Use `--url-only` when a script needs only the ready URL.

Do not combine `--json` and `--url-only`.

A non-zero exit code indicates that startup, the active share, or cleanup failed. Read standard error or the JSON failure event for the reason.
