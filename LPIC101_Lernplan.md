# LPIC-101 Lernplan

# Wichtiger Lernansatz

Linux wird nicht nur durch richtige Konfiguration gelernt.

Ein wichtiger Teil der Ausbildung ist:
- Systeme absichtlich beschädigen
- Fehler analysieren
- Reparaturen durchführen
- Recovery üben

Vor destruktiven Übungen:
- immer zuerst einen UTM-Snapshot erstellen

Typische spätere Übungen:
- /etc/fstab beschädigen
- PATH zerstören
- Rechte falsch setzen
- Dienste deaktivieren
- Benutzer aussperren
- volle Dateisysteme simulieren
- Bootprobleme analysieren

## Prioritätskennzeichnung

- A = direkt LPIC-101-prüfungsrelevant
- B = wichtiges Kontextwissen
- C = eher LPIC-102 oder spätere Vertiefung

## Rahmendaten

- Zielprüfung: LPIC-1 Exam 101-500
- Zeitrahmen: ca. 20 Wochen
- Tageszeit: 30 Minuten/Tag
- Pruefungstag: Freitags (Phasenpruefung)
- Naechste Phase: nur nach bestandener Pruefung (mind. 80%)

## Schwerpunktbewertung wichtiger Themen

| Thema | Kennzeichnung |
|---|---|
| grep/sed/awk | A |
| Filesysteme | A |
| GRUB/systemd | A |
| Benutzerverwaltung | B |
| Cron/at | B |
| Shell Scripting | C |
| Netzwerk-Grundlagen | C |

---

## Phase 1 – Shell Foundation

Ziel: sicheres Bewegen und Arbeiten im Dateisystem

Session 1: Navigation
- pwd, ls (alle relevanten Optionen), cd, stat, file
- Absolute vs. relative Pfade
- Versteckte Dateien

Session 2: Dateien und Verzeichnisse
- cp, mv, rm, touch, mkdir, rmdir
- Kombiniert mit: Navigation (Session 1)

Session 3: Dateiinhalte lesen
- cat, less, more, head, tail, wc
- Kombiniert mit: cp, mv (Session 2)

Session 4: Finden und Suchen
- find (Optionen: -name, -type, -mtime, -size, -user, -exec)
- locate, which, type, whereis
- Kombiniert mit: Navigation + Dateien (Session 1+2)

Session 5: Hilfesystem
- man (Sections), apropos, whatis, info, --help
- Kombiniert mit: allen bisherigen Befehlen

Freitags-Pruefung Phase 1:
10 Fragen ueber Sessions 1-5, LPIC-Niveau

---

## Phase 2 – Textverarbeitung und Streams

Ziel: Daten aus Dateien und Prozessen verarbeiten und kombinieren

Session 6: grep und Regex-Grundlagen
- grep, egrep, fgrep
- Regex: ., *, ^, $, [], [^], \b
- Kombiniert mit: find, cat (Phase 1)

Session 7: Textfilter
- cut, sort, uniq, tr, wc
- Kombiniert mit: grep (Session 6)

Session 8: Streams und Umleitungen
- stdin (0), stdout (1), stderr (2)
- >, >>, 2>, 2>&1, /dev/null
- Pipes |
- Kombiniert mit: grep, cut, sort (Session 6+7)

Session 9: sed
- Grundsyntax: s/alt/neu/flags
- Adressen, Loeschen, Einsetzen
- Kombiniert mit: Pipes, grep (Session 6+8)

Session 10: awk
- Feldverarbeitung ($1, $2, NF, NR)
- Bedingungen, Berechnungen
- Kombiniert mit: sed, Pipes (Session 8+9)

Freitags-Pruefung Phase 2:
10 Fragen, Kombination aus Streams + Textwerkzeuge

---

## Phase 3 – Prozesse und Jobs

Session 11: Prozesse lesen
- ps (aux, -ef), top, htop
- Prozessbaum: pstree
- Kombiniert mit: grep (Phase 2)

Session 12: Signals und kill
- kill, killall, pkill
- Signals: SIGTERM (15), SIGKILL (9), SIGHUP (1)
- Kombiniert mit: ps (Session 11)

Session 13: Jobs und Hintergrundprozesse
- &, jobs, fg, bg, nohup, disown
- Kombiniert mit: Signals (Session 12)

Session 14: cron und at
- crontab -e, crontab -l, /etc/cron.*
- at, atq, atrm
- Kombiniert mit: Shell-Befehle aus Phase 1+2

Freitags-Pruefung Phase 3

---

## Phase 4 – Rechte und Benutzer

Session 15: Permissions Grundlagen
- chmod (symbolisch und numerisch), umask
- Lesen, Schreiben, Ausfuehren fuer user/group/other

Session 16: Eigentuemerschaft
- chown, chgrp
- Kombiniert mit: chmod, ls -l (Session 15)

Session 17: Benutzer und Gruppen
- useradd, usermod, userdel
- groupadd, groupmod, groupdel
- /etc/passwd, /etc/shadow, /etc/group

