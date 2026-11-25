# Changelog

All notable changes to Niko's Cam are listed here, newest first. The GitHub Release
for each version uses its section of this file as the release notes.

## [Unreleased]

- Nothing yet

## [3.0.0-beta.1] - 2026-11-25

First build of the 3.0 line. The camera, quick sheet and stamp upgrades are in; the full interface redesign and the new Settings page come in the next betas.

### Changed
- The quick sheet is now a solid panel. While it is open the shooting controls step aside and the viewfinder shrinks into the strip above it, so ratio and grid changes stay visible. Choices are equal-sized 48 dp circles, long labels become pills, and large text stacks the rows.
- "JPEG 4:3" now shows once, in the format pill. The lens name shows only while you drag the zoom dial.
- Smooth, purposeful motion: the sheet rises from the format pill, a yellow ring slides between choices, the pill pulses when its value changes, flash icons cross-fade, and error banners slide in. All of it is skipped when your phone's animation setting is off and during 60 fps video.
- Scene detection is always on and its setting is removed.
- Dim front-camera selfies: a dark face gets a little extra exposure, and at high ISO on a steady phone three or four frames are merged. A switch in Settings > Phone > Testing turns this off.

### Added
- Flash for the front camera in Deep Night: an Off/On screen-light chip that lights the screen before the capture.
- New stamp styles: AMOLED black bar, colour-adaptive bar, gallery mat border, frosted corner pill and a centered signature layout. Optional 35mm-equivalent focal length, pipeline tag, date and time, rounded-coordinate place tag (no lookup) and your own signature line. Framed Ultra HDR photos now keep their HDR look, and the badge is sharp at any resolution.
- Deep Night photos now save a capture record too, and Diagnostics counts record failures.

### Fixed
- Mirrored selfies kept as the camera's own file now open upright in the in-app viewer and editor.
- Timer selfies keep their face-weighted exposure.
- The preview is no longer rebuilt in the middle of a capture.
- Tap-to-meter uses the same zoomed-view frame as face metering.
- The update check uses the current Android package-info calls.

### Known issues
- This is a beta: the redesign and the new Settings page are still to come, and several changes could only be tested on the build server, not on a phone. Please report anything odd with Diagnostics > Report a problem.

## [2.19.3] - 2026-11-24

### Changed
- Front-camera selfies in dim light now take one frame metered on your face and keep exactly what the camera collected. The old path cut the exposure by 1.1 stops and then lifted the shadows, which produced noisy, crushed, painterly selfies. The effect on picture quality is not yet confirmed on the phone, so please compare a dim selfie against your usual camera and send a report.
- A new quick sheet opens from the format pill, with General and Pro tabs. Timer, ratio, format and grid are in General. Ultra HDR, quality, Burst HDR strength and the viewfinder aids are in Pro.
- Settings now has three tabs: Smart, Stamp and Phone. Controls that were shown twice (flash, ratio, RAW/JPEG, aids) now have one home each.
- The timer has a home on the camera screen: the format pill shows it, and the sheet sets it.
- The header reads Settings, the chip reads Burst HDR, and the info icon is labelled About.

### Added
- Every photo now saves a small record of how it was taken (exposure, frames, noise and edge modes, timings), shown in Diagnostics. It holds no personal data and keeps the newest 200 shots.
- Settings > Phone > Testing has two switches: the front low-light route and mirroring by the file's orientation tag. Turn the first off to get the previous front-camera behaviour back.

### Fixed
- Choosing Off in the flash settings no longer lights the torch for a moment on the way.

### Known issues
- Burst HDR can still render dim scenes darker than the viewfinder on the back camera. Turn it off for now.
- Tap-to-meter may land slightly off-centre when zoomed in. It is being checked.
- Mirrored selfies kept as the camera's own file rely on an orientation tag. If a gallery shows one flipped, turn off the mirror-by-tag switch in Testing.

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
