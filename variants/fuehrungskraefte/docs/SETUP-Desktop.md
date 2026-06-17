# Setup: Claude Desktop + Obsidian

Diese Anleitung verbindet Claude mit deinem Vault. Danach kann Claude deine Notizen lesen und schreiben. Es ist der einzige technische Schritt, und du machst ihn nur einmal. Plan etwa fünfzehn Minuten ein.

> Du brauchst keine Programmierkenntnisse. Folge den Schritten der Reihe nach.

---

## Was du brauchst

1. **Obsidian** (kostenlos): [obsidian.md](https://obsidian.md)
2. **Claude Desktop**: [claude.ai/download](https://claude.ai/download)
3. **Node.js** (kostenlos, stellt das Verbindungsstück bereit): [nodejs.org](https://nodejs.org) – nimm die Version mit der Bezeichnung "LTS".

Installiere alle drei, falls noch nicht vorhanden. Bei Node.js einfach den Installer durchklicken, alle Voreinstellungen passen.

---

## Schritt 1: Vault in Obsidian öffnen

1. Entpacke die heruntergeladene ZIP-Datei deiner Variante an einen Ort, den du wiederfindest, z.B. `Dokumente\Mein-Vault`.
2. Öffne Obsidian, klicke "Open folder as vault" und wähle diesen Ordner.
3. Vertraust du dem Vault, bestätige "Trust author and enable plugins".

Du siehst jetzt links die Ordner (`00_SYSTEM`, `01_INBOX`, ...) und die Notiz `START-HIER`. Merk dir den **vollständigen Pfad** zu diesem Ordner, du brauchst ihn gleich.

> Pfad herausfinden (Windows): Rechtsklick auf den Ordner, "Als Pfad kopieren". Beispiel: `C:\Users\DeinName\Dokumente\Mein-Vault`.
> Mac: Rechtsklick, "Pfadname kopieren". Beispiel: `/Users/DeinName/Documents/Mein-Vault`.

---

## Schritt 2: Claude mit dem Vault verbinden

Claude liest eine kleine Konfigurationsdatei, in der steht, auf welchen Ordner er zugreifen darf. Die richten wir jetzt ein.

1. Öffne Claude Desktop.
2. Gehe in die Einstellungen: **Claude-Menü → Settings → Developer**.
3. Klicke **Edit Config**. Es öffnet sich eine Datei namens `claude_desktop_config.json` in deinem Texteditor.
4. Ersetze den gesamten Inhalt durch den folgenden Block. **Tausche den Pfad** gegen den Pfad zu deinem Vault aus Schritt 1.

**Windows:**

```json
{
  "mcpServers": {
    "vault": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "C:\\Users\\DeinName\\Dokumente\\Mein-Vault"
      ]
    }
  }
}
```

**Mac:**

```json
{
  "mcpServers": {
    "vault": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/Users/DeinName/Documents/Mein-Vault"
      ]
    }
  }
}
```

> Achtung bei Windows: Im Pfad müssen **doppelte** Backslashes stehen (`\\`), so wie oben gezeigt.

5. Speichern und den Editor schließen.
6. Claude Desktop **komplett beenden und neu starten** (nicht nur das Fenster schließen).

---

## Schritt 3: Verbindung prüfen

Nach dem Neustart von Claude Desktop:

1. Unten im Eingabefeld erscheint ein Werkzeug-Symbol. Klick darauf. Dort sollte "vault" mit mehreren Funktionen auftauchen (Dateien lesen, schreiben).
2. Schreib Claude testweise: *"Lies die CLAUDE.md in meinem Vault und fasse in zwei Sätzen zusammen, wie dieser Vault funktioniert."*

Antwortet Claude mit einer sinnvollen Zusammenfassung, steht die Verbindung und Claude kennt die Spielregeln deines Vaults.

> Wichtig: Claude Desktop liest die `CLAUDE.md` nicht von allein. Deshalb nennst du sie im Test und beim Onboarding ausdrücklich. Einmal gelesen, kennt Claude für den Rest des Gesprächs die Regeln.

---

## Schritt 4: Onboarding starten

Jetzt der schöne Teil. Schreib Claude genau das:

> **Lies die CLAUDE.md in meinem Vault und führe dann das Onboarding-Playbook aus (`00_SYSTEM/_Onboarding.md`).**

Die Datei beim Namen zu nennen ist hier wichtig, damit Claude Desktop sie sicher findet. Claude liest das Playbook, stellt dir ein paar Fragen und legt deine ersten Notizen, Projekte und Inhaltskarten an. Danach ist dein Vault bewohnt und du hast gesehen, wie das System für dich arbeitet.

Ab hier arbeitest du formlos: *"Nimm das auf"*, *"Was weiß ich über X?"*, *"Bereite mein Gespräch mit Y vor."*

---

## Wenn etwas klemmt

| Problem | Lösung |
|---------|--------|
| "vault" taucht nicht im Werkzeug-Menü auf | Pfad in der Config falsch. Prüfe ihn, achte bei Windows auf die doppelten Backslashes. Danach Claude neu starten. |
| Claude sagt, er habe keinen Zugriff | Hast du Claude nach dem Speichern wirklich komplett beendet und neu gestartet? |
| Fehlermeldung mit "npx" oder "command not found" | Node.js ist nicht installiert oder der Rechner wurde nach der Installation nicht neu gestartet. |
| Du willst Claude den Zugriff wieder entziehen | Den Block aus der Config löschen, speichern, Claude neu starten. |

---

## Alternative: Obsidian-eigener Zugang

Statt des Datei-Zugriffs oben kannst du auch einen Obsidian-spezifischen MCP-Server nutzen (über das Community-Plugin "Local REST API"). Das bringt zusätzliche Obsidian-Funktionen, ist aber aufwändiger einzurichten. Für den Start empfehlen wir den Weg oben. Details für den fortgeschrittenen Weg stehen in `SETUP-eigener-Stack.md`.
