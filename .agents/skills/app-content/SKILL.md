---
name: app-content
description: Use for any content work in this app - researching, writing, extending, correcting or reviewing its competencies, chapters, pages, rounds, questions, exercises, figures, terms or sources. This app's own content decisions; they take precedence over the generic lernapps content skills. Load it before you change any content.
---

# Content guide of this app

Orchesteraufbau: Instrumentengruppen nach der Tonerzeugung, Instrumente des Sinfonieorchesters, Sitzordnung.
Wiederholung vor einer Lernkontrolle in Klasse 8; die Selbsteinschätzung ist der Probetest. Archetyp `explainer`,
Strang `musik/klang`, nur Deutsch, keine eigene Komponente. Schwester-Apps: `musik-tonhoehe-harmonik`,
`musik-rhythmus-takt`.

## Curriculum

- Hessen, Gymnasium, Jahrgang 8, Musik. Kein Lehrplan nötig: Strang der Lernlandkarte.
- Kompetenzen der Karte in Richtstufe 5-6: Wiederholung.
- Aufbau nach zwei Arbeitsblättern des Erstellers (Instrumentenliste mit Gruppen; Sitzplan eines Sinfonieorchesters
  mittlerer Größe). Das Material bleibt lokal: nie committen, nicht zitieren; nur der Aufbau ist übernommen.

## Competencies

Ein Kapitel `orchester`; Ids und Sätze wörtlich von `https://lernapps.net/apps/map/musik.json`.
- `src/orchester/das-brauchst-du.yaml`: recap `musik/klangquellen-unterscheiden`, `musik/schwingung`.
- `instrumentenfamilien` – Ich kann Instrumente nach der Art, wie sie klingen, in Familien einordnen.
  → `src/orchester/saiten-und-blasinstrumente.yaml`, `src/orchester/weitere-instrumente.yaml`.
- `ensembles-besetzungen` – Ich kann Besetzungen wie Sinfonieorchester, Band oder Chor erkennen und ihre Instrumente
  oder Stimmen nennen. → `src/orchester/instrumente-im-orchester.yaml`, `src/orchester/sitzordnung.yaml`
  (Musterseite; nur Sinfonieorchester).

## Content structure

- Inhaltsseiten: `einstieg`, `regel`, `beispiel`, `uebung` (mindestens vier Übungen, leicht → schwer); Ziel am
  Anfang, Ausblick am Ende; höchstens 350 Wörter Lesetext, höchstens vier Textblöcke am Stück.
- Wiederholungsseite am Kapitelanfang, ohne Übung. Keine Geschichte. Anrede „du“.
- Selbsteinschätzung in `src/orchester/chapter.yaml`, 2–3 Übungen je Inhaltsseite, bevorzugt `generated` und
  Zuordnungen.

## Terminology

- Gruppen: Saiteninstrumente (Streichinstrumente, Zupfinstrumente), Blasinstrumente (Holzblasinstrumente,
  Blechblasinstrumente), Tasteninstrumente, Schlaginstrumente (aus Holz, aus Metall, mit Fell; tonerzeugend oder
  geräuscherzeugend), Harmonikainstrumente, elektronische Instrumente.
- Orchestergruppen: Streicher, Holzbläser, Blechbläser, Pauken und Schlagwerk.
- Instrumente: Geige (Violine), Bratsche, Cello (Violoncello), Kontrabass, Querflöte, Oboe, Klarinette, Fagott,
  Waldhorn (Horn), Trompete, Posaune, Tuba, Pauken. Im Sitzplan: 1. Violinen, 2. Violinen, Bratschen, Violoncelli,
  Kontrabässe, Flöten, Oboen, Klarinetten, Fagotte, Hörner, Trompeten, Posaunen, Pauken, Dirigent.
- Einteilung immer nach der Tonerzeugung, nicht nach dem Material.

## Exercise patterns

