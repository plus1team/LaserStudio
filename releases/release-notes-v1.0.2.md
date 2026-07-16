# Laser Studio v1.0.2

Laser Studio v1.0.2 adds GitHub release update checks, completes localization for update and material workflows, and strengthens macOS runtime packaging and startup verification.

## Downloads

Choose the package that matches your system:

- Windows x64: `LaserStudio-1.0.2-windows-x64-33335bc.zip`
- macOS Apple Silicon: `LaserStudio-v1.0.2-macOS-arm64.dmg`
- macOS Intel: `LaserStudio-v1.0.2-macOS-x86_64.dmg`

ZIP archives are also provided for macOS users who prefer a compressed app bundle:

- `LaserStudio-v1.0.2-macOS-arm64.zip`
- `LaserStudio-v1.0.2-macOS-x86_64.zip`

## What's New

- Added automatic startup checks for newer GitHub Releases. Background network failures are ignored silently and only a valid newer version opens a notification.
- Added a manual **Check for Updates** action. It reports when the current version is latest and provides the GitHub Releases link when the service cannot be reached.
- Localized the update workflow in English, Simplified Chinese, Traditional Chinese, German, and Japanese.
- Fresh installations now follow a supported system language and fall back to English when the system language is unknown or a translation is unavailable.
- Completed localized material names, categories, descriptions, precautions, and process summaries across all five supported languages.
- Expanded and corrected bundled material presets while preserving user-created materials and overrides.
- Improved settings and material-management layout consistency and translation coverage.
- Strengthened macOS Qt runtime deployment and explicit release signing behavior.
- Added a real macOS bundle startup smoke test so a structurally valid but unlaunchable app cannot pass packaging verification.
- Expanded automated regression coverage for update checks, language configuration, material management, and image overscan.
- Updated the application version to v1.0.2.

## Verification

The release packages were checked before publishing:

- Windows x64 ZIP archive integrity passed; the package is built from commit `33335bc`.
- The source regression suite passed 47/47 automated tests before packaging.
- Both macOS app bundle versions were verified as 1.0.2.
- Both macOS ZIP archives were extracted and verified for version, architecture, startup, and code signature.
- Both macOS DMG images were mounted and verified for image integrity, version, architecture, and code signature.
- The macOS arm64 and x86_64 bundles contain no linked dependencies on Homebrew or user-directory paths.
- SHA-256 checksums were generated from the files in this release directory.

## SHA-256 Checksums

```text
83c5526add16be94f777e0ecabf3c5126988a0927a8b9a3696baac28cc546351  LaserStudio-1.0.2-windows-x64-33335bc.zip
c65fd455d4aa19ca15a36f8f27fba79596ddcd5a0ccc034e76255c6c95469387  LaserStudio-v1.0.2-macOS-arm64.dmg
e533a2158e40c0dd6d48cbcbd582f48426308c1041b48196f0fdaaa45f98bb4f  LaserStudio-v1.0.2-macOS-arm64.zip
b86a0ff4d283cac42324f2fd4528701b438afd9baefc6d185a235d801ad25714  LaserStudio-v1.0.2-macOS-x86_64.dmg
92440a98c028964b6bac36f4c85ad84e59b7b387299e348f71d7c5c90a3d3c55  LaserStudio-v1.0.2-macOS-x86_64.zip
```
