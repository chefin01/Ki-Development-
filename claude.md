# Projektübergabe für Claude – aktueller Arbeitsstand

Stand: 8. Oktober 2026. Nutzerin: Britta Ebel, Köln.

Diese Datei dokumentiert den Stand für die Weiterarbeit auf einem anderen PC. Sie enthält Kontext und Arbeitsregeln. Der lauffähige HTML-Code liegt separat in `design-system.html`. Beide Dateien zusammen übertragen.

## 1. Aktuelles Projekt und Auftrag

Die Nutzerin hat ein vollständiges Designsystem als einzelne HTML-Datei mit Inline-CSS und Inline-JavaScript angefordert. Referenz: das IBM Carbon Design System unter https://www.carbondesignsystem.com/.

Ergebnis: **Studio Design System — Carbon Edition** in `design-system.html`.

Es ist ein eigenständig implementierter, umfangreicher Katalog nach Carbon-Prinzipien. Es ist keine vollständige Kopie der offiziellen Carbon-Bibliothek und verwendet keine React-Komponenten von Carbon. Diese Unterscheidung auch bei zukünftigen Beschreibungen beibehalten.

Der aktuelle Auftrag ist die Sicherung dieses Arbeitsstands für einen PC-Wechsel. Es gibt noch keinen Folgeauftrag, das Carbon-Designsystem auf die zuvor entwickelte Portfolio-Seite anzuwenden.

## 2. Dateien auf dem neuen PC

Für dieses Projekt einen eigenen Ordner anlegen:

```text
carbon-design-system/
├── claude.md
└── design-system.html
```

- `design-system.html`: vollständige Anwendung und maßgebliche Quelle für weitere Änderungen.
- `claude.md`: diese Übergabe und der Kontext für Claude.

`design-system.html` direkt im Browser öffnen. Installation, Build-Schritt und Internetverbindung sind für die Anwendung nicht erforderlich. Externe Dokumentationslinks benötigen Internet.

Optional kann ein lokaler Server verwendet werden, falls Python installiert ist:

```sh
cd carbon-design-system
python -m http.server 8000
```

Dann `http://localhost:8000/design-system.html` öffnen. Je nach System heißt der Python-Befehl `python3` oder `py`.

Wichtig: Der neue PC hat andere absolute Pfade. Immer mit dem tatsächlichen Projektordner und relativen Dateipfaden arbeiten. Die frühere Entwicklungsumgebung ist keine Laufzeitabhängigkeit.

## 3. Technischer Aufbau

- Eine HTML-Datei mit einem eingebetteten `<style>`- und einem eingebetteten `<script>`-Block.
- HTML-Sprache: Deutsch.
- Keine npm-, React-, GSAP- oder CDN-Abhängigkeit zur Laufzeit.
- IBM Plex Sans in 300, 400, 500 und 600 sowie IBM Plex Mono in 400 als eingebettete WOFF2-Dateien.
- Eigene SVG-Symbole für Icons, eingebettet in der Datei.
- Semantische Farbvariablen als CSS Custom Properties.
- Vier Themes: `white`, `g10`, `g90`, `g100`.
- Startzustand: Theme White, normale Dichte.
- Dichte umschaltbar: normal oder kompakt.
- Keine serverseitigen Funktionen, Anmeldung oder Datenübertragung.
- Formulardaten, Projektauswahl und Demo-Ergebnisse bleiben im aktuellen Seitenzustand; sie werden nicht dauerhaft gespeichert.
- Export über lokal erzeugte Downloads; Kopieren mit Clipboard-API und einem Fallback.

### Dateigröße und Identität beim Export

Die geprüfte HTML-Datei ist 325.313 Bytes groß. SHA-256:

```text
b175c9fd582daddb790cd88d3f0fb88e4030faf1689731d55a8d1e1a30317091
```

Diese Prüfsumme bezeichnet den Stand vor weiteren Änderungen. Nach einer Bearbeitung ist eine andere Prüfsumme erwartbar.

