---

copyright:
  years: 2014, 2018
lastupdated: "2018-07-10"

---
{:new_window: target="_blank"}

# Einführung in EVault Backup-Services

Sicherungen gewährleisten, dass Ihre Daten außerhalb Ihrer eigenen Einheit sicher gespeichert werden und im Verlustfall geschützt sind. EVault Backup ist ein automatisiertes agentenbasiertes Sicherungssystem, das über das browserbasierte Verwaltungsdienstprogramm EVault WebCC verwaltet wird. EVault bietet Benutzern ein Verfahren zur Sicherung von Daten zwischen Servern in einzelnen oder mehreren Rechenzentren des Netzes von {{site.data.keyword.BluSoftlayer_full}}. Administratoren können für Sicherungen einen stündlichen, täglichen, wöchentlichen oder angepassten Zeitplan erstellen, der ganze Systeme, bestimmte Verzeichnisse oder sogar einzelne Dateien abdeckt. Es stehen zusätzliche Plug-ins zur Verfügung, die die Kompatibilität mit Software wie Microsoft Exchange und Microsoft SQL sowie weiteren Typen von Software anderer Anbieter sicherstellen und Benutzer in die Lage versetzen, bei Bedarf eine Bare-Metal-Wiederherstellung durchzuführen.

## EVault bestellen 

Der EVault Backup-Service kann auf die folgenden beiden Arten erworben werden.

- EVault bei Bestellung eines Servers erwerben
- EVault im Rahmen eines Upgrades erwerben

