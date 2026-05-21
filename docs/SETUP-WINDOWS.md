# Setup für den AI Ready Day · Windows · Schritt für Schritt

> Diese Anleitung ist für dich, wenn du auf einem **Windows-PC** arbeitest und noch nie programmiert hast.
> Wir erklären alles. Wenn ein Wort neu ist — kein Stress, einfach weitermachen.

## Was du schon hast (gut!)

- ✅ Windows-PC (Windows 10 oder 11)
- ✅ Claude Pro-Account (über falkemedia)
- ✅ Claude Desktop App
- ✅ Falkemedia-Google-Account

## Was wir heute zusätzlich brauchen

- **GitHub** — wie Google Drive, aber für Code
- **Vercel** — bringt deine App ins Internet
- **Claude Code (CLI)** — das Werkzeug, mit dem wir heute bauen

---

## 1. GitHub-Account (3 Min)

- Geh auf https://github.com
- Klick oben rechts auf **"Sign up"**
- Nimm deine **falkemedia-Mail**
- Username egal — kann auch lustig sein
- E-Mail bestätigen

## 2. Vercel-Account (2 Min)

- Geh auf https://vercel.com/signup
- Klick **"Continue with GitHub"** → Autorisieren
- **"Hobby"**-Plan auswählen
- Fertig

## 3. PowerShell öffnen (nur für das einmalige Setup)

PowerShell ist ein Fenster, in dem du dem PC Befehle in Textform gibst. **Heute brauchst du es nur einmal, fürs Setup.**

- Drück die **Windows-Taste**
- Tipp `PowerShell`
- Drück Enter

Du siehst jetzt ein blaues oder schwarzes Fenster. Genau richtig.

## 4. Bootstrap ausführen

Kopier diese **zwei Befehle**, klick ins PowerShell-Fenster, rechte Maustaste (paste), Enter:

```powershell
irm https://raw.githubusercontent.com/mkleinsorg-creator/ai-ready-day/main/bootstrap.ps1 -OutFile $env:TEMP\bootstrap.ps1
```

```powershell
powershell -ExecutionPolicy Bypass -File $env:TEMP\bootstrap.ps1
```

Das Script erklärt unterwegs, was es macht. Lies mit — das hilft beim Verstehen.

**⚠️ Wichtige Momente im Script:**

1. **winget-Sicherheitsabfrage** (passiert mehrfach):
   - Wenn Windows fragt *„App-Quelle akzeptieren?"* → mit `Y` bestätigen.
   - Das passiert für jeden Tool-Install einmal.

2. **GitHub-Login** (etwa nach 2 Min):
   - Browser öffnet sich, du loggst dich mit deinem GitHub-Account ein, autorisierst — fertig.
   - Code aus PowerShell kopieren, im Browser einfügen.

3. **Windows SmartScreen / Defender-Warnung**:
   - Wenn Windows fragt, ob du den Befehl wirklich ausführen willst → bestätigen.
   - Das Script ist Open Source und liegt auf GitHub — du kannst es vorher anschauen.

## 5. Rüber in die Claude Desktop App — der erste echte Schritt heißt BMAD

Wenn das Script `✅ Fertig` sagt: **PowerShell kannst du jetzt liegenlassen.**

- Öffne die **Claude Desktop App** (kennst du schon — das ist die, in der du sonst chattest)
- Drück **`Ctrl + 3`** — das öffnet das integrierte Claude-Code-Fenster innerhalb der App. Dort funktionieren Slash-Commands wie `/bmad`.
  - *Falls `Ctrl + 3` nicht klappt: frag Max — das Tastenkürzel kann unter Windows leicht abweichen.*
- In die erste Nachricht eintippen oder reinkopieren (genau so):

```
Lies @C:\Users\<DEIN_USERNAME>\ai-ready-day\prompts\00-router.md vollständig und folge diesen Anweisungen als Master-Prompt.
```

> Ersetz `<DEIN_USERNAME>` durch deinen Windows-Benutzernamen — der steht oben im PowerShell-Fenster.

Claude begrüßt dich und fragt, was du heute bauen willst.

**Dein erster Arbeitsschritt heißt BMAD** — eine Methode, die mit dir gemeinsam deine Idee schärft, ein paar gezielte Fragen stellt und am Ende einen Bauplan mit konkreten Schritten liefert.

Lass dich davon nicht abschrecken — du musst die Methode nicht verstehen. Du beantwortest einfach die Fragen, BMAD macht den Rest.

*(Ausnahme: Wer Meta-Ads baut, überspringt BMAD und geht direkt zur Facebook Ads CLI.)*

## Wann brauchst du PowerShell nochmal?

Nur, wenn Claude dir sagt *„Kopier diesen Befehl in PowerShell"* — z. B. wenn deine Web-App lokal gestartet oder ins Internet gestellt werden soll.

---

## Wenn etwas hakt

Schau in `docs/TROUBLESHOOTING.md` oder ruf Max.
Das ist heute kein Versagen — das ist Plan.

## Wichtigste Windows-Unterschiede zur Mac-Anleitung

| Mac | Windows |
|---|---|
| Terminal (Cmd + Leertaste) | PowerShell (Windows-Taste) |
| Homebrew als Paket-Manager | winget als Paket-Manager |
| `~/ai-ready-day` | `C:\Users\<DEIN_USERNAME>\ai-ready-day` |
| `Cmd + 3` für Claude-Code-Fenster | `Ctrl + 3` (vermutlich) |
| `bash` | `PowerShell` / `pwsh` |
