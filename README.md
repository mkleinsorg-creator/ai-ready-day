# AI Ready Day · Evangelist-Track

> Bau heute dein eigenes Tool, deinen eigenen Workflow oder deine eigene Anzeige —
> mit Claude Code als Co-Pilot. Du brauchst keine Programmier-Erfahrung.

## Start in 3 Schritten

### 1. Terminal öffnen (nur für das einmalige Setup)

Drück `Cmd + Leertaste`, tipp `Terminal`, drück Enter.
Ein schwarzes Fenster geht auf. **Hier passiert nur das Setup** — danach arbeitest du komplett in der Claude Desktop App.

### 2. Diesen Befehl reinkopieren und Enter drücken

```bash
curl -fsSL https://raw.githubusercontent.com/mkleinsorg-creator/ai-ready-day/main/bootstrap.sh | bash
```

Das Script richtet dir alles ein und erklärt dabei, was es tut.
Dauert ca. 5 Minuten. Wenn etwas hakt: Max rufen.

### 3. In die Claude Desktop App wechseln

- **Öffne die Claude Desktop App** (die du eh schon hast)
- Drück **`Cmd + 3`** — das öffnet das integrierte Claude-Code-Fenster
- Kopier den Master-Prompt aus `~/ai-ready-day/prompts/00-router.md` in die erste Nachricht
  *(Alternativ:* `/load ~/ai-ready-day/prompts/00-router.md`*)*

**Was als nächstes passiert:**
1. Claude fragt nach deinem Namen + deiner Idee
2. **Schärfung mit BMAD** — eine Methode, die deine Idee in baubare Schritte zerlegt (außer bei Meta-Ads, da geht's direkt los)
3. Gemeinsam baust du Schritt für Schritt das, was du dir vorgenommen hast

Das Terminal kannst du danach geschlossen lassen oder im Hintergrund liegen — wir holen es nur raus, wenn ein echter Build-Befehl ansteht.

---

## Was ist hier drin?

| Ordner / Datei | Was es ist |
|---|---|
| `bootstrap.sh` | Setup-Script — macht alles startklar |
| `prompts/` | Der Master-Prompt + Spezial-Anleitungen für jeden Pfad |
| `docs/SETUP.md` | Wenn du's lieber Schritt für Schritt liest |
| `docs/TROUBLESHOOTING.md` | Wenn etwas hakt |
| `bundles/bmad/` | Das BMAD-Framework — Methode für strukturiertes Ideen-Bauen |
| `bundles/n8n/` | Spezialisten-Agenten für n8n-Workflows |

## Was du heute bauen kannst

- 🌐 **Eine eigene Web-App** (z. B. internes Tool, Mini-Dashboard, Landingpage)
- 🔁 **Einen n8n-Workflow** (Automatisierung, Slack-Bot, Daten-Pipeline)
- 📣 **Meta-Ads** über die neue Facebook Ads CLI steuern
- ✅ **Eine Asana-Automatisierung** (Tasks, Status, Reports)
- 💡 **Was ganz anderes** — beschreib's, wir finden einen Weg

## Falls du heute streiken willst

Das hier ist optional. Aber: das wird einer der besten Tage des Jahres. 💚

---

*Made with 💚 für die falkemedia Gruppe · AI Ready Day · 21.05.2026*
