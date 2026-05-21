# Troubleshooting · Wenn was hakt

> Erste Regel: Wenn du 5 Minuten irgendwo festhängst — ruf Max.
> Das hier ist kein Quiz.

## Allgemein

### "Ich verstehe nicht, was Claude gerade tut"

Frag Claude direkt im Chat: *"Erklär mir das nochmal in einfachen Worten."*
Claude ist genau dafür da. Es gibt keine dummen Fragen.

### "Claude macht etwas, das ich nicht wollte"

Tipp `Ctrl + C` (das stoppt Claude) und sag ihm:
*"Stopp. Lass uns nochmal anfangen — ich wollte eigentlich X."*

---

## Setup-Probleme

### "Ich kann beim Passwort nichts tippen"

Doch, du kannst — du siehst es nur nicht. **macOS zeigt Passwörter beim Tippen NIE an** (keine Sterne, keine Punkte, einfach nichts). Das ist ein Sicherheits-Feature, kein Bug.

Tipp einfach blind dein normales **Mac-Login-Passwort** (das, mit dem du dich morgens einloggst) und drück Enter. Auch wenn das Terminal aussieht, als würde nichts passieren — es funktioniert.

### "3 incorrect password attempts"

macOS hat dein Passwort dreimal nicht akzeptiert. Häufige Gründe:
- Du hast das falsche Passwort eingegeben (z. B. Apple-ID-Passwort statt Mac-Login-Passwort)
- Die Caps-Lock-Taste war an
- Du hast aus Versehen das alte Passwort eingegeben, falls du es kürzlich geändert hast

Lösung: Bootstrap nochmal starten und es nochmal probieren. Falls auch dann nicht: Max rufen.


### `command not found: claude`

Wahrscheinlich ist Node.js nicht richtig im PATH. Lösung:

```bash
echo 'export PATH="$HOME/.npm-global/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

Dann nochmal versuchen. Wenn's immer noch nicht klappt: Max.

### `EACCES: permission denied`

Du sollst **nie** `sudo npm install` machen. Wenn dir das jemand vorschlägt, sag nein. Stattdessen:

```bash
mkdir -p ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH="$HOME/.npm-global/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

Dann Bootstrap nochmal ausführen.

### `git: command not found`

Mac hat Git eigentlich vorinstalliert. Wenn nicht:

```bash
xcode-select --install
```

Das öffnet ein Apple-Fenster. Bestätigen, warten, fertig.

### Homebrew-Installation hängt

Wenn `brew install` bei "Updating Homebrew..." hängt, einfach `Ctrl + C` drücken und nochmal versuchen. Manchmal Netzwerkproblem.

### Bootstrap bricht in der Mitte ab

Kein Drama. Lauf ihn einfach nochmal — das Script ist so gebaut, dass es zweimal hintereinander laufen darf, ohne kaputtzugehen.

```bash
curl -fsSL https://raw.githubusercontent.com/mkleinsorg-creator/ai-ready-day/main/bootstrap.sh | bash
```

---

## Claude Code-Probleme

### "Claude Code Login öffnet den Browser nicht"

URL aus dem Terminal kopieren und manuell im Browser einfügen.

### "MCP-Server lädt nicht"

Schließ Claude Code (`Ctrl + C`), starte es neu. Falls das nicht klappt:

```bash
cat ~/.claude/.mcp.json
```

Wenn die Datei leer oder kaputt aussieht: Max rufen.

### "Asana sagt 'unauthorized'"

Du musst dich beim ersten Asana-Aufruf einmalig autorisieren. Claude Code öffnet dafür den Browser. Wenn das nicht passiert ist: in Claude eingeben:

```
/mcp asana reconnect
```

---

## Pfad-spezifische Probleme

### Web-App: `npm error code ENOENT`

Du bist wahrscheinlich nicht im richtigen Ordner. Check:

```bash
pwd
```

Du solltest in `~/ai-ready-day/projects/<dein-projekt>` sein.

### n8n: "Workflow lässt sich nicht importieren"

Die JSON-Datei muss valide sein. Lass Claude sie überprüfen:
*"Validier bitte die workflow.json und sag mir, wo der Fehler ist."*

### Meta-Ads: CLI-Installation hakt

Schau in die Anleitung: https://neuberaten.de/meta-ads-cli-installieren/
Oder lass Claude dich Schritt für Schritt durchführen.

---

## Windows-spezifisch

### "winget ist nicht installiert"

winget kommt mit dem **App Installer** aus dem Microsoft Store. Lösung:
- Microsoft Store öffnen
- "App Installer" suchen → aktualisieren oder installieren
- PowerShell neu öffnen
- Bootstrap erneut starten

### "Die Ausführung von Skripten ist auf diesem System deaktiviert"

Standard-PowerShell-Sicherheitseinstellung. Lösung:
- Den Bootstrap immer mit `-ExecutionPolicy Bypass` starten (steht im Setup-Befehl)
- Falls trotzdem Fehler: PowerShell als Administrator öffnen und einmalig ausführen:
  ```powershell
  Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
  ```

### `gh`-Browser-Login öffnet sich nicht

URL aus dem Code-Block kopieren und manuell im Browser einfügen. Der Code aus dem PowerShell-Fenster wird im Browser-Formular abgefragt.

### Claude-Code-Fenster geht mit Ctrl+3 nicht auf

Das Tastenkürzel kann auf Windows abweichen. Probier:
- `Ctrl + 3`
- `Alt + 3`
- Oder im Menü der Claude Desktop App nach "Code" oder "Developer" suchen

Wenn nichts klappt: Max rufen.

---

## Last Resort

**Max rufen.** Das ist heute kein Versagen — das ist Plan.
