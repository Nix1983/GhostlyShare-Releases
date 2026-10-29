# Cleanup and Uninstall

You do not need to uninstall GhostlyShare before updating it. Follow [Updating an Existing Installation](Installation.md#updating-an-existing-installation) instead.

## Before Uninstalling

1. Stop every public and LAN share.
2. End running `ghs share` and `ghs lan` commands with `Ctrl+C`.
3. Fully quit the desktop app so it can close its helper processes and clean up its temporary custom-domain resources.
4. Remove the saved Cloudflare token if you no longer want it stored:
   - Desktop: open the Cloudflare API-token section in **Settings** and choose **Delete**.
   - CLI: run `ghs cloudflare logout`.

Closing or minimizing the window is not always the same as fully quitting on a desktop with tray support. Use GhostlyShare's **Quit** action and confirm it when asked.

## Windows Desktop

- **Microsoft Store:** remove GhostlyShare from Windows **Installed apps** or from the Start menu.
- **Direct setup:** remove GhostlyShare from Windows **Installed apps**.

## Windows CLI

Delete the extracted CLI folder. Remove that folder from your user `PATH` if you added it manually.

## Ubuntu or Debian

```bash
sudo apt remove ghostlyshare ghostlyshare-cli
```

Remove only the package name you installed when keeping either the desktop app or CLI.

## Arch Linux

```bash
sudo pacman -R ghostlyshare ghostlyshare-cli
```

## Fedora, RHEL, Rocky Linux, AlmaLinux

```bash
sudo dnf remove ghostlyshare ghostlyshare-cli
```

## openSUSE

```bash
sudo zypper remove ghostlyshare ghostlyshare-cli
```

## Optional Settings Removal

Uninstalling can leave preferences, logs, and support data so a reinstall keeps your settings. Leaving these files is harmless.

Before uninstalling, use **Settings → Settings folder** to open the exact folder. Typical locations are:

- Windows: `%LOCALAPPDATA%\GhostlyShare`
- Linux: `${XDG_STATE_HOME:-$HOME/.local/state}/GhostlyShare`

Delete that specific GhostlyShare folder with the file manager only when you no longer need its settings, logs, or cleanup information.

Secure credentials can be stored separately by the operating system, so remove the Cloudflare token from GhostlyShare before uninstalling when you want a complete cleanup.

A separately installed system `cloudflared` does not belong to GhostlyShare and is not removed by uninstalling GhostlyShare.
