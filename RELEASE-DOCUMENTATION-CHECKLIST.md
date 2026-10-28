# Release Documentation Checklist

Use this short check after the final release artifacts exist. Document only behavior available in the published release, not work that is merely merged or planned.

## Release and Downloads

- Confirm the latest public version, date, and release URL.
- Compare every documented filename with the actual release assets and inspect the filenames inside both Windows ZIP files.
- Verify the Windows setup ZIP, Windows CLI ZIP, Linux desktop packages, Linux CLI packages, and RPM signing key.
- Check that Microsoft Store wording does not promise the same publication time as GitHub.

## Installation and Commands

- Install or update at least one real package from each changed package family.
- Run `ghs version`, `ghs --help`, and the help for changed commands.
- Verify install, update, and uninstall commands using the package manager shown in the guide.
- Confirm supported operating systems and CPU architectures.

## User-Visible Behavior

- Update the release notes with benefits and visible behavior, not internal class or algorithm names.
- Review LAN, Public, password, expiry, custom-domain, activity, discovery, and desktop-environment pages affected by the release.
- Keep the README concise and link to one detailed source for each topic.
- State important limits and security consequences in plain language.

## Safety and Publication

- Do not publish unreleased features, private implementation details, credentials, internal paths, or proprietary discovery rules.
- Check that examples contain no real tokens, private hostnames, or customer data.
- Test local Markdown links and inspect all changed pages for conflicting statements.
- After merge, mirror the reviewed `wiki` folder to the GitHub Wiki and check its sidebar and old page URLs.
- Have another person review factual claims and the rendered Markdown before merging.
