# Laser Studio

**Version: V1.0.1**

Languages:

- [简体中文](README.zh-CN.md)
- [繁體中文](README.zh-TW.md)
- [Deutsch](README.de.md)
- [日本語](README.ja.md)

Laser Studio is a free desktop application for laser engraving and laser cutting workflows.

LightBurn is powerful, and LaserGRBL is a useful lightweight option. I started Laser Studio because there are still not many free laser software choices with a modern editing workflow. The goal is to build a free laser engraver application inspired by the practical workflow ideas in xTool software and Bambu Studio: project management, visual editing, machine setup, process parameters, preview, and execution in one place.

Laser Studio is currently focused on GRBL-style XY laser engravers controlled through serial G-code streaming.

![Laser Studio home screen](screenshots/home.png)

## Downloads

Executable files are published in the [releases](releases/) directory or attached to GitHub Releases.

Available packages:

- Windows x64: [`LaserStudio-1.0.1-windows-x64-370b92c.zip`](releases/LaserStudio-1.0.1-windows-x64-370b92c.zip)
- macOS Apple Silicon: [`LaserStudio-v1.0.1-macOS-arm64.dmg`](releases/LaserStudio-v1.0.1-macOS-arm64.dmg)
- macOS Apple Silicon ZIP: [`LaserStudio-v1.0.1-macOS-arm64.zip`](releases/LaserStudio-v1.0.1-macOS-arm64.zip)
- macOS Intel: [`LaserStudio-v1.0.1-macOS-x86_64.dmg`](releases/LaserStudio-v1.0.1-macOS-x86_64.dmg)
- macOS Intel ZIP: [`LaserStudio-v1.0.1-macOS-x86_64.zip`](releases/LaserStudio-v1.0.1-macOS-x86_64.zip)
- SHA-256 checksums: [`checksums.txt`](releases/checksums.txt)
- Release notes: [`release-notes-v1.0.1.md`](releases/release-notes-v1.0.1.md)

## What's New in V1.0.1

- Added user-created materials and process presets with controlled overwrite and deletion workflows.
- Made laser-source selection match the connected device configuration.
- Improved array layout, vector path node editing, multiline text editing, and live object bounds.
- Improved QR-code generation for longer content with asynchronous progress.
- Excluded hidden objects from processing and improved print preparation responsiveness.
- Expanded cross-platform automated regression coverage.

## Main Features

### Project Workflow

- Create, open, save, and reopen local Laser Studio projects.
- Recent-project cards on the home screen make it easy to continue previous work.
- Project files store editable objects, workspace information, thumbnails, process presets, and asset references.
- The current project format is designed around `.lsproj`; task execution is separated from editable project data.

### Visual Editor

Laser Studio includes a canvas-based editor for preparing laser jobs visually.

- Grid workspace with millimeter positioning, rulers, zoom controls, and workspace fitting.
- Object transforms for position, size, rotation, mirroring, alignment, order, layout, offset, array, and path operations.
- Text objects with font family, font style, size, line height, letter spacing, alignment, and weld settings.
- Image import, vector objects, paths, rectangles, brush paths, QR codes, calibration objects, connection points, and built-in shape assets.
- Object list with per-object visibility, lock state, order, thumbnail, and assigned process settings.

![Workspace editor](screenshots/workspace.png)

### Built-In Shape Library

The left-side tool panel includes a reusable asset library for quick design work. The current build includes common geometric shapes, natural shapes, animals, symbols, stickers, and icon-style assets.

![Built-in shape library](screenshots/shape-library.png)

### Process Settings

Each object can have its own laser process preset.

Supported process modes include:

- Line engraving
- Fill engraving
- Line cutting
- Image engraving

Process parameters include:

- Laser source selection
- Power, minimum power, maximum power
- Speed in `mm/s`
- Pass count
- Fill density and line interval
- Fill order and fill path mode
- Scan angle
- Cross hatch
- Overscan
- Bidirectional compensation
- Dwell time
- Kerf compensation
- Breakpoints for cutting
- Enhanced cutting / wobble cut parameters
- Raster DPI and image point time
- Image threshold, gamma, contrast, black point, white point, dither strength, and invert
- Image algorithms including grayscale, blue noise, Bayer, Floyd-Steinberg, Jarvis, Stucki, Atkinson, and Sierra-style dithering

### Printer Management

Laser Studio can manage GRBL printer profiles and serial connections.

- Serial-port discovery and connection.
- Saved printer profiles.
- Workspace width and height.
- Origin-position selection.
- Laser source and power configuration.
- GRBL setting display.
- Machine status, `MPos`, and `WPos`.
- Jog controls.
- Home, unlock, set origin, pause, resume, stop, and laser-off commands.
- Optional return-to-origin behavior before and after jobs when the device supports homing.

![Printer management](screenshots/printer-management.png)

### G-code Preview and Print Control

Before sending a job to the machine, Laser Studio compiles the project into executable G-code and shows the generated command stream.

- G-code preview with line numbers.
- Large-job handling with a visible line window.
- Current-line highlighting during execution.
- Start, pause, resume, and stop controls.
- Device status and progress tracking.
- Safety checks for workspace bounds and invalid process settings.

![G-code preview](screenshots/gcode-preview.png)

### G-code Simulation

Laser Studio includes a G-code simulation dialog so you can inspect the generated path before sending it to the device.

- Simulated toolpath view on the workspace.
- Adjustable simulation speed.
- Optional travel-path display.
- Parsed-line progress and motion status.

![G-code simulation](screenshots/simulation.png)

## Current Scope

V1.0.1 focuses on reliable desktop editing, material and process management, and GRBL serial-stream execution for XY laser engravers.

Current focus:

- Local project editing
- GRBL device connection
- G-code generation
- G-code preview
- G-code simulation
- PC-side streaming execution

Planned or evolving areas:

- Broader device support
- Network device discovery
- Controller-managed task packages
- More material libraries and presets
- More import/export compatibility

## License Notice

Laser Studio is free to use, but it is proprietary software. Source code is not publicly released.

Laser Studio uses Qt. Qt is provided under the GNU LGPLv3 or the applicable open-source license for the Qt modules included with the application. Laser Studio dynamically links to Qt libraries, and users may replace or relink those Qt dynamic libraries according to the applicable Qt license terms.

Qt source code and license information are available from:

- https://www.qt.io/
- https://www.qt.io/download-open-source
- https://www.gnu.org/licenses/lgpl-3.0.html
