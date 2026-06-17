# Setup: Fortgeschritten (Obsidian-eigener Zugang)

Der Weg in `SETUP-Desktop.md` reicht für die meisten. Wer mehr Obsidian-spezifische Funktionen will (z.B. Notizen über die Obsidian-API statt über das Dateisystem ansprechen, Templates serverseitig erzeugen), kann einen Obsidian-MCP-Server einrichten.

## Variante A: Obsidian Local REST API + MCP

1. In Obsidian das Community-Plugin **"Local REST API"** installieren und aktivieren. Es vergibt einen API-Schlüssel.
2. Einen Obsidian-MCP-Server einrichten, der diese API anspricht (mehrere Open-Source-Server stehen zur Wahl). Den API-Schlüssel und die Adresse in der `claude_desktop_config.json` hinterlegen, analog zu `SETUP-Desktop.md`.
3. Claude Desktop neu starten.

Vorteil: Zugriff auf Obsidian-Funktionen jenseits des reinen Dateilesens. Nachteil: mehr Einrichtung, ein zusätzliches Plugin.

## Variante B: Eigener Stack

Wer einen eigenen MCP-Server und ein eigenes Obsidian-Plugin betreibt (wie im Brainsidian-Originalsetup), kann diese hier eintragen. Wichtig: Das Boilerplate und das Onboarding sind so geschrieben, dass sie **nur generisches Lesen und Schreiben** voraussetzen. Ein eigener Stack ist eine Erweiterung, keine Voraussetzung. Alles funktioniert auch mit dem einfachen Datei-Zugang aus `SETUP-Desktop.md`.
