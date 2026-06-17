# Brainsidian Templates

Vorbereitete Obsidian-Vaults, die du gemeinsam mit Claude betreibst. Du bringst Quellen und stellst Fragen, Claude pflegt deine Ablage: erfassen, ordnen, verknüpfen, wiederfinden, aufräumen. Ein geführtes Onboarding füllt deinen Vault beim ersten Start mit Leben, damit du sofort siehst, wie es funktioniert.

Kein proprietäres Format, keine Datenbank. Nur Markdown, das du behältst.

---

## Welche Variante ist für dich?

| Variante | Für wen | Schwerpunkt |
|----------|---------|-------------|
| **Führungskräfte** | Wer Menschen führt | Team und Stakeholder, Entscheidungen, Gesprächsvorbereitung, Strategie |
| **Privat** | Privatpersonen | Projekte, Lebensbereiche, Ziele, Lernen, Journal |
| **Team / Orga** | Kleine Teams | Geteiltes Wissen, Prozesse, Entscheidungen, Meetings |

> Stand: Die Variante **Führungskräfte** ist fertig. Privat und Team folgen.

---

## So startest du (nutzen)

1. Lade unter **[Releases](../../releases)** das ZIP deiner Variante herunter und entpacke es.
2. Öffne den Ordner in Obsidian ("Open folder as vault").
3. Verbinde Claude mit dem Vault: Anleitung in [`docs/SETUP-Desktop.md`](docs/SETUP-Desktop.md) (Claude Desktop) oder [`docs/SETUP-ClaudeCode.md`](docs/SETUP-ClaudeCode.md).
4. Sag Claude: **"Starte das Onboarding."**

Fertig. Ab jetzt arbeitest du formlos mit deinem zweiten Gehirn.

Die Setup-Anleitungen liegen auch im jeweiligen Vault selbst (Ordner `docs/`), du brauchst dieses Repo also nicht.

---

## So baust du eine eigene Variante (Macher)

Der gemeinsame Kern liegt in [`boilerplate/`](boilerplate/) mit eigener Anleitung. Kopieren, Persona setzen, Zielgruppen-Ordner und Onboarding-Fragen ergänzen, fertig. Details: [`boilerplate/README.md`](boilerplate/README.md).

---

## Was eingebaut ist

- **Drei Operationen** (`ingest`, `query`, `lint`): der Arbeits-Loop, beschrieben in der `CLAUDE.md` jedes Vaults.
- **Open Knowledge Format (OKF):** jede Notiz mit `type`-Feld, jeder Ordner mit `index.md`. Macht den Vault maschinell auswertbar.
- **LLM-Wiki-Muster:** drei Schichten (Quellen, Wiki, Schema), damit Wissen wächst statt bei jeder Frage neu gesucht zu werden.

Mehr zur Idee: [`docs/PHILOSOPHIE.md`](docs/PHILOSOPHIE.md).

---

## Aufbau dieses Repos

```
boilerplate/      Gemeinsamer Kern (für Macher)
variants/         Fertige, direkt nutzbare Vaults
  fuehrungskraefte/
docs/             Setup-Anleitungen und Hintergrund
```
