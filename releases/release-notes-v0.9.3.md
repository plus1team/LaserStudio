# Laser Studio v0.9.3

Laser Studio v0.9.3 is a release focused on packaging reliability, runtime stability, device/process workflow improvements, and a cleaner public release set.

## Downloads

Choose the package that matches your system:

- Windows x64: `LaserStudio-0.9.3-windows-x64-0cc2fd1.zip`
- macOS Apple Silicon: `LaserStudio-v0.9.3-macOS-arm64.dmg`
- macOS Intel: `LaserStudio-v0.9.3-macOS-x86_64.dmg`

ZIP archives are also provided for macOS users who prefer a compressed app bundle:

- `LaserStudio-v0.9.3-macOS-arm64.zip`
- `LaserStudio-v0.9.3-macOS-x86_64.zip`

## What's New

- Added a Rayforge-inspired device and process library foundation.
- Improved machine, material, recipe, and process data handling.
- Improved project process binding and print task compilation.
- Improved macOS Qt application bundle deployment.
- Fixed a Windows startup heap corruption issue.
- Improved UI translations and calibration dialog layout.
- Updated the application version to v0.9.3.

## Verification

The release packages were checked before publishing:

- macOS arm64 release build passed.
- macOS x86_64 release build passed.
- macOS automated test suite passed: 41/41 tests.
- macOS app bundle version verified as 0.9.3.
- macOS release archives were checked to ensure test binaries and build artifacts are not included.
- macOS code signing verification passed for both app bundles.
- Windows x64 package is built from commit `0cc2fd1`.

## SHA-256 Checksums

```text
1f713de385f020d02a1c00b4cec7aa0068724ae902edcd411587a7d0c9abb8b6  LaserStudio-0.9.3-windows-x64-0cc2fd1.zip
a68a358e4379c91ce6e3776eb6e0f9772c3b42a3c804f7d151a818d1410cdce1  LaserStudio-v0.9.3-macOS-arm64.dmg
4c57dc1dc7948eb8a458a5ad234f37698298e9064e123ded2c48cce8f9995791  LaserStudio-v0.9.3-macOS-arm64.zip
6d4b9566bef67a19334890274db477e8e2f36e26739d4b1139b3ecb890708dff  LaserStudio-v0.9.3-macOS-x86_64.dmg
6db559652fb8d894c2f48d2bd6af0c37b565363028c6bc3fe84bf27ce84b18b3  LaserStudio-v0.9.3-macOS-x86_64.zip
```

