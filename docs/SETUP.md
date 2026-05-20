# Setup für den AI Ready Day · Schritt für Schritt

> Diese Anleitung ist für dich, wenn du noch nie programmiert hast.
> Wir erklären alles. Wenn ein Wort neu ist — kein Stress, einfach weitermachen.

## Was du schon hast (gut!)

- ✅ Mac
- ✅ Claude Pro-Account (über falkemedia)
- ✅ Claude Desktop App
- ✅ Falkemedia-Google-Account

## Was wir heute zusätzlich brauchen

- **GitHub** — wie Google Drive, aber für Code
- **Vercel** — bringt deine App ins Internet
- **Supabase** — Datenbank, falls deine App eine braucht
- **Claude Code** — das CLI-Tool, mit dem wir heute bauen

---

## 1. GitHub-Account (3 Min)

GitHub ist wie Google Drive für Code. Wir brauchen einen Account, weil Vercel und Supabase darüber funktionieren.

- Geh auf https://github.com
- Klick oben rechts auf **"Sign up"**
- Nimm deine **falkemedia-Mail**
- Username egal — kann auch lustig sein
- E-Mail bestätigen

## 2. Vercel-Account (2 Min)

Vercel macht aus deinem Code eine echte Webseite im Internet. Kostenlos für unsere Zwecke.

- Geh auf https://vercel.com/signup
- Klick **"Continue with GitHub"** → Autorisieren
- **"Hobby"**-Plan auswählen
- Fertig

## 3. Supabase-Account (2 Min)

Supabase ist eine Datenbank — also der Ort, wo deine App ihre Infos speichert. Kostenlos für heute.

- Geh auf https://supabase.com
- Klick **"Start your project"** → **"Sign in with GitHub"**
- **Free**-Plan auswählen
- Fertig — Projekte legen wir später per Befehl an

## 4. Terminal öffnen (nur für das einmalige Setup)

Das Terminal ist ein Fenster, in dem du dem Computer Befehle in Textform gibst. **Heute brauchst du es nur einmal, fürs Setup.** Danach arbeitest du in der gewohnten Claude Desktop App weiter.

- Drück `Cmd + Leertaste`
- Tipp `Terminal`
- Drück Enter

Du siehst jetzt ein Fenster, in dem dein Benutzername steht. Genau richtig.

## 5. Bootstrap ausführen

Kopier diesen Befehl, klick ins Terminal, drück `Cmd + V`, dann Enter:

```bash
curl -fsSL https://raw.githubusercontent.com/mkleinsorg-creator/ai-ready-day/main/bootstrap.sh | bash
```

Das Script erklärt unterwegs, was es macht. Lies mit — das hilft beim Verstehen.

**Wenn das Script dich auffordert, dich irgendwo einzuloggen:**
- Browser geht von selbst auf
- Mit dem zugehörigen Account anmelden
- Zurück ins Terminal — Script läuft weiter

## 6. Rüber in die Claude Desktop App — der erste echte Schritt heißt BMAD

Wenn das Script `✅ Fertig` sagt: **Terminal kannst du jetzt liegenlassen.**

- Öffne die **Claude Desktop App** (kennst du schon — das ist die, in der du sonst chattest)
- Drück **`Cmd + 3`** — das öffnet das integrierte Claude-Code-Fenster innerhalb der App. Dort funktionieren Slash-Commands wie `/bmad`.
- In die erste Nachricht kopierst du den Master-Prompt aus `~/ai-ready-day/prompts/00-router.md` rein
  *(Alternativ:* `/load ~/ai-ready-day/prompts/00-router.md` *direkt eintippen)*

Claude begrüßt dich und fragt, was du heute bauen willst.

**Dein erster Arbeitsschritt heißt BMAD** — eine Methode, die mit dir gemeinsam deine Idee schärft, ein paar gezielte Fragen stellt und am Ende einen Bauplan mit konkreten Schritten liefert.

Lass dich davon nicht abschrecken — du musst die Methode nicht verstehen. Du beantwortest einfach die Fragen, BMAD macht den Rest.

*(Ausnahme: Wer Meta-Ads baut, überspringt BMAD und geht direkt zur Facebook Ads CLI.)*

Ab hier: einfach machen lassen. Du bist in guten Händen.

## Wann brauchst du das Terminal nochmal?

Nur, wenn Claude dir sagt *"Kopier diesen Befehl ins Terminal"* — z. B. wenn deine Web-App lokal gestartet oder ins Internet gestellt werden soll. Dann holst du das Terminal-Fenster kurz nach vorne, drückst Enter, und gehst zurück in die Claude Desktop App.

---

## Wenn etwas hakt

Schau in `docs/TROUBLESHOOTING.md` oder ruf Max.
Das ist heute kein Versagen — das ist Plan.
