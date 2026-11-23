# Changelog

All notable changes to Niko's Cam are listed here, newest first. The GitHub Release
for each version uses its section of this file as the release notes.

## [Unreleased]

- Nothing yet

## [2.18.1] - 2026-11-23

### Changed
- New names throughout the app. The night engine is now **Deep Night** (the Night chip reads "Deep"), the burst-merge HDR is now **Burst HDR**, and the looks category is now **Studio**, with Soft Natural, Deep Shadow, Cream and Studio Classic replacing the old names.
- Saved-photo notes now say "Night merge" and "Burst HDR". Photos taken earlier keep the text they were saved with.
- Your saved looks and settings carry over unchanged.

### Known issue
- In dim light, Burst HDR can render shadows darker than the viewfinder shows. Turn Burst HDR off for now. A proper fix is being designed.

## [2.18.0] - 2026-11-23

### Changed
- Sharper, cleaner photos: sharpening now works on brightness only and runs before film grain, so it no longer amplifies grain or colour noise or fringes coloured edges.
- Night, HDR+ and Realistic keep their colours: street lamps, skin and sky no longer shift hue when the shadows are lifted.
- Exposure fusion blends in linear light, with fewer halos around bright edges.
- Saturation, vibrance and the shadow/highlight weighting now use a P3 brightness weighting, so looks shift slightly compared with 2.17.
- The viewfinder match no longer clips colour channels separately when it brightens.
- Photos are tagged with the colour space they really have.

### Fixed
- Long manual exposures (up to 30 s) no longer time out.
- Ultra HDR gain maps are dropped when a lens warp or close-up crop changed the picture's geometry, instead of lighting the wrong areas.

### Security
- Safer updates: the update check rejects malformed or oversized update information, and an update is refused with a clear message if the downloaded file is for another app or signed with a different key.

## [2.17.20] - 2026-11-23

### Fixed
- Fixed crashes and lost shots in RAW merge, camera start/stop and background processing.
- Photos now save correctly on Android 8-9.
- The camera recovers when another app takes it.

### Changed
- Exposure is now a true stop.
- Clearer permission and busy-shutter feedback.

## [2.17.19] - 2026-11-22

### Added
- New Settings layout: switch rows, grouped sections and details on tap.

### Changed
- True Colour works in Display P3 and keeps the Ultra HDR file when nothing needs fixing.

### Fixed
- Scene detection start-up.

## [2.17.18] - 2026-11-22

### Added
- Adaptive Night Sight.
- ML Kit scene detection.
- Arc sliders.

### Changed
- Pro mode redesigned.

## [2.17.17] - 2026-11-22

### Changed
- First build signed with the new release key.

## [2.17.16] - 2026-11-22

### Added
- Night chip.
- Look picker.
- Ratio picker.

### Changed
- Video now records at 16:9.

## [2.17.15]

### Added
- Close-up mode.
- Tone sliders.
- Thumb-zone toggles.
- More hints.

### Fixed
- Black viewfinder.
