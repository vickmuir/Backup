---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup,  EVault, Carbonite, backup, restore

subcollection: Backup

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Daten von einer virtuellen Serverinstanz (VSI) in ein anderes VSI in einem anderen Rechenzentrum wiederherstellen
{: #restoreVSIotherlocation}

In bestimmten Fällen kann es vorkommen, dass Sie Daten auf einem anderen Server wiederherstellen wollen. Die beschriebene Prozedur gilt nur für Wiederherstellungen auf Dateiebene für Dateien, die keine Betriebssystemdateien sind. Anweisungen zum Wiederherstellen eines Systemimages enthält der Abschnitt zu [Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR).

Der Prozess umfasst das erneute Registrieren des Sicherungsagenten auf dem zweiten Server, um auf die Vaultposition des ersten Servers zuzugreifen, sowie das Durchführen der Aktion **Aus anderem Computer wiederherstellen**.

**Vorbedingungen**

- Server 1 und Server 2 müssen über dasselbe Betriebssystem verfügen. Plattformübergreifende Wiederherstellungen werden nicht unterstützt.
- Für Server 1 und Server 2 müssen Sicherungsagenten vorhanden sein, die zuvor konfiguriert wurden. Weitere Informationen zum Konfigurieren der Sicherungsagenten finden Sie im Abschnitt [Sicherungsagent im {{site.data.keyword.backup_notm}}-Portal konfigurieren](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).
- Ein Sicherungsjob für Server 1, der eine Sicherung an der Vaultposition von Server 1 erstellt hat.

Inaktivieren Sie auf beiden Servern alle geplanten Tasks, um Konflikte zu vermeiden.
{:important}

## {{site.data.keyword.backup_notm}}-Portal auf Server2 starten
{: #startWebCCotherDC}

Denken Sie daran, Ihre {{site.data.keyword.BluVPN}}-Verbindung zu starten, damit Sie Zugang zum privaten {{site.data.keyword.BluSoftlayer_full}}-Netz erhalten, da der Link zum {{site.data.keyword.backup_notm}}-Portal andernfalls nicht funktioniert.
{:tip}

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}-Konsole]https://{DomainName}){:new_window} an und klicken Sie oben links auf das **Menüsymbol**. Wählen Sie **Klassische Infrastruktur** aus. <br/>
   Alternativ können Sie sich am [{{site.data.keyword.slportal}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){:new_window} anmelden.
2. Klicken Sie auf **Speicher** > **Sicherung**, um die Server mit Backup-Service anzuzeigen.
3. Wählen Sie Server 2 aus. Klicken Sie auf den nach rechts zeigenden Erweiterungspfeil, um den Link zum {{site.data.keyword.backup_notm}}-Portal sichtbar zu machen.
4. Klicken Sie auf **{{site.data.keyword.backup_notm}}-Portalanmeldung**, um den Portalclient in Ihrem Browser zu starten.

## Vault erneut registrieren
{: #reregistervaultotherDC}

1. Klicken Sie auf **Alle Agenten** und öffnen Sie den Agenten, den Sie ändern wollen.
2. Klicken Sie auf **Bearbeiten** und wählen Sie **Vaulteinstellungen** aus.
3. Klicken Sie auf **Erneut registrieren**, um Server 1 mit Server 2 zu verbinden.
4. Wählen Sie in der Anzeige **Vault erneut registrieren** für den Eintrag **Vaultprofil verwenden** die Option **Vaulteinstellungen eingeben** aus.
5. Geben Sie den Vaultnamen ein; dieser ist mit dem Vaultnamen von Server 1 identisch.
6. Geben Sie die Berechtigungsnachweise für Server 1 ein, um sich bei der Vaultinstanz für Server 1 anzumelden.
7. Klicken Sie auf **Computer laden**. Daraufhin werden die Server angezeigt, die der Vaultposition zugeordnet sind.
8. Klicken Sie auf **Änderungen speichern**.
9. Klicken Sie bei der entsprechenden Eingabeaufforderung auf **Ja**, um die erneute Registrierung der Vaultinstanz zu bestätigen.

## Sicherungsjob von Server 1 als Wiederherstellungsjob auf Server 2 ausführen
{: #runbackuprestoreotherDC}

1. Klicken Sie auf **Alle Agenten**.

   Möglicherweise müssen Sie die Seite aktualisieren, damit die auf Server 1 definierten Jobs auf der Registerkarte **Jobs** für Server 2 als zugänglich und synchronisiert angezeigt werden.
   {:tip}
2. Bewegen Sie den Mauscursor auf **Erweitert** und wählen Sie die Option **Aus anderem Computer wiederherstellen** aus.
3. Klicken Sie in der Anzeige **Aus anderem Computer wiederherstellen** auf **Hinzufügen**. Die Felder werden automatisch mit den Standardwerten ausgefüllt, sodass Sie sie ggf. ändern müssen.
4. Klicken Sie auf das Feld 'Vault', wählen Sie **Vaulteinstellungen eingeben** aus und geben Sie die IP-Adresse der Vault von Server 1 ein. Klicken Sie auf **Hinzufügen**.
5. Aktualisieren Sie die Berechtigungsnachweise auf die Berechtigungsnachweise von Server 1.
6. Klicken Sie auf **Änderungen speichern**. Durch diese Aktion wird eine Verbindung zur Vault von Server 1 hergestellt.
7. Aktualisieren Sie, nachdem Sie wieder die Anzeige **Aus anderem Computer wiederherstellen** aufgerufen haben, die Felder für den Computer und den Job.
  - Computer - Wählen Sie Server 1 als Sicherungscomputer für die Wiederherstellung aus.
  - Job - Wählen Sie den Sicherungsjob aus Server 1 aus.
8. Klicken Sie auf **Weiter**, um den Wiederherstellungsprozess auf Server 2 in einem anderen Rechenzentrum zu starten.
9. Geben Sie an der entsprechenden Eingabeaufforderung das Sicherungskennwort ein und klicken Sie dann auf **Weiter**.
10. Vergewissern Sie sich, dass der richtige Sicherungsjob ausgewählt wurde, und klicken Sie dann auf **Weiter**. Der Wiederherstellungsjob ist nun auf Server 2 konfiguriert.
11. Wählen Sie den neu konfigurierten Job aus und klicken Sie dann auf **Wiederherstellung durchführen**.
12. Wählen Sie die Dateien aus, die wiederhergestellt werden sollen.
13. Klicken Sie auf das Pluszeichen, um die Dateiauswahl zu erweitern.
14. Klicken Sie auf das Kontrollkästchen der einzelnen Dateien oder Ordner, die von Server 1 auf Server 2 wiederhergestellt werden sollen. Klicken Sie anschließend auf **Einschließen**.
15. Das Fenster 'Sicherungsgruppe' auf der rechten Seite wird mit den Dateien gefüllt. Klicken Sie auf **Weiter**.
16. Nachdem Sie die Datenauswahl abgeschlossen haben, wählen Sie die gewünschten Optionen aus.
    - Wählen Sie **An ursprünglicher Position wiederherstellen** aus.
    - Wählen Sie **Vorhandene Dateien überschreiben** aus.
17. Klicken Sie auf **Wiederherstellung durchführen**. Das Fenster 'Prozessdetails' enthält den Status des aktiven Sicherungsjobs. Klicken Sie nach Abschluss der Sicherung auf **Schließen**.


## Wiederherstellung prüfen
{: #verifyrestoreotherDC}

1. Stellen Sie über SSH eine Verbindung zum Stammverzeichnis von Server 2 her.
2. Listen Sie die Dateien und alle Verzeichniseinträge in einem Langformat auf.
  ```
  ls -la
  ```
  {: pre}

3. Vergleichen Sie die Ausgabe.

## Normalen Sicherungszeitplan wieder aufnehmen
{: #resumescheduleotherCD}

1. Entfernen Sie nach Abschluss der Wiederherstellung die Registrierungsinformationen von Server 1, aus dem die Daten wiederhergestellt wurden.
2. Geben Sie die aktuelle Registrierung von Server 2 ein und aktivieren Sie die Zeitplanungstasks.
