# Setup: Claude Desktop

Claude Desktop bietet zwei Oberflächen, mit denen du deinen Vault nutzen kannst. Beide funktionieren gleich gut, wähle nach Geschmack. Du machst das Setup nur einmal.

> Obsidian brauchst du nur, wenn du die Notizen auch selbst durchblättern willst. Der eigentliche Vault ist einfach ein Ordner mit Markdown-Dateien. Claude arbeitet direkt mit diesem Ordner.

## Was du brauchst

1. **Claude Desktop**: [claude.ai/download](https://claude.ai/download)
2. **Dein Vault** entpackt an einen Ort, den du wiederfindest (z.B. `Dokumente\Mein-Vault`).
3. **Obsidian** (optional, zum Anschauen): [obsidian.md](https://obsidian.md)

Je nach Weg unten kommt noch eine Kleinigkeit dazu (Git oder Node.js).

---

## Weg A: Der Code-Tab (am einfachsten, nichts zu konfigurieren)

Der **"Code"-Tab** in Claude Desktop ist dieselbe Technik wie Claude Code. Er greift direkt auf einen Ordner zu, ganz ohne Server und ohne Konfigurationsdatei.

**Zusätzlich nötig:** Git (ein kleines Programm, einmalig installieren): [git-scm.com](https://git-scm.com)

**Schritte:**

1. Git installieren, falls noch nicht vorhanden. Installer durchklicken, alle Voreinstellungen passen.
2. Claude Desktop öffnen und oben den **Code**-Tab wählen.
3. Deinen Vault-Ordner öffnen (auswählen).
4. Schreib Claude:

   > **Lies die CLAUDE.md und führe dann das Onboarding-Playbook aus (`00_SYSTEM/_Onboarding.md`).**

Fertig. Claude legt deine ersten Notizen an. Ab jetzt arbeitest du formlos: *"Nimm das auf"*, *"Was weiß ich über X?"*

---

## Weg B: Der Chat-Tab (vertraute Chat-Oberfläche, einmalige Einrichtung)

Wenn du lieber im normalen Chat arbeitest, verbindest du den Vault einmalig über einen kleinen Datei-Server.

**Zusätzlich nötig:** Node.js (kostenlos, Version "LTS"): [nodejs.org](https://nodejs.org)

**Schritte:**

1. Node.js installieren. Installer durchklicken, danach den Rechner einmal neu starten.
2. Den **vollständigen Pfad** zu deinem Vault herausfinden.
   - Windows: Rechtsklick auf den Ordner, "Als Pfad kopieren". Beispiel: `C:\Users\DeinName\Dokumente\Mein-Vault`.
   - Mac: Rechtsklick, "Pfadname kopieren". Beispiel: `/Users/DeinName/Documents/Mein-Vault`.
3. In Claude Desktop: **Claude-Menü → Settings → Developer → Edit Config**. Es öffnet sich `claude_desktop_config.json`.
4. Ersetze den Inhalt durch den passenden Block und **setze deinen Pfad ein**.

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

> Bei Windows müssen im Pfad **doppelte** Backslashes stehen (`\\`), genau wie oben.

5. Speichern und Claude Desktop **komplett beenden und neu starten** (nicht nur das Fenster schließen).
6. Test: Schreib *"Lies die CLAUDE.md in meinem Vault und fasse in zwei Sätzen zusammen, wie er funktioniert."* Kommt eine sinnvolle Antwort, steht die Verbindung.
7. Onboarding starten:

   > **Lies die CLAUDE.md und führe dann das Onboarding-Playbook aus (`00_SYSTEM/_Onboarding.md`).**

> Claude Desktop liest die `CLAUDE.md` nicht von allein. Deshalb nennst du sie im Test und beim Onboarding ausdrücklich. Einmal gelesen, kennt Claude für den Rest des Gesprächs die Regeln.

---

## Wenn etwas klemmt

| Problem | Lösung |
|---------|--------|
| Code-Tab findet den Ordner nicht | Ist Git installiert? Nach der Installation Claude Desktop neu starten. |
| "vault" taucht im Chat-Tab nicht auf | Pfad in der Config prüfen, bei Windows auf die doppelten Backslashes achten. Danach Claude neu starten. |
| Claude sagt, er habe keinen Zugriff (Chat-Tab) | Claude nach dem Speichern wirklich komplett beendet und neu gestartet? |
| Fehler mit "npx" / "command not found" | Node.js fehlt oder der Rechner wurde nach der Installation nicht neu gestartet. |

---

## Was nicht funktioniert

Der **Cowork**-Tab läuft in der Cloud und hat keinen Zugriff auf deine lokalen Dateien. Für deinen Vault nimmst du den **Code**- oder den **Chat**-Tab, nicht Cowork.
