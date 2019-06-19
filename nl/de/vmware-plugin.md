---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-13"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Informationen zu vSphere Recovery Agent
{: #VRA}

Die Windows-Anwendung vSphere Recovery Agent (VRA) kann VMDKs bis zu 10 TB sichern und wiederherstellen. Sie können vSphere Recovery Agent auf einer physischen oder virtuellen Maschine installieren, die über lokalen Netzzugriff auf das vCenter verfügt, das geschützt werden soll. Installieren Sie VRA auf einer Maschine, die sich im selben Teilnetz wie das vCenter befindet, um die Leistung zu optimieren. Zum Verteilen der Workload können bis zu fünf VRA-Instanzen die VMs schützen, die an ein einzelnes vCenter angeschlossen sind.

In einem standortübergreifenden vSAN-Cluster hat jede VM einen bevorzugten Standort. Im Idealfall ist eine lokale VRA-Instanz an jedem Standort installiert, die die bevorzugten VMs dieses Standorts sichert. Wenn eine VM (aufgrund von Wartungen oder Ausfällen) an einen anderen Standort verschoben wird, kann die Sicherungsleistung vermindert werden, bleibt aber akzeptabel.

## Plug-in installieren
{: #installVRAPlugin}

Stellen Sie sicher, dass das Energiemanagement auf dem Server, auf dem Sie VRA installieren, inaktiviert ist.
{: important}

1. Laden Sie das Installationskit von der Website `http://downloads.service.softlayer.com/evault/` herunter. Klicken Sie anschließend doppelt auf das Installationskit.
2. Klicken Sie in der Bestätigungsnachricht auf **JA**.
3. Klicken Sie auf der Begrüßungsseite auf **Weiter**.
4. Lesen Sie auf der Seite mit der Endbenutzer-Lizenzvereinbarung die Lizenzvereinbarung. Wenn Sie den Bedingungen zustimmen, klicken Sie auf **Ich akzeptiere die Bedingungen der Lizenzvereinbarung** und klicken Sie anschließend auf **Weiter**.
5. Führen Sie auf der Zielordnerseite eine der folgenden Aktionen aus.
   * Klicken Sie auf **Weiter**, um VRA an der Standardposition zu installieren.
   * Klicken Sie auf **Ändern**, um VRA an einer anderen Position zu installieren. Navigieren Sie im Dialogfenster zum Ändern des Zielordners zum neuen Installationsordner oder geben Sie ihn in das Feld für den Ordnernamen ein. Klicken Sie auf **OK**. Klicken Sie auf der Zielordnerseite auf **Weiter**.
6. Geben Sie auf der Seite zum Registrieren des Agenten beim Portal die folgenden Informationen an.
   * Geben Sie in das Feld **Netzadresse** den Wert `ev-webcc01.service.softlayer.com` ein.
   * Geben Sie in das Feld **Port** den Wert `8086` ein.
   * Geben Sie im Feld **Benutzername** den {{site.data.keyword.backup_notm}}-Benutzernamen für die Verwaltung von VRA ein.
   * Geben Sie im Feld **Kennwort** das Kennwort für den angegebenen {{site.data.keyword.backup_notm}}-Benutzer ein.
7.	Klicken Sie auf **Weiter**. Klicken Sie nach Abschluss der Installation auf **Fertigstellen**.

## vSphere Recovery Agent konfigurieren
{: #configureVRA}

Nachdem VRA installiert wurde, müssen Sie die Software im {{site.data.keyword.backup_notm}}-Portal konfigurieren.

1. Melden Sie sich beim {{site.data.keyword.backup_notm}}-Portal an. Weitere Informationen zum Zugriff auf das {{site.data.keyword.backup_notm}}-Portal finden Sie im [Lernprogramm zur Einführung](/docs/infrastructure/Backup?topic=Backup-getting-started#accessingWebCC).
2. Wählen Sie auf der Registerkarte für Computer den Server aus, den Sie sichern möchten.
3. Konfigurieren Sie die Vaultinformationen.

   Für die Konfiguration von Vaultinformationen gibt es zwei Optionen: **Automatisch** und **Manuell**.<br/>Wenn der Agent zum ersten Mal konfiguriert wird, kann er mit der Option [Automatische Konfiguration](#VRAautoconfig) konfiguriert werden.<br/>Wenn der Computer zuvor bei einer Vault registriert wurde, funktioniert die automatische Konfiguration nicht, und die Vault muss [manuell konfiguriert](#VRAmanualconfig) werden.
   {: tip}

4. Konfigurieren Sie die [vCenter-Einstellungen](#vCenterSettingsconfig).   

### Vault automatisch konfigurieren
{: #VRAautoconfig}

Wenn die Vaulteinstellungen automatisch konfiguriert werden sollen, klicken Sie auf **Automatisch konfigurieren**. Der Konfigurationsassistent wird ausgeführt und konfiguriert die Vaulteinstellungen für Sie. Wenn die Konfiguration abgeschlossen ist, klicken Sie auf **Zu Agent wechseln**, um die Informationen auf der Registerkarte **Vaulteinstellungen** zu überprüfen.
 

### Vault manuell konfigurieren
{: #VRAmanualconfig}

Wenn die Vaulteinstellungen manuell konfiguriert werden sollen, klicken Sie auf **Manuell konfigurieren**.   
1. Klicken Sie auf **Vaulteinstellungen**.
2. Klicken Sie auf **Vault hinzufügen**. Das Fenster für Vaulteinstellungen wird angezeigt. Wählen Sie in den Optionen unter **Vaultprofil** die entsprechende Vault aus.
   Wenn der Computer zuvor bei einer {{site.data.keyword.backup_notm}}-Vault registriert wurde, werden alle Informationen automatisch gefüllt, wenn die Vault aus dem Vaultprofil ausgewählt wird.
   {:note}

3. Überprüfen Sie alle Informationen auf der Seite für Vaulteinstellungen und klicken Sie auf **Speichern**.
4. Wenn Sie die Vaulteinstellungen speichern, werden die Vaultinformationen auf der Registerkarte **Vaulteinstellungen** angezeigt.


### vCenter-Agenteneinstellungen konfigurieren
{: #vCenterSettingsconfig}
Nach der erfolgreichen Vaultregistrierung müssen die vCenter-Einstellungen konfiguriert werden, bevor Sie Sicherungsjobs erstellen und ausführen können.

1. Klicken Sie auf die Registerkarte **vCenter-Einstellungen**.
2. Geben Sie die vCenter-IP-Adresse, den Domänennamen und die Berechtigungsnachweise für das vCenter an, das geschützt werden soll.
   Der Benutzer muss über Verwaltungszugriff auf das vCenter verfügen, um diese Task erfolgreich ausführen zu können.
   {:note}

3. Inaktivieren Sie Change Block Tracking (CBT), indem Sie das Häkchen entfernen. CBT ist eine VMware-Funktion, die geänderte Plattensektoren verfolgt und die Leistung von VM-Sicherungen verbessert. Sie wird automatisch vom vSphere-Agenten aktiviert.
4. Klicken Sie auf **vCenter-Verbindung testen**. In einem neuen Fenster werden die Ergebnisse angezeigt. Wenn die bereitgestellten Anmeldeinformationen korrekt sind, wird eine Nachricht wie "Die vCenter-Berechtigungsnachweise wurden erfolgreich validiert" angezeigt.
5. Klicken Sie auf **Speichern**, um die Einstellungen zu speichern.

## vSphere-Sicherungsjob konfigurieren
{: #configvmwarebackup}

Weitere Informationen finden Sie in [Sicherungsjob konfigurieren, planen und ausführen](/docs/infrastructure/Backup?topic=Backup-ConfigureVRA#VConfigureVRA). 

## vSphere-Daten wiederherstellen
{: #restoringvSphereData}

Weiere Informationen finden Sie in [vSphere-Daten wiederherstellen](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore). 


Stellen Sie eine Verbindung zum {{site.data.keyword.cloud}}-Netz mit {{site.data.keyword.BluVPN}} her, damit Sie auf das Benutzerhandbuch zugreifen und es über die [für den Download verfügbare {{site.data.keyword.backup_notm}}-Dokumentation](http://downloads.service.softlayer.com/evault/Documentation/){: external} herunterladen können.
{:tip}
