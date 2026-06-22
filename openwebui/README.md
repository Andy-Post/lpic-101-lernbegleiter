# Open WebUI Setup

Anleitung fuer den Betrieb des LPIC-101 Lernbegleiters mit Open WebUI und einem lokalen Sprachmodell.

---

## Voraussetzungen

- Open WebUI installiert und erreichbar (https://github.com/open-webui/open-webui)
- Ollama mit einem geeigneten Modell (mindestens 27B empfohlen)
- Admin-Zugang zu Open WebUI

---

## Modellempfehlung

Fuer dieses Projekt eignen sich Modelle mit breitem Faktenwissen und guter Instruktionstreue.

Getestete Optionen:

| Modell | Groesse | Eignung |
|---|---|---|
| Mixtral | 46.7B | gut |
| Qwen3 | 30B | gut |
| Gemma3 | 27B | ausreichend |
| Llama3.1 | 8B | nicht empfohlen |
| Gemma4 | 8B | nicht empfohlen |

Modelle unter 27B halten sich bei komplexen Mehrschicht-Anweisungen (Sokratik, keine Monologe, Fehler als Wiederholungsanlass) erfahrungsgemaess nicht zuverlaessig an die Instruktionen.

---

## Schritt 1: Knowledge Base anlegen

In Open WebUI: Workspace > Knowledge > New Knowledge

Name: `LPIC-101 Lernbegleiter`

Folgende Dateien hochladen:
- Alle `.md`-Dateien aus dem `knowledge/`-Verzeichnis
- `LPIC101_Lernplan.md`
- `LPIC1_Gesamtstrategie.md`

---

## Schritt 2: Modell konfigurieren

In Open WebUI: Workspace > Models > New Model

Einstellungen:
- Name: `LPIC-101 Lernbegleiter`
- Base Model: gewaehltes Ollama-Modell (z.B. `mixtral:latest`)
- Knowledge: die eben erstellte Knowledge Base verknuepfen
- System Prompt: gesamten Inhalt von `project-prompt.md` einfuegen

---

## Schritt 3: Erste Session starten

Das neue Modell auswaehlen und eine neue Konversation beginnen.

Einstieg mit:

```
Starte eine neue LPIC-Lernsession. Welche Phase bin ich gerade in und was war das letzte Thema?
```

---

## Bekannte Einschraenkungen gegenueber Claude Projects

- RAG (Retrieval Augmented Generation): Open WebUI laedt nur relevante Chunks aus den Knowledge-Dateien, nicht den vollstaendigen Kontext. Das kann bei phasenubergreifenden Fragen zu Luecken fuehren.
- Instruktionstreue: Lokale Modelle verlassen die Sokratik-Regeln gelegentlich. In diesem Fall explizit darauf hinweisen: "Frag mich zuerst, was ich vermute."
- Kein bash_tool: Die Zeitstempel-Funktion im System Prompt (TZ=Europe/Berlin date) funktioniert in Open WebUI nicht. Den entsprechenden Abschnitt im System Prompt ggf. entfernen oder ignorieren.

---

## Hinweis zu Datenschutz

Bei Betrieb auf einem firmeneigenen Open-WebUI-Server: alle Eingaben sind fuer die Administratoren der Instanz potenziell sichtbar. Keine persoenlichen Daten eingeben.
