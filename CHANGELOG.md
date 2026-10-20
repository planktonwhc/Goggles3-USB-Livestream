# Changelog

**English** | [Bahasa Indonesia](./CHANGELOG.id.md)

## 1.0.3 — 2026-10-20

### Fixed

- **Virtual camera on Windows 10.** In 1.0.2 the virtual camera only worked on
  Windows 11; on Windows 10 it never appeared in OBS, Zoom or other apps. It
  now works on both Windows 10 and Windows 11, in 64-bit and 32-bit apps.
- **Virtual camera start order.** Opening OBS or Zoom before Goggles3 USB Live
  (or before turning the virtual camera on) no longer leaves the source blank
  until you re-select it. The camera shows dark grey while no video is
  available and switches to the live picture by itself.
- **Windows app icon.** The icon was blank in File Explorer, the Start menu,
  desktop shortcuts and Settings › Apps. It now shows everywhere.
- **In-app update.** After the update is downloaded and its checksum is
  verified, the app now closes (finishing any recording or stream first)
  and then opens the installer, so the installer no longer has to replace
  files that are still in use.

### Changed

- **The virtual camera is now called "Orbit-Virtual Camera"** (it was
  "goggles3"). In OBS, open your existing *Video Capture Device* source once
  and pick **Orbit-Virtual Camera** from the Device list.
- The virtual camera outputs 1920×1080 at 30 fps, with black bars around the
  goggles picture. It stays available while Goggles3 USB Live is open with
  **Settings › Output › Virtual camera** turned on; without video it shows dark
  grey, and when the app stops sending it shows the last picture, darkened.
- The virtual camera works in Zoom, Teams, OBS, Discord, browsers and other
  apps that use webcams, but not in the built-in Windows Camera app.
- Updating from 1.0.2 on Windows 11 removes the old "goggles3" camera
  automatically.

## 1.0.2 — 2026-10-20

### Highlights

- **Every feature is now free to use.** Lens correction, dewarp, LUTs,
  streaming, recording and the virtual camera all work without a license, and
  the 10-minute trial limit is gone. Without a license, an **UNLICENSED**
  watermark is shown on the preview and burnt into streams, recordings and the
  virtual camera, and those outputs are limited to 720p30. A license removes
  the watermark and keeps the original quality.
- **Live streaming.**
  - *Local streaming*: send the original video (no re-encoding) to OBS or VLC
    on this computer or your network, with copyable addresses.
  - *Social media streaming*: YouTube, Facebook, Twitch, TikTok or any custom
    RTMP/RTMPS server. The stream key is hidden by default; Low/Medium/High
    quality.
- **Recording.** Save the live feed as MP4, MKV or raw H.264 to your Movies
  folder, with a **Show** button for the last file. MP4 recordings are written
  so that a crash loses at most the last second.
- **Refreshed interface.** A calmer dark theme with larger text, rounded
  controls and toggle switches. Settings open as a centered window with pages
  for Info & License, Picture, Streaming, Recording, Output, System and Log.

### Added

- **Dewarp (DJI Fly style):** a one-click preset that corrects lens
  distortion to roughly match the DJI Fly app's look. Fine-tune with the
  Strength slider.
- **Software stabilization (experimental):** reduces small shakes in the live
  view, with a Strength slider. It zooms in slightly and is not a replacement
  for RockSteady/EIS on the air unit.
- **Brightness** slider (−1 to +1 EV) with a reset button.
- **LUT opacity:** blend a LUT's look with the original picture.
- **Use GPU render** (System page, on by default): decodes video on the GPU
  for lower CPU use, and switches back to software decoding automatically if
  the GPU decoder fails.
- **Virtual camera "goggles3" on Windows 11:** use the goggles feed as a
  camera in Zoom, Teams, OBS and other apps. Off by default; turn it on in
  Settings › Output.
- **Help button and illustrated 5-step tutorial** covering the USB cable,
  LiveView sharing, Camera View Recording and OTG Wired Connection.
- **System information** in settings: computer ID (copyable), operating
  system, GPU and CPU. This helps when reporting issues.
- **Required updates:** when an older version is no longer supported, the app
  asks you to update before it connects.
- New application icon.

### Changed

- **License activation** now uses the **email address and license key** the
  license was issued to.
- **Licenses are per computer, not per goggles.** One license works with any
  goggles on a limited number of computers.
- **Moving a license to another computer happens automatically.** The
  **Deactivate this computer** button is gone. A computer stays bound for
  7 days after activation; after that, activating the license on another
  computer frees it.
- **License session:** the license is checked online when the app opens. A
  licensed session lasts 4 hours from launch; the License page shows the time
  left, and **Start new session** renews it. A running stream or recording
  keeps going and switches to the correct watermark when the license state
  changes.
- The status pill now reads **Waiting for camera** instead of "Waiting feed".

### Fixed

- **macOS 11 and later:** the video decoder in 1.0.1 could fail to start on
  macOS versions older than the latest one.
- **Smoother, cleaner video:** the app now reads every network packet in each
  USB transfer and discards late fragments from older frames, which reduces
  stutter and corrupted frames.
- Activating a license during a trial session no longer leaves the session
  subject to the trial time limit.

## 1.0.1 — 2026-09-23

- One universal macOS package for both Apple Silicon and Intel Macs.
- Windows installer.
- Live view over USB, 16:9 crop, GPU lens correction and LUT color presets.
- License activation with offline verification.
- Automatic update check.
