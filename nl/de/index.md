---

copyright:
  years: 2014, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Erste Schritte mit {{site.data.keyword.backup_notm}}-Services

Sicherungen gewährleisten, dass Ihre Daten außerhalb Ihrer eigenen Einheit sicher gespeichert werden und im Verlustfall geschützt sind. {{site.data.keyword.backup_full}} ist ein automatisiertes agentenbasiertes Sicherungssystem, das über das browserbasierte WebCC-Verwaltungsdienstprogramm verwaltet wird. {{site.data.keyword.backup_notm}} bietet Benutzern ein Verfahren zur Sicherung von Daten zwischen Servern in einzelnen oder mehreren Rechenzentren im {{site.data.keyword.BluSoftlayer_full}}-Netz. Administratoren können für Sicherungen einen täglichen, wöchentlichen oder angepassten Zeitplan erstellen, der ganze Systeme, bestimmte Verzeichnisse oder sogar einzelne Dateien abdeckt. Es stehen zusätzliche Plug-ins zur Verfügung, die die Kompatibilität mit Software wie Microsoft Exchange und Microsoft SQL sowie weiteren Typen von Software anderer Anbieter sicherstellen und Benutzer in die Lage versetzen, bei Bedarf eine Bare-Metal-Wiederherstellung durchzuführen.

## {{site.data.keyword.backup_notm}} bestellen

Sie können den {{site.data.keyword.backup_notm}}-Service auf zwei Arten erwerben.