## 4. Enthaltene Grundlagen

### Farben und Themes

- 82 enthaltene Farbvariablen pro Theme.
- Referenz der Farbwerte: `@carbon/themes` Version `11.83.0`.
- Rollen für Hintergrund, Ebenen, Felder, Texte, Icons, Rahmen, Fokus, Aktionen und Status.
- Farbflächen können angeklickt werden, um die jeweilige CSS-Variable zu kopieren.
- Blau- und Grauskala mit jeweils zehn Stufen.
- Layering-Beispiele für Hintergrund und drei Ebenen.

### Typografie

- IBM Plex Sans für Inhalt und Oberfläche, IBM Plex Mono für Code.
- Dokumentierte Stile: `label-01`, `helper-text-01`, `body-compact-01`, `body-01`, `body-02`, `heading-compact-01`, `heading-01` bis `heading-07`, `code-01`.
- CSS-Tokens für Schriftgröße, Zeilenhöhe und Gewicht dieser Stile.
- Produktive Typografie für Arbeitsoberflächen und eine expressive Einstiegsüberschrift.

### Raster und Abstände

- 13 Spacing-Tokens: 2, 4, 8, 12, 16, 24, 32, 40, 48, 64, 80, 96 und 160 px.
- Carbon-Breakpoints: 320, 672, 1056, 1312 und 1584 px.
- Rasterbeispiele mit 4, 8 oder 16 Spalten.
- Die lokale Seitenleiste klappt zusätzlich bei maximal 800 px ein.
- Gezeigte Größenvarianten für Buttons: 32, 40, 48 und 64 px.

### Bewegung und Icons

- Eigenständig gezeichnete SVG-Icons im sachlichen Carbon-Stil.
- Lokale Bewegungstokens: 110, 240 und 400 ms.
- `prefers-reduced-motion` wird berücksichtigt.

## 5. Bereiche und Komponenten

Die Seite enthält eine Übersicht und 14 weitere Bereiche:

| Bereich | HTML-ID |
| --- | --- |
| Übersicht | `overview` |
| Farben & Themes | `colors` |
| Typografie | `typography` |
| Raster & Abstände | `layout` |
| Icons & Bewegung | `motion` |
| Buttons & Links | `actions` |
| Formulare | `forms` |
| Navigation | `navigation` |
| Inhalte & Flächen | `surfaces` |
| Feedback & Status | `feedback` |
| Tabellen & Daten | `data` |
| Dialoge & Muster | `patterns` |
| Barrierefreiheit | `accessibility` |
| Tokens & Export | `tokens` |
| Regeln & Quellen | `documentation` |

Es gibt **42 Komponentenbeispiele**. Die Zahl bezeichnet Beispielkarten, nicht 42 vollständig unterschiedliche offizielle Carbon-Komponenten.

- Aktionen: Button-Varianten, Button-Zustände und Größen, Icon-Button, Link.
- Formulare: Text-Input, Validierung, Passwort, Suche, Text-Area, Select, Combo-Box, Multi-Select, Checkbox, Radio-Button, Toggle, Number-Input, Slider, Datum/Zeit, File-Uploader.
- Navigation: Breadcrumb, Tabs, Content-Switcher, Progress-Indicator, Overflow-Menü, hierarchische Disclosure-Navigation.
- Inhalte: statische/verlinkte Tile, Selectable-Tile, Expandable-Tile, Accordion, Tags, Tooltip/Definition.
- Feedback: Inline-Notification, Toast, Loading, Skeleton, Progress-Bar.
- Daten: Data-Table mit Seitennavigation und Sammelaktionen, Empty-State, Code-Snippet.
- Muster: transaktionales Modal, Danger-Modal, vollständiges Projektbriefing mit einer kleinen UI-Shell.

Zu jedem Komponentenbeispiel kann der HTML-Code eingeblendet und kopiert werden. Beim Übernehmen in andere Seiten IDs und ihre Referenzen eindeutig halten; wiederverwendete Beispiele können zusätzliche JavaScript-Anbindung benötigen.

