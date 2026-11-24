---
# Read by the hooks, the review, the evals. Schema: @lernapps/tooling/guidance/plan-front-matter.v1.schema.json
# Written by `lernapps plan` and the hooks. Never change a key or a value by hand.
# Archetype, null until chosen in Explore. Allowed values: explainer, interactive, quiz.
archetype: explainer
# Current phase. Allowed values: explore, plan, code, commit.
phase: code
# prePushFailures: failed pre-push runs, written by the hook.
prePushFailures: 0
# failedChecks: failed rules and runs, written by lernapps check and the hooks.
failedChecks: {}
---

# Plan: musik-klang, first version

<!--
For you, the assistant. The process is in AGENTS.md; this plan holds the method.
- `npx --no -- lernapps plan next` prints the task to do now, `plan done` ticks it and prints the next one.
- You write only below Goal, Key decisions, Notes, Answers, Entry draft, Content method and Retrospective, in the
  creator's language. Delete the comment of a section once the section is filled.
- Work on the branch `work`, locally: push nothing before Commit.
-->

*Started 2026-11-24. Explore, Plan, Code, Commit.*

## Goal

Lernende der 8. Klasse ordnen Instrumente nach ihrer Tonerzeugung in Gruppen und Untergruppen, erkennen die
Instrumente des Sinfonieorchesters und beschriften seine Sitzordnung. Ein Probetest zeigt, was für die Lernkontrolle
sitzt.

## Key decisions

- Archetyp `explainer` wie die Schwester-Apps: Erklärseiten, Zuordnen mit immer neuen Instrumenten, Sitzplan als
  beschriftete Figur, Selbsteinschätzung als Probetest; ohne eigene Komponente.
- Kein `scope`: keine `open-task`; das Material des Erstellers bleibt lokal, die App übernimmt nur seinen Aufbau.
- Name `musik-klang`: Schema `musik-<Strang>`.

## Notes

### Material des Erstellers (bleibt lokal, wird nicht committet) und Lernlandkarte

Der Ersteller hat zwei Arbeitsblätter gezeigt (Fotos, nur in dieser Sitzung): einen Sitzplan „Sinfonieorchester
mittlerer Größe“ zum Beschriften und eine Liste der Musikinstrumente mit Überschriften zum Ergänzen. Daraus
abgeleitet, ohne Wortlaut:

- Instrumentengruppen mit Untergruppen: Saiteninstrumente (Streich-, Zupfinstrumente), Blasinstrumente (Holz-,
  Blechblasinstrumente), Tasteninstrumente, Schlaginstrumente (drei Untergruppen, nach Material; tonerzeugend oder
  geräuscherzeugend), Harmonikainstrumente, elektronische Instrumente; dazu: welche Instrumente gehören ins Orchester.
- Sitzordnung: Streicher vorn (1. und 2. Violinen links, Bratschen Mitte, Violoncelli rechts, Kontrabässe ganz
  rechts), Holzbläser dahinter links (Flöten, Oboen, Klarinetten, Fagotte), Blechbläser dahinter rechts (Hörner,
  Trompeten, Posaunen), Pauken ganz hinten in der Mitte, Dirigent vorn in der Mitte.
- Kompetenzen der Karte (Strang `musik/klang`, Richtstufe 5-6): `instrumentenfamilien` (Schritt 3),
  `ensembles-besetzungen` (Schritt 4); Voraussetzungen `klangquellen-unterscheiden`, `schwingung` → Wiederholung.
- Keine dieser Kompetenzen übt bisher eine App.

### Wie die Lernenden üben (Skill `lernapps-exercise-patterns`)

- Zuordnen (Instrument ↔ Gruppe/Untergruppe): `matching`, `generated` mit Auswahl aus einer Datendatei der
  Instrumente (immer neue Instrumente), `multiple-choice` („Welche gehören ins Orchester?“).
