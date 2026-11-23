# Niko's Cam releases

Niko's Cam is a Pro camera app for Android built with Camera2 and Jetpack Compose, with a
Leica-inspired dark UI, RAW/DNG capture, HDR+ and Night burst merging, Looks and custom LUTs.

This repository is the only place Niko's Cam is released. The private source repository
never publishes anything.

## Releases

- All releases: https://github.com/VK-VfX/Niko-Cam-Releases/releases
- Latest release: https://github.com/VK-VfX/Niko-Cam-Releases/releases/latest
- What changed: [CHANGELOG.md](CHANGELOG.md)

## Install and update

- Install: download the APK from the latest release and sideload it (allow installs
  from your browser or file manager when Android asks).
- Update: installed apps check `version.json` on the `never-spiral-apk-builds` branch
  and offer the update in-app.

## How a release is made

The manual workflow "Build and release" in this repository builds the private source,
signs it, checks the signing certificate, publishes the APK and `version.json` to the
`never-spiral-apk-builds` branch, tags `vX.Y.Z` and creates the GitHub Release, using
that version's section of `CHANGELOG.md` as the notes. A real release fails if
`CHANGELOG.md` has no section for the version.

## Signing

Releases are signed with the Nikezvera release key. Certificate SHA-256 fingerprint:

`5D:1E:B0:A9:2F:DF:E3:A6:41:28:72:11:4B:6F:4A:94:B2:16:4C:FA:64:F2:42:05:E0:7F:76:BF:14:09:B8:0F`

Each release run prints the signer certificate in its "Verify the signing key" step and
refuses to publish if it does not match this key, or if the APK is signed with the debug key.
