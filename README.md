# GyroLock Motion Photo — Single-File Fix 2.9.9

This project keeps the intended single-file Motion Photo behavior. For a Motion Photo capture, GyroLock writes one `.jpg` file containing the JPEG still image, XMP metadata, and the MP4 motion segment appended to the same file. It does **not** publish a separate MP4 to the public gallery for Motion Photo captures.

## Changes in 2.9.9
- Reverts the 2.9.8 behavior that published a standalone companion MP4.
- Keeps the Motion Photo as one JPEG container with embedded video.
- Writes an XMP packet wrapper and both current Motion Photo container metadata and legacy `GCamera:MicroVideo*` properties.
- Keeps the fallback path single-file as well.
- Increments the Android app version and updates the GitHub Actions artifact name.

## Important compatibility note
A single-file Motion Photo can be recognized only by apps that implement the relevant Motion Photo format. Some Android galleries may display only the still image, and TikTok versions may not import Android Motion Photo JPEGs as moving media. This source change cannot guarantee TikTok support; the generated file must be tested on the target phone and TikTok version. FOMZ's proprietary implementation is not fully reproduced just from APK strings/class names.

Build through GitHub Actions: open **Actions**, select the workflow, run it, then download the `GyroLock-Single-File-Motion-Photo-Fix-debug-apk` artifact.