- Entscheiden: tonerzeugend oder geräuscherzeugend; gehört ins Orchester oder nicht (`generated`, `true-false`).
- Sitzordnung: eigener Sitzplan als SVG (selbst gezeichnet), als `labelled-figure` mit Buchstaben und `matching`
  aus dem Material (`pairsFrom: material`): jeder Buchstabe eine Gruppe; dazu `ordering` (von vorn nach hinten).
- Keine eigene Komponente nötig: eingebaute Blöcke reichen.
- Fehler, die die Rückmeldung abfängt: Saxophon und Querflöte als Blechblasinstrument (sie sind aus Metall, zählen
  aber nach der Tonerzeugung zu den Holzblasinstrumenten); Harfe als Streichinstrument; Klavier als
  Saiteninstrument statt Tasteninstrument (in dieser Einteilung); Pauken als geräuscherzeugend; Bratsche und Cello
  im Sitzplan vertauscht; Hörner zu den Holzbläsern.

### Strang und Kompetenzen (ein Kapitel `orchester`)

Strang `musik/klang`. Sätze wörtlich von der Karte.
- Wiederholung `das-brauchst-du`: recap `klangquellen-unterscheiden` („Ich kann Stimme, Körper, Gegenstände und
  Instrumente als Klangquellen unterscheiden.“), `schwingung` („Ich kann erklären, dass jeder Klang durch eine
  Schwingung entsteht.“).
- `instrumentenfamilien` – Ich kann Instrumente nach der Art, wie sie klingen, in Familien einordnen. → zwei Seiten:
  `saiten-und-blasinstrumente`, `weitere-instrumente` (Tasten, Schlag, Harmonika, elektronisch).
- `ensembles-besetzungen` – Ich kann Besetzungen wie Sinfonieorchester, Band oder Chor erkennen und ihre Instrumente
  oder Stimmen nennen. → zwei Seiten: `instrumente-im-orchester`, `sitzordnung` (nur Sinfonieorchester).

### Didaktik

- Familien nach der Tonerzeugung herleiten (streichen, zupfen, Luft an einer Kante oder einem Rohrblatt, Lippen im
  Kesselmundstück, schlagen, Tasten, durchschlagende Zunge, Strom), nicht nach dem Material: darum ist das Saxophon
  ein Holzblasinstrument.
- Schlaginstrumente: Material (Holz, Metall, Fell) und tonerzeugend (bestimmte Tonhöhe) oder geräuscherzeugend.
- Orchester: vier Gruppen (Streicher, Holzbläser, Blechbläser, Pauken/Schlagwerk), Instrumente je Gruppe.
- Sitzordnung: Streicher vorn im Halbkreis, Holzbläser hinten links, Blechbläser hinten rechts, Pauken ganz hinten,
  Dirigent vorn; Grund: leise Instrumente vorn, laute hinten (guess, als Merkhilfe).

### Umfang

- Drin: die sechs Gruppen mit Untergruppen und den Instrumenten des Materials; Orchesterinstrumente; Sitzordnung
  wie im Material (amerikanische Aufstellung: 2. Violinen neben den 1.).
- Draußen: Band, Chor, Klänge hören, Bilder der Instrumente; deutsche Aufstellung nur als Hinweis (guess).

### Quellen (geöffnet 2026-11-24, CC BY-SA 4.0; nur Fakten)

