---
type: log
title: Aktivitätslog
description: Fortlaufendes Protokoll der Eingriffe am Vault.
tags: [system, log]
created: 2026-06-17
status: aktiv
---

# Aktivitätslog

Append-only. Neueste Einträge oben. Jeder größere Eingriff bekommt eine Zeile.
Präfix ist eine der drei Operationen: `ingest`, `query`, `lint`.

Format:

```
## [YYYY-MM-DD] ingest | Kurztitel
- Was passiert ist (kurz). Quelle: ...
```

---

## [2026-06-17] setup | Vault angelegt
- Boilerplate initialisiert. Warte auf Onboarding.
