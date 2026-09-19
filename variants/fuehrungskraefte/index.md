---
type: index
layer: schema
title: Katalog
description: Eine Zeile pro Notiz im gesamten Vault. Einstiegspunkt für Claude.
tags: [system, katalog]
created: 2026-06-17
updated: 2026-06-17
status: aktiv
---

# Katalog

Jede Notiz im Vault mit einer Zeile. Das ist die Landkarte, die Claude als Erstes liest,
bevor er sucht. Menschen fangen dagegen bei [[START-HIER]] an.

Gepflegt von Claude bei `ingest` und abgeglichen bei `lint`, nicht von Hand.

## Format

Eine Zeile pro Notiz, Felder mit `|` getrennt, in dieser Reihenfolge:

```
- Pfad | type | status | updated | [[Titel]] – ein Satz, worum es geht.
```

Der Pfad steht vorn, damit der Treffer direkt zu öffnen ist. Die Trennung mit `|` macht
die Zeile mit einfachen Textwerkzeugen filterbar, ohne dass jemand YAML lesen muss.

Beispiele:

```
- 02_PEOPLE/anna-berger.md | person | aktiv | 2026-09-12 | [[Anna Berger]] – Teamleitung Fertigung, verantwortet den Rollout.
- 03_DECISIONS/tool-wechsel-2026.md | entscheidung | erledigt | 2026-07-03 | [[Tool-Wechsel 2026]] – Warum wir bei der bestehenden Lösung geblieben sind.
- 08_KNOWLEDGE/delegation-stufen.md | notiz | aktiv | 2026-08-30 | [[Delegation in Stufen]] – Fünf Stufen von Auftrag bis Vollmacht.
```

Wer nach einem Menschen oder einem Vorhaben sucht, filtert nicht hier, sondern über die
Felder `people` und `project` im Frontmatter der Notizen. Der Katalog sagt, was es gibt,
die Felder sagen, wozu es gehört.

## Notizen

> Leer, solange der Vault frisch ist. Das Onboarding legt die ersten Zeilen an,
> danach wächst der Katalog mit jedem `ingest`.

-
