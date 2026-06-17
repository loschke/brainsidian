# Setup: Claude Code

Wer lieber im Terminal arbeitet, nutzt Claude Code direkt im Vault-Ordner. Claude Code liest und schreibt die Dateien dann ohne Umweg über einen MCP-Server.

> Dieselbe Technik steckt im **Code-Tab von Claude Desktop**. Wer keine Lust aufs Terminal hat, nimmt den Code-Tab in der Desktop-App (siehe `SETUP-Desktop.md`, Weg A) und folgt sinngemäß denselben Schritten.

## Voraussetzungen

1. **Claude Code** installiert: siehe [docs.claude.com/claude-code](https://docs.claude.com/en/docs/claude-code).
2. Deine Vault-Variante entpackt (z.B. aus dem Release-ZIP).

## Schritte

1. Terminal öffnen und in den Vault-Ordner wechseln:

   ```bash
   cd Pfad/zu/Mein-Vault
   ```

2. Claude Code starten:

   ```bash
   claude
   ```

3. Claude Code liest automatisch die `CLAUDE.md` im Ordner. Das ist das Playbook deines Vaults. Schreib dann:

   > Starte das Onboarding (`00_SYSTEM/_Onboarding.md`).

Claude führt das Interview und legt deine ersten Notizen an. Danach arbeitest du formlos weiter.

## Hinweise

- Der optionale Onboarding-Skill liegt unter `.claude/skills/onboarding/`. Claude Code findet ihn automatisch. Du brauchst nichts zu konfigurieren.
- Claude Code fragt bei Schreibzugriffen nach Erlaubnis. Du kannst häufige Aktionen dauerhaft erlauben.
- Obsidian und Claude Code können parallel laufen. Änderungen, die Claude schreibt, erscheinen sofort in Obsidian.
