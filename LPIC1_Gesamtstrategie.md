# LPIC-1 Vorbereitung – Gesamtstrategie
 
## Ziel
 
- LPIC-1 101 Prüfung bis spätestens Oktober/November 2026 bestehen
- Fokus zunächst auf 101
- Nicht nur „Befehle lernen“, sondern Linux-Systemdenken entwickeln
---
 
# Wichtige Erkenntnis
 
LPIC-1 ist KEIN einfacher Bash-Kurs.
 
Die Prüfung testet:
- Linux-/UNIX-Verständnis
- Systemadministration
- Shell-Denken
- Textverarbeitung
- Prozesse
- Filesysteme
- Rechte
- Bootprozess
- Paketmanagement
- Netzwerke
- Automatisierung
Die Prüfung enthält:
- Detailfragen
- Trickfragen
- historische UNIX-Konzepte
- distributionsübergreifende Themen
---
 
# Lernphilosophie
 
Nicht:
- stumpfes Auswendiglernen
Sondern:
- Muster erkennen
- Zusammenhänge verstehen
- echte Praxis
- tägliche Shell-Nutzung
- Probleme lösen
Linux ist eine „Sprache“.
 
Das Ziel lautet:
„GNU/Linux sprechen lernen.“
 
---
 
# Wichtigste Kompetenzbereiche
 
## EXTREM wichtig
 
- Shell/Bash
- Pipes
- stdin/stdout/stderr
- grep/sed/awk
- find/xargs
- Filesysteme
- Mounts
- Permissions
- Prozesse/Signals
## Sehr wichtig
 
- systemd
- Paketmanagement
- Netzwerkgrundlagen
- Scripting
- Regex
- Cron
- Logging
---
 
# Lernstrategie
 
## 1. Echte Linux-VM verwenden
 
Docker allein reicht NICHT.
 
Empfohlen:
- Debian Server
- Ubuntu Server
Ohne GUI.
 
---
 
# Warum keine reine Docker-Umgebung?
 
Docker bildet viele LPIC-Themen NICHT realistisch ab:
- Bootprozess
- systemd
- Runlevel/Targets
- Kernel-/Device-Themen
- echtes Service-Management
- echtes Netzwerk-/Mount-Verhalten
Docker eignet sich nur ergänzend.
 
---
 
# Zusätzliche wichtige Erkenntnisse zur Lernumgebung
 
## Host-/Gast-System-Denken
 
### Host-System
macOS bleibt das Alltagssystem für:
- Browser
- Dokumentation
- PDFs
- Lernmaterial
- Notizen
- ChatGPT
### Gast-System
Die Debian-VM wird der eigentliche Trainingsserver für:
- Shell
- LPIC-Übungen
- Scripting
- Administration
- Fehlersuche
- Reparaturübungen
---
 
# ARM64 / Apple Silicon
 
Da ein Apple Silicon Mac (M4) verwendet wird:
- ARM64/aarch64 verwenden
- KEINE x86_64-Emulation
- natives ARM64 Debian installieren
Die meisten LPIC-Themen sind architekturunabhängig:
- Bash
- systemd
- Prozesse
- Rechte
- Netzwerk
- Filesysteme
- grep/sed/awk
---
 
# Snapshots sind extrem wichtig
 
Vor größeren Experimenten:
- Snapshot erstellen
- Änderungen durchführen
- System absichtlich beschädigen
- Reparatur versuchen
- notfalls Snapshot zurückrollen
Das ist eine der effektivsten Lernmethoden überhaupt.
 
---
 
# Dinge, die absichtlich kaputtgemacht werden sollten
 
Später gezielt üben:
- Rechte zerstören
- PATH beschädigen
- Dienste deaktivieren
- fstab falsch konfigurieren
- Netzwerkfehler erzeugen
- volle Dateisysteme simulieren
- Benutzer aussperren
- GRUB-/Bootprobleme erzeugen
Linux lernt man durch:
- Fehler
- Analyse
- Reparatur
---
 
# SSH als Standard-Arbeitsweise
 
Ziel:
Die VM hauptsächlich per SSH administrieren.
 
Beispiel:
 
```bash
ssh user@debianvm
```
 
Das entspricht echter Linux-/Serverpraxis deutlich stärker als Arbeiten direkt in einer VM-Konsole.
 
---
 
# Empfohlene Virtualisierung auf dem Mac
 
## Gute Optionen
 
- UTM
- VMware Fusion
- Parallels
## Empfehlung
 
Debian Server minimal installieren.
 
---
 
# Die wichtigste Lernmethode
 
Nicht lesen.
Nicht Videos konsumieren.
 
SONDERN:
 
- selbst tippen
- experimentieren
- Systeme kaputtmachen
- Fehler analysieren
- reparieren
Linux lernt man durch Praxis.
 
---
 
# Täglicher Lernansatz
 
## Ziel:
Jeden Tag echte Shell-Zeit.
 
Mindestens:
- 30–90 Minuten
Besser:
- kleine tägliche Praxis
als
- seltene große Theorieblöcke.
---
 
# Lernstruktur
 
## Ebene 1 – Syntax
Befehle kennen.
 
## Ebene 2 – Patterns
Werkzeuge kombinieren.
 
Beispiel:
 
```bash
cat logfile | grep ERROR | sort | uniq -c
```
 
## Ebene 3 – Systemdenken
Verstehen:
- Prozesse
- Pipes
- Dateideskriptoren
- Inodes
- PATH
- Exitcodes
- Umleitungen
## Ebene 4 – LPIC-Prüfungsmuster
Verstehen:
- Trickfragen
- ähnliche Optionen
- historische Tools
- Unterschiede zwischen Distributionen
---
 
# Wichtigster Grundsatz
 
Nicht:
„Ich kenne viele Befehle.“
 
Sondern:
„Ich verstehe, wie UNIX denkt.“
 
---
 
# Realistische Einschätzung
 
Vorhandene Vorteile:
- IT-Erfahrung
- Linux-Erfahrung
- Automatisierungsdenken
- Incident-Management
- Shell-/Skript-Erfahrung
- Prozessdenken
- Regex-/Logikverständnis
Wahrscheinlich fehlt weniger Wissen als:
- Struktur
- Wiederholung
- Prüfungsroutine
- systematische Abdeckung
---
 
# Wichtigste Quellen
 
## Offizielle Objectives
 
https://www.lpi.org/our-certifications/exam-101-102-objectives/
 
## Learning Materials
 
https://learning.lpi.org/en/learning-materials/101-500/
 
## Wikiversity-Testfragen
 
https://de.wikiversity.org/wiki/Kurs:Wissenstest_Linux/LPIC1-101
 
---
 
# Entscheidender Erfolgsfaktor
 
Nicht:
„Alles wissen.“
 
Sondern:
- regelmäßig üben
- echte Probleme lösen
- Shell täglich benutzen
- Objective-orientiert lernen
- Zusammenhänge verstehen
---
 
