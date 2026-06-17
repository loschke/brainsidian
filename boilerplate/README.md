# Boilerplate – das Skeleton für eigene Varianten

Dies ist der gemeinsame Kern aller Brainsidian-Vaults: die Engine, die Standards und das Onboarding, aber ohne Zuschnitt auf eine Zielgruppe. Wer eine neue Variante bauen will (z.B. für Studierende, Creator, Vereine), startet hier.

> Du willst den Vault nur **nutzen**, nicht selbst bauen? Dann ist nicht dieser Ordner gemeint. Lade unter den Releases die fertige Variante (Führungskräfte, Privat, Team) und folge deren `START-HIER.md`.

## Was drin ist

```
CLAUDE.md            Das Playbook: Schichten, Konventionen, die drei Operationen
START-HIER.md        Einstieg für Menschen
00_SYSTEM/           Struktur-Guide, Profil, Onboarding, Log, Templates
Sources/             Originalquellen (unveränderlich)
01_INBOX/            Eingang
02_KNOWLEDGE/        Das Wiki
03_PROJECTS/         Aktive Vorhaben
99_ARCHIVE/          Abgeschlossenes
.obsidian/           Vorkonfiguriert (Dark Mode, Templates-Plugin, keine Community-Plugins)
```

## Die eingebauten Standards

- **Open Knowledge Format (OKF):** Jede Notiz trägt ein `type`-Feld im Frontmatter, jeder Ordner eine `index.md`. Macht den Vault maschinell auswertbar, kostet eine Zeile.
- **LLM-Wiki-Muster:** Drei Schichten (Quellen, Wiki, Schema) und drei Operationen (`ingest`, `query`, `lint`), beschrieben in `CLAUDE.md`.

Beide sind als Konvention eingebaut, nicht als Abhängigkeit. Setzen sie sich nicht durch, bleibt sauberes Markdown.

## Eine eigene Variante ableiten

1. **Kopieren:** `boilerplate/` nach `variants/<deine-variante>/` kopieren.
2. **Persona setzen:** In `00_SYSTEM/_persona.md` den Wert `persona:` anpassen.
3. **Ordner ergänzen:** Zielgruppen-Ordner anlegen (z.B. `02_PEOPLE/`, `05_MEETINGS/`), jeweils mit `index.md`. Die generischen Ordner bleiben oder werden umbenannt. Weniger ist mehr.
4. **Templates ergänzen:** Spezifische Vorlagen in `00_SYSTEM/Templates/` hinzufügen.
5. **CLAUDE.md füllen:** Den Abschnitt `{{VARIANT_ADDITIONS}}` mit den zusätzlichen Ordnern, Notiztypen und Arbeitsabläufen der Variante ersetzen. `{{PERSONA_LABEL}}` setzen.
6. **Onboarding-Fragen ergänzen:** In `00_SYSTEM/_Onboarding.md` den persona-spezifischen Fragenblock anlegen.
7. **Platzhalter auflösen:** `{{TODAY}}` durch das aktuelle Datum ersetzen. `{{USER_NAME}}` und `{{VAULT_NAME}}` bleiben stehen, die füllt das Onboarding beim Nutzer.

## Platzhalter im Überblick

| Platzhalter | Wer ersetzt ihn | Wann |
|-------------|-----------------|------|
| `{{PERSONA_LABEL}}` | Maker | beim Ableiten der Variante |
| `{{VARIANT_ADDITIONS}}` | Maker | beim Ableiten der Variante |
| `{{TODAY}}` | Maker | beim Ableiten (aktuelles Datum) |
| `{{USER_NAME}}` | Onboarding | beim Nutzer |
| `{{VAULT_NAME}}` | Onboarding | beim Nutzer |
| `{{date}}`, `{{title}}` | Obsidian | beim Einfügen eines Templates |
