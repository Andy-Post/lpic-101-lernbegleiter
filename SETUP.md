# Unterdokument – Installation und Einrichtung der LPIC-1 Lernumgebung
 
## Ziel
 
Aufbau einer kostenlosen, stabilen und praxisnahen Linux-Lernumgebung auf einem Apple Silicon Mac (M4).
 
---
 
# Zielarchitektur
 
| Komponente | Rolle |
|---|---|
| macOS | Host-System |
| UTM | Virtualisierung |
| Debian ARM64 | Linux-Trainingssystem |
| SSH | Standardzugriff |
 
---
 
# Verwendete Software
 
## Virtualisierung
 
UTM:
https://mac.getutm.app/
 
## Linux-Distribution
 
Debian ARM64 Netinstall:
https://www.debian.org/distrib/netinst
 
Wichtig:
- ARM64 / aarch64 auswählen
- NICHT x86_64
---
 
# Schritt 1 – UTM installieren
 
## Download
 
UTM von der offiziellen Website herunterladen.
 
## Installation
 
- DMG öffnen
- UTM nach „Programme“ ziehen
- starten
macOS kann beim ersten Start Sicherheitsrückfragen anzeigen.
Diese bestätigen.
 
---
 
# Schritt 2 – Debian ISO herunterladen
 
Von:
https://www.debian.org/distrib/netinst
 
Die ARM64-Netinstall-ISO herunterladen.
 
Beispiel:
- debian-12.x.x-arm64-netinst.iso
---
 
# Schritt 3 – Neue VM erstellen
 
## In UTM
 
- „Create a New Virtual Machine“
- „Virtualize“ auswählen
- Linux auswählen
---
 
# Schritt 4 – ISO auswählen
 
Die heruntergeladene Debian ARM64 ISO auswählen.
 
---
 
# Schritt 5 – VM-Ressourcen konfigurieren
 
## Empfehlung
 
| Einstellung | Wert |
|---|---|
| CPU | 2–4 Kerne |
| RAM | 4–8 GB |
| Disk | 30–50 GB |
| Netzwerk | NAT |
 
---
 
# Schritt 6 – Debian installieren
 
## Sprache
 
Deutsch oder Englisch.
 
Für LPIC ist Englisch langfristig sinnvoller.
 
---
 
# Schritt 7 – Hostname setzen
 
Beispiel:
 
```text
lpic-debian
```
 
---
 
# Schritt 8 – Benutzer anlegen
 
Beispiel:
 
```text
Benutzername: lpicuser
```
 
Ein starkes Passwort verwenden.
 
---
 
# Schritt 9 – Partitionierung
 
Für den Anfang:
 
- Guided
- Entire Disk
- All files in one partition
Später können komplexere Partitionierungskonzepte geübt werden.
 
---
 
# Schritt 10 – Paketquellen
 
Standardmäßig übernehmen.
 
---
 
# Schritt 11 – Softwareauswahl
 
WICHTIG:
 
KEINE Desktop-Umgebung installieren.
 
Nicht auswählen:
- GNOME
- KDE
- XFCE
- Cinnamon
Nur auswählen:
- SSH server
- standard system utilities
Das System soll terminalorientiert bleiben.
 
---
 
# Schritt 12 – Installation abschließen
 
Nach Abschluss:
- Neustart
- ISO auswerfen
- VM booten
---
 
# Schritt 13 – Erstes Login
 
Mit dem angelegten Benutzer anmelden.
 
---
 
# Schritt 14 – Erstes Systemupdate
 
```bash
sudo apt update
sudo apt full-upgrade -y
```
 
---
 
# Schritt 15 – Wichtige Basiswerkzeuge installieren
 
```bash
sudo apt install -y \
vim \
curl \
wget \
git \
htop \
net-tools \
rsync \
zip \
unzip \
man-db \
bash-completion
```
 
---
 
# Schritt 16 – SSH-Zugriff vorbereiten
 
## IP-Adresse prüfen
 
```bash
ip a
```
 
---
 
## Test von macOS-Terminal
 
```bash
ssh lpicuser@IPDERVM
```
 
Beispiel:
 
```bash
ssh lpicuser@192.168.64.5
```
 
---
 
# Schritt 17 – Snapshot erstellen
 
Sobald das System sauber läuft:
 
- VM herunterfahren
- Snapshot in UTM anlegen
Das ist der Basis-Rettungspunkt.
 
---
 
# Empfohlene tägliche Nutzung
 
## Nicht GUI-zentriert arbeiten
 
Sondern:
- SSH verwenden
- man-Pages lesen
- Shell nutzen
- Logs analysieren
- Skripte schreiben
- Dinge kaputtmachen
- reparieren
---
 
# Erste wichtige Übungsbefehle
 
## Navigation
 
```bash
pwd
ls -lah
cd
```
 
---
 
## Dateien
 
```bash
cp
mv
rm
touch
mkdir
```
 
---
 
## Lesen
 
```bash
cat
less
tail
head
```
 
---
 
## Prozesse
 
```bash
ps
top
htop
kill
```
 
---
 
## Netzwerk
 
```bash
ip a
ss -tulpen
ping
curl
```
 
---
 
## Textverarbeitung
 
```bash
grep
cut
sort
uniq
awk
sed
```
 
---
 
# Wichtiger Lernhinweis
 
Nicht versuchen:
- alles gleichzeitig zu lernen.
Sondern:
- täglich üben
- wiederholen
- Muster erkennen
- echte Probleme lösen
LPIC-1 ist kein Sprint.
Aber mit täglicher Praxis bis Oktober/November absolut realistisch.
 
