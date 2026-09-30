# Release Notes

## Upcoming: 1.2.9.3

- Improved detection of local websites that redirect to a page with substantial inline CSS before the HTML title. These sites could previously be missing from the app list or `ghs scan` even though they were running correctly.
- The fix applies to both the desktop app and CLI on Windows and Linux. No command or configuration changes are required.

After a release containing this fix becomes available, update the desktop app and/or CLI package you use. Microsoft Store availability depends on the separate Store submission and certification process.

See [published releases](https://github.com/Nix1983/GhostlyShare-Releases/releases) for available downloads and [Troubleshooting](https://github.com/Nix1983/GhostlyShare-Releases/wiki/Troubleshooting) if a local app is still missing.