Session 18: Erhoehte Rechte und Sonderbits
- su, sudo, sudoers
- SUID, SGID, Sticky Bit
- Kombiniert mit: find -perm (Phase 1)

Session 19: Links
- ln (hard links vs. symbolic links)
- Unterschiede, Verhalten, Inode-Konzept
- Kombiniert mit: ls -lai, find (Phase 1)

Freitags-Pruefung Phase 4

---

## Phase 5 – Filesysteme

Session 20: Partitionskonzepte
- MBR vs. GPT
- fdisk, parted, lsblk, blkid

Session 21: Filesysteme erstellen und einhaengen
- mkfs (ext4, xfs, vfat)
- mount, umount, /etc/fstab
- Kombiniert mit: lsblk (Session 20)

Session 22: Speicherplatz und Zustand
- df, du
- fsck, tune2fs
- Kombiniert mit: find -size (Phase 1)

Session 23: Swap
- swapon, swapoff, mkswap
- /proc/swaps
- Kombiniert mit: fstab (Session 21)

Freitags-Pruefung Phase 5

---

## Phase 6 – Paketmanagement

Session 24: dpkg
- dpkg -i, -r, -l, -L, -S, --status
- .deb-Pakete verstehen

Session 25: apt
- apt install, remove, purge, update, upgrade
- apt-cache search, show
- /etc/apt/sources.list
- Kombiniert mit: dpkg (Session 24)

Session 26: rpm Grundlagen
- rpm -i, -e, -q, -ql, -qf
- Distributionsuebergreifend (LPIC-relevant)

Session 27: yum und dnf
- yum/dnf install, remove, search, info
- Kombiniert mit: rpm (Session 26)

Freitags-Pruefung Phase 6

---

## Phase 7 – Shell Scripting

Session 28: Variablen und Quoting
- Variablen, Umgebungsvariablen, export
- Quoting: single, double, backtick, $()
- Kombiniert mit: Streams (Phase 2)

Session 29: Conditionals
- if/then/else/fi, test, [ ], [[ ]]
- Exitcodes ($?)
- case/esac
- Kombiniert mit: Prozesse (Phase 3)

Session 30: Loops
- for, while, until, break, continue
- Kombiniert mit: Textwerkzeuge (Phase 2)

Session 31: Funktionen und Fehlerbehandlung
- Funktionen deklarieren und aufrufen
- Parameter ($1, $2, $@, $#)
- Fehlerbehandlung, trap
- Kombiniert mit: alles bisherige

Freitags-Pruefung Phase 7

---

## Phase 8 – Boot und System

Session 32: BIOS/UEFI und Bootloader
- BIOS vs. UEFI
- GRUB2: grub.cfg, update-grub, grub-install
- (Theorie + killercoda.com)

Session 33: Bootsequenz und Kernel
- Bootsequenz: BIOS > GRUB > Kernel > init
- Kernel-Parameter, initrd/initramfs
- /proc/cmdline

Session 34: systemd
- systemctl start/stop/enable/disable/status
- Units, Targets
- journalctl
- Kombiniert mit: Prozesse (Phase 3)

Session 35: SysV-Runlevel (Legacy)
- Runlevel 0-6
- /etc/init.d, service, chkconfig, update-rc.d
- Warum LPIC das noch abfragt

Freitags-Pruefung Phase 8

---

## Phase 9 – Hardware und System-Internals

Session 36: Hardware-Informationen
- lspci, lsusb, lscpu, lsblk, dmidecode
- dmesg, /proc, /sys

Session 37: Kernel-Module
- lsmod, modinfo, modprobe, insmod, rmmod
- /etc/modprobe.d

Session 38: Shared Libraries
- ldd, ldconfig, /etc/ld.so.conf
- LD_LIBRARY_PATH

Session 39: FHS – Filesystem Hierarchy Standard
- Bedeutung und Inhalt von /bin, /sbin, /usr, /var, /etc, /home, /tmp, /proc, /sys, /dev

Freitags-Pruefung Phase 9

---

## Phase 10 – Netzwerk-Grundlagen

Session 40: Netzwerk-Interfaces
- ip addr, ip link, ip route
- ifconfig (Legacy)
- /etc/network/interfaces, /etc/netplan

Session 41: DNS und Name Resolution
- /etc/hosts, /etc/resolv.conf, /etc/nsswitch.conf
- host, dig, nslookup

Session 42: Netzwerk-Diagnose
- ping, traceroute, ss, netstat
- curl, wget
- Kombiniert mit: Prozesse, find (Phase 1+3)

Freitags-Pruefung Phase 10

---

## Abschlussphase – Pruefungssimulation

2 Wochen vollstaendige Simulation:
- Gemischte Fragen aus allen Phasen
- Trickfragen und historische Konzepte
- Distributionsuebergreifende Fragen
- Zeitdruck (LPIC: 90 Minuten, 60 Fragen)
- Ziel: konstant 80%+