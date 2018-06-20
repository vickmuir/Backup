---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# EVault-Plug-in für SQL Server installieren

Das Plug-in für SQL Server wird mit dem Windows-Agenten auf dem Host der SQL-Datenbank installiert. Mit dem WebCC-Portal können Sie Jobs konfigurieren, SQL-Datenbanken in einer sicheren fernen Vault sichern und SQL-Datenbanken wiederherstellen. 

## Bereitgestelltes Leistungsspektrum

- Sie können Datenbankgesamtsicherungen, Datenbankgesamtsicherungen mit Transaktionsprotokollsicherungen oder reine Transaktionsprotokollsicherungen ausführen.
- Sie können gleichzeitig mehrere Sicherungen ausführen. 
- Sie können SQL-Datenbanken in derselben SQL-Instanz oder in einer anderen SQL-Instanz wiederherstellen.
- Sie können Datenbanken mit den ursprünglichen Datenbanknamen wiederherstellen, vorhandene Datenbanken überschreiben oder die Option 'Keine Wiederherstellung' verwenden.

## Plug-in bestellen

1. Melden Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an.
2. Klicken Sie auf **Speicher** > **Sicherung**.
3. Wählen Sie Ihr EVault-Konto aus und klicken Sie auf **Plug-ins bestellen**.
4. Wählen Sie **EVault-Plug-in - MS SQL** aus und klicken Sie auf **Weiter**.
5. Geben Sie einen gegebenenfalls verfügbaren Werbeaktionscode ein und klicken Sie auf **Neu berechnen**.
6. Die aktualisierten Gebühren werden angezeigt. Prüfen Sie Ihre Bestellung.
7. Wählen Sie die entsprechenden Kontrollkästchen aus, um anzugeben, dass Sie die **Rahmenvereinbarung** gelesen haben und den **Bedingungen für Software anderer Anbieter** zustimmen. 
8. Klicken Sie auf **Bestellung aufgeben**.

## Plug-in für MS SQL installieren

Zur Installation des SQL-Plug-ins für Windows führen Sie das Agenteninstallationskit aus. Das Plug-in wird auf der Seite **Angepasste Installation** als Option angezeigt.

**Hinweis**: Stoppen Sie vor der Installation des EVault-Plug-ins für MS SQL für Ihren Microsoft Windows-Server beide EVault-Services in `services.msc`.  

1. Navigieren Sie zum Ordner `c:\installs\evault` und führen Sie die Datei '.exe' mit der höchsten Überarbeitungsnummer aus.
2. Klicken Sie in der Anzeige für die Sprache auf **OK**.
3. Klicken Sie in der Eingangsanzeige auf **Weiter**.
4. Wählen Sie die Option **Installation ändern** aus und klicken Sie auf **Weiter**.
5. Wählen Sie die Option **Unverändert beibehalten** aus und klicken Sie auf **Weiter**.
6. Wählen Sie in der Anzeige für die Anpassung der Installation jedes gekaufte Plug-in aus und wählen Sie die Option **Feature wird installiert auf...** aus. Klicken Sie anschließend auf **Weiter**.
7. Wählen Sie das Optionsfeld **Aktuelle Registrierung beibehalten** aus und klicken Sie auf **Weiter**.
8. Klicken Sie auf **Installieren**.
9. Stellen Sie nach Abschluss der Installation sicher, dass beide Services aktiviert und in Betrieb sind.
10. Falls WebCC in der Lage ist, auf die Datenbank(en) zuzugreifen, also die Datenbanken angezeigt werden, war die Installation erfolgreich. 

## Benutzerhandbuch

