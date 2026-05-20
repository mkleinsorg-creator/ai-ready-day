# Pfad: Asana-Automatisierung bauen

## Tools verfügbar
- **Asana-MCP** (direkt in Claude Code aufrufbar — als SSE über Asanas hosted Server)
- **BMAD-Methode** für die Ideation (sollte schon gelaufen sein)

## Vorgehen

### 1. BMAD-Output aufgreifen
Klarer Use-Case: was soll passieren, wann, mit welchen Asana-Objekten?

### 2. Asana-MCP testen

Sag dem User:
> *"Ich verbinde mich jetzt einmal kurz mit Asana, um zu prüfen, dass alles funktioniert."*

Test-Aufruf:
```
@asana Zeig mir meine Projekte.
```

Falls eine Autorisierungs-Anfrage im Browser aufgeht: User loggt sich mit falkemedia-Asana ein. Das ist normal und passiert nur einmal.

Wenn die Projekt-Liste kommt: **Erfolg sichtbar machen.**
> *"Klappt! Wir sehen jetzt deine Asana-Projekte direkt aus Claude heraus."*

### 3. Konkrete Use-Cases anbieten (wenn der User unsicher ist)

- *"Schreib jeden Freitag einen Wochen-Status aus den Tasks meines Projekts in Slack."*
- *"Wenn ein Task in 'Review' kommt, schick mir eine Erinnerung."*
- *"Erzeug aus diesem Briefing-Dokument 10 Tasks mit Verantwortlichen und Deadlines."*
- *"Mach mir eine wöchentliche Übersicht über alle Blocker im Projekt X."*

### 4. Projekt-Ordner anlegen
```bash
mkdir -p ~/ai-ready-day/projects/<projektname>
cd ~/ai-ready-day/projects/<projektname>
```

Hier landen Skripte / Scheduler-Definitionen / Notizen.

### 5. Bauen — abhängig vom Use-Case

**Variante A: Einmalige Aktion** (z. B. Tasks aus Briefing generieren)
- Direkt in Claude Code: User liefert Input, Claude erstellt Tasks via Asana-MCP
- **Sicherheitsregel:** Vor Schreib-Operationen IMMER fragen — *"Soll ich den Task jetzt wirklich erstellen?"*

**Variante B: Wiederkehrende Aktion** (z. B. Wochenstatus jeden Freitag)
- Das Skript lebt in `~/ai-ready-day/projects/<name>/`
- Cron / Scheduled-Run / n8n-Schedule überlegen
- Für heute: erstmal manuell laufen lassen, später automatisieren

### 6. Iterieren

- Testlauf → schauen, was passiert
- User-Feedback einholen — *"Sieht der Output so aus, wie du wolltest?"*
- Anpassen, neu testen

## Wichtige Prinzipien für diesen Pfad

- **Vor Schreib-Operationen** (Tasks anlegen, Status ändern, löschen): explizit fragen.
- User hat Zugriff auf seine Asana-Projekte — nicht zwingend auf alle. Wenn etwas verweigert wird: nicht panisch, Berechtigungs-Thema mit Max klären.
- **Klein anfangen:** Ein Task auf einmal. Erst wenn das läuft, in die Breite.
- Asana-Daten sind echt. Was du anlegst, sehen Kolleg:innen. Sei vorsichtig.
