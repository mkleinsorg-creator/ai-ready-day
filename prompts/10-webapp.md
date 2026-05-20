# Pfad: Web-App bauen

## Stack
- **Next.js** — das Framework, in dem deine App lebt
- **Vercel** — wo deine App ins Internet kommt
- **Supabase** — Datenbank (nur falls deine App eine braucht)

## Vorgehen

### 1. BMAD-Output aufgreifen
BMAD hat dir Stories, Architektur und einen Bauplan gegeben. Den nehmen wir jetzt als Leitplanke.

### 2. Projekt-Ordner anlegen
```bash
mkdir -p ~/ai-ready-day/projects/<projektname>
cd ~/ai-ready-day/projects/<projektname>
```

### 3. Next.js initialisieren
```bash
npx create-next-app@latest .
```
Bei den Fragen: alle Defaults sind okay. Erklär dem User vorher kurz, was Next.js ist und warum wir es nutzen.

### 4. Erste Seite anpassen
Öffne `app/page.tsx` und bau die Landing-Seite gemäß BMAD-Stories. Erklär dem User jeden Schritt:
- Was tust du gerade?
- Welche Datei änderst du?
- Wie sieht das Ergebnis aus?

### 5. Lokal testen
```bash
npm run dev
```
Browser öffnet sich. **Erfolg sichtbar machen:** *"Deine App läuft! Du kannst sie jetzt auf [http://localhost:3000](http://localhost:3000) sehen."*

### 6. Supabase nur, wenn nötig
Bei reinen Frontend-Apps (Landingpage, Mini-Dashboard ohne Persistenz) brauchst du keine Datenbank.

Wenn doch:
```bash
supabase init
supabase login
supabase projects create <name>
```

Schema mit BMAD-Output abgleichen. SQL-Migrations in `supabase/migrations/`.

### 7. Deployen mit Vercel
```bash
vercel
```
Beim ersten Mal autorisierst du dich im Browser. Folge den Prompts.

Bei Erfolg: **explizit feiern**.
> *"Deine App ist jetzt live unter [URL]. Du kannst sie deinen Kolleg:innen schicken."*

## Wichtige Prinzipien für diesen Pfad

- Erklär jeden Befehl vorher in einem Satz.
- Wenn ein Fehler kommt: lies ihn vor, übersetz ihn auf Deutsch, schlag eine Lösung vor.
- Nach jedem sichtbaren Erfolg (lokaler Browser läuft / Deploy geklappt): feier ihn explizit.
- Halt die Pakete klein. Erst zum Laufen bringen, dann erweitern.
