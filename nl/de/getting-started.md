---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-28"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}_
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:shortdesc: .shortdesc}

# Lernprogramm zur Einführung
{: #gettingstarted}

Sicherungen gewährleisten, dass Ihre Daten außerhalb Ihrer eigenen Einheit sicher gespeichert werden und im Verlustfall geschützt sind. {{site.data.keyword.backup_full}} ist ein automatisiertes agentenbasiertes Sicherungssystem, das über das browserbasierte {{site.data.keyword.backup_notm}}-Verwaltungsdienstprogramm verwaltet wird. {{site.data.keyword.backup_notm}} bietet Benutzern ein Verfahren zur Sicherung von Daten zwischen Servern in einzelnen oder mehreren Rechenzentren im {{site.data.keyword.BluSoftlayer_full}}-Netz. Administratoren können für Sicherungen einen täglichen, wöchentlichen oder angepassten Zeitplan erstellen, der ganze Systeme, bestimmte Verzeichnisse oder sogar einzelne Dateien abdeckt. Es stehen zusätzliche Plug-ins zur Verfügung, die die Kompatibilität mit Software wie Microsoft Exchange und Microsoft SQL sowie weiteren Typen von Software anderer Anbieter sicherstellen und Benutzer in die Lage versetzen, bei Bedarf eine Bare-Metal-Wiederherstellung durchzuführen.
{:shortdesc}

## Vorbereitungen
{: #prereqs}

Für die Verwendung von IBM Cloud Backup ist eine gültige Lizenz erforderlich. Sie können den {{site.data.keyword.backup_notm}}-Service auf zwei Arten erwerben.

- [Sicherungen bei der Bestellung eines Servers kaufen](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingwithserver).
- [Sicherungen als Upgrade kaufen](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingasupgrade).

Weitere Informationen zu Bestellverfahren und Preisstrukturen finden Sie in [Bereitstellung von {{site.data.keyword.backup_notm}}](/docs/infrastructure/Backup?topic=Backup-ordering). 

## {{site.data.keyword.backup_notm}}-Agenten installieren

Der {{site.data.keyword.backup_notm}}-Agent wird von den folgenden Betriebssystemen unterstützt:

**Windows**
 - Windows Server 2016
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
 - RHEL 7.x
 - RHEL 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

Führen Sie die entsprechenden Anweisungen für Ihr Betriebssystem aus:
- [Backup-Client unter Linux installieren](/docs/infrastructure/Backup?topic=Backup-InstallinLinux)
- [Backup-Client unter Windows installieren](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)
- [Backup-Client unter Windows 2016 installieren](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016)

## Auf das {{site.data.keyword.backup_notm}}-Portal (vorher WebCC) zugreifen

Das {{site.data.keyword.backup_notm}}-Portal wird für die Interaktion mit jedem {{site.data.keyword.backup_notm}}-Service verwendet, der von {{site.data.keyword.BluSoftlayer_full}} angeboten wird. Das {{site.data.keyword.backup_notm}}-Portal ist ein browserbasierter Client, der im privaten Netz von {{site.data.keyword.BluSoftlayer_full}} ausgeführt wird und die uneingeschränkte Steuerung eines beliebigen {{site.data.keyword.backup_notm}}-Service (einschließlich Konfiguration und Wiederherstellungen) ermöglicht.

1. Greifen Sie über ein VPN auf das private Netz zu.

   Das {{site.data.keyword.backup_notm}}-Portal kann nicht über das öffentliche Netz aufgerufen werden. Es muss zuerst eine VPN-Verbindung eingerichtet werden.
   {:important}
2. Greifen Sie auf die Anzeige des Sicherungsspeichers im [{{site.data.keyword.slportal}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){:new_window} zu.
3. Klicken Sie auf eine beliebige Stelle in der Zeile des {{site.data.keyword.backup_notm}}-Service, den Sie anzeigen möchten, um die Ansicht zu erweitern.
4. Klicken Sie auf **{{site.data.keyword.backup_notm}}-Portalanmeldung**, um den Portalclient in Ihrem Browser zu starten.

## Backup-Client und Sicherungszeitplan konfigurieren

Nachdem Sie Ihren {{site.data.keyword.backup_notm}} bestellt haben und der Agent auf dem Server installiert ist, können Sie mit der Sicherung Ihrer Daten beginnen. Führen Sie diese Schritte aus, um den Agenten und den Aufbewahrungszeitplan zu konfigurieren. 

1. Melden Sie sich beim {{site.data.keyword.backup_notm}}-Portal an.
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

      Weitere Informationen zu Aufbewahrungsschemas finden Sie in den [FAQs](faqs.html).
      {:tip}

## Ersten Sicherungsjob ausführen

1. Melden Sie sich beim {{site.data.keyword.backup_notm}}-Portal an.
2. Klicken Sie auf **Alle Agenten** und wählen Sie dann den soeben konfigurierten Agenten aus.
3. Klicken Sie auf **Sicherung durchführen**.
4. Bestätigen Sie das Ziel und wählen Sie ein Aufbewahrungsschema aus.
5. Klicken Sie auf **Sicherung starten**. Während der Prozess ausgeführt wird, können Sie sich die Sicherungsdetails ansehen.
6. Klicken Sie nach Abschluss der Sicherung auf **Schließen**.

Weitere Informationen finden Sie in [Einfache Sicherung auf Dateiebene unter Linux konfigurieren](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup).
{:tip}

## Über die Konsole auf Speicherdetails von {{site.data.keyword.backup_notm}} zugreifen und diese anzeigen

Die Speicherdetails Ihres Service können jederzeit in der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}/){:new_window} und im {{site.data.keyword.slportal}} angezeigt werden. Zu den anzeigbaren Details gehören das Kennwort, die Speicheradresse und die Nutzung, die dem ausgewählten {{site.data.keyword.backup_notm}}-Service zugeordnet sind.

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}){:new_window} an und klicken Sie oben links auf das **Menüsymbol**. Wählen Sie **Klassische Infrastruktur** aus.</br>
   Alternativ können Sie sich beim [{{site.data.keyword.slportal}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){:new_window} anmelden. 
2. Klicken Sie auf **Speicher** und wählen Sie in der Liste den Eintrag **Sicherung** aus.
2. Klicken Sie in der Zeile für die gewünschte Vault auf eine beliebige Stelle, um die zugehörigen Speicherdetails anzuzeigen. Das Kennwort ist in dieser Ansicht nicht zu sehen.
3. Klicken Sie auf das Kontrollkästchen **Anzeigen** neben dem Feld **Kennwort**, um das Kennwort für den ausgewählten {{site.data.keyword.backup_notm}}-Service anzuzeigen.

Änderungen, die Sie am Kennwort für {{site.data.keyword.backup_notm}} im {{site.data.keyword.slportal}} vornehmen, werden auf den Service selbst angewendet. Zum Zurücksetzen des Kennworts führen Sie die Schritte aus, die in [Kennwort für den Sicherungsservice ändern](/docs/infrastructure/Backup?topic=Backup-changePassword) beschrieben sind.
{:important}

## Weitere Onlinehilfe anfordern

Die Systeme des {{site.data.keyword.backup_notm}}-Portals sind vollständig dokumentiert und die Unterstützung für die Anwendung ist im {{site.data.keyword.backup_notm}}-Portal zugänglich. Klicken Sie auf das weiße Fragezeichen in dem blauen Kreis, das sich in der oberen rechten Ecke befindet, wenn Sie **Hilfe** benötigen. Klicken Sie in der Navigationsleiste auf der linken Seite auf einen beliebigen Artikel oder Abschnitt, um weitere Informationen anzuzeigen.
