# Rate Limits and Sessions

## Active Public Apps

GhostlyShare allows up to three apps to be public at the same time.

LAN sharing does not use a public slot and can remain active independently.

## Random-Link Cooldown

Random public links use Cloudflare Quick Tunnels. Cloudflare can temporarily rate-limit new tunnel creation.

When this happens:

- Existing working links may remain active.
- A new random link may need to wait.
- GhostlyShare shows the failure or cooldown state.
- Repeatedly pressing **Go Public** does not bypass the external limit.

Wait for the cooldown and try again, or use an existing configured custom domain when appropriate.

## Password Sessions

A visitor who enters the correct public-link password receives an unlocked browser session for the configured number of minutes.

This visitor session is separate from:

- The public link lifetime.
- The local app's own login session.
- Other visitors.

Stopping the public link ends access regardless of the remaining visitor-session time.

## CLI Processes

Every running `ghs share` process represents one public sharing session. Every running `ghs lan` process represents one LAN sharing session.

Press `Ctrl+C` in the owning terminal to stop and clean up that session.
