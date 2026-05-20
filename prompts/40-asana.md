# Tech-Briefing für BMAD · Pfad: Asana-Automatisierung

> Diese Datei ist **kein User-Prompt**, sondern ein **Pflicht-Kontext für BMAD**.
> Der Master-Prompt übergibt diesen Inhalt beim Start von `/bmad` an die BMAD-Agenten.
> BMAD-Architect und BMAD-Dev richten ihre Empfehlungen nach diesem Briefing.

## Tools & Setup

- **Asana-MCP** ist in `~/.claude/.mcp.json` als SSE konfiguriert
- Beim ersten Aufruf passiert ein einmaliger OAuth-Flow im Browser
- User authentifiziert sich mit seinem falkemedia-Asana-Account
- Danach hat Claude direkten Lese- und Schreibzugriff auf die Asana-Projekte des Users

## Was BMAD-Architect berücksichtigen muss

- **Smoke-Test zuerst:** Lass BMAD-Dev als ersten Schritt `@asana Zeig mir meine Projekte` ausführen. Wenn das nicht klappt — Berechtigung klären, bevor irgendwas anderes passiert.
- **Klein anfangen:** Eine Aktion, ein Asana-Objekt. Erst zum Laufen bringen, dann erweitern.
- **Schreib- vs. Lese-Operationen trennen:** Reine Reports/Status-Abfragen sind risikoarm. Tasks anlegen / Status ändern / löschen ist riskant → vor jeder Schreib-Operation **explizit fragen**.

## Was BMAD-Dev berücksichtigen muss

- **Schreib-Confirmations:** Vor jedem Schreibzugriff (Task erstellen, Status ändern, Task löschen) **explizit nachfragen**: *"Soll ich den Task jetzt wirklich erstellen?"*
- **Berechtigung kann verweigert werden:** User hat nur Zugriff auf seine Projekte, nicht auf alle. Bei `403 Forbidden`: ruhig erklären, Max einbinden.
- **Output-Files** (Skripte, Wiederholbarkeit) landen in `~/ai-ready-day/projects/<projektname>/`
- **Asana-Sprache:** Wenn der User von "Tasks" spricht, BMAD übersetzt zu Asana-Terminologie (Sections, Custom Fields, Followers).

## Typische Use-Cases (BMAD darf vorschlagen)

- *"Schreib jeden Freitag einen Wochen-Status aus den Tasks meines Projekts in Slack."*
- *"Wenn ein Task in 'Review' kommt, schick mir eine Erinnerung."*
- *"Erzeug aus diesem Briefing-Dokument 10 Tasks mit Verantwortlichen und Deadlines."*
- *"Mach mir eine wöchentliche Übersicht über alle Blocker im Projekt X."*

## Wiederkehrende Aktionen (Wenn der Workflow regelmäßig laufen soll)

- BMAD-Dev legt Skript in `~/ai-ready-day/projects/<projektname>/` ab
- Für heute: manuell laufen lassen reicht
- Vollautomatisierung (Cron, n8n-Schedule) ist Bonus, nicht Pflicht

## falkemedia-spezifische Constraints

- **Echte Asana-Daten:** Was BMAD anlegt, sehen Kolleg:innen. Bei produktiven Projekten besonders vorsichtig.
- **Test-Projekt bevorzugen:** Wenn der User Sorge hat, in echtem Projekt zu experimentieren — empfehle, ein "AI Ready Day Sandbox"-Projekt in Asana anzulegen und dort zu testen.

## Was BMAD-QA berücksichtigen muss

- **Verifizieren in Asana selbst:** Nach jeder Schreib-Aktion in Asana nachschauen — ist der Task da, wo er hin soll?
- **Rollback-Strategie:** Wenn etwas falsch angelegt wurde, BMAD soll wissen wie es rückgängig zu machen ist (Task löschen, Status zurücksetzen).

## Erfolgs-Definition für diesen Pfad

Am Ende des Tages hat der User:
1. Eine funktionierende Asana-Automatisierung (mindestens einmal erfolgreich ausgeführt)
2. Echtes Ergebnis sichtbar in Asana oder im Zielsystem (z. B. Slack)
3. Bonus: Repeatability — Skript, das er nochmal laufen lassen kann

Wenn nur 1 + 2 erreicht werden: völlig okay.
