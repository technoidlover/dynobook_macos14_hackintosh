# Hackintosh EFI for Dynabook G83

## OS: MacOS 14 Sonoma
## Table of Contents
1. [System Specifications](#system-specifications)
2. [Devices Working](#devices-working)
3. [Not Working / Issues](#not-working--issues)
4. [Known Issues and Fixes](#known-issues-and-fixes)
   - [Sleep Mode Issue](#1-sleep-mode-issue)
   - [FileVault](#2-filevault)
   - [Microphone Issue](#3-microphone-issue)
   - [Bluetooth Not Working](#4-bluetooth-not-working)
5. [Additional Information](#additional-information)
6. [Recommended kexts](#recommended-kexts)
7. [Credits](#credits)

## System Specifications:
- **CPU**: Intel® Core™ i5-8250U
- **SSD**: 256GB
- **RAM**: 8GB
- **Display**: 13.3-inch
- **Graphics**: Intel® UHD Graphics 620
- **Sound**: Intel® High Definition Audio compliant, stereo speakers, PCM recording/playback function, MIDI Stereo Speakers
- **Ports**:
  - HDMI® output terminal x 1
  - LAN (RJ45) x 1
  - USB3.0 x 2
  - USB Type-C™ connector with DisplayPort x 1
  - Microphone input/headphone output terminal x 1

## Devices Working:
- Intel UHD Graphics 620
- Display (13.3-inch)
- HDMI Output
- Sound (stereo speakers, microphone input)
- Ethernet (LAN)
- USB 3.0 Ports
- USB Type-C Port with DP (with DisplayPort )

## Not Working / Issues:
- **Bluetooth**: Unsupported
- **Webcam**: Not available (no webcam hardware)
- **Microphone**: Not functional
- **Sleep**: Sleep mode is unstable, causing wake-up issues
- **FileVault**: Enabling FileVault may lead to boot problems. It is recommended to keep it disabled.

## Known Issues and Fixes:
1. **Sleep Mode Issue**:
   - Sleep may cause the system to hang or become unresponsive upon wake. This is a common issue with Hackintosh builds.
   - **Fix**: You can disable sleep mode or use alternative methods like `Clover` or `OpenCore` to fine-tune the sleep settings. Using a custom DSDT patch might also help improve sleep/wake behavior.

2. **FileVault**:
   - Enabling FileVault can cause boot loops or prevent the system from booting entirely.
   - **Fix**: Keep FileVault disabled as it can lead to incompatibility with Hackintosh EFI builds. To ensure data security, consider using third-party encryption solutions instead.

3. **Microphone Issue**:
   - Although the system detects the microphone input, it might not work properly.
   - **Fix**: You can try experimenting with different `AppleALC` layouts or use an external USB microphone as a workaround.

4. **Bluetooth Not Working**:
   - Bluetooth functionality is not supported out of the box.
   - **Fix**: Replace the internal Bluetooth module with a Hackintosh-compatible USB Bluetooth adapter, or use a compatible PCIe card that includes supported Bluetooth.

## Additional Information:
- **Graphics Performance**: Intel UHD Graphics 620 should work smoothly with MacOS 14 using the `WhateverGreen.kext` and `Lilu.kext` for graphics patching.
- **USB Ports**: Ensure you have implemented a proper USB port mapping to avoid issues with wake/sleep and unsupported USB devices. This can be done by creating a custom SSDT or using tools like `Hackintool`.
- **Sound**: To ensure full compatibility with the sound system, make sure to use `AppleALC.kext` and try different layout IDs for better audio output.

## Recommended kexts:
- `Lilu.kext`: Essential for various patches and driver loading.
- `WhateverGreen.kext`: Ensures graphics compatibility with Intel UHD 620.
- `AppleALC.kext`: Provides audio support.
- `VirtualSMC.kext`: Necessary for system management and sensors.
- `IntelMausi.kext`: Enables Ethernet functionality.
- `USBInjectAll.kext`: For initial USB support (custom USB mapping recommended later).

## Credits:
Special thanks to the Hackintosh community for providing tools, guides, and continuous support.

---

**Disclaimer**: This EFI is provided as-is, and I take no responsibility for any damage or data loss resulting from its use. Please make sure to back up your data and proceed with caution.
