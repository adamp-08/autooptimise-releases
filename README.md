# AutoOptimise Releases

This repository hosts public release files for AutoOptimise, a macOS app that watches selected folders and automatically optimises images and videos.

## What This Repo Is For

This is a release hosting repository. It is used for:

- Sparkle update feed: `appcast.xml`
- Release notes
- Public app downloads through GitHub Releases

The app source code does not need to live in this repository.

## Downloads

Download the latest version from the repository's **Releases** page.

Each release should include a zip archive named like:

```text
AutoOptimise-1.0.0-100.zip
```

Where:

- `1.0.0` is the user-facing app version.
- `100` is the internal build number.

## Auto Updates

AutoOptimise uses [Sparkle](https://sparkle-project.org/) for automatic macOS updates.

Sparkle reads the public update feed:

```text
https://adamp-08.github.io/autooptimise-releases/appcast.xml
```

The feed points to signed release archives hosted on GitHub Releases.

## Repository Structure

```text
appcast.xml
downloads/
  AutoOptimise-1.0.0-100.zip
  AutoOptimise-1.0.1-101.zip
release-notes/
  1.0.0.html
  1.0.1.html
```

The `downloads/` directory contains the zipped `.app` builds used by Sparkle.

## Release Checklist

1. Build a versioned app archive.
2. Sign the archive with Sparkle's EdDSA key.
3. Upload the zip to GitHub Releases.
4. Update `appcast.xml`.
5. Add or update release notes.
6. Confirm an older installed app detects the new version.

## Notes

This repository should remain public unless the app update system is changed to support authenticated downloads.

Subscriptions or licensing should be enforced inside AutoOptimise itself, not by hiding update downloads.
