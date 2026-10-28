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

## First CLI Walkthrough

1. Start your local app and confirm that it opens in a browser, for example on port 5173.
2. Find it:

   ```bash
   ghs scan
   ```

3. Check that the listed name, port, and local URL belong to the intended app.
4. Start LAN sharing:

   ```bash
   ghs lan 5173
   ```

5. Open the printed LAN URL on a phone connected to the same trusted network.
6. Return to the terminal and press `Ctrl+C` to stop sharing.

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

## Machine-Readable Output

`ghs scan --json` prints one JSON array. This is real output from the published 1.3.8.0 CLI against the GhostlyShare test app:

```json
[{"port":5101,"name":"Static HTML Test App","url":"http://127.0.0.1:5101"}]
```

When no apps are found, the successful result is `[]`.

`ghs lan --json` and `ghs share --json` print newline-delimited JSON: every line is a complete event object. The values below are examples, while the field and event names are the exact 1.3.8.0 format:

```json
{"event":"lan_starting","port":5173}
{"event":"lan_ready","url":"http://192.168.1.20:49152/","localUrl":"http://127.0.0.1:5173","interfaceName":"Wi-Fi","address":"192.168.1.20","expiresAtUtc":null}
```

A public share uses `starting` and `ready` events:

```json
{"event":"starting","port":5173}
{"event":"ready","url":"https://example.trycloudflare.com","localUrl":"http://127.0.0.1:5173"}
```

When expiry is enabled, a `ready` event also contains `expiresAtUtc` as an ISO 8601 timestamp.

LAN failures provide a stable event name and reason code. This message was produced by the published CLI when the local app was unavailable:

```json
{"event":"lan_failed","reason":"origin_unavailable","message":"The local application could not be reached or safely verified. Make sure the application is still running, then retry the check."}
```

Not every error is a JSON event. Parser errors and some public-share startup errors are written as plain text to standard error, including when `--json` is selected. Automation must therefore check the process exit code and standard error as well as JSON events from standard output.

## Scripting and Automation

Press `Ctrl+C` to stop the owning LAN or public session. Custom-domain resources created by that command are cleaned up as the command exits.

- `--json` and `--url-only` cannot be combined.
- `--password` and `--password-env` cannot be combined.
- `--password` prompts interactively for the password and confirmation. Use `--password-env <name>` for unattended scripts and protect that environment variable from logs.
- `--url-only` writes the ready URL to standard output; progress and errors use standard error.
- `lan` and `share` remain in the foreground for the lifetime of the link. Keep the process running until the caller intentionally stops it.

A non-zero exit code means startup, the active share, or cleanup failed. Read standard error or the JSON failure event for the reason. Avoid printing passwords, tokens, and private URLs in CI logs.