Stellen Sie eine Verbindung zum {{site.data.keyword.BluSoftlayer_full}}-Netz mit {{site.data.keyword.BluVPN}} her, damit Sie die PDF-Datei mit dem Handbuch 'EVault Agent for Microsoft Windows v8.0 - SQL Server Plug-in Guide' von der Seite [Für den Download verfügbare EVault-Dokumentation](http://downloads.service.softlayer.com/evault/Documentation/){:new_window} herunterladen können.

## Häufig gestellte Fragen

### Wozu wird VSS verwendet?

Die aktuelle Version des Plug-ins für SQL Server verwendet VSS (Volume Shadow Copy Services, Volumenschattenkopie-Dienste) zur Ausführung von Sicherungen. Das Plug-in für SQL Server mit Verwendung von VSS sichert effizient SQL-Datenbanken sowie datenträgerübergreifende SQL-Datenbanken. Es ermöglicht die Ausführung von Sicherungen, während Anwendungen weiterhin Daten auf einen Datenträger schreiben, und gewährleistet die Datenkonsistenz innerhalb von und zwischen Datenbanken. VSS ermöglicht die gleichzeitige Ausführung von mehreren Sicherungen.

### Welches sind die Hauptfunktionen des Plug-ins für SQL?

- Möglichkeit zur Angabe der Namen von Datenbanken, die in SQL Server-Sicherungsjobs ein- oder ausgeschlossen werden sollen, unter Verwendung von Platzhalterzeichen (Sterne und Fragezeichen). Neue Datenbanken mit Namen, die mit den Filtern eines Sicherungsjobs übereinstimmen, werden bei Ausführung des Jobs automatisch ein- oder ausgeschlossen. 
- Möglichkeit zum Schützen von sekundären Datenbanken in AlwaysOn-Verfügbarkeitsgruppen unter Verwendung des 64-Bit-Agenten und des Plug-ins für SQL Server.
- Möglichkeit zur gemeinsamen Nutzung von SQL-Sicherungsgruppen, die Inhaltsdatenbanken von SharePoint 2010/2013 enthalten, zur Verwendung bei der Anwendung zur differenzierten Wiederherstellung für Microsoft SharePoint. Sobald eine Sicherungsgruppe gemeinsam genutzt wird, kann die Anwendung zur differenzierten Wiederherstellung für die Wiederherstellung von Siteerfassungen, Websites, Listen, Bibliotheken, Ordnern, Listeneinträgen oder Dokumenten verwendet werden.
- Unterstützung von Deltasicherungen für Datenbanken, die sich auf übergreifenden Datenträgern befinden.
Möglichkeit zum Schutz von Datenbanken bei einem Gesamtwiederherstellungsmodell mit einem einzigen Zeitplaneintrag. Diese Option ermöglicht das Schützen von Datenbanken und das Verwalten des Umlaufs von Transaktionsprotokollen in einem einzigen Zeitplaneintrag.
- Das Plug-in für SQL Server unterstützt vollständige Sicherungen, vollständige Sicherungen mit Transaktionsprotokollen und Transaktionsprotokollsicherungen (die Terminologie wurde aktualisiert und orientiert sich jetzt an der Begrifflichkeit von SQL Server). EVault unterstützt weiterhin die Funktion für die Wiederherstellung in einem einzigen Arbeitsgang, mit der ein Kunde einen Zeitpunkt in einer Transaktionsprotokollsicherung auswählen kann. EVault stellt vollständige Datenbanken und alle Transaktionsprotokolle wieder her, die zur Wiederherstellung der Datenbank für den ausgewählten Zeitpunkt erforderlich sind.
- Ein Sicherungsjob kann eine oder mehrere Datenbanken aus derselben SQL Server-Instanz enthalten. Zum Sichern anderer Datenbanken aus einer anderen SQL Server-Instanz kann ein separater Job erstellt werden, der bei Bedarf gleichzeitig ausgeführt werden kann.
- Datenbanken können mit der Option 'Keine Wiederherstellung' wiederhergestellt werden, um zusätzliche Wiederherstellungsoptionen über SQL Server Management Studio bereitzustellen.
- Die Option für die alternative Wiederherstellung unterstützt die Wiederherstellung in Dateien, was dem Datenbankadministrator das Anhängen der Datenbanken über SQL System Manager ermöglicht.
- Die alternative Wiederherstellung beinhaltet die Möglichkeit, die Wiederherstellung einer Datenbank selbst dann in einer anderen Datenbank anzuweisen, wenn die logischen Datenbanknamen nicht übereinstimmen. Bei abweichenden Objekten erstellt das Plug-in Datenbanken an der Standarddatenbankposition für die Instanz.
- Transparent Data Encryption (TDE) wird bei SQL Server 2008 R2 64-Bit (SP1) und SQL Server 2012 unterstützt.
- Falls ein SQL Server-Host vollständig ausfällt, kann die SQL Server-Software installiert und die Datenbank vollständig wiederhergestellt werden. (Zuerst muss die Masterdatenbank wiederhergestellt werden.)
- Nachdem die Sicherung gestartet wurde, findet die Sicherung mit oder ohne Ausführung der Datenbankservices statt.
- Wiederherstellungen werden mit ursprünglichen Datenbanknamen (mit oder ohne Überschreibung von vorhandenen Datenbanken), als Wiederherstellung über einer vorhandenen Datenbank oder in Dateien auf einem Datenträger unterstützt.