## 6. Funktionsumfang

- Durchsuchbarer Katalog inklusive Suchbegriffen für Komponenten und Grundlagen.
- Sofortiger Wechsel der vier Themes.
- Anpassung der Oberflächendichte.
- Validierung mit verknüpften Fehlermeldungen.
- Passwort anzeigen/verbergen.
- Lokale Suche, Zeichenzähler und Auswahlrückmeldungen.
- Checkbox-Gruppen mit unbestimmtem Elternzustand.
- Nummerneingabe mit Grenzen und Slider mit sichtbarem Wert.
- Lokale Dateiauswahl und Drag & Drop für PDF/TXT, maximal 5 MB pro Datei; Entfernen ist möglich.
- Tabs mit Pfeiltasten, Home und End.
- Menü mit Pfeiltasten und Escape.
- Schritte im Fortschrittsindikator.
- Kachelauswahl und ausklappbare Inhalte.
- Meldungen und lokale Lade-/Import-Simulationen.
- Tabelle mit Textsuche, alphabetischer/numerischer Sortierung, Zeilenauswahl und Pagination.
- Zeilenauswahl bleibt beim Seitenwechsel erhalten.
- Export ausgewählter Demoprojekte als JSON.
- Dialoge mit Fokusführung, Tab-Begrenzung, Escape und Rückkehr zum Auslöser.
- Vollständiges Briefingformular mit Fehlerübersicht und sicherer Ergebnisdarstellung.
- Berechnung ausgewählter Kontrastpaare im aktuellen Theme.
- Export von Design-Tokens als JSON und der vier Theme-Definitionen als CSS.
- Druckansicht.

Tabellendaten und Beispielbudgets sind ausdrücklich Demodaten. Sie dürfen nicht als reale Geschäftszahlen von Britta Ebel oder me:works beschrieben werden.

## 7. Prüfstand

Der Stand wurde im Headless-Browser **Chrome for Testing 145.0.7632.6** geprüft.

### Erfolgreiche Funktionsprüfungen

- Alle vier Themes und das Laden der eingebetteten Schrift.
- Katalogsuche und leere Suchergebnisse.
- Validierung, Passwortanzeige, Textsuche und Zeichenzähler.
- Checkbox-Teilauswahl, Number-Input-Grenzen und Slider.
- Dateiauswahl sowie Ablehnung eines nicht erlaubten Dateityps.
- Tastaturwechsel in Tabs und im Menü.
- Tabellensuche, numerische Sortierung, Seitennavigation und Auswahl über mehrere Seiten.
- JSON-Downloads für Auswahl und Tokens.
- Dialogfokus, Tab-Begrenzung, Escape und Fokus-Rückgabe.
- Briefingvalidierung und sichere Darstellung von Eingaben mit HTML-Zeichen.
- Fortschrittssimulation und Reduced Motion.
- Kein JavaScript-Seitenfehler und keine externen Netzwerkanfragen beim getesteten lokalen Ablauf.

### Responsive Prüfung

Geprüfte Breiten: 1584, 1440, 1312, 1056, 1024, 800, 736, 672, 375 und 320 px. Kein horizontaler Überlauf der gesamten Seite im abschließenden Test; breite Tabellen dürfen innerhalb ihres eigenen Bereichs scrollen.

Desktop-, dunkle Komponenten- und Mobilansicht wurden zusätzlich visuell angesehen.

### Automatische Barrierefreiheitsprüfung

`axe-core` Version `4.10.3`, Prüftags `wcag2a`, `wcag2aa`, `wcag21a`, `wcag21aa`:

| Theme | Gemeldete Verstöße im geprüften Seitenzustand |
| --- | --- |
| White | 0 |
| Gray 10 | 0 |
| Gray 90 | 0 |
| Gray 100 | 0 |

Das ist keine vollständige WCAG-Zertifizierung und kein Ersatz für manuelle Screenreader-Tests. Safari, Firefox und die konkrete Umgebung des neuen PCs wurden noch nicht geprüft.

