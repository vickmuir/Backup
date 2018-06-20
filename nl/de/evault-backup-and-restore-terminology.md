---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-04"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Terminologie für Sicherungen und Wiederherstellungen mit EVault 

## Deltatechnologie:
Die erste Sicherung ist ein so genannter 'Seed' (vollständige Gesamtsicherung). Die nächste und alle nachfolgenden Sicherungen sind 'Deltasicherungen' (enthalten also nur Änderungen), sind jedoch zu Gesamtsicherungen äquivalent und werden als solche betrachtet. Dies bedeutet, dass Sie aus diesen Sicherungen alle oder einige Dateien wiederherstellen können. Diese Technologie ermöglicht die Durchführung von Gesamtsicherungen in jeder Sitzung, spart jedoch enorm Speicherplatz in der Vault und verringert die Zeit, die zur Ausführung aller nachfolgenden Sicherungen benötigt wird.

## Aufbewahrungsschemas: 
EVault ermöglicht es Ihnen, Daten so lange aufzubewahren, wie Sie in der Lage zu einer Rollback-Operation sein wollen. Aufbewahrungsschemas des Typs 'Täglich' behalten Daten für sieben Tage bei, während beim Typ 'Wöchentlich' Daten für einen Monat und beim Typ 'Monatlich' Daten für ein Jahr aufbewahrt werden. Am Ende jedes Zeitraums wird der älteste Datenbestand turnusmäßig herausgenommen und die erste erstellte 'Deltasicherung' wird zum ältesten verfügbaren Wiederherstellungspunkt. 

## Komprimierung: 
EVault bietet 6 verschiedene Verschlüsselungslösungen für Ihre Daten, nämlich DES 56-Bit, Blowfish 56-Bit, Triple DES 112-Bit, Blowfish 128-Bit, AES 128-Bit und AES 256-Bit. Komprimierungsverhältnisse ermöglichen die Verwendung von keiner Komprimierung bis hin zu einem maximalen Komprimierungsverhältnis, das je nach Dateityp zwischen 20% und 30% liegen kann.
## Verschlüsselung:
Standardmäßig findet die gesamte Verschlüsselung über die Verbindung unter Verwendung von AES 128-Bit statt. Falls Sie Daten in einem verschlüsselten Format speichern wollen, stehen Ihnen im Rahmen des Sicherungsprozesses mehrere Optionen zur Verfügung. Denken Sie daran, dass Sie Ihre Daten NICHT wiederherstellen können, wenn Sie Ihr Kennwort vergessen. 

## Spezialsicherungen: 
Systemstatussicherungen umfassen - abhängig vom System - unter anderem die COM- und Klassenregistrierungsdatenbank, die Registry, Bootdateien Systemdateien und Leistungszähler, sind jedoch nicht hierauf beschränkt. Systemdateien variieren nach Betriebssystem und Service-Packs des Systems. Normalerweise gibt es mehrere Tausend dieser Dateien. MS Windows erstellt eine dynamische Liste dieser DLLs, wenn Sie sie in die Sicherung einbeziehen. Durch die Einbeziehung der Systemdateien können Sie eine Wiederherstellung bei beschädigten Systemdateien, bei einer versehentlichen Installation von Service-Packs oder bei einer erforderlichen Bare-Metal-Wiederherstellung vornehmen. Sie können zum Status der Sicherung zurückkehren, ohne das Betriebssystem mit dem Installationskit erneut installieren und anschließend jedes Service-Pack separat installieren zu müssen. 

## Geöffnete Dateien: 
Der Basisclient ist standardmäßig mit ausgereifter Technologie ausgestattet, um die meisten geöffneten Dateien im Betriebssystem zu behandeln. In wenigen Fällen, bei denen Sicherungen aufgrund einer Einschränkung für geöffnete Dateien fehlschlagen, können Sie sekundäre Plug-ins kaufen, um die Behandlung von geöffneten Dateien zu verbessern. Als Faustregel gilt, dass Sie das Plug-in für geöffnete Dateien erst dann benötigen, wenn Ihre Sicherungen für geöffnete Dateien Fehler enthalten. Dann können Sie die Plug-ins bestellen.