- [{{site.data.keyword.backup_notm}} bei der Bestellung eines Servers kaufen](#purchasing-ibm-cloud-backup-when-you-order-a-server)
- [{{site.data.keyword.backup_notm}} als Upgrade kaufen](#purchasing-ibm-cloud-backup-as-an-upgrade)

Weitere Informationen zur Preisgestaltung finden Sie unter [{{site.data.keyword.backup_notm}}-Speicher](https://www.ibm.com/cloud/backup-and-restore){:new_window} und [{{site.data.keyword.backup_notm}} on IBM Cloud](https://www.ibm.com/cloud/evault/pricing){:new_window}.

### {{site.data.keyword.backup_notm}} bei der Bestellung eines Servers kaufen

1. Melden Sie sich beim [IBM Cloud-Katalog](https://{DomainName}/catalog/){:new_window} oder dem [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} an.
2. Bestellen Sie ein Bare Metal Server-System pro Monat. Weitere Informationen zum Bestellen von Bare-Metal-Servern finden Sie im Abschnitt zum Thema [Angepasste Bare-Metal-Server erstellen](bare-metal/baremetal-provision.html){:new_window}.
   1. Wählen Sie die Menge und die Abrechnungsoption aus. Geben Sie den Host- und Domänenname ein. Sie können jeden gewünschten Host- und Domänennamen auswählen.

   Der {{site.data.keyword.backup_notm}}-Service ist nicht verfügbar, wenn Sie einen Server bestellen, der auf Stundenbasis abgerechnet wird. Der Service kann jedoch später als Upgrade hinzugefügt werden.
   {:tip}

   2. Wählen Sie die Position aus.
   3. Wählen Sie die Serverkonfiguration und einen Betriebssystemimagetyp aus. Sie können auch mehrere Add-ons auswählen.
   4. Klicken Sie im Abschnitt **Speicherplatten** auf **Add-ons** und wählen Sie **{{site.data.keyword.backup_notm}}-Sicherung** aus. Wählen Sie die Option aus, die Ihren Anforderungen am besten entspricht.
   5. Wählen Sie unter **Netzschnittstelle** die Uplink-Port-Geschwindigkeit und alle gewünschten Add-ons aus.
3. Überprüfen Sie auf der rechten Seite Ihre Bestellübersicht.
4. Danach markieren Sie das Kontrollkästchen **Die im Folgenden aufgeführten Servicevereinbarungen anderer Anbieter habe ich gelesen und stimme ihnen zu:**.
5. Klicken Sie auf **Bereitstellung**. Sie werden zu einer Anzeige geführt, der Sie die Bestellnummer für Ihre Bereitstellung entnehmen können. Sie können die Anzeige ausdrucken, weil es sich hierbei auch um die Bestätigung des Bestelleingangs für Ihre Bereitstellung handelt.

   Sie können diese Bestellung auch ohne Einkauf speichern, indem Sie auf **Als Angebot speichern** klicken. {:tip}

An Ihren Administrator wird eine Reihe von E-Mails gesendet, nämlich zur Bestätigung der Bereitstellungsbestellung, zur Genehmigung und Verarbeitung der Bereitstellungsbestellung sowie zur Fertigstellung der Bereitstellung. Die E-Mail zur Fertigstellung der Bereitstellung enthält einen Link zu Ihrer Seite *Gerätedetails*, auf die Sie zugreifen können, nachdem Sie sich bei {{site.data.keyword.cloud_notm}} angemeldet haben. Sie können sich auch direkt beim {{site.data.keyword.slportal}} anmelden.

#### {{site.data.keyword.backup_notm}}-Einkauf bestätigen
1. Klicken Sie in der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}/catalog/){:new_window} oben links auf das Symbol **Menü**. Wählen Sie **Klassische Infrastruktur** aus.

   Alternativ können Sie sich beim [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} anmelden.
2. Klicken Sie auf **Gerät** > **Geräteliste**.
2. Suchen Sie nach dem neuen Server, den Sie bestellt haben.
  - Wenn das Uhrsymbol neben der URL angezeigt wird, müssen Sie warten, bevor Sie mit der Kaufbestätigung für {{site.data.keyword.backup_notm}} fortfahren können. Sie können die Seite aktualisieren und so einen aktualisierten Status Ihres neuen Servers anzeigen. Wenn das Uhrsymbol nicht mehr angezeigt wird, können Sie mit den nächsten Schritten fortfahren, um den Kauf des {{site.data.keyword.backup_notm}}-Service zu bestätigen.
  - Wenn das Uhrsymbol nicht mehr für Ihren Server angezeigt wird, klicken Sie auf den Link (die URL des Servers), um auf die Seite **Gerätedetails** zu wechseln.
3. Klicken Sie auf die Registerkarte **Speicher**, um die {{site.data.keyword.backup_notm}}-Informationen anzuzeigen.
4. Überprüfen Sie den Abschnitt {{site.data.keyword.backup_notm}} und vergewissern Sie sich, dass die Größe angezeigt wird, die Sie während des Kaufvorgangs ausgewählt haben.

### {{site.data.keyword.backup_notm}} als Upgrade kaufen

#### Wählen Sie einen Server aus, auf dem Sie {{site.data.keyword.backup_notm}} installieren möchten.

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}Konsole](https://{DomainName}/catalog/){:new_window} an und klicken Sie oben links auf das Symbol **Menü**. Wählen Sie **Klassische Infrastruktur** aus.

   Alternativ können Sie sich beim [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} anmelden.
2. Wählen Sie im Hauptmenü die Optionen **Geräte** > **Geräteliste** aus. Suchen Sie nach dem Gerät, für das Sie den {{site.data.keyword.cloud_notm}}-Sicherungsservice hinzufügen möchten.
3. Klicken Sie auf den Gerätenamen, um zu der Seite **Gerätedetails** zu gelangen.

#### {{site.data.keyword.backup_notm}}-Service hinzufügen (kaufen)
1. Klicken Sie auf die Registerkarte **Speicher** und blättern Sie nach unten zum Abschnitt {{site.data.keyword.backup_notm}}.
2. Klicken Sie auf den Link **Hinzufügen**.
3. Wählen Sie im Fenster einen Standort und anschließend eine Größe aus.
4. Wählen Sie den Zahlungstyp aus und klicken Sie dann auf **Weiter**.
5. Geben Sie (falls vorhanden) den **Werbeaktionscode** ein und klicken Sie auf **Neu berechnen**.
6. Prüfen Sie Ihre Bestellung und klicken Sie auf den Link, um die Bedingungen zu lesen.
7. Klicken Sie auf das Kontrollkästchen, wenn Sie den Bedingungen zustimmen.
7. Klicken Sie auf **Bestellung aufgeben**.

#### Kauf des {{site.data.keyword.backup_notm}}-Upgrade bestätigen
1. Aktualisieren Sie die Seite **Gerätedetails** und achten Sie darauf, dass die Registerkarte **Speicher** ausgewählt ist.
2. Überprüfen Sie den Abschnitt {{site.data.keyword.backup_notm}} und vergewissern Sie sich, dass die Größe angezeigt wird, die Sie während des Kaufvorgangs ausgewählt haben.

   Falls für die Größe des Speichers weiterhin die Kapazität 0 angezeigt wird, müssen Sie die Seite möglicherweise ein zweites Mal aktualisieren. {:tip}

## Auf Speicherdetails von {{site.data.keyword.backup_notm}} zugreifen und diese anzeigen

Die Speicherdetails Ihres {{site.data.keyword.backup_notm}}-Service können jederzeit in der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}/catalog/){:new_window} und im {{site.data.keyword.slportal}} angezeigt werden. Zu den anzeigbaren Details gehören das Kennwort, die Speicheradresse und die Nutzung, die dem ausgewählten {{site.data.keyword.backup_notm}}-Service zugeordnet sind.

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}Konsole](https://{DomainName}/catalog/){:new_window} an und klicken Sie oben links auf das Symbol **Menü**. Wählen Sie **Klassische Infrastruktur** aus.

   Alternativ können Sie sich beim [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} anmelden.
2. Klicken Sie auf **Speicher** und wählen Sie in der Liste den Eintrag **Sicherung** aus.
2. Klicken Sie in der Zeile für die gewünschte Vault auf eine beliebige Stelle, um die zugehörigen Speicherdetails anzuzeigen. Das Kennwort ist in dieser Ansicht nicht zu sehen. Fahren Sie mit dem nächsten Schritt fort, um das Kennwort anzuzeigen, das Ihrem {{site.data.keyword.backup_notm}}-Service zugeordnet ist.
3. Klicken Sie auf das Kontrollkästchen **Anzeigen** neben dem Feld **Kennwort**, um das Kennwort für den ausgewählten {{site.data.keyword.backup_notm}}-Service anzuzeigen.

Für viele Produkte und Services von {{site.data.keyword.BluSoftlayer_full}} wird die Kennwortspeicherfunktion im {{site.data.keyword.slportal}} ausschließlich zur Speicherung und Protokollierung des Kennworts verwendet. Für diese Angebote werden Änderungen, die im {{site.data.keyword.slportal}} vorgenommen werden, nicht auf das jeweilige Produkt oder den jeweiligen Service angewendet.

Dies gilt _nicht_ für {{site.data.keyword.backup_notm}}. Änderungen, die Sie am Kennwort für {{site.data.keyword.backup_notm}} im {{site.data.keyword.slportal}} vornehmen, werden auf den Service selbst angewendet. Wenn Sie Ihr Kennwort ändern, müssen Sie bedenken, dass sich dieser Schritt direkt auf Ihren Service auswirkt. Zum Zurücksetzen Ihres Kennworts befolgen Sie die Schritte in [Kennwort für {{site.data.keyword.backup_notm}} im {{site.data.keyword.slportal}} ändern](change-password.html).
{:important}

## {{site.data.keyword.backup_notm}}-Agenten installieren

Der {{site.data.keyword.backup_notm}}-Agent wird von den folgenden Betriebssystemen unterstützt:

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
- [Backup-Client unter Linux installieren](install-backup-client-linux.html)
- [Backup-Client unter Windows installieren](install-backup-client-windows.html)
- [Backup-Client für Windows 2016 installieren](install-windows2016.html)

## Auf WebCentralControl (WebCC) zugreifen

WebCentralControl (WebCC) ist der Client, der für die Interaktion mit jedem {{site.data.keyword.backup_notm}}-Service verwendet wird, der von {{site.data.keyword.BluSoftlayer_full}} angeboten wird. WebCC ist ein browserbasierter Client, der im privaten Netz von {{site.data.keyword.BluSoftlayer_full}} ausgeführt wird und die uneingeschränkte Steuerung eines beliebigen {{site.data.keyword.backup_notm}}-Service (einschließlich Konfiguration und Wiederherstellungen) ermöglicht. Führen Sie die folgenden Schritte aus, um auf WebCC zuzugreifen.

1. Greifen Sie über ein VPN auf das private Netz zu.

   WebCC kann nicht über das öffentliche Netz aufgerufen werden. Es muss zuerst eine VPN-Verbindung eingerichtet werden.
   {:important}
2. Greifen Sie auf die Anzeige des Sicherungsspeichers im [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} zu.
3. Klicken Sie auf eine beliebige Stelle in der Zeile des {{site.data.keyword.backup_notm}}-Service, den Sie in der Ansicht erweitern möchten.
4. Klicken Sie auf **WebCC-Anmeldung**, um den WebCC-Client in Ihrem Browser zu starten.

## Sicherungsagenten in WebCC konfigurieren

Nachdem Sie Ihren {{site.data.keyword.backup_notm}} bestellt haben und der Agent auf dem Server installiert ist, können Sie mit der Sicherung Ihrer Daten beginnen. Führen Sie die folgenden Schritte aus, um den Agenten und den Aufbewahrungszeitplan zu konfigurieren und Ihren ersten Sicherungsjob zu starten.

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

      Weitere Informationen zu Aufbewahrungsschemas finden Sie in den [FAQs](faqs.html)
      {:tip}
5. Führen Sie den Agenten aus und starten Sie eine Sicherung.
   1. Klicken Sie auf **Alle Agenten** und wählen Sie dann den soeben konfigurierten Agenten aus.
   2. Klicken Sie auf **Sicherung durchführen**.
   3. Bestätigen Sie das Ziel und wählen Sie ein Aufbewahrungsschema aus.
   4. Klicken Sie auf **Sicherung starten**. Während der Prozess ausgeführt wird, können Sie sich die Sicherungsdetails ansehen.
   5. Klicken Sie nach Abschluss der Sicherung auf **Schließen**.

Weitere Informationen zu Sicherungen auf Dateiebene unter Linux finden Sie unter [Einfache Sicherung auf Dateiebene unter Linux konfigurieren](configure-simple-file-backup-linux.html).
{:tip}

## Onlinehilfe anfordern

Die WebCC-Systeme sind vollständig dokumentiert und die Unterstützung für die Anwendung ist in WebCC zugänglich. Klicken Sie auf das weiße Fragezeichen in dem blauen Kreis, das sich in der oberen rechten Ecke befindet, wenn Sie **Hilfe** benötigen. Klicken Sie in der Navigationsleiste auf der linken Seite auf einen beliebigen Artikel oder Abschnitt, um weitere Informationen anzuzeigen.
