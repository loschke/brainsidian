---
type: system
layer: schema
title: Onboarding-Playbook
description: Einmaliges Interview, das den frischen Vault mit Leben füllt.
tags: [system, onboarding]
created: 2026-06-17
updated: 2026-06-17
status: aktiv
---

# Onboarding-Playbook

> Für Claude. Dies ist eine ausführbare Anleitung, kein Fließtext zum Vorlesen. Arbeite die Phasen der Reihe nach ab. Nutze nur Lesen und Schreiben von Notizen, setze keine besonderen Werkzeuge voraus.

Ziel: Aus einem kurzen Gespräch entsteht ein bewohnter Vault. Der Nutzer soll am Ende **sehen**, wie das System für ihn arbeitet, nicht nur davon lesen.

Dauer: rund zehn Minuten. Lieber wenige gute Notizen als ein überfüllter Vault.

---

## Phase 0 – Vorbereitung

1. Lies `00_SYSTEM/_persona.md` und merke dir die Variante (`persona:`).
2. Lies `00_SYSTEM/_About.md`. Ist sie schon ausgefüllt (Status `aktiv`), ist der Vault nicht mehr frisch. Frag den Nutzer, ob er das Onboarding wirklich wiederholen will.
3. Begrüße kurz und erkläre in zwei Sätzen, was gleich passiert: ein paar Fragen, danach legst du erste Notizen an.

---

## Phase 1 – Interview

Stelle die Fragen **einzeln oder in kleinen Gruppen**, nicht alle auf einmal. Reagiere auf Antworten, hak nach, wenn etwas vage ist. Halte dich kurz.

### Allgemeiner Block (immer)

1. **Name und Ansprache:** Wie heißt du, und wie soll ich dich ansprechen (du/Sie, Spitzname)?
2. **Kontext:** Was machst du, in einem Satz? (Rolle, Tätigkeit, Lebenssituation)
3. **Jetzt gerade:** Was beschäftigt dich aktuell am meisten? (Nenn zwei bis drei Dinge.)
4. **Menschen:** Welche zwei bis vier Menschen prägen gerade deinen Alltag oder deine Arbeit?
5. **Ziele:** Was willst du in den nächsten Monaten erreichen? (Ein bis drei Ziele.)
6. **Arbeitsweise:** Wie soll ich mit dir arbeiten? Was hilft dir, was nervt dich?

### Persona-Block (Führungskräfte)

7. **Team:** Wen führst du, und wie groß ist dein Team oder Verantwortungsbereich?
8. **Stakeholder:** Mit wem oben und seitwärts musst du dich abstimmen (Vorgesetzte, Peers, wichtige Schnittstellen)?
9. **Größte Entscheidung:** Welche Entscheidung steht bei dir gerade an oder beschäftigt dich?
10. **Wiederkehrende Gespräche:** Welche regelmäßigen 1:1s oder Meetings willst du besser vorbereiten?

---

## Phase 2 – Profil schreiben

Fülle `00_SYSTEM/_About.md` mit den Antworten. Ersetze die leeren Felder, setze `status: aktiv`.

Ersetze außerdem überall im Vault die Platzhalter:

- `{{USER_NAME}}` → der Name des Nutzers
- `{{VAULT_NAME}}` → ein passender Vault-Name (frag kurz oder schlage einen vor, z.B. "Zweites Gehirn von <Name>")

Betroffen sind mindestens: `CLAUDE.md`, `START-HIER.md`. Prüfe per Suche, ob weitere Stellen offen sind.

---

## Phase 3 – Seed-Notizen anlegen

Jetzt wird der Vault bewohnt. Lege aus den Antworten echte Notizen an, mit korrektem Frontmatter (`type` Pflicht) und Wikilinks untereinander. Nutze die Vorlagen aus `00_SYSTEM/Templates/`.

Richtwert insgesamt: **acht bis fünfzehn Notizen**. Konkret:

- **Pro Mensch (Fragen 4, 7, 8):** eine Notiz in `02_PEOPLE/` (`type: person`). Team und Stakeholder.
- **Pro Projekt / aktuelles Thema (Frage 3):** eine Notiz in `04_PROJECTS/` (`type: projekt`).
- **Pro Ziel (Frage 5):** eine Notiz in `06_STRATEGY/` (`type: ziel`).
- **Anstehende Entscheidung (Frage 9):** falls genannt, eine Notiz in `03_DECISIONS/` (`type: entscheidung`).
- **Wiederkehrendes Gespräch (Frage 10):** falls genannt, eine erste Meeting-Notiz in `05_MEETINGS/` als Vorbereitung.
- **Ein bis zwei Wissens- oder Lernnotizen** zu Themen, die beiläufig fielen (`type: notiz` in `08_KNOWLEDGE/` oder `07_LEARNING/`).

Verlinke großzügig: Ein Projekt verweist auf die beteiligten Menschen (`02_PEOPLE/`) und das zugehörige Ziel (`06_STRATEGY/`) und umgekehrt.

---

## Phase 4 – Inhaltskarten aktualisieren

Trage die neuen Notizen in die `index.md` der jeweiligen Ordner ein (je eine Zeile mit Kurzbeschreibung) und lege den globalen Katalog `index.md` im Vault-Root an, eine Zeile pro Notiz im dort beschriebenen Format. So entsteht sofort Navigation. Lege bei Bedarf zwei bis drei thematische MOC-Notizen an, wenn sich Cluster zeigen.

---

## Phase 5 – Abschluss

1. Schreibe eine Zeile in `00_SYSTEM/log.md` mit Präfix `ingest`, z.B. `## [DATUM] ingest | Onboarding`.
2. Gib dem Nutzer eine **kurze Übersicht**, was du angelegt hast (Anzahl Notizen, welche Ordner).
3. Schlage **drei konkrete nächste Schritte** vor, die er sofort ausprobieren kann, z.B.:
   - *"Nimm diesen Artikel auf"* (Quelle in `Sources/` ziehen)
   - *"Was weiß ich über <eines seiner Themen>?"*
   - *"Bereite mein Gespräch mit <Person> vor"*

Halte den Abschluss knapp und einladend. Der Nutzer soll Lust bekommen, weiterzumachen.

---

## Wichtig

- Echte Umlaute im Text (ä, ö, ü, ß), keine Umlaute in Dateinamen.
- Lieber nachfragen als Struktur raten.
- Wenn der Nutzer wenig liefert, ist das in Ordnung. Lege weniger an, aber sauber. Der Vault wächst später durch Nutzung.
