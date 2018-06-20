---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Sicherung und Wiederherstellung in demselben Rechenzentrum von einer virtuellen Serverinstanz auf einer anderen virtuellen Serverinstanz durchführen

Es kann mitunter vorkommen, dass Sie Daten auf einem anderen Server desselben Rechenzentrums wiederherstellen wollen. Die Anweisungen in diesem Abschnitt helfen Ihnen bei der Durchführung dieser Task. Die beschriebene Prozedur ist nur auf Wiederherstellungen auf Dateiebene für Dateien anwendbar, die keine Betriebssystemdateien sind. Anweisungen zum Wiederherstellen eines Systemimage enthält der Abschnitt zu [Windows BMR](restoring-evault-bmr-system-volume-image.html).

Dieser Prozess umfasst das erneute Registrieren des EVault-Agenten auf dem zweiten Server, um auf die EVault-Position des ersten Servers zuzugreifen, sowie das Durchführen einer **Wiederherstellung aus einem anderen Computer**.


## Vorbedingungen

- Server 1 und Server 2 müssen dasselbe Betriebssystem verwenden. Plattformübergreifende Wiederherstellungen werden nicht unterstützt.
- Server 1 und Server 2 müssen über konfigurierte EVault-Agenten verfügen. Informationen zum Konfigurieren der EVault-Agenten finden Sie [hier](index.html#configuring-evault-agent-in-webcc).
- Ein Sicherungsjob für Server 1 hat eine Sicherung an der EVault-Position von Server 1 erstellt.

**Hinweis**: Inaktivieren Sie auf beiden Servern alle Zeitplanungstasks, um Konflikte zu vermeiden. 

## WebCC auf Server 2 starten

**Hinweis**: Denken Sie daran, Ihre {{site.data.keyword.BluVPN}}-Verbindung zu starten, damit Sie Zugang zum privaten {{site.data.keyword.BluSoftlayer_full}}-Netz erhalten, da die Links zu WebCC andernfalls nicht funktionieren.

1. Melden Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an und klicken Sie im Hauptmenü auf **Speicher** > **Sicherung**, um die Server mit EVault Backup-Service anzuzeigen. 
2. Wählen Sie Server 2 aus. Klicken Sie auf den nach rechts zeigenden Erweiterungspfeil, um den Link zu WebCC sichtbar zu machen.
3. Klicken Sie auf **WebCC-Anmeldung**, um den WebCC-Client in Ihrem Browser zu starten.

## EVault-Agenten erneut registrieren:
1. Klicken Sie auf **Alle Agenten** und öffnen Sie den betreffenden Agenten, den Sie ändern wollen.
2. Klicken Sie auf **Bearbeiten** und wählen Sie 'Vaulteinstellungen' aus.
3. Klicken Sie auf **Erneut registrieren**, um Server 1 mit Server 2 zu verbinden.
4. Wählen Sie in der Anzeige **Vault erneut registrieren** für den Eintrag **Vaultprofil verwenden** die Option **Vaulteinstellungen eingeben** aus.
5. Geben Sie den Vaultnamen ein; dieser ist mit dem EVault-Namen von Server 1 identisch.
6. Geben Sie die Berechtigungsnachweise für Server 1 ein, um sich bei der EVault-Instanz für Server 1 anzumelden.
7. Klicken Sie auf **Computer laden**. Daraufhin werden die Server angezeigt, die der Vaultposition zugeordnet sind.
8. Klicken Sie auf **Änderungen speichern**.
9. Klicken Sie bei der entsprechenden Eingabeaufforderung auf **Ja**, um die erneute Registrierung der EVault-Instanz zu bestätigen.

## Sicherungsjob aus Server 1 als Wiederherstellungsjob auf Server 2 ausführen

1. Klicken Sie auf **Alle Agenten**. <br/> **Hinweis**: Möglicherweise müssen Sie die Seite aktualisieren, damit die auf Server 1 definierten Jobs auf der Registerkarte **Jobs** für Server 2 als zugänglich/synchronisiert angezeigt werden.
2. Bewegen Sie den Mauscursor auf **Erweitert** und wählen Sie die Option **Aus anderem Computer wiederherstellen** aus.
3. Wählen Sie in der Anzeige **Aus anderem Computer wiederherstellen** die folgenden Einstellungen aus:
  - Vault: Dieser Eintrag sollte standardmäßig die EVault-Instanz von Server 1 annehmen.
  - Computer: Wählen Sie Server 1 als Sicherungscomputer für die Wiederherstellung aus. 
  - Job: Wählen Sie den Sicherungsjob aus Server 1 aus.
4. Klicken Sie auf **Weiter**.
5. Bestätigen Sie die Quelleninformationen:
  - **Position der Sicherungsgruppe** sollte die Vaultposition für Server 1 sein.
  - Die im Abschnitt **Sicherungsversion auswählen** angegebene Sicherungsversion sollte Ihre Sicherung aus Server 1 sein.
  - Das Verschlüsselungskennwort sollte das Kennwort sein, das Sie beim Durchführen der Sicherung auf Server 1 verwendet haben.
6. Klicken Sie auf **Weiter**.
7. Datenauswahl: Wählen Sie aus, welche Dateien aus der Sicherung von Server 1 wiederhergestellt werden müssen. Wählen Sie die Kontrollkästchen neben den Dateien und Verzeichnissen aus, die Sie einbeziehen wollen, und klicken Sie anschließend auf **Einschließen**, um Ihre Auswahl zu speichern.
8. Klicken Sie auf **Weiter**, um zu den Optionen für die Wiederherstellung zu wechseln.
9. Führen Sie im Fenster 'Optionen' Folgendes aus:
  - Ziel: Wählen Sie **An ursprünglicher Position wiederherstellen** aus.
  - Datei überschreiben: Wählen Sie **Vorhandene Dateien überschreiben** aus.
10. Klicken Sie auf **Wiederherstellung durchführen**.
11. In der Anzeige 'Prozessdetails' wird jetzt der Status des Wiederherstellungsjobs angezeigt.


## Wiederherstellung prüfen

1. Stellen Sie über SSH eine Verbindung zum Stammverzeichnis von Server 2 her.
2. Listen Sie die Dateien inklusive aller Verzeichniseinträge in einem Langformat auf.
  ```
  ls -la
  ```
  {: pre}
  
3. Vergleichen Sie die Ausgabe.
  
## Normalen Sicherungszeitplan wiederaufnehmen

1. Entfernen Sie nach Abschluss der Wiederherstellung die Registrierungsinformationen von Server 1, aus dem die Daten wiederhergestellt wurden. 
2. Geben Sie die aktuelle Registrierung von Server 2 ein und aktivieren Sie die Zeitplanungstasks.
 

  

 
 
  
  
