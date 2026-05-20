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

## 4. Terminal öffnen

Das Terminal ist ein Fenster, in dem du dem Computer Befehle in Textform gibst. Es sieht erstmal nackt aus — keine Sorge.

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

## 6. Loslegen

Wenn das Script `✅ Fertig` sagt, tippst du:

```bash
cd ~/ai-ready-day
claude
```

Du bist jetzt in Claude Code. Dann:

```
/load prompts/00-router.md
```

Claude begrüßt dich und fragt, was du heute bauen willst.
Ab hier: einfach machen lassen. Du bist in guten Händen.

---

## Wenn etwas hakt

Schau in `docs/TROUBLESHOOTING.md` oder ruf Max.
Das ist heute kein Versagen — das ist Plan.
