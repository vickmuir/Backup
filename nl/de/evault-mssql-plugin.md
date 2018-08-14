---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# EVault-Plug-in für SQL Server installieren

Das Plug-in für SQL Server wird mit dem Windows-Agenten auf dem Host der SQL-Datenbank installiert. Mit dem WebCC-Portal können Sie Jobs konfigurieren, SQL-Datenbanken in einer sicheren fernen Vault sichern und SQL-Datenbanken wiederherstellen.

**Bereitgestelltes Leistungsspektrum**

- Sie können Datenbankgesamtsicherungen, Datenbankgesamtsicherungen mit Transaktionsprotokollsicherungen oder reine Transaktionsprotokollsicherungen ausführen.
- Sie können gleichzeitig mehrere Sicherungen ausführen. 
- Sie können SQL-Datenbanken in derselben SQL-Instanz oder in einer anderen SQL-Instanz wiederherstellen.
- Sie können Datenbanken mit den ursprünglichen Datenbanknamen wiederherstellen, vorhandene Datenbanken überschreiben oder die Wiederherstellung mit der Option 'Keine Recovery' durchführen.

## Plug-in bestellen

1. Melden Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an.
2. Klicken Sie auf **Speicher** > **Sicherung**.
3. Wählen Sie Ihr EVault-Konto aus und klicken Sie auf **Plug-ins bestellen**.
4. Wählen Sie **EVault-Plug-in - MS SQL** aus und klicken Sie auf **Weiter**.
5. Geben Sie einen gegebenenfalls verfügbaren Werbeaktionscode ein und klicken Sie auf **Neu berechnen**.
6. Die aktualisierten Gebühren werden angezeigt. Prüfen Sie Ihre Bestellung.
7. Aktivieren Sie das Kontrollkästchen, um anzugeben, dass Sie die Servicevereinbarung eines anderen Anbieters gelesen haben und akzeptieren. 
8. Klicken Sie auf **Bestellung aufgeben**.

## Plug-in für MS SQL installieren

Zur Installation des SQL-Plug-ins für Windows führen Sie das Agenteninstallationskit aus. Das Plug-in wird auf der Seite **Angepasste Installation** als Option angezeigt.

**Hinweis**: Stoppen Sie vor der Installation des EVault-Plug-ins für MS SQL für Ihren Microsoft Windows-Server beide EVault-Services in `services.msc`.  

1. Navigieren Sie zum Ordner `c:\installs\evault` und führen Sie die Datei '.exe' mit der höchsten Überarbeitungsnummer aus.
2. Klicken Sie in der Anzeige für die Sprache auf **OK**.
3. Klicken Sie in der Eingangsanzeige auf **Weiter**.
4. Wählen Sie die Option **Installation ändern** aus und klicken Sie auf **Weiter**.
5. Wählen Sie die Option **Unverändert beibehalten** aus und klicken Sie auf **Weiter**.
6. Wählen Sie in der Anzeige für die angepasste Installation die einzelnen Plug-ins aus, die Sie erworben haben.
7. Wählen Sie **Feature wird installiert auf ...** aus und klicken Sie dann auf **Weiter**.
8. Wählen Sie **Aktuelle Registrierung beibehalten** aus und klicken Sie auf **Weiter**.
9. Klicken Sie auf **Installieren**.
10. Stellen Sie nach Abschluss der Installation sicher, dass beide Services aktiviert und in Betrieb sind.
11. Falls WebCC in der Lage ist, auf die Datenbank zuzugreifen bzw. die Datenbank anzuzeigen, war die Installation erfolgreich. 

## Benutzerhandbuch herunterladen

