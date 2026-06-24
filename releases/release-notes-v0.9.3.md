# Laser Studio v0.9.3

Laser Studio v0.9.3 is a release focused on packaging reliability, runtime stability, device/process workflow improvements, and a cleaner public release set.

## Downloads

Choose the package that matches your system:

- Windows x64: `LaserStudio-0.9.3-windows-x64-cd5e9a2.zip`
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
- Refreshed the v0.9.3 packages with the latest bug fix from commit `cd5e9a2`.
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
- Windows x64 package is built from commit `cd5e9a2`.

## SHA-256 Checksums

```text
8e94013c709c127aad13dbdfb095ca47d0c2372736671653ccdd259c577ba61b  LaserStudio-0.9.3-windows-x64-cd5e9a2.zip
d88f2b1c63c320cd97238e77e73516ff371a20da9d2f48d570e351b88f3588e9  LaserStudio-v0.9.3-macOS-arm64.dmg
4fe3da980f3588cbd5a0c01e9f07a1061dca19b4d08cbdba3f668ab47af6d40c  LaserStudio-v0.9.3-macOS-arm64.zip
1838a3b556950797bf2d1f7a5cecc4bda0f72dbe39b85367fd6725a1dea5be63  LaserStudio-v0.9.3-macOS-x86_64.dmg
f55e6777e8fa1012b8024448d025696f614d779191587dfdebe7e0ae52d968c6  LaserStudio-v0.9.3-macOS-x86_64.zip
```
