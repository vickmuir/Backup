---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, Exchange, plug-in, plugin, EVault, Carbonite

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Exchange-Plug-in installieren
{: #Exchangeplugin}

Das Plug-in für Exchange wird mit dem Windows-Agenten auf dem Host installiert. Mit dem {{site.data.keyword.backup_notm}}-Portal können Sie Jobs konfigurieren, Exchange-Datenbanken in einer sicheren, fernen Vault sichern und Exchange-Datenbanken wiederherstellen. Das Plug-in wird in die vorhandene Architektur integriert.

**Bereitgestelltes Leistungsspektrum**

- Möglichkeit zur Sicherung und Wiederherstellung von Microsoft Exchange-Datenbanken.

## Plug-in bestellen
{: #orderingExchangePlugin}

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}){: external} an und klicken Sie oben links auf das **Menüsymbol**. Wählen Sie **Klassische Infrastruktur** aus. <br/>
   Alternativ können Sie sich am [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external} anmelden.
2. Klicken Sie auf **Speicher** > **Sicherung**, um die Server mit Backup-Service anzuzeigen.
3. Wählen Sie Ihr Konto aus und klicken Sie auf **Plug-ins bestellen**.
4. Wählen Sie **{{site.data.keyword.backup_notm}}-Plug-in - Exchange** aus und klicken Sie auf **Weiter**.
5. Geben Sie einen gegebenenfalls verfügbaren Werbeaktionscode ein und klicken Sie auf **Neu berechnen**.
6. Die aktualisierten Gebühren werden angezeigt. Prüfen Sie Ihre Bestellung.
7. Aktivieren Sie das Kontrollkästchen, um anzugeben, dass Sie die Servicevereinbarung eines anderen Anbieters gelesen haben und akzeptieren.
8. Klicken Sie auf **Bestellung aufgeben**.

## Plug-in installieren
{: #installExchangePlugin}

Das Plug-in für Exchange wird während der Installation des 64-Bit-Windows-Agenten installiert. Das Plug-in kann zusammen mit dem Agenten oder auch später installiert werden, indem die Installation mit der Auswahl **Ändern** erneut ausgeführt wird.

Bevor Sie das Plug-in für Ihren Microsoft Windows-Server installieren, stoppen Sie beide {{site.data.keyword.backup_notm}}-Services in `services.msc`.
{:tip}

1. Navigieren Sie zum Ordner `c:\installs\{{site.data.keyword.backup_notm}}` und führen Sie die Datei mit der Erweiterung '.exe' mit der höheren Revisionsnummer aus.
2. Klicken Sie in der Anzeige für die Sprache auf **OK**.
3. Klicken Sie in der Eingangsanzeige auf **Weiter**.
4. Wählen Sie die Option **Installation ändern** aus und klicken Sie auf **Weiter**.
5. Wählen Sie die Option **Unverändert beibehalten** aus und klicken Sie auf **Weiter**.
6. Wählen Sie in der Anzeige für die angepasste Installation die einzelnen Plug-ins aus, die Sie erworben haben.
7. Wählen Sie **Feature wird installiert auf ...** aus und klicken Sie dann auf **Weiter**.
8. Wählen Sie **Aktuelle Registrierung beibehalten** aus und klicken Sie auf **Weiter**.
9. Klicken Sie auf **Installieren**.
10. Stellen Sie nach Abschluss der Installation sicher, dass beide Services aktiviert und in Betrieb sind.
11. Falls das {{site.data.keyword.backup_notm}}-Portal in der Lage ist, auf die Datenbank zuzugreifen bzw. die Datenbank anzuzeigen, war die Installation erfolgreich.

## Benutzerhandbuch herunterladen
{: #ExchangeUserGuide}

Stellen Sie eine Verbindung zum {{site.data.keyword.BluSoftlayer_full}}-Netz mit {{site.data.keyword.BluVPN}} her, damit Sie auf das Benutzerhandbuch zugreifen und es über die [für den Download verfügbare {{site.data.keyword.backup_notm}}-Dokumentation](http://downloads.service.softlayer.com/evault/Documentation/){: external} herunterladen können. In diesem Handbuch ist beschrieben, wie Sie Microsoft Exchange-Datenbanken mit dem Plug-in für Exchange sichern und wiederherstellen können. Im Handbuch wird außerdem beschrieben, wie eine Sicherungsgruppe für eine DR-Sicherung gemeinsam genutzt werden kann. Mit einer Sicherungsgruppe für eine DR-Sicherung können Sie bestimmte Mailboxen, Nachrichten oder andere Objekte mit der Anwendung zur differenzierten Wiederherstellung für Microsoft Exchange in einer PST-Datei (.pst) wiederherstellen.
