# English — Unterrichtsmaterial

## Was hier liegt
- Interaktive Lern- und Übungsmaterialien als HTML.
- Gegliedert nach Schulstufe bzw. Klassenstufe.

## Repo-Struktur
- Einzige Inhaltsordner: `SEK-I/` und `SEK-II/`. Das ist die Struktur, die
  zwischen mehreren Rechnern über GitHub synchronisiert wird (push/pull).
- Keine losen Dateien im Repo-Root ablegen (Erfahrung: das ist schon mal
  über Jahre zugemüllt und musste aufwendig in `SEK-I/…` einsortiert werden).
  Neues Material immer direkt unter `SEK-I/year<N>/…` bzw. `SEK-II/…` anlegen.
- Root enthält nur Metadateien: `CLAUDE.md`, `.gitignore`.

## Konventionen
- Kommunikation mit mir: Deutsch.
- Oberflächensprache der Materialien: Englisch (Zielsprache).
- HTML immer als einzelne, offline lauffähige Datei — keine CDN-Abhängigkeiten.
- Typst (.typ) für PDF-Dokumente, sobald welche dazukommen.
  Build-Ergebnisse (PDFs) gehören nach iCloud, nicht ins Repo.

## Öffentlich — Vorsicht
- Dieses Repo ist public. Keine Schüler-Klarnamen, Noten oder
  personenbezogenen Daten in Dateien oder Commit-Nachrichten.
