---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-27"

---
{:new_window: target="_blank"}

# EVault-Plug-in für Exchange installieren

Das Plug-in für Exchange wird mit dem Windows-Agenten auf dem Host installiert. Mit dem WebCC-Portal können Sie Jobs konfigurieren, Oracle-Datenbanken in einer sicheren fernen Vault sichern und Oracle-Datenbanken wiederherstellen. Das Plug-in für Oracle wird in die vorhandene Architektur integriert.

**Bereitgestelltes Leistungsspektrum**

- Möglichkeit zur Sicherung und Wiederherstellung von Microsoft Exchange-Datenbanken.

## Plug-in bestellen

1. Melden Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an.
2. Klicken Sie auf **Speicher** > **Sicherung**.
3. Wählen Sie Ihr EVault-Konto aus und klicken Sie auf **Plug-ins bestellen**.
4. Wählen Sie **EVault-Plug-in - Exchange** aus und klicken Sie auf **Weiter**.
5. Geben Sie einen gegebenenfalls verfügbaren Werbeaktionscode ein und klicken Sie auf **Neu berechnen**.
6. Die aktualisierten Gebühren werden angezeigt. Prüfen Sie Ihre Bestellung.
7. Aktivieren Sie das Kontrollkästchen, um anzugeben, dass Sie die Servicevereinbarung eines anderen Anbieters gelesen haben und akzeptieren. 
8. Klicken Sie auf **Bestellung aufgeben**.

## Exchange-Plug-in installieren

Das Plug-in für Exchange wird während der Installation des 64-Bit-Windows-Agenten installiert. Das Plug-in kann zusammen mit dem Agenten oder auch später installiert werden, indem die Installation mit der Auswahl **Ändern** erneut ausgeführt wird.

**Hinweis**: Stoppen Sie vor der Installation des Plug-ins für Ihren Microsoft Windows-Server beide EVault-Services in `services.msc`.  

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

Stellen Sie eine Verbindung zum {{site.data.keyword.BluSoftlayer_full}}-Netz mit {{site.data.keyword.BluVPN}} her, damit Sie die PDF-Datei mit dem Handbuch 'EVault Agent v8.0 for Microsoft Windows (64-bit) - Exchange plug-in Guide' von der Seite [Für den Download verfügbare EVault-Dokumentation](http://downloads.service.softlayer.com/evault/Documentation/){:new_window} herunterladen können. In diesem Handbuch ist beschrieben, wie Sie Microsoft Exchange-Datenbanken mit dem Plug-in für Exchange sichern und wiederherstellen können. Im Handbuch wird außerdem beschrieben, wie eine Sicherungsgruppe für eine DR-Sicherung gemeinsam genutzt werden kann. Mit der Sicherungsgruppe für eine DR-Sicherung können Sie bestimmte Mailboxen, Nachrichten oder andere Objekte mit der Anwendung zur differenzierten Wiederherstellung für Microsoft Exchange in einer PST-Datei (.pst) wiederherstellen.

