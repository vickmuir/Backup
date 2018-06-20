---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# EVault-Plug-in für Oracle installieren

Das Plug-in für Oracle wird mit dem Windows-Agenten auf dem Host der Oracle-Datenbank installiert. Mit dem WebCC-Portal können Sie Jobs konfigurieren, Oracle-Datenbanken in einer sicheren fernen Vault sichern und Oracle-Datenbanken wiederherstellen. Das Plug-in für Oracle wird in die vorhandene Architektur integriert.

## Bereitgestelltes Leistungsspektrum

- Unterstützung für die Sicherung und Wiederherstellung von Oracle-Datenbanken.
- Das Plug-in für Oracle stellt auf ARCHIVELOG basierende Sicherungen ohne Recovery Manager (RMAN) von vollständigen Online-Datenbankinstanzen bereit. Alle nicht temporären Tabellenbereiche und Instanzparameterdateien werden automatisch gesichert. Die Oracle Corporation empfiehlt, Sicherungen in Zeiten mit geringer Datenbankaktivität auszuführen.
- Datenbanken werden mit den üblichen vom Benutzer verwalteten Oracle-Wiederherstellungsmechanismen ganz und teilweise wiederhergestellt.

## Plug-in bestellen

1. Melden Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an.
2. Klicken Sie auf **Speicher** > **Sicherung**.
3. Wählen Sie Ihr EVault-Konto aus und klicken Sie auf **Plug-ins bestellen**.
4. Wählen Sie **EVault-Plug-in - Oracle** aus und klicken Sie auf **Weiter**.
5. Geben Sie einen gegebenenfalls verfügbaren Werbeaktionscode ein und klicken Sie auf **Neu berechnen**.
6. Die aktualisierten Gebühren werden angezeigt. Prüfen Sie Ihre Bestellung.
7. Wählen Sie die entsprechenden Kontrollkästchen aus, um anzugeben, dass Sie die Rahmenvereinbarung gelesen haben und den Bedingungen für Software anderer Anbieter zustimmen. 
8. Klicken Sie auf **Bestellung aufgeben**.

## Plug-in für Oracle installieren

Das Oracle-Plug-in für Windows wird mit dem 32-Bit- oder 64-Bit-Windows-Agenten installiert. Zur Installation des Oracle-Plug-ins für Windows führen Sie das Agenteninstallationskit aus. Das Oracle-Plug-in wird auf der Seite **Angepasste Installation** als Option angezeigt.

**Hinweis**: Stoppen Sie vor der Installation des Plug-ins für Ihren Microsoft Windows-Server beide EVault-Services in `services.msc`.  

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

Stellen Sie eine Verbindung zum {{site.data.keyword.BluSoftlayer_full}}-Netz mit {{site.data.keyword.BluVPN}} her, damit Sie die PDF-Datei mit dem Handbuch 'EVault Agent v8.0 for Microsoft Windows - Oracle Plug-in Guide' von der Seite [Für den Download verfügbare EVault-Dokumentation](http://downloads.service.softlayer.com/evault/Documentation/){:new_window} herunterladen können.

## Häufig gestellte Fragen

### Welche Einschränkungen bestehen für das Oracle-Plug-in?
- Es werden nur einzelne Instanzen von lokalen, datenträgerbasierten Datenbanken gesichert.
- Datenbankcluster werden nicht gesichert.
- Roheinheiten werden nicht gesichert.
- Ferne Datenbanken werden nicht gesichert.
- Die Datenbank muss sich im Modus ARCHIVELOG befinden und der Benutzer, unter dem die Sicherung konfiguriert ist, muss die Berechtigung SYSDBA besitzen.
- Datenbankkennwörter werden zur verstärkten Sicherheit über scriptbasierte Methoden verschlüsselt.
