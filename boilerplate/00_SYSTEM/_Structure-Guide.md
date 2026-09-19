---
type: index
layer: schema
title: Struktur-Guide
description: Wie dieser Vault aufgebaut ist und warum.
tags: [system, struktur]
created: {{TODAY}}
updated: {{TODAY}}
status: aktiv
---

# Struktur-Guide

Dieser Vault ist eine Denkwerkstatt, kein Ablageordner. Wer das Prinzip versteht, hält ihn ohne Mühe sauber.

## Die drei Schichten

1. **Quellen (`Sources/`)** sind das Rohmaterial: PDFs, Artikel, Transkripte, hingeworfene Notizen. Sie bleiben unverändert. Wenn du etwas weißt, soll nachvollziehbar bleiben, woher.
2. **Wissen** ist das, was Claude daraus baut: verlinkte Notizen in `02_KNOWLEDGE/` und den anderen Inhaltsordnern. Diese Schicht wächst und wird gepflegt.
3. **Schema (`CLAUDE.md`, `00_SYSTEM/`)** sind die Spielregeln: Struktur, Templates, Profil. Selten geändert, immer maßgeblich.

Diese Trennung stammt aus zwei bewährten Mustern: dem **LLM-Wiki** (Quellen, Wiki, Schema; plus die Operationen aufnehmen / wiederfinden / aufräumen) und dem **Open Knowledge Format** (Markdown mit `type`-Frontmatter und Inhaltskarten). Beides ist hier nur leichtgewichtig eingebaut: Es kostet etwas Frontmatter-Disziplin und bringt Zukunftssicherheit.

## Drei Ordnungsmittel

| Mittel | Frage | Beispiel |
|--------|-------|----------|
| **Ordner** | Wo gehört es hin? | `03_PROJECTS/` |
| **Tags** | Was ist es? | `tags: [strategie, 2026]` |
| **Links** | Was hängt zusammen? | `[[Andere Notiz]]` |

Ordner sind grob (ein Ort pro Notiz). Tags und Links sind beliebig viele. Wer ordnet, denkt zuerst an den Ort, dann an die Verbindungen.

## Die Inhaltskarte (`index.md`)

Jeder Ordner hat eine `index.md`. Sie ist die Landkarte des Ordners: die wichtigsten Notizen mit je einer Zeile. Wer einsteigt, liest zuerst die Karte, nicht die Dateiliste. Claude hält sie aktuell.

## Status-Werte

Im Frontmatter steuert `status` den Lebenszyklus einer Notiz:

`entwurf` → `aktiv` → `ruht` / `erledigt` / `veraltet` → `archiviert`

`veraltet` heißt: die Notiz stand mal richtig da, gilt aber nicht mehr. Sie bleibt liegen,
damit nachvollziehbar bleibt, was man mal dachte. Archiviertes wandert nach `99_ARCHIVE/`,
wird aber nicht gelöscht.

Zwei Felder daneben tragen den Lebenszyklus mit: `updated` sagt, wann der Inhalt zuletzt
geprüft wurde, `source` sagt, woraus er stammt. Ohne beides kann `lint` Überholtes nicht
von Gültigem trennen.

## Erweitern

Diese Grundstruktur ist absichtlich knapp. Jede Variante (Führungskraft, Privat, Team) ergänzt eigene Ordner und Notiztypen. Wer eine neue Variante baut, startet vom Boilerplate und fügt nur hinzu, was die Zielgruppe wirklich braucht. Mehr ist hier weniger.
