# Vorgehen: Aus Vorjahresmaterial einen Lernpfad bauen

Diese Datei dokumentiert, wie dieser Lernpfad (`index.html`) aus dem
Vorjahresmaterial entstanden ist — als Vorlage für weitere Lektionen
(LP 01, 02, Unit 1&ndash;5 usw.). Bei künftigen Anfragen wie „bau mir die
Stunde X aus dem Material in iCloud-Ordner Y" dieses Vorgehen wiederholen.

## Wo die Rohdaten liegen

Pro Lektion liegt in iCloud unter
`Material SEK I/Englisch/year6/<Unit>/<NN-Lektionsname>/` typischerweise:
- `<Name> presentation.goodnotes` + `<Name> presentation.pdf` (GoodNotes-Export,
  **die PDF-Version lesen**, nicht versuchen, `.goodnotes` direkt zu öffnen)
- `<Name> solutions.pdf` (Musterlösungen — im Original per Farbbalken verdeckt,
  in der Lösungsdatei aufgedeckt)
- `Plickers.pdf` (Multiple-Choice-Fragen für den Plickers-Kartensatz)
- `stuff/` (Rohbilder, Scans, teils mit **echten Klassenlisten/Rosters** — z. B.
  `English 6.3 Roster - Plickers.pdf`. Nie anfassen für den öffentlichen Lernpfad.)

Ergänzend ggf. externe Handreichung-PDFs (Verlags-Lehrerhandreichung, vom
Nutzer z. B. vom Schreibtisch übergeben) mit der didaktischen Verlaufsplanung
(Einstieg / Erarbeitung / Überleitung / Sicherung, Musterlösungen, Hinweise
zur Differenzierung).

## Arbeitsschritte

1. **PDFs lesen.** Read-Tool mit `pages`-Parameter nutzen. Falls Fehler
   „pdftoppm is not installed": einmalig `brew install poppler` ausführen,
   danach erneut lesen — die reine Metadaten-Antwort ohne Bilder bedeutet,
   dass nichts gerendert wurde, nicht dass die PDF leer ist.
2. **Didaktisches Gerüst aus der Handreichung übernehmen** (Einstieg →
   Erarbeitung → Sicherung als Blockreihenfolge im Lernpfad), aber:
3. **Copyright-Regel (kritisch, da Repo public):** Der Lernpfad reproduziert
   **niemals** Verlagsinhalte wörtlich/als Bild — keine Textbuch-/Workbook-
   Scans, keine Foto-Illustrationen des Lehrwerk-Casts, keine Songtexte,
   keine wortgleich übernommenen Musterlösungssätze. Stattdessen:
   - eigene Beispielsätze zum selben Grammatik-/Wortschatzpunkt schreiben,
   - eigene, simple SVG-Illustrationen statt Fotos zeichnen (Stil: siehe
     `Informatik/SEK-I/ITG/hallo-computer/01anmelden-umschauen-loslegen.html`),
   - bei „Kennenlern"-/Rollenspielen eigene, wiederverwendbare Szenarien statt
     der Lehrwerk-Figuren (Namen, Beziehungen) verwenden — oder, wo passend,
     die Übung auf die *echten* Schüler:innen selbst beziehen (z. B. „Two
     truths and a lie" über sich selbst statt über Buchfiguren).
   - Reine Wortschatz-Übersetzungspaare (ein Wort → eine deutsche Übersetzung)
     sind unproblematisch, da nicht schöpferisch genug für Urheberrechtsschutz.
   - Reale, überprüfbare Fakten (z. B. dass Brighton einen Pier und einen
     Kiesstrand hat) sind ebenfalls unproblematisch — nur eigene Formulierung.
4. **Plickers-Fragen digitalisieren.** Die Plickers-MC-Fragen liefern die
   *Fragetypen* (Bildverständnis, Grammatik-Lückensatz) — als natives
   `.quizblock`-Multiple-Choice im Lernpfad nachbauen, mit eigener
   Formulierung/Illustration (siehe Punkt 3).
5. **Sprache der sichtbaren Texte: Englisch** (Zielsprache, siehe
   `English/CLAUDE.md`) — nur Kommunikation mit dem Nutzer bleibt Deutsch.
6. **Stilvorlage strikt übernehmen**, nicht neu erfinden:
   - Lernpfad-Einzelseite: `Informatik/SEK-I/ITG/hallo-computer/01anmelden-umschauen-loslegen.html`
     (CSS-Variablen `--key/--edge/--tint/--ktext` pro Unit anpassen, sonst
     Klassennamen/Struktur 1:1: `.block`, `.quizblock`/`.q`/`.opts`, `.steps`,
     `.merk`, `.selfcheck-wrap` mit `localStorage`-Key `en6_lp_<NN>`, `.lp-nav`).
   - Kursübersicht: `Informatik/SEK-I/ITG/itg-kursuebersicht.html`
     (Halbjahres-Umschalter `.sem-tile`/`.sem-content`, `.unit`/`.lp`-Kacheln).
   - Neue interaktive Elemente (z. B. Aufdecken-Button für Musterlösungen)
     als eigene CSS-Klasse ergänzen, aber demselben Look (Fredoka/Nunito/
     JetBrains Mono, abgerundete Karten mit „Schatten"-Rand) folgen.
7. **Ordnernamen synchron halten.** Lokal und iCloud bekommen denselben
   Bindestrich-Namen (`00-Welcome-back-to-Brighton` statt `00 Welcome back
   to Brighton`) — bei neuen Lektionsordnern in iCloud zuerst umbenennen,
   dann das lokale Pendant mit demselben Namen anlegen.
8. **Kursübersicht aktualisieren.** Neue fertige Lernpfade bekommen einen
   echten Link + „Lernpfad →"-Badge; noch nicht gebaute Lektionen bleiben
   unverlinkte Platzhalter-Kacheln.

## Nicht vergessen

- Nach Fertigstellung: `git status` prüfen, dass keine PDFs/Bilder aus
  iCloud versehentlich mitkopiert wurden.
- Push aus diesem Environment schlägt an der fehlenden Git-Keychain-
  Authentifizierung fehl — der Nutzer stößt `git push` selbst an
  (`! git -C /Users/poremski/Schule/English push origin main`).