Weitere Informationen zur Preisstruktur finden Sie im Abschnitt zum [Sicherungsspeicher](https://www.ibm.com/cloud/backup-and-restore){:new_window} und unter [EVault on IBM Cloud](https://www.ibm.com/cloud/evault/pricing){:new_window}.

### EVault bei Bestellung eines Servers erwerben

1. Melden Sie sich beim [IBM Cloud-Katalog](https://console.bluemix.net/catalog/){:new_window} oder beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an.
2. Bestellen Sie ein Bare Metal Server-System pro Monat. Weitere Informationen zum Bestellen von Bare Metal Server-Systemen finden Sie [hier](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html){:new_window}.
3. Sie werden zum Verwaltungsportal weitergeleitet, wo Sie die Bestellung abschließen können. <br/>
   >**Hinweis** - Der EVault Backup-Service ist nicht verfügbar, wenn Sie einen Server bestellen, der auf stündlicher Basis abgerechnet wird. Der Service kann jedoch später als Upgrade hinzugefügt werden. 
4. Wählen Sie unter **Add-ons** eine der Optionen für EVault aus (also nicht die Option 'Ohne').
6. Blättern Sie nach unten und klicken Sie auf **Zur Bestellung hinzufügen**.
7. Suchen Sie nach dem Abschnitt 'Host- und Domänennamen' und geben Sie die Host- und Domänennamen ein. Sie können jeden gewünschten Host- und Domänennamen auswählen.
8. Klicken Sie rechts auf die Kontrollkästchen **Bedingungen für Cloud-Services** und **Servicevereinbarungen anderer Anbieter**.
9. Bestätigen Sie Ihre Zahlungsinformationen bzw. geben Sie sie ein und klicken Sie auf **Bestellung abschicken**. Sie werden zu einer Anzeige geführt, der Sie die Bestellnummer für Ihre Bereitstellung entnehmen können. Sie können die Anzeige ausdrucken, weil es sich hierbei auch um die Bestätigung des Bestelleingangs für Ihre Bereitstellung handelt. <br/>**Hinweis**: Diese Bestellung können Sie außerdem speichern, ohne den Einkauf vorzunehmen, indem Sie auf **Als Angebot speichern** klicken.

An Ihren Administrator wird eine Reihe von E-Mails gesendet, nämlich zur Bestätigung der Bereitstellungsbestellung, zur Genehmigung und Verarbeitung der Bereitstellungsbestellung sowie zur Fertigstellung der Bereitstellung. Die E-Mail zur Fertigstellung der Bereitstellung enthält einen Link zu Ihrer Seite *Gerätedetails*, auf die Sie zugreifen können, nachdem Sie sich bei {{site.data.keyword.cloud_notm}} angemeldet haben. Sie können sich auch direkt beim {{site.data.keyword.slportal}} anmelden.

**Kauf des EVault-Service bestätigen**
1. Wählen Sie im [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} im Hauptmenü die Optionen **Geräte** > **Geräteliste** aus. 
2. Suchen Sie nach dem neuen Server, den Sie bestellt haben.
  - Falls neben der URL ein Uhrsymbol angezeigt wird, müssen Sie warten, bis Sie mit der Bestätigung des EVault-Kaufs fortfahren können. Sie können die Seite aktualisieren und so einen aktualisierten Status Ihres neuen Servers anzeigen. Sobald das Uhrsymbol nicht mehr vorhanden ist, können Sie mit den nächsten Schritten fortfahren und den Kauf des EVault-Service bestätigen.
  - Wenn das Uhrsymbol nicht mehr für Ihren Server angezeigt wird, klicken Sie auf den Link (die URL des Servers), um auf die Seite **Gerätedetails** zu wechseln. 
3. Klicken Sie auf die Registerkarte **Speicher**, um die EVault-Informationen anzuzeigen.
4. Prüfen Sie den Abschnitt für EVault und vergewissern Sie sich, dass neben dem EVault-Link die Größe angezeigt wird, die Sie während des Kaufprozesses für EVault ausgewählt haben.

### EVault im Rahmen eines Upgrades erwerben

**Server zur Installation von EVault auswählen**
1. Melden Sie sich beim [IBM Cloud-Katalog](https://console.bluemix.net/catalog/){:new_window} oder beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an.
2. Wählen Sie im Hauptmenü die Optionen **Geräte** > **Geräteliste** aus. Suchen Sie nach dem Gerät, für das Sie den EVault-Service hinzufügen wollen.
3. Klicken Sie auf den Gerätenamen, um auf die Seite 'Gerätedetails' zu wechseln.

**EVault-Service hinzufügen (kaufen)**
1. Klicken Sie auf die Registerkarte **Speicher** und blättern Sie nach unten bis zum EVault-Abschnitt.
2. Klicken Sie auf den Link **Hinzufügen**.
3. Wählen Sie im Fenster einen Standort und anschließend eine Größe aus.
4. Wählen Sie den Zahlungstyp aus und klicken Sie dann auf **Weiter**.
5. Geben Sie (falls vorhanden) den **Werbeaktionscode** ein und klicken Sie auf **Neu berechnen**.
6. Prüfen Sie Ihre Bestellung und klicken Sie auf den Link, um die Bedingungen zu lesen.
7. Klicken Sie auf das Kontrollkästchen, wenn Sie den Bedingungen zustimmen.
7. Klicken Sie auf **Bestellung aufgeben**.

**EVault-Kauf im Rahmen eines Upgrades bestätigen**
1. Aktualisieren Sie die Seite **Gerätedetails** und achten Sie darauf, dass die Registerkarte **Speicher** ausgewählt ist.
2. Prüfen Sie den Abschnitt für EVault und vergewissern Sie sich, dass neben dem EVault-Link die Größe angezeigt wird, die Sie während des EVault-Kaufprozesses ausgewählt haben.<br /> **Hinweis** - Falls für die Größe des EVault-Speichers weiterhin die Kapazität 0 angezeigt wird, müssen Sie die Seite möglicherweise ein zweites Mal aktualisieren. 

## Im {{site.data.keyword.slportal}} auf Speicherdetails für EVault Backup zugreifen und Details anzeigen

Die Speicherdetails für Ihren EVault Backup-Service können Sie jederzeit im {{site.data.keyword.slportal}} einsehen. Zu den anzeigbaren Details gehören das Kennwort, die Speicheradresse und die Nutzung, die dem ausgewählten EVault Backup-Service zugeordnet ist. 

1. Um auf die Anzeige **EVault Backup-Speicher** zuzugreifen, melden Sie sich mit Ihren eindeutigen Berechtigungsnachweisen beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an.
2. Klicken Sie auf **Speicher** und wählen Sie in der Liste den Eintrag **Sicherung** aus.
2. Klicken Sie in der Zeile für die gewünschte EVault Backup-Vault auf eine beliebige Stelle, um die zugehörigen Speicherdetails anzuzeigen. Das Kennwort ist in dieser Ansicht nicht zu sehen. Fahren Sie mit dem nächsten Schritt fort, um das Kennwort anzuzeigen, das Ihrem EVault Backup-Service zugeordnet ist.
3. Klicken Sie auf das Kontrollkästchen **Anzeigen** neben dem Feld **Kennwort**, um das Kennwort für den ausgewählten EVault Backup-Service anzuzeigen.

Für viele Produkte und Services von {{site.data.keyword.BluSoftlayer_full}} wird die Kennwortspeicherfunktion im {{site.data.keyword.slportal}} ausschließlich zur Speicherung und Protokollierung des Kennworts verwendet. Für diese Angebote werden Änderungen, die im {{site.data.keyword.slportal}} vorgenommen werden, nicht auf das jeweilige Produkt oder den jeweiligen Service angewendet. 

Bei EVault Backup ist dies _nicht_ der Fall. Änderungen, die Sie im {{site.data.keyword.slportal}} am Kennwort für EVault Backup vornehmen, werden auf den Service selbst angewendet. Wenn Sie Ihr Kennwort ändern, müssen Sie bedenken, dass sich dieser Schritt direkt auf Ihren Service auswirkt. Um Ihr Kennwort zurückzusetzen, befolgen Sie die Schritte im Abschnitt [Kennwort für EVault Backup im {{site.data.keyword.slportal}} ändern](/docs/infrastructure/Backup/change-password-evault-backup-service.html).

## EVault-Agenten installieren

Der EVault-Agent wird bei den folgenden Betriebssystemen unterstützt:

**Windows**
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

**Linux**
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - Red Hat Enterprise Linux 7.x
 - Red Hat Enterprise Linux 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

Führen Sie die entsprechenden Anweisungen für Ihr Betriebssystem aus:
- [EVault Backup-Client unter Linux installieren](install-evault-backup-client-linux.html)
- [EVault Backup-Client unter Windows installieren](install-evault-backup-client-windows.html)
- [EVault Backup-Client unter Windows 2016 installieren](install-evault-windows2016.html)

## Auf WebCentralControl (WebCC) für EVault Backup zugreifen

WebCentralControl (WebCC) ist der Client, der für die Interaktion mit einem der von {{site.data.keyword.BluSoftlayer_full}} bereitgestellten EVault Backup-Services verwendet wird. WebCC ist ein browserbasierter Client, der im privaten Netz von {{site.data.keyword.BluSoftlayer_full}} ausgeführt wird und die uneingeschränkte Steuerung eines beliebigen EVault Backup-Service (einschließlich Konfiguration und Wiederherstellungen) ermöglicht. Führen Sie die folgenden Schritte aus, um auf WebCC für EVault Backup zuzugreifen.

1. Greifen Sie über ein VPN auf das private Netz zu.<br/>**Hinweis**: Der Zugriff auf WebCC über ein öffentliches Netz ist nicht möglich. Es muss zuerst eine VPN-Verbindung eingerichtet werden.
2. Greifen Sie auf die Anzeige 'Speicher' für EVault Backup im [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} zu.
3. Klicken Sie auf eine beliebige Stelle in der Zeile für die gewünschte EVault Backup-Instanz, um die Ansicht zu erweitern.
4. Klicken Sie auf **WebCC-Anmeldung**, um den WebCC-Client in Ihrem Browser zu starten.

## EVault-Agenten in WebCC konfigurieren

Nachdem Sie Ihren EVault-Service bestellt haben und der Agent auf dem Server installiert wurde, können Sie mit dem Erstellen von Sicherungen Ihrer Daten beginnen. Führen Sie die folgenden Schritte aus, um den Agenten und den Aufbewahrungszeitplan zu konfigurieren und Ihren ersten Sicherungsjob zu starten.

1. Melden Sie sich bei WebCC an.
2. Klicken Sie auf **Alle Agenten**> **Nicht konfigurierte Agenten**.
3. Klicken Sie auf den Link **Neuer Agent, der konfiguriert werden soll**. Durchlaufen Sie den Prozess und geben Sie hierbei die folgenden Informationen ein:
   1. Agentenkonfiguration: Geben Sie die Agentenbeschreibung an und klicken Sie auf **Weiter**.
   2. Jobtypauswahl: Geben Sie den Jobnamen, die Jobbeschreibung und den Sicherungsquellentyp ein und klicken Sie auf **Weiter**.
   3. Auswahl: Wählen Sie Verzeichnisse aus und klicken Sie auf **Einschließen...**
   4. Optionen: Geben Sie Kennwörter an.
   5. Zeitplan: Klicken Sie auf **Hinzufügen**, um einen Zeitplan zu erstellen, und klicken Sie auf **Weiter**.
   6. Wählen Sie den Standardwert aus und klicken Sie auf **OK**.
   7. Klicken Sie auf **Speichern**.
4. Erstellen Sie einen Aufbewahrungszeitplan.
   1. Wählen Sie die Optionen **Bearbeiten** > **Agenteneinstellungen** aus.
   2. Klicken Sie auf **Hinzufügen**.
   3. Geben Sie Ihre Aufbewahrungsdetails ein.
   4. Klicken Sie auf **OK**.
   5. Klicken Sie auf **Speichern**.
   **Hinweis:** Weitere Informationen zur Funktionsweise von Aufbewahrungsschemas finden Sie [hier](evault-backup-faq.html).
5. Führen Sie den Agenten aus und starten Sie eine Sicherung.
   1. Klicken Sie auf **Alle Agenten** und wählen Sie dann den soeben konfigurierten Agenten aus.
   2. Klicken Sie auf **Sicherung durchführen**.
   3. Bestätigen Sie das Ziel und wählen Sie ein Aufbewahrungsschema aus.
   4. Klicken Sie auf **Sicherung starten**. Während der Prozess ausgeführt wird, können Sie sich die Sicherungsdetails ansehen.
   5. Klicken Sie nach Abschluss der Sicherung auf **Schließen**.
   
>**Hinweis** - Weitere Informationen dazu, wie Sie einfache Sicherungen auf Dateiebene unter Linux konfigurieren können, finden Sie [hier](configure-simple-file-backup-linux.html).

## Onlinehilfe anfordern

Die WebCC-Systeme sind vollständig dokumentiert und die Unterstützung für die Anwendung ist in WebCC zugänglich. Klicken Sie auf das weiße Fragezeichen in dem blauen Kreis, das sich in der oberen rechten Ecke befindet, wenn Sie **Hilfe** benötigen. Klicken Sie in der Navigationsleiste auf der linken Seite auf einen beliebigen Artikel oder Abschnitt, um weitere Informationen anzuzeigen.


