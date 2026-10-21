# Cleanup and Uninstall

## Before Uninstalling

1. Stop every LAN and public share.
2. Close running `ghs lan` and `ghs share` commands with `Ctrl+C`.
3. For custom domains, allow GhostlyShare to remove temporary DNS and tunnel resources.
4. Remove the saved Cloudflare token:
   - Desktop: **Settings → API token → Delete**
   - CLI: `ghs cloudflare logout`
5. Optionally delete the downloaded `cloudflared` helper from desktop settings.

## Windows Desktop

- **Microsoft Store:** uninstall GhostlyShare from Windows **Installed apps** or the Start menu.
- **Direct setup:** uninstall GhostlyShare from Windows **Installed apps**.

## Windows CLI

Delete the extracted CLI folder. Remove that folder from `PATH` if you added it manually.

## Ubuntu / Debian

```bash
sudo apt remove ghostlyshare ghostlyshare-cli
```

Use only the package name you installed when removing just one component.

## Arch Linux

```bash
sudo pacman -R ghostlyshare ghostlyshare-cli
```

## Fedora / RHEL-Compatible

```bash
sudo dnf remove ghostlyshare ghostlyshare-cli
```

## openSUSE

```bash
sudo zypper remove ghostlyshare ghostlyshare-cli
```

## Optional Local Data Removal

Uninstalling a package can leave preferences and support data so an update or reinstall keeps your settings.

Desktop users can open the exact location with **Settings → Settings folder** before uninstalling.

Typical locations:

- Windows: `%LOCALAPPDATA%\GhostlyShare`
- Linux: `${XDG_STATE_HOME:-$HOME/.local/state}/GhostlyShare`

Linux removal command:

```bash
rm -rf "${XDG_STATE_HOME:-$HOME/.local/state}/GhostlyShare"
```

Delete local data only after confirming that no settings, logs, or recorded cleanup state are still needed.

Secure credentials can be stored outside this folder by the operating system. Remove the Cloudflare token from GhostlyShare before uninstalling when you want a complete cleanup.
