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

The macOS packages require macOS 13.0 or later. Choose `arm64` for Apple Silicon Macs and `x86_64` for Intel Macs.

## What's New

- Added automatic startup checks for newer GitHub Releases. Background network failures are ignored silently and only a valid newer version opens a notification.
- Added a manual **Check for Updates** action. It reports when the current version is latest and provides the GitHub Releases link when the service cannot be reached.
- Localized the update workflow in English, Simplified Chinese, Traditional Chinese, German, and Japanese.
- Fresh installations now follow a supported system language and fall back to English when the system language is unknown or a translation is unavailable.
- Completed localized material names, categories, descriptions, precautions, and process summaries across all five supported languages.
- Expanded and corrected bundled material presets while preserving user-created materials and overrides.
- Improved settings and material-management layout consistency and translation coverage.
- Rebuilt both macOS packages with Qt 6.11 and an explicit macOS 13.0 deployment target.
- Isolated release Qt and OpenSSL dependencies from Homebrew and added recursive Mach-O minimum-version auditing.
- Strengthened macOS Qt runtime deployment and explicit release signing behavior.
- Added a real macOS bundle startup smoke test so a structurally valid but unlaunchable app cannot pass packaging verification.
- Expanded automated regression coverage for update checks, language configuration, material management, and image overscan.
- Updated the application version to v1.0.2.

## Verification

The release packages were checked before publishing:

- Windows x64 ZIP archive integrity passed; the package is built from commit `33335bc`.
- The source regression suite passed 49/49 automated tests for both macOS release architectures before packaging.
- Both macOS app bundle versions were verified as 1.0.2.
- Every Mach-O executable, framework, plugin, and static OpenSSL object was audited to require no newer than macOS 13.0.
- Both macOS ZIP archives were extracted and verified for version, architecture, startup, and code signature.
- Both macOS DMG images were mounted and verified for image integrity, version, architecture, and code signature.
- The macOS arm64 and x86_64 bundles contain no linked dependencies on Homebrew or user-directory paths.
- SHA-256 checksums were generated from the files in this release directory.

## SHA-256 Checksums

```text
83c5526add16be94f777e0ecabf3c5126988a0927a8b9a3696baac28cc546351  LaserStudio-1.0.2-windows-x64-33335bc.zip
ab457ac8e95cf26572972e9f728dc9683ab890d46d52692ff72b0647c35e90f3  LaserStudio-v1.0.2-macOS-arm64.dmg
e33024677533e00fde95ea32645868c181be72fa43e9374a278bc1d1daef950c  LaserStudio-v1.0.2-macOS-arm64.zip
5b7f15e16bb1cf46ca7e6f9b23ecb80392b757d2a335e4d1aa6d8ee11c8c65f4  LaserStudio-v1.0.2-macOS-x86_64.dmg
411b513c81dab387b2993e9de32417be0dfd8b55a133769fac8c136c8d50b04b  LaserStudio-v1.0.2-macOS-x86_64.zip
```
