---
type: index
layer: schema
title: Katalog
description: Eine Zeile pro Notiz im gesamten Vault. Einstiegspunkt für Claude.
tags: [system, katalog]
created: {{TODAY}}
updated: {{TODAY}}
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

Beispiel:

```
- 02_KNOWLEDGE/wochenplanung-prinzip.md | notiz | aktiv | 2026-03-14 | [[Wochenplanung nach Prinzip]] – Warum ein fester Wochenrahmen mehr trägt als Tagespläne.
```

## Notizen

> Leer, solange der Vault frisch ist. Das Onboarding legt die ersten Zeilen an,
> danach wächst der Katalog mit jedem `ingest`.

-
