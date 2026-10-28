# Rate Limits and Sessions

## Random Public Links

The desktop app keeps room for up to three random public URLs during its current run. Active links and recently stopped links whose URL is being kept for quick reuse both occupy a place.

- If all three links are active, another random share cannot start.
- When an additional place is needed, GhostlyShare can release the oldest inactive random URL.
- Releasing an inactive URL means that app receives a new random URL the next time it is shared.
- Fully restarting GhostlyShare ends the previous random-URL session.
- Custom domains are separate from this three-link limit.

LAN sharing does not use a public-link place.

## Temporary Cloudflare Limits

Random public links use Cloudflare Quick Tunnels. Cloudflare can temporarily limit creation of new links.

Existing links may continue to work, but a new link may need to wait. Repeatedly selecting **Go Public** does not bypass that external limit. Wait and try again later, or use an already configured custom domain when appropriate.

## Password Sessions

After a visitor enters the correct password, that browser remains unlocked for the configured number of minutes.

This visitor session is separate from the link lifetime and from the local app's own login. Stopping the GhostlyShare link ends access regardless of the remaining visitor-session time.

## CLI Processes

Every running `ghs share` process owns one public sharing session. Every running `ghs lan` process owns one LAN session.

Press `Ctrl+C` in the owning terminal to stop and clean up that session. There is no separate background daemon, `list`, or `stop` command.