- **Instrument einordnen**: `generated` aus `src/data/instrumente.yaml`, `compare: choice` mit den Gruppen- oder
  Untergruppennamen; Fehler: die naheliegende falsche Gruppe (Feld `falsch`) mit Meldung (Feld `warum`).
- **Zuordnen**: `matching` (Tonerzeugung ↔ Untergruppe, Instrument ↔ Orchestergruppe, Schlaginstrument ↔ Material).
- **Auswählen, entscheiden**: `multiple-choice`, `single-choice` mit typischem Fehler als Option, `true-false`.
- **Sitzplan beschriften**: `matching` mit `pairsFrom: material` aus einer `labelled-figure` (`sitzplan-leer.svg`,
  `legend: false`, Buchstaben A–N); `ordering` von vorn nach hinten.

## Figures

- `src/images/sitzplan.svg` (farbig nach Orchestergruppen, für die Regel mit Legende) und
  `src/images/sitzplan-leer.svg` (einfarbig, für Aufgaben), selbst gezeichnet, CC BY 4.0: Bühne von oben, Dirigent
  vorn, Streicher im inneren Halbkreis, Holzbläser hinten links, Blechbläser hinten rechts, Pauken ganz hinten. Die
  Markierungen setzt die `labelled-figure` (x/y in Prozent, siehe die Seite `sitzordnung`).
- `src/images/familien.svg`: Baum der Gruppen und Untergruppen aus Text-Kästen, selbst gezeichnet, CC BY 4.0.
- Keine Bilder von Instrumenten. Farben nie allein: die Legende nennt die Gruppen.

## Sources

Geöffnet 2026-11-24, CC BY-SA 4.0, nur Fakten:
- Lernlandkarte Musik, https://lernapps.net/apps/map/musik.json.
- „Holzblasinstrument“, „Blechblasinstrument“, „Streichinstrument“, „Zupfinstrument“, „Schlaginstrument“,
  „Harmonikainstrument“ auf https://de.wikipedia.org/wiki/… – Einteilung nach der Tonerzeugung.
- „Orchester“ (https://de.wikipedia.org/wiki/Sinfonieorchester), „Amerikanische Aufstellung“
  (https://de.wikipedia.org/wiki/Amerikanische_Aufstellung) – Gruppen, 2. Violinen neben den 1.
- Plätze von Bläsern und Pauken: nach dem Material des Erstellers (in der Quelle nicht beschrieben).

## Adding a chapter or round

1. Kompetenzen des Strangs `musik/klang` von der Karte (z. B. `stimmlagen`, `dynamik-zeichen`), neues Kapitel in
   `src/app.yaml`.
2. Wiederholungsseite für Voraussetzungen.
3. Seiten mit `einstieg`, `regel`, `beispiel`, `uebung`; neue Instrumente in `src/data/instrumente.yaml`.
4. 1–3 Übungen je Seite in `selfAssessment`.
5. `npx --no -- lernapps check`, Screenshots ansehen, committen.

## Rules learned from mistakes

Aus den Schwester-Apps übernommen:
- Erklärfiguren benennen nur Anker; Aufgaben-Figuren verraten nichts (einfarbiger Sitzplan in Übungen).
- Merke-Kästen vor die Figur, die sie erklären; Fehlermeldungen nennen nur, was schon erklärt ist.
- Der Einstieg ist ohne Raten lösbar; Übungen haben einen Denkschritt, nicht nur Abschreiben.
- Tabellen höchstens zwei lange Spalten (360 px).
- Die Sitzordnung folgt dem Material des Erstellers (Flöten außen links, Posaunen außen rechts), auch wenn echte
  Orchester die Holzbläser oft in zwei Reihen in der Mitte setzen; links/rechts aus Sicht von Publikum und Dirigent.
- Marker der Regel-Figur sind Ziffern (1–4), damit sie nicht mit den Buchstaben der Übung kollidieren.
