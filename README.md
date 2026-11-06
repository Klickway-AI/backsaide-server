# backsAIde Server

Selbst gehosteter Server für **backsAIde**: Markdown-Notizen (nach dem Vorbild von Obsidian), die auf deinem eigenen Gerät liegen, verschlüsselt sind und sich zwischen Geräten und Personen synchronisieren. Dazu ein KI-Connector (MCP), damit Claude und andere KI-Systeme dein „Second Brain“ nutzen können.

Dieses Repo enthält **nur die fertigen Programme**, keinen Quellcode. Der Quellcode ist nicht öffentlich.

© 2026 Anette Käpplinger. Alle Rechte vorbehalten. Nutzungsbedingungen: [LICENSE.txt](LICENSE.txt) · [Impressum](IMPRESSUM.md) · [Datenschutz](DATENSCHUTZ.md)

## Download

Unter [**Releases**](../../releases) findest du je Betriebssystem ein Paket und die Datei `SHA256SUMS`:

| System | Datei |
|---|---|
| Raspberry Pi (64 Bit, Standard seit 2023) | `backsAIde-Server-linux-arm64.tar.gz` |
| Raspberry Pi (32 Bit) | `backsAIde-Server-linux-armv7.tar.gz` |
| Linux-Server, normaler PC (Intel/AMD) | `backsAIde-Server-linux-x64.tar.gz` |
| Windows 10/11 (64 Bit) | `backsAIde-Server-windows-x64.zip` |
| Mac mit Apple-Chip | `backsAIde-Server-macos-arm64.tar.gz` |
| Mac mit Intel-Prozessor | `backsAIde-Server-macos-x64.tar.gz` |

Node.js wird nicht benötigt. In jedem Paket liegt eine Anleitung (`LIESMICH-…`).

**Prüfsumme kontrollieren:** `sha256sum -c SHA256SUMS --ignore-missing` (Linux), `shasum -a 256 -c SHA256SUMS --ignore-missing` (Mac), unter Windows `Get-FileHash <Datei>` und mit der Zeile in `SHA256SUMS` vergleichen.

## Kurzanleitung

- **Linux / Raspberry Pi:** `tar xzf backsAIde-Server-linux-<arch>.tar.gz && cd backsaide-server && sudo sh install-server.sh <dein-name>`
- **Windows:** ZIP entpacken, `Server-starten.cmd` doppelklicken.
- **Mac:** `tar xzf …`, `cd backsaide-server`, `sh server-starten.sh`.

Beim ersten Start zeigt der Server dein Zugangs-Token **einmal** an. Es ist zugleich der Schlüssel zu deinen verschlüsselten Notizen: **Token verloren = Notizen verloren.**

## Wichtig zu wissen

- Der Server sendet von sich aus keine Daten an Dritte (keine Telemetrie, keine Update-Abfrage).
- Notizen liegen verschlüsselt (AES-256-GCM) auf deinem Gerät. Datei- und Ordnernamen sind nicht verschlüsselt.
- Ehrlicher Teststand: Die Pakete werden automatisch auf GitHub gebaut und getestet (Linux echt mit systemd, ARM im Emulator, Windows und macOS auf Test-Rechnern). **Auf echten Geräten (Raspberry Pi, Windows-PC, Mac) und mit dem claude.ai-Connector ist es noch nicht erprobt.**
- Die Windows-Programme sind nicht digital signiert (SmartScreen-Warnung), die Mac-Programme nur ad-hoc signiert (Gatekeeper-Hinweis). Die Anleitungen im Paket erklären den Umgang damit.
- Weitere Versionen für Android und Desktop gibt es später.

## Kontakt

Anette Käpplinger, Raiffeisenstr. 29, 76767 Hagenbach, E-Mail: backsAIt@mail.de