Stellen Sie eine Verbindung zum {{site.data.keyword.BluSoftlayer_full}}-Netz mit {{site.data.keyword.BluVPN}} her, damit Sie die PDF-Datei mit dem Handbuch 'EVault Agent for Microsoft Windows v8.0 - SQL Server plug-in Guide' von der Seite [Für den Download verfügbare EVault-Dokumentation](http://downloads.service.softlayer.com/evault/Documentation/){:new_window} herunterladen können.

## Häufig gestellte Fragen

**Wozu wird VSS verwendet?**

Die aktuelle Version des Plug-ins für SQL Server verwendet VSS (Volume Shadow Copy Services, Volumenschattenkopie-Dienste) zur Ausführung von Sicherungen. Mit VSS kann das Plug-in für SQL Server SQL-Datenbanken auch dann effektiv sichern, wenn diese mehrere Datenträger umfassen. Sicherungen können durchgeführt werden, während Anwendungen weiterhin Schreiboperationen auf dem Datenträger ausführen. Das Plug-in für SQL Server bietet Ihnen Datenkonsistenz innerhalb von Datenbanken und auch datenbankübergreifend. VSS ermöglicht die gleichzeitige Ausführung von mehreren Sicherungen.

**Welches sind die Hauptfunktionen des Plug-ins für SQL?**

- Möglichkeit zur Angabe der Namen von Datenbanken, die in SQL Server-Sicherungsjobs ein- oder von diesen ausgeschlossen werden sollen, unter Verwendung von Platzhalterzeichen (Sterne und Fragezeichen). Neue Datenbanken mit Namen, die mit den Filtern eines Sicherungsjobs übereinstimmen, werden bei Ausführung des Jobs automatisch ein- oder ausgeschlossen. 
- Möglichkeit zum Schützen von sekundären Datenbanken in AlwaysOn-Verfügbarkeitsgruppen unter Verwendung des 64-Bit-Agenten und des Plug-ins für SQL Server.
- Möglichkeit zur gemeinsamen Nutzung von SQL-Sicherungsgruppen, die Inhaltsdatenbanken von SharePoint 2010/2013 enthalten, zur Verwendung bei der Anwendung zur differenzierten Wiederherstellung für Microsoft SharePoint. Nachdem die Sicherheitsgruppe zur gemeinsamen Nutzung freigegeben wurde, kann die Anwendung zur differenzierten Wiederherstellung verwendet werden, um Standortsammlungen, Websites, Listen, Bibliotheken, Ordner, Listenelemente oder Dokumente wiederherzustellen.
- Unterstützung von Deltasicherungen für Datenbanken, die sich auf übergreifenden Datenträgern befinden.
- Möglichkeit zum Schutz von Datenbanken bei einem Gesamtwiederherstellungsmodell mit einem einzigen Zeitplaneintrag. Diese Option ermöglicht das Schützen von Datenbanken und das Verwalten des Umlaufs von Transaktionsprotokollen in einem einzigen Zeitplaneintrag.
- Das Plug-in für SQL Server unterstützt vollständige Sicherungen, vollständige Sicherungen mit Transaktionsprotokollen und Transaktionsprotokollsicherungen (die Terminologie wurde aktualisiert und orientiert sich jetzt an der Terminologie von SQL Server). EVault unterstützt weiterhin die Funktion für die Wiederherstellung in einem einzigen Arbeitsgang, mit der ein Kunde einen Zeitpunkt in einer Transaktionsprotokollsicherung auswählen kann. EVault stellt die vollständige Datenbank und alle Transaktionsprotokolle wieder her, die zur Wiederherstellung der Datenbank für den ausgewählten Zeitpunkt erforderlich sind.
- Ein Sicherungsjob kann eine oder mehrere Datenbanken aus derselben SQL Server-Instanz enthalten. Zum Sichern anderer Datenbanken aus einer anderen SQL Server-Instanz kann ein separater Job erstellt werden, der bei Bedarf gleichzeitig ausgeführt werden kann.
- Datenbanken können mit der Option 'Keine Recovery' wiederhergestellt werden, um zusätzliche Recovery-Optionen über SQL Server Management Studio bereitzustellen.
- Die Option für die alternative Wiederherstellung unterstützt die Wiederherstellung in Dateien, was dem Datenbankadministrator das Anhängen der Datenbanken über SQL System Manager ermöglicht.
- Die alternative Wiederherstellung beinhaltet die Möglichkeit, die Wiederherstellung einer Datenbank selbst dann in einer anderen Datenbank anzuweisen, wenn die logischen Datenbanknamen nicht übereinstimmen. Bei abweichenden Objekten erstellt das Plug-in Datenbanken an der Standarddatenbankposition für die Instanz.
- Transparent Data Encryption (TDE) wird bei SQL Server 2008 R2 64-Bit (SP1) und SQL Server 2012 unterstützt.
- Falls ein SQL Server-Host ausfällt, kann die SQL Server-Software installiert und die Datenbank wiederhergestellt werden. (Zuerst muss die Masterdatenbank wiederhergestellt werden.)
- Wenn die Sicherung gestartet wird, findet die Sicherung mit oder ohne Ausführung der Datenbankservices statt.
- Wiederherstellungen werden mit ursprünglichen Datenbanknamen (mit oder ohne Überschreibung von vorhandenen Datenbanken), als Wiederherstellung über einer vorhandenen Datenbank oder in Dateien auf einem Datenträger unterstützt.

