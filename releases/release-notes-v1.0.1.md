# Laser Studio v1.0.1

Laser Studio v1.0.1 improves editor reliability, material and process preset management, device-aware laser settings, and print preparation performance.

## Downloads

Choose the package that matches your system:

- Windows x64: `LaserStudio-1.0.1-windows-x64-d21dae8.zip`
- macOS Apple Silicon: `LaserStudio-v1.0.1-macOS-arm64.dmg`
- macOS Intel: `LaserStudio-v1.0.1-macOS-x86_64.dmg`

ZIP archives are also provided for macOS users who prefer a compressed app bundle:

- `LaserStudio-v1.0.1-macOS-arm64.zip`
- `LaserStudio-v1.0.1-macOS-x86_64.zip`

## What's New

- Added user-created materials and process presets, including confirmed deletion of user-created materials.
- Added explicit confirmation before overwriting the current material preset for the active process mode and laser source.
- Limited process laser-source selection to sources configured for the connected device; single-source devices no longer expose an invalid switch.
- Excluded hidden objects from generated jobs while preserving locked objects in processing.
- Improved rectangular arrays: users set row and column counts explicitly, while total size changes adjust spacing.
- Added in-canvas vector path node editing with a synchronized toggle state.
- Improved multiline text editing, cursor placement, live bounds updates, font-size scaling, line height, and letter spacing behavior.
- Improved QR-code generation for long content with asynchronous progress and fill-engraving defaults.
- Improved print preparation responsiveness and progress display for larger jobs.
- Refreshed the Windows package with complete print-workspace localization, supported system-language selection on fresh installations, and English fallback for unknown or missing translations.
- Improved offset paths, mirror controls, calibration patterns, sticker cut outlines, and object ordering behavior.
- Expanded automated regression coverage for Windows feedback and cross-platform editor workflows.
- Updated the application version to v1.0.1.

## Verification

The release packages were checked before publishing:

- Windows x64 ZIP archive integrity passed; the package is built from commit `d21dae8`.
- macOS arm64 release build passed 45/45 automated tests.
- macOS x86_64 release build passed 45/45 automated tests.
- Both macOS app bundle versions were verified as 1.0.1.
- Both macOS ZIP archives were extracted and verified for version, architecture, and code signature.
- Both macOS DMG images were mounted and verified for image integrity, version, architecture, and code signature.
- SHA-256 checksums were generated from the files in this release directory.

## SHA-256 Checksums

```text
64f5b11b59754fb82a313378ccfc002d541c3d9246ae4779739fe7f13f52e822  LaserStudio-1.0.1-windows-x64-d21dae8.zip
13b54239faa71a03c9e0da44a59f04664b5061f054328a957fe52eda5fa073b1  LaserStudio-v1.0.1-macOS-arm64.dmg
d45a5c36b62c32337e440bc3aa06304d4a8cf140a4f464db86e862b4370a3ce6  LaserStudio-v1.0.1-macOS-arm64.zip
4e5ae89af486598013dee201d2815b3471ebb50c17ef4429bef9d5ae714d03f6  LaserStudio-v1.0.1-macOS-x86_64.dmg
761a0e2007b45cc55a10e779b91f38a462d02c135a40b05803c82165f450303c  LaserStudio-v1.0.1-macOS-x86_64.zip
```
