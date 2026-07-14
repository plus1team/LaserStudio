# Laser Studio

**Version: V1.0.1**

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

Verfügbare Pakete:

- Windows x64: [`LaserStudio-1.0.1-windows-x64-d21dae8.zip`](releases/LaserStudio-1.0.1-windows-x64-d21dae8.zip)
- macOS Apple Silicon: [`LaserStudio-v1.0.1-macOS-arm64.dmg`](releases/LaserStudio-v1.0.1-macOS-arm64.dmg)
- macOS Apple Silicon ZIP: [`LaserStudio-v1.0.1-macOS-arm64.zip`](releases/LaserStudio-v1.0.1-macOS-arm64.zip)
- macOS Intel: [`LaserStudio-v1.0.1-macOS-x86_64.dmg`](releases/LaserStudio-v1.0.1-macOS-x86_64.dmg)
- macOS Intel ZIP: [`LaserStudio-v1.0.1-macOS-x86_64.zip`](releases/LaserStudio-v1.0.1-macOS-x86_64.zip)
- SHA-256-Prüfsummen: [`checksums.txt`](releases/checksums.txt)
- Versionshinweise: [`release-notes-v1.0.1.md`](releases/release-notes-v1.0.1.md)

## Neuerungen in V1.0.1

- Benutzerdefinierte Materialien und Prozessvorgaben können mit kontrollierten Abläufen zum Überschreiben und Löschen verwaltet werden.
- Die Auswahl der Laserquelle richtet sich nach der Konfiguration des verbundenen Geräts.
- Rechteckige Arrays, die Bearbeitung von Vektorpfadknoten, mehrzeiliger Text und die laufende Aktualisierung von Objektgrenzen wurden verbessert.
- Die QR-Code-Erzeugung für längere Inhalte läuft mit einer asynchronen Fortschrittsanzeige.
- Ausgeblendete Objekte werden nicht mehr verarbeitet; zugleich reagiert die Druckvorbereitung flüssiger.
- Das aktualisierte Windows-Paket vervollständigt die Übersetzungen im Druckarbeitsbereich, wählt unterstützte Systemsprachen automatisch und verwendet Englisch als Rückfalloption für unbekannte oder fehlende Übersetzungen.
- Die automatisierten plattformübergreifenden Regressionstests wurden erweitert.

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

Bevor ein Job an die Maschine gesendet wird, öffnet Laser Studio einen bildschirmfüllenden Druckarbeitsbereich: links den G-Code-Befehlsstrom, in der Mitte die Pfadvorschau und rechts die Drucksteuerung.

- G-Code-Vorschau mit Zeilennummern.
- Sichtbares Zeilenfenster für große Jobs.
- Zentrale Pfadvorschau für simulierte Bewegungen und gesendeten G-Code.
- Hervorhebung der aktuellen Zeile während der Ausführung.
- Start-, Pause-, Fortsetzen- und Stoppsteuerung.
- Gerätestatus und Fortschrittsverfolgung.
- Ein Druckauftrag-Tab zeigt den Fortschritt dauerhaft an und öffnet den Arbeitsbereich erneut.
- Sicherheitsprüfungen für Arbeitsbereichsgrenzen und ungültige Prozesseinstellungen.

![Druckarbeitsbereich](screenshots/gcode-preview.png)

### G-Code-Simulation

Die Simulation läuft im selben Druckarbeitsbereich, damit sich der erzeugte Pfad vor dem Senden an das Gerät prüfen lässt. Im Simulationsmodus erscheinen die Steuerelemente unterhalb der Pfadvorschau.

- Simulierte Werkzeugbahn im Arbeitsbereich.
- Einstellbare Simulationsgeschwindigkeit.
- Optionale Anzeige von Leerfahrwegen.
- Fortschritt beim Parsen der Zeilen und Bewegungsstatus.

![G-Code-Simulation im Druckarbeitsbereich](screenshots/simulation.png)

## Aktueller Umfang

V1.0.1 konzentriert sich auf zuverlässige Desktop-Bearbeitung, Material- und Prozessverwaltung sowie GRBL-Streaming über serielle Schnittstellen für XY-Lasergravierer.

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