### Bereits korrigierte Punkte

- Gut lesbare Tertiary-Button-Beschriftung im Hoverzustand dunkler Themes.
- Explizite Tab-Begrenzung im Dialog.
- Verhindern des Datei-Input-Überlaufs bei 320 px.
- Zugängliche Namen der Theme-/Dichteauswahl auch bei ausgeblendeten visuellen Labels.
- Zulässige Rollen für beschriftete Raster- und Meldungsbereiche.
- Tastaturzugang zu scrollbaren Tabellen, Code und Lizenzen.
- Besserer Textkontrast auf der dritten Ebene im Gray-90-Theme.
- Unsichtbare mobile Seitenleiste ist über `inert` nicht mit Tab erreichbar.

## 8. Arbeitsregeln für die Weiterentwicklung

1. Vor einer Änderung die vorhandene `design-system.html` lesen; sie ist die maßgebliche Projektquelle.
2. Dieses Projekt im eigenen Ordner halten. Portfolio und andere Apps getrennt bearbeiten.
3. Die Ein-Datei-Struktur mit Inline-CSS, Inline-JavaScript, eingebetteten Fonts und Icons beibehalten, solange die Nutzerin keinen Architekturwechsel verlangt.
4. Farben über semantische Tokens ändern; alle vier Themes berücksichtigen.
5. Keyboard-, Fokus-, Label-, Fehler- und Reduced-Motion-Verhalten erhalten.
6. Bei Komponentenänderungen die zugehörigen Interaktionen und schmalen Ansichten prüfen.
7. Keine echten Daten, Namen, Budgets oder Projektresultate erfinden.
8. Lizenzen und Quellenhinweise in der HTML erhalten.
9. Vorhandene Entscheidungen nicht stillschweigend neu interpretieren. Änderungen konkret zeigen; die Nutzerin arbeitet gerne mit einer Ansicht und anschließenden Änderungswünschen.
10. Nicht ohne Auftrag veröffentlichen, auf einen Server hochladen oder das Portfolio umgestalten.

Der nächste sinnvolle Schritt auf dem neuen PC: beide Dateien öffnen, den Stand kurz prüfen und anschließend die nächste konkrete Änderung der Nutzerin umsetzen. Nicht das Designsystem von Grund auf neu bauen.

## 9. Referenzen und Lizenzen

- Hauptreferenz: https://www.carbondesignsystem.com/
- Farben/Themes: https://www.carbondesignsystem.com/building-blocks/foundations/color/overview
- Typografie: https://www.carbondesignsystem.com/building-blocks/foundations/typography/style-strategies
- Raster: https://www.carbondesignsystem.com/building-blocks/foundations/2x-grid/overview
- Spacing: https://www.carbondesignsystem.com/building-blocks/foundations/spacing/overview
- Buttons: https://www.carbondesignsystem.com/building-blocks/core/components/button/guidelines
- Dialogfokus: https://www.carbondesignsystem.com/building-blocks/core/components/modal/accessibility

Die eingebetteten IBM-Plex-Schriften stehen unter SIL Open Font License 1.1. Der enthaltene Carbon-Token-Ausschnitt basiert auf `@carbon/themes 11.83.0` unter Apache 2.0. Die Lizenztexte stehen vollständig in der HTML-Datei. Die Komponenten wurden eigenständig in HTML/CSS/JavaScript umgesetzt.

## 10. Separates Vorgängerprojekt: Portfolio Britta Ebel

Vor dem Designsystem entstand eine eigene lokale Portfolio-Seite. Beide Projekte sind voneinander getrennt. Das neue Carbon-Designsystem wurde noch nicht auf dieses Portfolio übertragen.

Dateien im ursprünglichen Portfolio-Projekt:

```text
portfolio-chefin/
├── dist/
│   └── index.html
├── README.md
└── THIRD_PARTY_NOTICES.txt
```

