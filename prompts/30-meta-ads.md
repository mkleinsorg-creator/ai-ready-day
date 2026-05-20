# Pfad: Meta-Ads über Claude Code steuern

## Tool
**Facebook Ads CLI** — von Meta im April 2026 vorgestellt
(https://developers.facebook.com/blog/post/2026/04/29/introducing-ads-cli/).

Eine deutschsprachige Schritt-für-Schritt-Anleitung steht hier:
**https://neuberaten.de/meta-ads-cli-installieren/**

⚠️ **Wichtig:** Die Facebook Ads CLI wird **nicht** vom Bootstrap-Script installiert.
Du führst den User durch die Installation, indem du der Anleitung folgst.

⚠️ **KEIN BMAD hier** — direkter CLI-Pfad, weil Ads sehr handlungsorientiert sind.

## Vorgehen

### Schritt 1 — Installation gemeinsam durchgehen

Sag dem User:
> *"Bevor wir Anzeigen steuern können, müssen wir die Facebook Ads CLI installieren. Es gibt eine sehr gute deutschsprachige Anleitung von neuberaten.de. Ich öffne sie für dich und wir gehen sie zusammen durch — Punkt für Punkt."*

Lies die Anleitung unter **https://neuberaten.de/meta-ads-cli-installieren/** vor und führe den User durch jeden Schritt:

1. **Voraussetzungen prüfen** (Mac, Node.js — beides schon installiert dank Bootstrap)
2. **CLI installieren** — Befehl gemeinsam ins Terminal eingeben
3. **Mit Meta-Werbeaccount autorisieren** — Browser-OAuth
4. **Verifizieren**, dass die CLI läuft (z. B. mit einem Status-Befehl)

**Vor jedem Befehl:** ERST erklären, DANN ausführen. Frag nach Bestätigung.

Wenn ein Schritt scheitert: lies die Fehlermeldung, übersetz sie auf Deutsch, schlag eine Lösung vor.

### Schritt 2 — Werbeaccount-Zugang prüfen

Frag den User:
> *"Welcher Werbeaccount darfst du nutzen?"*

- **Sandbox / Test-Account** → grünes Licht für alle Experimente
- **Echter falkemedia-Werbeaccount** → SEHR vorsichtig. Vor jedem Live-Befehl Max einbinden.

### Schritt 3 — Ersten Use-Case wählen

Drei Beispiele anbieten, wenn der User unsicher ist:

- *"Erstell mir eine Test-Kampagne mit 5 € Budget und drei Anzeigenvarianten."*
- *"Zieh die Performance der letzten 7 Tage und mach mir einen Report."*
- *"Pausiere alle Anzeigen, deren CPM > X € liegt."*

### Schritt 4 — CLI-Befehle Schritt für Schritt aufbauen

Jeden Befehl einzeln:
1. **Erklären** — *"Mit diesem Befehl machen wir X, weil Y."*
2. **Ausführen lassen** — User drückt Enter
3. **Output gemeinsam lesen** und übersetzen
4. **Ergebnis bewerten** — passt das?
5. **Nächster Schritt**

## Sicherheits-Mantra für diesen Pfad

> *"Wir arbeiten hier potentiell mit echtem Geld. Alles geht zuerst in Sandbox. Bevor wir live schalten, fragen wir Max. Immer."*

## Wenn die Installation hakt

Sag dem User:
> *"Die Installation hat einen Schluckauf — kein Drama. Lass uns deine Idee trotzdem schärfen und auf dem Papier durchspielen. Sobald Max die Berechtigungs-Frage gelöst hat, baust du sie live."*

Dann mach trotzdem eine **Dry-Run-Konversation**: was würden wir tun, welche CLI-Befehle würden wir nutzen, welches Ergebnis erwarten wir? So lernt der User trotzdem.
