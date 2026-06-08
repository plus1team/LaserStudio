# Laser Studio

**Version: V0.9.2**

Sprachen:

- [English](README.md)
- [简体中文](README.zh-CN.md)
- [繁體中文](README.zh-TW.md)
- [日本語](README.ja.md)

Laser Studio ist eine kostenlose Desktop-Anwendung für Workflows rund um Lasergravur und Laserschneiden.

LightBurn ist sehr leistungsfähig, und LaserGRBL ist eine praktische schlanke Alternative. Ich habe Laser Studio begonnen, weil es weiterhin nur wenige kostenlose Laserprogramme mit einem modernen Bearbeitungsablauf gibt. Ziel ist eine kostenlose Anwendung für Lasergravierer, inspiriert von den praktischen Workflow-Ideen aus xTool-Software und Bambu Studio: Projektverwaltung, visuelle Bearbeitung, Geräteeinrichtung, Prozessparameter, Vorschau und Ausführung an einem Ort.

Laser Studio konzentriert sich derzeit auf GRBL-basierte XY-Lasergravierer, die per seriellem G-Code-Streaming gesteuert werden.

![Startseite von Laser Studio](screenshots/home.png)

## Downloads

Ausführbare Dateien werden im Verzeichnis [releases](releases/) bereitgestellt oder als Anhänge zu GitHub Releases veröffentlicht.

Empfohlene Paketnamen:

- `Laser-Studio-v0.9.2-macOS-arm64.dmg`
- `Laser-Studio-v0.9.2-macOS-x64.dmg`
- `Laser-Studio-v0.9.2-Windows-x64.exe`
- `Laser-Studio-v0.9.2-Windows-x64.zip`
- `Laser-Studio-v0.9.2-Linux-x64.AppImage`
- `checksums.txt`

## Hauptfunktionen

### Projekt-Workflow

- Lokale Laser-Studio-Projekte erstellen, öffnen, speichern und erneut öffnen.
- Karten für zuletzt verwendete Projekte auf der Startseite erleichtern das Fortsetzen früherer Arbeiten.
- Projektdateien speichern bearbeitbare Objekte, Arbeitsbereichsdaten, Vorschaubilder, Prozessvorgaben und Asset-Referenzen.
- Das aktuelle Projektformat ist auf `.lsproj` ausgelegt; ausführbare Jobdaten sind von den bearbeitbaren Projektdaten getrennt.

### Visueller Editor

Laser Studio enthält einen Canvas-basierten Editor zur Vorbereitung von Laserjobs.

- Arbeitsbereich mit Raster, Millimeterpositionierung, Linealen, Zoomsteuerung und automatischer Ansichtsoptimierung.
- Objekttransformationen für Position, Größe, Drehung, Spiegelung, Ausrichtung, Reihenfolge, Layout, Versatz, Array- und Pfadoperationen.
- Textobjekte mit Schriftfamilie, Schriftschnitt, Schriftgröße, Zeilenhöhe, Zeichenabstand, Ausrichtung und Weld-Einstellungen.
- Import von Bildern sowie Vektorobjekte, Pfade, Rechtecke, Freihandpfade, QR-Codes, Kalibrierobjekte, Verbindungspunkte und integrierte Form-Assets.
- Objektliste mit Sichtbarkeit, Sperrstatus, Reihenfolge, Vorschaubild und zugewiesenen Prozesseinstellungen pro Objekt.

![Arbeitsbereich-Editor](screenshots/workspace.png)

### Integrierte Formenbibliothek

Die linke Werkzeugleiste enthält eine wiederverwendbare Asset-Bibliothek für schnelles Gestalten. Der aktuelle Build enthält grundlegende geometrische Formen, Naturmotive, Tiere, Symbole, Sticker und iconartige Assets.

![Integrierte Formenbibliothek](screenshots/shape-library.png)

### Prozesseinstellungen

Jedes Objekt kann eine eigene Laservorgabe erhalten.

Unterstützte Bearbeitungsmodi:

- Liniengravur
- Füllgravur
- Linienschnitt
- Bildgravur

Prozessparameter umfassen:

- Auswahl der Laserquelle
- Leistung, Mindestleistung und Maximalleistung
- Geschwindigkeit in `mm/s`
- Anzahl der Durchgänge
- Fülldichte und Linienabstand
- Füllreihenfolge und Füllpfadmodus
- Scanwinkel
- Kreuzschraffur
- Overscan
- Kompensation für bidirektionales Scannen
- Verweilzeit
- Schnittfugenkompensation
- Haltepunkte für Schneidjobs
- Erweiterte Schneidparameter / Wobble Cut
- Raster-DPI und Punktzeit für Bildgravur
- Bildschwelle, Gamma, Kontrast, Schwarzpunkt, Weißpunkt, Dither-Stärke und Invertierung
- Bildalgorithmen wie Graustufen, Blue Noise, Bayer, Floyd-Steinberg, Jarvis, Stucki, Atkinson und Sierra-artiges Dithering

### Geräteverwaltung

Laser Studio kann GRBL-Geräteprofile und serielle Verbindungen verwalten.

- Erkennung und Verbindung serieller Schnittstellen.
- Gespeicherte Geräteprofile.
- Breite und Höhe des Arbeitsbereichs.
- Auswahl der Ursprungslage.
- Konfiguration von Laserquelle und Leistung.
- Anzeige von GRBL-Einstellungen.
- Maschinenstatus, `MPos` und `WPos`.
- Jog-Steuerung.
- Referenzfahrt, Entsperren, Nullpunkt setzen, Pause, Fortsetzen, Stopp und Laser-aus-Befehle.
- Optionales Zurückfahren zum Ursprung vor und nach Jobs, sofern das Gerät Homing unterstützt.

![Geräteverwaltung](screenshots/printer-management.png)

### G-Code-Vorschau und Jobsteuerung

Bevor ein Job an die Maschine gesendet wird, kompiliert Laser Studio das Projekt zu ausführbarem G-Code und zeigt den erzeugten Befehlsstrom an.

- G-Code-Vorschau mit Zeilennummern.
- Sichtbares Zeilenfenster für große Jobs.
- Hervorhebung der aktuellen Zeile während der Ausführung.
- Start-, Pause-, Fortsetzen- und Stoppsteuerung.
- Gerätestatus und Fortschrittsverfolgung.
- Sicherheitsprüfungen für Arbeitsbereichsgrenzen und ungültige Prozesseinstellungen.

![G-Code-Vorschau](screenshots/gcode-preview.png)

### G-Code-Simulation

Laser Studio enthält einen G-Code-Simulationsdialog, mit dem sich der erzeugte Pfad vor dem Senden an das Gerät prüfen lässt.

- Simulierte Werkzeugbahn im Arbeitsbereich.
- Einstellbare Simulationsgeschwindigkeit.
- Optionale Anzeige von Leerfahrwegen.
- Fortschritt beim Parsen der Zeilen und Bewegungsstatus.

![G-Code-Simulation](screenshots/simulation.png)

## Aktueller Umfang

V0.9.2 konzentriert sich auf Desktop-Bearbeitung und GRBL-Streaming über serielle Schnittstellen für XY-Lasergravierer.

Aktueller Fokus:

- Lokale Projektbearbeitung
- Verbindung zu GRBL-Geräten
- G-Code-Erzeugung
- G-Code-Vorschau
- G-Code-Simulation
- PC-seitige Streaming-Ausführung

Geplante oder laufend weiterentwickelte Bereiche:

- Breitere Geräteunterstützung
- Erkennung von Netzwerkgeräten
- Vom Controller verwaltete Jobpakete
- Mehr Materialbibliotheken und Prozessvorgaben
- Weitere Import- und Exportkompatibilität

## Lizenzhinweis

Laser Studio kann kostenlos genutzt werden, ist jedoch proprietäre Software. Der Quellcode wird nicht öffentlich veröffentlicht.

Laser Studio verwendet Qt. Qt wird unter der GNU LGPLv3 oder der jeweils anwendbaren Open-Source-Lizenz für die enthaltenen Qt-Module bereitgestellt. Laser Studio linkt dynamisch gegen Qt-Bibliotheken. Nutzer können diese dynamischen Qt-Bibliotheken gemäß den anwendbaren Qt-Lizenzbedingungen ersetzen oder neu linken.

Qt-Quellcode und Lizenzinformationen:

- https://www.qt.io/
- https://www.qt.io/download-open-source
- https://www.gnu.org/licenses/lgpl-3.0.html

