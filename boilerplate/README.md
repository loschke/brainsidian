# Boilerplate – das Skeleton für eigene Varianten

Dies ist der gemeinsame Kern aller Brainsidian-Vaults: die Engine, die Standards und das Onboarding, aber ohne Zuschnitt auf eine Zielgruppe. Wer eine neue Variante bauen will (z.B. für Studierende, Creator, Vereine), startet hier.

> Du willst den Vault nur **nutzen**, nicht selbst bauen? Dann ist nicht dieser Ordner gemeint. Lade unter den Releases die fertige Variante (Führungskräfte, Privat, Team) und folge deren `START-HIER.md`.

## Was drin ist

```
CLAUDE.md            Das Playbook: Schichten, Konventionen, die drei Operationen
index.md             Globaler Katalog: eine Zeile pro Notiz (Einstieg für Claude)
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

- **Open Knowledge Format (OKF):** Jede Notiz trägt `type`, `layer`, `created`, `updated`, `status` und `source` im Frontmatter, jeder Ordner eine `index.md`. Macht den Vault maschinell auswertbar und filterbar, kostet ein paar Zeilen.
- **LLM-Wiki-Muster:** Drei Schichten (Quellen, Wiki, Schema), drei Operationen (`ingest`, `query`, `lint`) und ein globaler Katalog `index.md` im Vault-Root, den der Agent als Erstes liest. Beschrieben in `CLAUDE.md`.

Beide sind als Konvention eingebaut, nicht als Abhängigkeit. Setzen sie sich nicht durch, bleibt sauberes Markdown.

## Unveränderliches Gerüst

Diese Pfade heißen in **jeder** Variante gleich, jeweils relativ zum Vault-Root. Werkzeuge
und Skills dürfen sich darauf verlassen, Varianten dürfen sie nicht umbenennen:

| Pfad | Warum |
|------|-------|
| `CLAUDE.md` | Einstiegspunkt für den Agenten |
| `index.md` | Globaler Katalog, eine Zeile pro Notiz |
| `START-HIER.md` | Einstiegspunkt für Menschen |
| `00_SYSTEM/` | inkl. `log.md`, `_persona.md`, `_About.md`, `_Onboarding.md`, `_Structure-Guide.md`, `Templates/` |
| `Sources/` | Quellschicht, auch in `.obsidian/app.json` referenziert |
| `01_INBOX/` | Eingang |
| `99_ARCHIVE/` | Ausgang |
| `.claude/`, `docs/` | Schema und Doku |

**Frei belegbar sind die Nummern `02_` bis `98_`.** Dort legt jede Variante ihre
Zielgruppen-Ordner an, benennt und nummeriert sie, wie es passt.

Daraus folgt eine Regel für alles, was gegen einen Vault gebaut wird: **kein Werkzeug darf
aus dem Ordnernamen schließen, was eine Notiz ist.** Ob eine Notiz zur Wiki-Schicht gehört,
steht im Frontmatter (`layer:`), nicht im Pfad.

## Eine eigene Variante ableiten

1. **Kopieren:** `boilerplate/` nach `variants/<deine-variante>/` kopieren. Danach `README.md`
   löschen (Macher-Doku, gehört nicht in den Nutzer-Vault) und `docs/` aus dem Repo-Root
   hineinkopieren (Setup und Philosophie reisen mit).
2. **Persona setzen:** In `00_SYSTEM/_persona.md` den Wert `persona:` anpassen.
3. **Ordner ergänzen:** Zielgruppen-Ordner im freien Bereich `02_` bis `98_` anlegen, jeweils mit `index.md`. Das unveränderliche Gerüst (siehe oben) bleibt, wie es ist. Weniger ist mehr.
4. **Templates ergänzen:** Spezifische Vorlagen in `00_SYSTEM/Templates/` hinzufügen.
5. **CLAUDE.md füllen:** Den Abschnitt `{{VARIANT_ADDITIONS}}` mit den zusätzlichen Ordnern, Notiztypen und Arbeitsabläufen der Variante ersetzen. `{{PERSONA_LABEL}}` setzen.
6. **Onboarding-Fragen ergänzen:** In `00_SYSTEM/_Onboarding.md` den persona-spezifischen Fragenblock anlegen.
7. **Platzhalter auflösen:** `{{TODAY}}` durch das aktuelle Datum ersetzen. `{{USER_NAME}}` und `{{VAULT_NAME}}` bleiben stehen, die füllt das Onboarding beim Nutzer.
8. **Gegenprobe:** `boilerplate/` gegen die fertige Variante diffen. Abweichen dürfen nur
   Ordnernamen, `_persona.md`, der Varianten-Abschnitt in `CLAUDE.md`, die zusätzlichen
   Templates, die Felder `people`/`project` und die aufgelösten Platzhalter. Alles andere
   muss identisch sein. Das ist die einzige Stelle, an der Drift zwischen Varianten auffällt.

## Platzhalter im Überblick

| Platzhalter | Wer ersetzt ihn | Wann |
|-------------|-----------------|------|
| `{{PERSONA_LABEL}}` | Maker | beim Ableiten der Variante |
| `{{VARIANT_ADDITIONS}}` | Maker | beim Ableiten der Variante |
| `{{TODAY}}` | Maker | beim Ableiten (aktuelles Datum) |
| `{{USER_NAME}}` | Onboarding | beim Nutzer |
| `{{VAULT_NAME}}` | Onboarding | beim Nutzer |
| `{{date}}`, `{{title}}` | Obsidian | beim Einfügen eines Templates |
