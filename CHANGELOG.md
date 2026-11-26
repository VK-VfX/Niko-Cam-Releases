# Changelog

All notable changes to Niko's Cam are listed here, newest first. The GitHub Release
for each version uses its section of this file as the release notes.

## [Unreleased]

- Nothing yet

## [3.0.0-beta.5] - 2026-11-27

### Fixed
- Burst HDR no longer comes out dark with a blown-out sky. It used to shoot four frames about 1.1 stops under and brighten them with a curve. It now shoots a dark frame (keeps the clouds), two normal frames and a bright frame (lifts the shadows), fuses them, and holds the result to the viewfinder's brightness.
- The dark frame goes deeper with the Burst HDR strength (1.2 to 2 stops under), so cloud detail survives in bright skies.

### What to check
- A cloudy sky from a window or rooftop: clouds keep their shape and the buildings are not black. Compare with your usual camera from the same spot.
- A dim room: the Burst HDR shot is about as bright as the viewfinder. The saved photo's record should show a parity value near 0.

### Known issues
- Beta; verified by tests only, not yet on a phone. Settings > Advanced > Comparison tests > the exposure-match switch turns the old four-dark-frames merge back on.

## [3.0.0-beta.4] - 2026-11-26

### Fixed
- Zebra stripes and the histogram now use the same brightness weights as the photo pipeline, so what they show matches the saved photo.
- Focus peaking no longer lights up on sensor noise at high ISO.
- Noise reduction and sharpening ramp smoothly with the real ISO (boost included) instead of jumping at ISO 800.
- Panorama stamps now carry the date and, when location is on, the place.
- The Settings stamp preview shows the DEEP NIGHT box as an example.

### What to check
- Zebra on a bright green object matches how bright it is in the saved photo.
- Peaking stays calm in a dark room.
- A panorama stamp shows the date.

### Known issues
- Beta; these changes are verified by tests only, not yet on a phone.

## [3.0.0-beta.3] - 2026-11-25

### Fixed
- Daylight photos are no longer handed to the Deep Night engine. Photo mode now hands off only in genuinely dark light (very high ISO and a long exposure).
- The DEEP NIGHT box in the stamp appears only on photos shot in the Night section.
- Multi-frame photos keep the viewfinder's brightness (the result is held to within about a third of a stop of the preview), and the exposure-drift log now reads the right frame.
- The stamp logo is the real app icon again, not a redrawn copy.

### Added
- Video ratio: video has the same ratio choices as photo (in the quick sheet, General tab). When the camera has no native size for a ratio, the clip is recorded at the normal size and cropped afterwards; the full-frame original is kept if the crop fails.
- Mode-bar scrub: the highlight follows your finger across the modes, with a light tick per mode, and settles on release. It works on the classic and the new bar, and on swiping the picture.

### Known issues
- Beta. The video crop's rotation and the scrub feel are unverified on a phone: please try a portrait 1:1 clip, a landscape 4:3 clip, and scrubbing both bars.

## [3.0.0-beta.2] - 2026-11-25

Second beta of the 3.0 line: more consistent photos, a new Settings page, a safety net for shots, and the first stage of the new interface (opt-in).

### Fixed
- Front-camera photos taken without flash no longer come out grainy and washed while flash photos look clean. The still frame was allowed a 60 fps range, so the camera picked a very short exposure with huge gain (about ISO 7500 effective); it now follows the preview's own range.
- Deep Night photos from the camera's night engine now carry their details (lens, aperture, shutter, ISO, date, place) in the stamp.
- The own-merge Night mode limits the number of frames and the shutter time when your hand is shaking, instead of merging twelve blurry frames.

### Added
- DEEP NIGHT box in the stamp: a small bordered label in every layout, shown together with the other items.
- Rough place name in the stamp ("Shah Alam, Selangor"), worked out on the phone from a bundled city list. Nothing is looked up online and no permission is added. A switch shows coordinates instead. City data: GeoNames, CC BY 4.0.
- Never-lose-a-shot safety net: every shot is journalled when its first copy is saved. If the app is closed while a photo is still being finished, the next launch keeps that copy and tells you.
- New Settings page: one solid sheet with sections (Photo, Stamp, Privacy, Help and app, Advanced), a "Photo intelligence" card that shows what runs automatically, and an Advanced fold for rare options and the comparison tests.
- First-run welcome for fresh installs (existing installs skip it).
- New interface, first stage (opt-in): a cleaner top band, a tool tray, a mode carousel (swipe the bar or the picture) and a Look and tone dock. Turn it on with the "New interface" switch at the top of Settings. After two launches that fail to draw, the app falls back to the classic screen by itself.
- Each photo's record now logs how far the saved exposure drifted from the viewfinder.

### Changed
- Scene detection is always on and has no setting.

### Known issues
- This is a beta. Several changes could only be tested on the build server, not on a phone. Please report anything odd with Diagnostics > Report a problem.
- The new interface is only its first stage: the viewer, editor, player and landscape layout still use the classic design.
- Place names rely on a bundled list. If you see coordinates instead of a name, tell me.

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
