# Goggles3 USB Livestream

**English** | [Bahasa Indonesia](./README.id.md)

View your DJI Goggles live feed on a computer over USB. Available for **Windows** and **macOS**, with video preview, 16:9 cropping, lens correction, and LUT color presets.

This repository provides application installers. Source code is not included.

## Download

Version **1.0.1**:

| Platform | Installer |
| --- | --- |
| Windows (64-bit) | [Download Windows Setup](https://github.com/planktonwhc/Goggles3-USB-Livestream/releases/download/v1.0.1/goggles3-usb-live-1.0.1-windows-x86_64-setup.exe) |
| macOS (Apple Silicon and Intel) | [Download macOS Package](https://github.com/planktonwhc/Goggles3-USB-Livestream/releases/download/v1.0.1/goggles3-usb-live-1.0.1-macos-universal.pkg) |

One universal macOS package now covers both Apple Silicon (M1 or later) and Intel Macs -- no need to check which chip your Mac has before downloading.

## Supported devices and requirements

- **DJI Goggles 3:** tested.
- **DJI Goggles N3:** untested; compatibility has not been confirmed.
- A USB cable that supports **data transfer**.
- An aircraft/air unit linked to the goggles to display the camera feed.

## Installation

### Windows

1. Download and run the Windows installer.
2. Follow the installation instructions, then open the application.
3. Connect your goggles using a USB data cable.
4. When the application requests administrator permission to configure the goggles' network adapter, approve it to complete connection setup.

The application uses Windows' built-in RNDIS adapter support. You do not need to replace the goggles' driver with WinUSB using Zadig. Keep the DLL files installed alongside the application.

### macOS

1. Download the `.pkg` installer (see [Download](#download) -- one universal package works on both Apple Silicon and Intel Macs), then open it.
2. Follow the installation instructions.
3. Open the installed application, then connect your goggles using a USB data cable.

#### Allow the application to open

If macOS blocks the installer or application because the developer cannot be verified:

1. Try opening the installer or application once.
2. Open **System Settings → Privacy & Security**.
3. Scroll to **Security**, find the blocked installer/application, and click **Open Anyway**.
4. Authenticate when prompted, then confirm **Open**.

The option is called **Open Anyway**, rather than “Trusted Developer.” See [Apple's instructions](https://support.apple.com/en-qa/guide/mac-help/mh40616/mac).

If the installed application is still blocked by its quarantine attribute, and you trust the downloaded release, open **Terminal** and run:

```sh
sudo xattr -r -d com.apple.quarantine /Applications/Goggles3\ USB\ Live.app
```

Enter your Mac administrator password when prompted (no characters appear as you type), then open the application again. This removes the quarantine attribute from this application bundle; it does not sign or notarize the application. The command assumes the app is installed at the path shown above.

## Start live view

1. Turn on the goggles and aircraft/air unit.
2. Make sure the camera feed is visible in the goggles.
3. Enable **LiveView Sharing** from the goggles' shortcut menu: press the 5D button down/toward you, then enable live view sharing. Although the description mentions Wi-Fi, this setting also enables the sharing path used over USB.
4. Connect the goggles to your computer.
5. Open the application and press the connect button.
6. Wait for the video to appear. Use the disconnect button to end the session.

### Testing without an aircraft

On the goggles, enable:

**Settings → Camera → Advanced Camera Settings → Camera View Recording**

This setting can display a waiting screen for connection testing. For a camera view with less OSD, disable **Camera View Recording**. If no camera source is connected, the image may become blank.

## Trial and PRO

| Feature | Trial | PRO |
| --- | --- | --- |
| Live view over USB | Yes | Yes |
| Session duration | 10 minutes per session | Unlimited |
| Crop a 4:3 source to 16:9 | Yes | Yes |
| Lens correction | — | Yes |
| LUT color presets | — | Yes |

Buy a PRO license at [fly.gadgetid.cloud](https://fly.gadgetid.cloud/).

### Free PRO keys

Try full PRO features free with one of these license keys:

```
FL-L3J4-F8M9-A2G9-HRRP
FL-CZBC-8P9Z-CGNT-ZAXD
```

To activate PRO, connect your goggles, open the application's license settings, and enter a license key — a free one above, or one you purchased. Activation requires an internet connection and is tied to the goggles' serial number. After successful activation, the license certificate can be verified offline for those goggles.

## Image settings

### 16:9 crop

Enable **Fill 16:9 (crop top / bottom)** to display the center of a 4:3 source at a 16:9 aspect ratio. The top and bottom are cropped without stretching the image.

For example, a 1440×1080 source displays a central 1440×810 area. This option is disabled for sources that are already 16:9. Cropping does not automatically detect or remove OSD.

### Lens correction — PRO

Enable **Lens correction**, then gradually increase **Strength** to reduce the bulging effect. Each time you enable it, strength resets to **0%**, leaving the initial image unchanged.

Correction runs on the GPU. Adjust the strength to suit your camera feed; this feature does not perform automatic lens calibration.

### Color grade (LUT) — PRO

Choose a LUT preset in the image settings to change the color appearance. If video playback feels sluggish, try disabling the LUT first.

## Troubleshooting

| Problem | What to check |
| --- | --- |
| Goggles not detected | Make sure the goggles are on, use a USB data cable, and try another USB port. |
| Connected but no video | Check LiveView Sharing and the aircraft/air unit connection. For testing without an aircraft, enable Camera View Recording. |
| Connection fails on Windows | Make sure the RNDIS adapter is available and adapter configuration requiring administrator permission has completed. |
| Video stutters or shows artifacts | Close other applications accessing the goggles, try a direct USB connection, and test with the LUT disabled. |
| Crop cannot be enabled | This feature is available only when the source frame dimensions are close to a 4:3 aspect ratio. |
| Lens correction unavailable | Check PRO activation and any error messages in the settings panel. |
| Session stops after 10 minutes | The trial session time limit has been reached. |
| Application reports a missing DLL | Reinstall using the complete installer package. Do not move the executable out of its installation folder on its own. |

Release builds do not display verbose logs in the terminal. Connection information and application errors are available in the built-in log panel.

VSync is disabled by default to reduce display waiting time. If you notice broken horizontal lines during motion (*tearing*), launch the application with the **`GOGGLES_VSYNC=1`** environment variable to enable it again.

## Reporting issues

When reporting a problem through this repository's Issues, include the application version, operating system, goggles model, steps to reproduce the problem, and messages from the log panel. Do not include your license key or device serial number in public reports.