Das Paket `Portfolio_Chefin.zip` enthält diesen Stand. Für die Weiterarbeit am Portfolio zusätzlich dieses ZIP übertragen und in einen eigenen Ordner entpacken.

### Aktueller Portfolio-Stand

- Vier Bereiche: Einstieg, Über mich, Projekte, Kontakt.
- Name: **Britta Ebel**, nicht „Chefin“.
- Hero-Eyebrow: `Producing · Finance · Agile Coaching`.
- Große Überschrift: `Geschichten. Teams. Struktur.`
- Letzte Änderung: React-Bits-**Masked Heading** mit eingebettetem Demo-Video innerhalb der Buchstaben, sanftem Rise-Effekt und leichtem Parallax.
- Das zuvor ausprobierte Text-Loop-Wellenband wurde entfernt.
- Ein Pause-/Fortsetzen-Button ist vorhanden; reduzierte Bewegung und Sichtbarkeit werden berücksichtigt.
- Stern-/Orbit-Element und leicht geneigte Projektkarten bleiben Bestandteil des Layouts.
- Ein persönliches Foto wurde besprochen, aber noch nicht eingefügt. Kein Porträt erfinden.

### Bestätigte Farben

| Rolle | Wert |
| --- | --- |
| Hero/Blau | `#2449ed` |
| Dunkler Text | `#14151a` |
| me:works / meworks.tv Orange | `#ef6c2f` |
| Olive Flächen | `#4c5534` |
| Papier | `#f5f5f1` |
| Linien | `#d7d8d4` |
| Hellgrün | `#d5f266` |

Die Nutzerin wollte die Farben später noch genauer prüfen. Diese Prüfung ist noch offen; keine neue Palette als bereits bestätigt behandeln.

### Inhaltliche Entscheidungen

- Firmenmarke orange und zweizeilig: `me:works` / `media productions`.
- `meworks.tv` im Kontaktbereich orange.
- Rolle: **Business Managerin und Finanzmanagerin**, nicht Herstellungsleiterin.
- Projekttext: **Business- und Finanzmanagement** bei M.E. Works.
- Erster Projekt-Einblick: Autorin und Producerin des Reiseformats **„2für300“ (WDR)**.
- Zum Produktionsumfeld von meworks gehören **„Die Spur“ (ZDF)**, **„Besser? So!“ (RTL)** und **„Die Lebensretter von Murnau“ (ZDF)**.
- Firmenumfeld nicht als persönliche Mitarbeit an jedem Format darstellen.
- Finanztool heißt auf der Portfolio-Seite **Conever**, nicht CTRL Flow.
- Drittes Projekt: **Cologne Ceramic Art**, ausdrücklich in Entwicklung.
- Kontaktüberschrift mit zwei getrennten hellgrünen Hinterlegungen: **„Eine gute Idee“** und **„ist ein Anfang.“** Schwarzer Text, damit „gute“ vollständig lesbar bleibt.
- Keine persönliche E-Mail-Adresse oder LinkedIn-URL ergänzen: Es lag keine konkrete Adresse vor. Kontaktlink ist die Firmenwebsite.

### Prüflimit des Portfolios

Für die letzte Masked-Heading-Variante wurden Struktur, Sprungziele, eingebettete Medien und JavaScript-Syntax geprüft. Für diese Variante wurde damals kein vollständiger visueller Browser-Test abgeschlossen. Die späteren umfassenden Browser- und axe-Prüfungen betrafen das Carbon-Designsystem, nicht automatisch das Portfolio.

## 11. Startanweisung für Claude

> Lies zuerst diese `claude.md` und danach `design-system.html`. Übernimm den vorhandenen Stand. Das aktuelle Projekt ist ein lokales Carbon-orientiertes Designsystem in einer einzigen HTML-Datei. Das frühere Britta-Ebel-Portfolio ist ein separates Projekt. Ändere die Dateien erst entsprechend meinem nächsten konkreten Wunsch und zeige mir anschließend das Ergebnis.
