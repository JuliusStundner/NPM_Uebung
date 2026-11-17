# NPM Übung

Ein Frontend-Projekt mit npm, Sass, Bootstrap, Bootstrap Icons und BrowserSync.

Die Testseite enthält ein responsives Layout, angepasste Bootstrap-Farben und Icons. Änderungen an SCSS und HTML werden während der Entwicklung automatisch im Browser angezeigt, wenn Watcher und BrowserSync laufen.

## Voraussetzungen

- Node.js 22.14.0 mit npm
- Git

## Installation

Repository von GitHub klonen:

```bash
git clone https://github.com/DEIN-NAME/DEIN-REPOSITORY.git NPM_Uebung
cd NPM_Uebung
```

Abhängigkeiten installieren:

```bash
npm install
```

CSS einmalig erzeugen:

```bash
npm run scss:build
```

## Entwicklung starten

Im ersten Terminal den Sass-Watcher starten:

```bash
npm run scss:watch
```

Im zweiten Terminal BrowserSync starten:

```bash
npm run serve
```

Die Seite ist normalerweise unter http://localhost:3000 erreichbar.
Falls ein anderer Port verwendet wird, steht die Adresse im Terminal.

Beide Terminals müssen sich im Projektordner befinden.
Die Prozesse bleiben während der Entwicklung aktiv und lassen sich jeweils mit Strg+C beenden.

## Verfügbare Befehle

| Befehl | Funktion |
|---|---|
| npm install | Installiert die benötigten Pakete. |
| npm run scss:build | Übersetzt SCSS einmalig in CSS. |
| npm run scss:watch | Überwacht SCSS und erzeugt bei Änderungen neues CSS. |
| npm run serve | Startet BrowserSync mit automatischer Aktualisierung. |

## Projektstruktur

- src/scss/style.scss: Sass-Quelltext, eigene Variablen und Bootstrap-Imports
- dist/css/style.css: generiertes Stylesheet
- index.html: responsive Testseite
- package.json: Abhängigkeiten und npm-Scripts
- package-lock.json: genaue Paketversionen
- .gitignore: ausgeschlossene Dateien und Ordner
- README.md: Projektbeschreibung und Anleitung

## Verwendete Pakete

Produktionsabhängigkeiten:

- bootstrap: responsives Grid und Gestaltungselemente
- bootstrap-icons: Symbole für die Webseite

Entwicklungsabhängigkeiten:

- sass: übersetzt SCSS in CSS
- browser-sync: lokaler Entwicklungsserver mit automatischer Browser-Aktualisierung

## Gestaltung mit Sass

Bootstrap wird modular eingebunden. Dadurch werden nur die benötigten Komponenten in die CSS-Datei übernommen. Das reduziert die Dateigröße gegenüber dem vollständigen Bootstrap-Stylesheet.

Eigene Variablen wie $primary stehen vor dem Import der Bootstrap-Standardvariablen. Dadurch lässt sich beispielsweise die Hauptfarbe der Buttons anpassen.

Eigene Styles werden in src/scss/style.scss bearbeitet. Die Datei dist/css/style.css wird automatisch erzeugt und sollte nicht direkt geändert werden.

## Automatischen Workflow testen

1. Sass-Watcher und BrowserSync starten.
2. Die Seite im Browser öffnen.
3. Eine Überschrift in index.html ändern und speichern.
4. Prüfen, ob der Browser die Änderung automatisch anzeigt.
5. Die Variable $primary in style.scss ändern und speichern.
6. Prüfen, ob sich die Farbe des primären Buttons aktualisiert.

Bei schmalen Browserfenstern stehen die beiden Inhaltsbereiche untereinander. Ab einer Breite von 768 Pixeln werden sie nebeneinander dargestellt.

## Versionsverwaltung

Die .gitignore schließt folgende Dateien und Ordner aus:

```gitignore
node_modules/
dist/css/*.map
.DS_Store
```

node_modules enthält die installierten Pakete. Dieser Ordner wird nicht versioniert, weil er mit npm install wiederhergestellt werden kann.

package.json und package-lock.json bleiben im Repository. Das fertige CSS wird ebenfalls mit versioniert.

Die Bootstrap-Icon-Schriften werden aus node_modules geladen. Deshalb muss npm install auch dann ausgeführt werden, wenn die CSS-Datei bereits vorhanden ist.