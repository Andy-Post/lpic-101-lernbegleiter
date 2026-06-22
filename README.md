# LPIC-101 Lernbegleiter

Ein vollstaendiges Claude-Projekt-Setup fuer die praxisorientierte Vorbereitung auf die LPIC-1 Pruefung 101-500.

Das Projekt setzt auf aktives Lernen durch Shell-Praxis, Sokratik und prufungsnahe Uebungen – nicht auf passive Theorievermittlung.

---

## Inhalt

```
README.md                    Diese Datei
LICENSE                      CC BY-SA 4.0
project-prompt.md            System Prompt fuer Claude Projects
LPIC101_Lernplan.md          Strukturierter Lernplan (10 Phasen, 42 Sessions)
LPIC1_Gesamtstrategie.md     Lernstrategie, Philosophie, Ressourcen
SETUP.md                     Schritt-fuer-Schritt VM-Einrichtung (Debian ARM64 / UTM)
knowledge/                   Wissensdateien pro LPIC-Topic (101.1 bis 104.7)
openwebui/                   Anleitung fuer Open WebUI + lokale Modelle
```

---

## Voraussetzungen

- Apple Silicon Mac (M4 empfohlen) oder vergleichbares System
- UTM (https://mac.getutm.app) oder VMware Fusion / Parallels
- Debian ARM64 Netinstall (https://www.debian.org/distrib/netinst)
- SSH-Zugriff auf die VM
- Claude-Account mit Projects-Zugang (claude.ai/projects) ODER lokales Open-WebUI-Setup

Die vollstaendige VM-Einrichtung ist in `SETUP.md` dokumentiert.

---

## Setup: Claude Projects (empfohlen)

### 1. Neues Projekt anlegen

Auf https://claude.ai/projects ein neues Projekt erstellen.

### 2. System Prompt setzen

Den gesamten Inhalt von `project-prompt.md` in das Feld "Project Instructions" kopieren.

### 3. Wissensdateien hochladen

Alle Dateien aus dem `knowledge/`-Verzeichnis sowie `LPIC101_Lernplan.md` und `LPIC1_Gesamtstrategie.md` als Projektdateien hochladen.

### 4. Loslegen

Eine neue Konversation im Projekt starten. Der Lernbegleiter orientiert sich automatisch am Lernplan und den Wissensdateien.

---

## Setup: Open WebUI (Alternative)

Siehe `openwebui/README.md` fuer die vollstaendige Anleitung.

Empfohlenes Modell: Mixtral 47B oder groesseres Modell. Modelle unter 27B eignen sich nicht zuverlaessig fuer die komplexen Instruktionen dieses Projekts.

---

## Lernmethodik

Das Projekt arbeitet nach einem festen Prinzip:

1. Kurzer theoretischer Einstieg
2. Vorhersage: Was wird der Befehl tun?
3. Ausfuehren in der VM
4. Eigene Interpretation der Ausgabe
5. Korrektur und Ergaenzung durch Claude
6. Variation mit anderen Optionen / Fehlerszenarien

Sessions dauern typischerweise 30 Minuten. Freitags gibt es eine Phasenpruefung (10 LPIC-nahe Fragen, Bestehensgrenze 80%).

---

## Lernplan-Struktur

| Phase | Thema | Sessions |
|---|---|---|
| 1 | Shell Foundation | 1-5 |
| 2 | Textverarbeitung und Streams | 6-10 |
| 3 | Prozesse und Jobs | 11-14 |
| 4 | Rechte und Benutzer | 15-19 |
| 5 | Filesysteme | 20-23 |
| 6 | Paketmanagement | 24-27 |
| 7 | Shell Scripting | 28-31 |
| 8 | Boot und System | 32-35 |
| 9 | Hardware und System-Internals | 36-39 |
| 10 | Netzwerk-Grundlagen | 40-42 |

Gesamtumfang: ca. 20 Wochen bei 30 Minuten taeglich.

---

## Wissensdateien (knowledge/)

Die Dateien basieren auf den offiziellen LPI Learning Materials (CC BY-NC-ND 4.0) und eigenen Mitschriften. Sie decken alle pruefungsrelevanten Topics der LPIC-101 Pruefung ab.

| Datei | Topic |
|---|---|
| 101_1.md | Hardwareeinstellungen ermitteln |
| 101_2.md | Linux-System booten |
| 101_3.md | Runlevel / Boot-Targets |
| 102_1.md | Festplattenlayout |
| 102_2.md | Bootmanager installieren |
| 102_3.md | Shared Libraries |
| 102_4.md | Debian-Paketverwaltung |
| 102_5.md | RPM und YUM/DNF |
| 102_6.md | Linux als Virtualisierungsgast |
| 103_1.md | Shell-Kommandozeile |
| 103_2.md | Dateien verarbeiten |
| 103_3.md | Grundlegende Dateiverwaltung |
| 103_4.md | Datenstroeme, Pipes, Umleitungen |
| 103_5.md | Prozessmanagement |
| 103_6.md | Prozesspriorisierung |
| 103_7.md | Regulaere Ausdruecke |
| 103_8.md | vi-Editor |
| 104_1.md | Partitionen und Dateisysteme |
| 104_2.md | Dateisystem-Integritaet |
| 104_3.md | Einhängen und Aushaengen |
| 104_5.md | Dateiberechtigungen |
| 104_6.md | Hard- und Softlinks |
| 104_7.md | Systemdateien finden |

---

## Ressourcen

- LPI Exam Objectives: https://www.lpi.org/our-certifications/exam-101-102-objectives/
- LPI Learning Materials: https://learning.lpi.org/en/learning-materials/101-500/
- Wikiversity Testfragen: https://de.wikiversity.org/wiki/Kurs:Wissenstest_Linux/LPIC1-101

---

## Lizenz

Dieses Projekt steht unter der Lizenz **Creative Commons BY-SA 4.0**.

Die enthaltenen Wissensdateien basieren teilweise auf LPI Learning Materials (CC BY-NC-ND 4.0, learning.lpi.org). Diese Dateien duerfen ausschliesslich fuer nicht-kommerzielle Zwecke genutzt werden.
