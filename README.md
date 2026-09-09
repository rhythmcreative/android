<h1 align="center">LineageOS Manifest</h1>

<div align="center">

<p><i>Source tree manifest for LineageOS, providing custom manifest configurations and device integrations.</i></p>

[![LineageOS](https://img.shields.io/badge/LineageOS-167C80?style=for-the-badge&logo=lineageos&logoColor=white)](https://lineageos.org/)
[![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)](https://www.android.com/)
[![Manifest](https://img.shields.io/badge/Manifest-Repo-167C80?style=for-the-badge&logo=git&logoColor=white)](#)
[![Active](https://img.shields.io/badge/Status-Active-2EA44F?style=for-the-badge)](#)

</div>

## About

This repository contains the source manifest required to initialize and synchronize the LineageOS source tree.

The repository is intentionally structured to provide the necessary manifests and snippets for building LineageOS with custom device trees and security integrations.

## Branches

| Branch        | Android Version | LineageOS Version | Status   |
| ------------- | --------------- | ----------------- | -------- |
| `lineage-24.0` | Android 17      | LineageOS 24.0    | Active   |
| `lineage-24.1` | Android 17 QPR1 | LineageOS 24.1    | Upcoming |

## Repository Structure

```text
.
├── default.xml
└── snippets/
    ├── kernel-5.15.xml
    ├── kernel-6.6.xml
    ├── kernel-6.12.xml
    ├── kernel-6.18.xml
    ├── lineage.xml
    └── rhythmcreative.xml
```

## Getting Started

To initialize your local repository using the manifest:

```bash
repo init -u https://github.com/rhythmcreative/android.git -b lineage-24.0
```

Then sync the source tree:

```bash
repo sync
```

> **Note:** For the upcoming Android 17 QPR1 release, switch branch to `lineage-24.1`.

## Disclaimer

This is an unofficial project and is not affiliated with or endorsed by the LineageOS project or Google.
<div align="center">

<p>Made with ❤️ from rhythmcreative.</p>

</div>