- Lernlandkarte Musik, https://lernapps.net/apps/map/musik.json – verified.
- „Holzblasinstrument“, „Blechblasinstrument“, „Streichinstrument“, „Zupfinstrument“, „Schlaginstrument“,
  „Harmonikainstrument“ (https://de.wikipedia.org/wiki/…) – Einteilung nach der Tonerzeugung, Saxophon und Querflöte
  als Holzblasinstrumente – verified.
- „Orchester“ (https://de.wikipedia.org/wiki/Sinfonieorchester) und „Amerikanische Aufstellung“
  (https://de.wikipedia.org/wiki/Amerikanische_Aufstellung) – Gruppen, 2. Violinen neben den 1. – verified; die
  Plätze von Bläsern und Pauken stehen dort nicht, die App folgt dem Material des Erstellers.

## Explore

<!--
- Find out what the app teaches, for whom, how much and how it looks. Ask; write no code, run no `create`.
- An answer counts only in the creator's words under "Answers". At most 2 questions per message, one topic each.
-->

### Tasks

- [x] Check the start: the folder `.agents/skills/lernapps-app` exists (else stop and tell the creator that the folder
      was not started with `init`), and `git branch --show-current` prints `work` (else `git switch -c work`).
- [x] Load skill `lernapps-app`. Tell the creator in two sentences what a lernapps app is and where it will live: at
      their own address, free and public, and once listed as a copy on lernapps.net. Say that the technical part
      (GitHub) comes at the end and that you do it.
- [x] Interview: ask the topics "Goal" and "Learners" of "Answers".
- [x] Load skill `lernapps-map-assignment` and read the learning map of the subject as it says. The creator brings
      the content themselves (material, a word list, the pages): note under "Notes" which competencies of the map it
      covers. Else write the skill's assignment, with its story; the creator's yes answers the topics Content and
      Amount. A subject without a map: skip this task and say so.
- [x] Load skill `lernapps-exercise-patterns` and read its reference for the subject. Note under "Notes" how learners
      will practise what the goal names.
- [x] Choose the archetype as skill `lernapps-app` says: read the README of each archetype in question, then tell the
      creator in plain words what the chosen one can and cannot do. Write the archetype and its reason under "Key
      decisions".
- [x] Run `npx --no -- lernapps skills --archetype <name>` with the chosen archetype. It installs the archetype's
      skills and adds the archetype's tasks to this plan.
- [x] Load skill `lernapps-explainer-design`. An explainer has the look of the runtime: write "fixed by the
      archetype" under the topic "Look and feel" of "Answers".
- [x] Interview: ask every other topic of "Answers", in order. Leave out only a topic that an answer of the creator
      already covers, and note which answer. A topic nobody answered is asked once before you write an assumption
      with "(guess)".
- [x] Load skill `lernapps-content-research` and research as it says. Write under "Notes": the strand or subject, the
      competencies by chapter with their ids, the sources you opened.
- [x] Write under "Notes" which competency goes on which page and which pages form a chapter, as "Map the content" of
      skill `lernapps-explainer-design` says. Per page, name the prerequisites the app does not practise.
- [x] Write under "Notes", one line per competency: how learners get there (they derive it, they do not only read it
      off), and which misconception the feedback catches.
- [x] Write under "Notes" the scope: what is in, what is out and why, the data range (for example "all main-group
      elements", never a silent "1–20"), the languages.
- [x] **Checkpoint:** research. Show in plain words: the strand or why none, the competencies by chapter, the didactic
      approach, the scope, every "(guess)", the sources and what is unchecked, the archetype and its reason. Stop and
      wait. Changes: change them, then ask again.
      Creator: passt so

### Answers

<!-- The interview: per topic the creator's answer, in their words. Keep the topics. -->

- Goal: what learners do in the app, what they learn.
  - Aus dem Gespräch zur ersten App: „Es geht um eine Lernkontrolle … 6. Orchesteraufbau“; „frei üben und
    Probestest, also beides“; Namensschema mit drei Apps bestätigt; „fang mit Orchesteraufbau an“.
- Learners: subject, school year, prior knowledge.
  - „Gymnasium, 8. Klasse, hessen, Musik“; „Vorwissen ist alles aus der Klasse 7. Was das ist, weiss ich nicht“.
- Model and focus: an app of the catalog (https://lernapps.net/apps/llms.txt) as model; what matters most (exercises,
  - Abgedeckt durch die Antwort zur ersten App: „all diese Sachen sind mir wichtig.“ Vorbild: die Schwester-Apps (guess).
  visualisations, game feel).
- Hurdles: misconceptions and mistakes of the learners; the creator's examples and experiments.
  - „passt so“ zu: Saxophon/Querflöte als Blechbläser, Harfe als Streichinstrument, Pauken als geräuscherzeugend, Bratschen und Celli im Sitzplan vertauscht, Hörner als Holzbläser.
- Content: who writes it (creator, you, from sources); own material (worksheets, tests).
  - Material des Erstellers (zwei Arbeitsblätter, lokal). Vorschlag mit fünf Seiten und Untergruppen der Schlaginstrumente „aus Holz, aus Metall, mit Fell“ – Antwort: „passt so“. Inhalte schreibe ich aus Quellen nach dem Aufbau des Materials.
- Amount: how much content in the first version; what comes later.
  - Fünf Seiten, ein Kapitel, nur Sinfonieorchester, keine Band, kein Chor: „passt so“.
- Languages: German only, or German and English. Never English only.
  - Abgedeckt durch die Antwort zur ersten App: „nur Deutsch“.
- Look and feel: calm like a worksheet, or like a game (colours, praise, effects); dark mode.
  - fixed by the archetype (explainer)
- Terms: the creator's words for the main things in the app, used everywhere.
  - Untergruppen der Schlaginstrumente „aus Holz, aus Metall, mit Fell“: „passt so“. Instrumentennamen wie im Material: Geige (Violine), Bratsche, Cello (Violoncello), Kontrabass, Waldhorn (Horn) (guess).
- Finding the app: what teachers and parents would search for.
  - Vorschlag: „Orchesteraufbau“, „Sitzordnung Orchester“, „Instrumentengruppen“, „Holzblasinstrumente Blechblasinstrumente“, „Musikinstrumente Klasse 8“ – Antwort: „passt so“.

## Plan

<!--
- Map the confirmed content onto the archetype. No new content questions: a gap in the content goes back to Explore.
- The creator confirms the plan in one read. After the yes you work on your own.
-->

### Tasks

- [x] Map the content as "Map the content" of skill `lernapps-explainer-design` says, and write the result under
      "Content method".
- [x] Choose a pattern per competency as skill `lernapps-exercise-patterns` says, and add it to "Content method".
- [x] Add to "Content method" one line per page, as "Engagement" of skill `lernapps-explainer-design` says: the
      opening task, the change of activity, the reward, the story.
- [x] Add the tasks of Code, each one a piece of work that ends in a commit. First the pattern: one complete page or
      screen, `npx --no -- lernapps plan add --at pattern "<task>"`. Then the others, one call each:
      `npx --no -- lernapps plan add --at pages "<task>"`. Each task says what it builds and what it shows.
- [x] Draw a sketch of each screen, component or interactive exercise: a static SVG or image, or the steps with what
      learners see after each. Keep the files in `.vibe/sketches/`.
- [x] Show the creator, short: goal, competencies by chapter, the Code tasks, the sketches, and the content method in
      plain words (what learners see and do, what the app cannot do). At most 2 questions.
- [x] **Checkpoint:** confirm the plan and the content method. Stop and wait for an explicit yes. Changes: change
      them, then ask again.
      Creator: ja

### Content method

#### Aufbau

`strand: musik/klang`, ein Kapitel `orchester`, Abschnitte `einstieg`, `regel`, `beispiel`, `uebung` wie in den
Schwester-Apps; Anrede „du“; keine Geschichte; keine eigene Komponente.

| Seite (id) | Kompetenz | Voraussetzungen, die die App nicht übt |
|---|---|---|
| `das-brauchst-du` | recap `klangquellen-unterscheiden`, `schwingung` | – |
| `saiten-und-blasinstrumente` | `instrumentenfamilien` | `schwingung` → Wiederholung |
| `weitere-instrumente` | `instrumentenfamilien` | – |
| `instrumente-im-orchester` | `ensembles-besetzungen` | – |
| `sitzordnung` | `ensembles-besetzungen` | – |

Selbsteinschätzung im Kapitel (Probetest), 2–3 `generated` oder Zuordnungen je Inhaltsseite.

#### Datendatei

`src/data/instrumente.yaml`: je Instrument `name`, `gruppe` (Saiteninstrument, Blasinstrument, Tasteninstrument,
Schlaginstrument, Harmonikainstrument, elektronisches Instrument), `untergruppe` (Streichinstrument, Zupfinstrument,
Holzblasinstrument, Blechblasinstrument, aus Holz, aus Metall, mit Fell, sonst = gruppe), `orchester` (ja/nein),
`ton` (tonerzeugend/geräuscherzeugend, nur Schlaginstrumente), `warum` (ein Satz zur Tonerzeugung). Nur die
Instrumente des Materials.

#### Muster je Seite

| Seite | Übungen |
|---|---|
| `saiten-und-blasinstrumente` | `generated` „Zu welcher Untergruppe gehört {{i.name}}?“ (Auswahl, aus Saiten- und Blasinstrumenten); `matching` Tonerzeugung ↔ Untergruppe; `multiple-choice` „Welche sind Holzblasinstrumente?“ (mit Saxophon, Querflöte); `single-choice` Harfe |
| `weitere-instrumente` | `generated` Gruppe eines Instruments (alle Gruppen); `generated` tonerzeugend oder geräuscherzeugend; `matching` Schlaginstrument ↔ Material; `true-false` |
| `instrumente-im-orchester` | `generated` „Gehört {{i.name}} ins Sinfonieorchester?“; `matching` Instrument ↔ Orchestergruppe; `multiple-choice` Blechbläser des Orchesters; `number` „Wie viele Gruppen hat das Orchester?“ |
| `sitzordnung` | `labelled-figure` des Sitzplans (A–L) als `material` eines `matching` mit `pairsFrom: material`; `ordering` von vorn nach hinten; `single-choice` Platz der Pauken; `single-choice` Bratschen/Celli |

#### Figuren

- `src/images/sitzplan.svg` (selbst gezeichnet, CC BY 4.0): Bühne von oben, Halbkreise, Felder mit Buchstaben;
  Dirigentenpult vorn. Auf der Regel-Seite mit Namen (`labelled-figure` mit Legende), in der Übung nur Buchstaben.
- `src/images/familien.svg`: Baum der Gruppen und Untergruppen (Text-Kästen), ohne Bilder von Instrumenten.

#### Engagement

- Saiten/Blas: „Ist das Saxophon aus Holz?“ · ordnen, entscheiden · „Du ordnest nach der Tonerzeugung“.
- Weitere: „Hat eine Trommel einen Ton?“ · zuordnen, entscheiden · „Du kennst alle sechs Gruppen“.
- Orchester: „Gehört die Gitarre ins Sinfonieorchester?“ · zuordnen · „Du nennst die vier Orchestergruppen“.
- Sitzordnung: „Wo sitzen die lauten Instrumente?“ · beschriften, ordnen · Rückblick und Probetest.

#### Was die App nicht kann

Keine Klänge, keine Bilder von Instrumenten, keine Band, kein Chor.

## Code

<!--
- Build the app, locally on `work`, on your own. After each task: `plan done`, then one commit with the work and this
  plan. The hooks check each commit; a failing check is fixed from its message, as skill `lernapps-cli` says.
- What you cannot decide: choose, write it under "Key decisions" with "(guess)", go on.
- The creator asks for a change: say your reading in one sentence first, then change every place it holds for
  (`feedback-applied-everywhere`).
-->

### Tasks

- [x] Load skill `lernapps-cli`. Create the app as its section "Create" says:
      `npx --no -- lernapps create --archetype explainer`.
- [x] Fill the content guide `.agents/skills/app-content/SKILL.md` from "Notes" and "Content method": every heading,
      no "FILL IN" left. Commit it before any content.
- [x] Load skill `lernapps-explainer`.
- [x] Load skill `lernapps-content-questions`. Read whole, with your file tool:
      `.agents/skills/lernapps-explainer/references/blocks.md` and
      `.agents/skills/lernapps-explainer/references/exercises.md`. A foreign language: also
      `references/language-tasks.md` in the same folder. A component in the plan: also `references/components.md`.
- [x] Decide whether the app needs `scope`, as "`scope`" in
      `.agents/skills/lernapps-explainer/references/structure.md` says. Write the choice under "Key decisions".
- [x] Musterseite orchester/sitzordnung: Sitzplan-SVG, labelled-figure mit Legende in der Regel, matching mit pairsFrom material, ordering, single-choice
<!-- tasks: pattern (1 added): the one page or screen that is the pattern for the others -->
- [x] **Checkpoint:** the pattern page. Load skill `lernapps-learner-check` and do its learner check on the page. Fix
      what it finds. Then show the creator the page and ask whether the others may follow it. Stop and wait. A
      change: change the pattern first.
      Creator: ja
- [x] Kapitel orchester: Wiederholungsseite das-brauchst-du (recap klangquellen-unterscheiden, schwingung)
- [ ] Seite orchester/saiten-und-blasinstrumente: Datendatei instrumente.yaml, Familien-Baum, generated Untergruppe, matching, multiple-choice, single-choice
- [ ] Seite orchester/weitere-instrumente: generated Gruppe und tonerzeugend/geräuscherzeugend, matching Material, true-false
- [ ] Seite orchester/instrumente-im-orchester: generated Orchester ja/nein, matching Orchestergruppe, multiple-choice, number; Selbsteinschätzung des Kapitels
<!-- tasks: pages (4 added): the other pages or screens, after the pattern -->
- [ ] Update the content guide so that it describes the app as built (`app-content-matches`).
- [ ] Run `npx --no -- lernapps check` until it passes.
- [ ] Look at every screen and state, at 360 px and on a desktop, as "Look at the app" of skill `lernapps-cli` says.
      Compare each with its sketch.
- [ ] Do the whole-app check of skill `lernapps-learner-check`. Fix what it finds and write under "Notes" what you
      fixed.

## Commit

<!--
- Put the app on GitHub, publish it with the creator's yes, then list it. A push to `main` publishes.
- Open the pull requests (to `main`, to the catalog) without asking: they publish nothing.
- The creator asked to stop before publishing (a trial): stop here and say so.
-->

### Tasks

- [ ] Load skill `lernapps-explainer-self-assessment`. Add the self-assessment as it says, or write under "Key
      decisions" why the app has none. Commit.
- [ ] Load skill `lernapps-github`. Set up the repository and Pages as it says. Ask for the repository's name and
      every click only the creator can make, in one message.
- [ ] Push `work`, open the preview pull request and see its checks to green, as skill `lernapps-github` says.
- [ ] **Checkpoint:** publish. Show what the app does and the preview link from the comment "Vorschau der App". Ask
      whether it may go online. Stop and wait for the yes.
- [ ] Load skill `lernapps-commit`. Publish as skill `lernapps-github` says: `work` into `main` as one squash commit,
      the run of `Pages` watched to its end.
- [ ] Open the address the job `deploy` printed and confirm that the app shows. Never use a derived address.
- [ ] Load skill `lernapps-listing`. Write the entry under "Entry draft" as it says, with the creator's answer to
      "Finding the app".
- [ ] Fill the retrospective.
- [ ] Commit this plan on `main` and push it: the listing check and the review read it there.
- [ ] **Checkpoint:** list. Open the listing pull request as skill `lernapps-listing` says, without asking first: the
      pull request is the review. See it to "bestanden", then show the creator the pull request and its result.
- [ ] If the plan changed since its last push, commit it on `main` and push again.

### Entry draft

<!-- YAML valid against the entry schema the listing skill names. Only known values, never invented. -->

```yaml
```

## Retrospective

<!-- At the end of Commit, before the listing pull request. Facts, short, no names. Read by review and evals. -->

### Phases reached

<!-- Last phase completed, checkpoints passed. E.g. "commit; confirmed, published". -->

### Creator turns after the plan

<!-- Number of creator messages after the confirmation, topic of each. Target: at most 3. -->

### Where I had to guess

<!-- Each gap in plan, skills, messages or answers, and your choice. "None" if none. -->
