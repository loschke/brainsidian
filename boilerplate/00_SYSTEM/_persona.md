---
type: system
layer: schema
title: Persona-Marker
description: Legt fest, welche Variante dieser Vault ist. Steuert das Onboarding.
tags: [system]
created: {{TODAY}}
updated: {{TODAY}}
status: aktiv
---

# Persona-Marker

Dieser Wert sagt Claude, welche Variante des Vaults vorliegt. Das Onboarding stellt danach die passenden Fragen.

```yaml
persona: boilerplate    # boilerplate | fuehrungskraft | privat | team
```

**persona: boilerplate**

Das reine Boilerplate ohne Zielgruppen-Zuschnitt. Wer von hier aus eine eigene Variante baut, ändert diesen Wert und ergänzt die Variante laut `boilerplate/README.md`.
