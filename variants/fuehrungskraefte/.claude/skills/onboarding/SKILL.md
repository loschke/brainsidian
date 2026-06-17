---
name: onboarding
description: Richtet einen frischen Brainsidian-Vault ein. Führt ein kurzes Interview und legt die ersten Notizen, Projekte, Inhaltskarten und das Profil an. Nutze dies, wenn der Vault neu ist oder der Nutzer "Onboarding", "einrichten" oder "Start" sagt.
---

# Onboarding-Skill

Dies ist ein dünner Komfort-Wrapper. Die eigentliche Logik liegt als Markdown-Playbook im Vault, damit sie auch ohne Skill-Framework funktioniert (z.B. in Claude Desktop über einen Standard-MCP).

**Vorgehen:**

1. Lies `00_SYSTEM/_persona.md`, um die Variante zu bestimmen.
2. Lies und befolge das Playbook in `00_SYSTEM/_Onboarding.md` Schritt für Schritt.
3. Nutze ausschließlich generische Lese-/Schreib-Operationen (Notizen lesen und schreiben). Setze keine proprietären MCP-Funktionen voraus.

Das Playbook ist die Quelle der Wahrheit. Dieser Skill macht nur das Auffinden bequemer.
