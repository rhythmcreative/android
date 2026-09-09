# RhythmCreative Android Source Manifest

Custom LineageOS manifest with integrated GrapheneOS security hardening, privacy features, and Pixel device support.

## Getting Started

To initialize your local repository using this manifest:

```bash
repo init -u https://github.com/rhythmcreative/android.git -b lineage-24.0
```

For the upcoming **Android 17 QPR1** release:

```bash
repo init -u https://github.com/rhythmcreative/android.git -b lineage-24.1
```

Then sync the source tree:

```bash
repo sync -j$(nproc --all)
```

## Building

Automated build, signing, and OTA generation scripts are included in `lineage-build-scripts/`:

```bash
DEVICE=akita ./lineage-build-scripts/build_lineage_flame.sh --publish --channel=stable
```
