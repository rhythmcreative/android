<h1 align="center">RhythmCreative Android Manifest</h1>

<div align="center">

<p><i>Unified Android source manifest combining official LineageOS 24 with GrapheneOS security hardening, privacy features, and Google Pixel enhancements.</i></p>

[![LineageOS](https://img.shields.io/badge/LineageOS-24.0%20%7C%2024.1-167C80?style=for-the-badge&logo=lineageos&logoColor=white)](https://lineageos.org/)
[![Android](https://img.shields.io/badge/Android-17%20(Baklava)-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://www.android.com/)
[![Hardened](https://img.shields.io/badge/Security-GrapheneOS%20Endured-E0245E?style=for-the-badge&logo=shield&logoColor=white)](https://grapheneos.org/)
[![Status](https://img.shields.io/badge/Status-Active-2EA44F?style=for-the-badge)](#)

</div>

## About

This repository contains the `repo` source manifest for **RhythmCreative Android**, an enhanced distribution of **LineageOS 24 (Android 17 / Baklava)** designed with uncompromising security, privacy, and performance for modern Pixel hardware (including Google Pixel 8a - `akita`).

The manifest seamlessly stitches together upstream LineageOS repositories with proprietary and open-source GrapheneOS security components and custom hardware fixes.

## Key Features & Security Enhancements

* 🛡️ **Hardened Memory Allocator (`hardened_malloc`)**: Integrated allocator from GrapheneOS providing probabilistic memory corruption mitigations, quarantine queues, and fine-tuned slab sizing for ARM64 39-bit virtual address space (Tensor G3).
* 🔒 **Granular Network Isolation**: Complete per-application network toggle (`POLICY_REJECT_WIFI` and cellular isolation), giving users total sovereignty over app internet traffic.
* 📶 **Wi-Fi Optimization & Anti-Tracking**:
  * Fixes aggressive background Wi-Fi suspension issues on Google Tensor platforms (`PixelWifiOverlay2024_midyearZuma`).
  * Automatic Wi-Fi timeout disconnect to avoid continuous broadcast probe beacon tracking when not connected to trusted networks.
  * Native per-network MAC randomization.
* 🔋 **LineageOS Charging Control HAL**: Native hardware-level battery charging thresholds (limit at 80% / battery lifespan prolonging).
* 🔄 **Integrated OTA Updates**: Pre-configured with native OTA updater endpoints powered by [`lineageos-akita-ota`](https://github.com/rhythmcreative/lineageos-akita-ota) with multi-channel support (`stable`, `beta`, `alpha`).
* 📱 **GrapheneOS Modern Launcher Layout**: Streamlined home screen and custom application iconography.

## Supported Branches

| Branch | Android Version | LineageOS Target | Status |
| :--- | :--- | :--- | :--- |
| **[`lineage-24.0`](https://github.com/rhythmcreative/android/tree/lineage-24.0)** | Android 17 (Baklava) | LineageOS 24.0 | 🟢 Active / Production |
| **[`lineage-24.1`](https://github.com/rhythmcreative/android/tree/lineage-24.1)** | Android 17 QPR1 | LineageOS 24.1 | 🚀 Prepared / Ready |

## Getting Started

### 1. Initialize the Source Repository

For **LineageOS 24.0 (Android 17)**:
```bash
repo init -u https://github.com/rhythmcreative/android.git -b lineage-24.0
```

For the upcoming **LineageOS 24.1 (Android 17 QPR1)**:
```bash
repo init -u https://github.com/rhythmcreative/android.git -b lineage-24.1
```

### 2. Synchronize the Tree

```bash
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

## Building

Automated build, signing, and OTA release deployment scripts are maintained in [`lineage-build-scripts`](https://github.com/rhythmcreative/lineage-build-scripts):

```bash
# Example build & publish for Google Pixel 8a (akita)
DEVICE=akita ./lineage-build-scripts/build_lineage_flame.sh --from build --publish --channel=stable
```

## Repository Structure

```text
.
├── default.xml                  # Main LineageOS source manifest
├── README.md                    # Project documentation
└── snippets/
    ├── kernel-5.15.xml          # Kernel 5.15 manifests
    ├── kernel-6.6.xml           # Kernel 6.6 manifests
    ├── kernel-6.12.xml          # Kernel 6.12 manifests
    ├── lineage.xml              # LineageOS additions
    └── rhythmcreative.xml       # RhythmCreative security & device modules
```

## Disclaimer

This is an unofficial project and is not officially affiliated with or endorsed by the LineageOS Project, GrapheneOS, or Google LLC. Android is a trademark of Google LLC.

<div align="center">

<p>Made with ❤️ by <b>rhythmcreative</b>.</p>

</div>
