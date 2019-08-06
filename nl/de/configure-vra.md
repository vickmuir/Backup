---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# VRA-Sicherungsjobs konfigurieren
{: #ConfigureVRA}

Nachdem die VMware vSphere-Umgebung im {{site.data.keyword.backup_notm}}-Portal hinzugefügt wurde, können Sie einen Sicherungsjob erstellen, der angibt, welche virtuellen Maschinen (VMs) gesichert werden sollen und wo die Sicherungsdaten gespeichert werden sollen. Zum Sichern der Daten können Sie den Sicherungsjob manuell ausführen oder die Ausführung des Sicherungsjobs planen.

Sie müssen die Vaulteinstellungen und vCenter-Informationen konfigurieren, bevor Sie einen Sicherungsjob hinzufügen können.
{:important}

## Das {{site.data.keyword.backup_notm}}-Portal starten
{: #startWebCCVRA}

Sie müssen mit dem privaten {{site.data.keyword.cloud}}-Netz verbunden sein, um das {{site.data.keyword.backup_notm}}-Portal starten zu können.
{:important}

1. Melden Sie sich bei der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}){: external} an. Wählen Sie im Navigationsmenü **Klassische Infrastruktur** aus.
2. Klicken Sie auf **Speicher** > **Cloud-Sicherung**, um die Server mit Backup-Services anzuzeigen.
3. Wählen Sie den Server aus, auf dem sich die zu sichernden Dateien befinden. Klicken Sie auf den Erweiterungspfeil, um den Link zum {{site.data.keyword.backup_notm}}-Portal sichtbar zu machen.
4. Klicken Sie auf **{{site.data.keyword.backup_notm}}-Portalanmeldung**, um den Portalclient in Ihrem Browser zu starten.

   Falls das {{site.data.keyword.backup_notm}}-Portal nicht gestartet wird, liegt möglicherweise ein Problem mit Ihrer VPN-Verbindung vor. Außerdem wird möglicherweise die Nachricht ausgegeben, dass das Formular, das Sie senden, nicht sicher ist. Dies entspricht dem erwarteten Verhalten; fahren Sie mit dem Senden des Formulars fort.
   {:tip}

## vSphere-Sicherungsjob hinzufügen

1. Klicken Sie im Navigationsbereich auf **Computer**. Auf der Seite für Computer werden die registrierten Computer und Umgebungen angezeigt.
2. Klicken Sie auf **Jobs**.
3. Wählen Sie im Menü für die Auswahl der Job-Task auf **Neuen VMware vCenter-Job erstellen**.
4. Geben Sie die folgenden Informationen an.
   * Geben Sie im Feld **Name** einen Namen für den Sicherungsjob ein.
   * Geben Sie im Feld **Beschreibung** optional eine Beschreibung für den Sicherungsjob ein.
   * Wählen Sie in der Liste **Ziel** die Vault aus, in der die Sicherungsdaten gespeichert werden sollen.
   * Geben Sie in den Feldern **Kennwort** und **Kennwort bestätigen** ein Verschlüsselungskennwort ein. Sie können auch einen Kennworthinweis in das entsprechende Feld eingeben.
   Eine Vault wird in der Liste nur angezeigt, wenn sie dem Benutzer zugeordnet ist oder wenn der Benutzer sie zu den Vaulteinstellungen des Computers hinzugefügt hat. <br/>
   Für neue Sicherungsjobs ist die Verschlüsselungsmethode AES 256 Bit. Vorhandene Jobs können andere Verschlüsselungsmethoden haben.
   {:note}

5.	Führen Sie im Feld **In Sicherung einschließen** einen oder mehrere der folgenden Schritte aus, bis im Feld für die Sicherungsgruppe die VMs angezeigt werden, die Sie in den Sicherungsjob aufnehmen möchten.

   * Wenn Sie dem Sicherungsjob bestimmte VMs hinzufügen möchten, wählen Sie jede VM aus und klicken Sie dann auf **Einschließen**.
   * Wenn Sie bestimmte VMs aus dem Sicherungsjob ausschließen möchten, wählen Sie jede VM aus und klicken Sie dann auf **Ausschließen**.
   * Wenn Sie dem Sicherungsjob VMs nach Namen hinzufügen möchten, aktivieren Sie das Kästchen für virtuelle Maschinen und klicken Sie dann auf **Einschließen**.
   * Wenn Sie einen Einschluss- oder Ausschlussdatensatz aus dem Feld für die Sicherungsgruppe entfernen möchten, klicken Sie neben dem Datensatz auf **Löschen**.

6. Klicken Sie auf **Jetzt anwenden**, um die Datensätze im Feld für die Sicherungsgruppe zu konsolidieren und zu vereinfachen, wenn Änderungen angewendet werden müssen.
7. Klicken Sie auf **Job erstellen**.

## Zeitplan einrichten

Nachdem der Sicherungsjob erstellt wurde, können Sie einen oder mehrere Zeitpläne für die automatische Ausführung des Jobs hinzufügen.

1. Wenn Sie auf **Job erstellen** klicken, wird das Fenster für Zeitplan angezeigt, über das Sie einen angepassten Zeitplan für den Sicherungsjob einrichten können.

   Standardmäßig ist die tägliche Aufbewahrung für den Job ausgewählt. In diesem Fenster können Sie die Aufbewahrung und den Jobzeitplan ändern. Sie können dem Sicherungsjob auch mehrere Aufbewahrungschemas zuordnen.
   {:note}
2. Klicken Sie auf **Speichern**, um den neuen Zeitplan zu speichern. Der neue Job wird auf der Registerkarte für Computer im Abschnitt für Jobs angezeigt. Der Status der letzten Sicherung zeigt an, dass der Job nie ausgeführt wurde. Der geplante Sicherungsjob wird zum geplanten Zeitpunkt automatisch ausgeführt.

## Geplanten Job ausführen

Geplante Sicherungsjobs können auch sofort ausgeführt werden.

1. Klicken Sie auf **Aktion auswählen** und wählen Sie **Job ausführen** aus. Das Fenster für die Ausführung des Jobs wird angezeigt und enthält Informationen zu Zielvault und Aufbewahrungsschema, die dem Job zugeordnet sind.

   Wenn dem Job mehrere Vaults und Aufbewahrungsschemas zugeordnet sind, können Sie diese Optionen im Fenster für die Ausführung des Jobs ändern, indem Sie auf die Menüoptionen für Ziel und Aufbewahrungsschema klicken.
   {:note}
2. Klicken Sie auf **Sicherungsjob starten**, um den Sicherungsjob sofort auszuführen. Im Fortschrittsfenster wird der Status des Sicherungsjobs angezeigt. Wenn der Job fertiggestellt ist, ändert sich der Jobstatus von "Nie ausgeführt" in "Abgeschlossen".

Klicken Sie auf die Registerkarte für Jobs, um den Status des letzten Sicherungsjobs anzuzeigen, der ausgeführt wurde. Auf alle Jobprotokolle kann über das Aktionsmenü zugegriffen werden. Klicken Sie auf **Aktion** und wählen Sie **Verlauf/Protokolle** aus.
{:tip}

Weitere Informationen zum Wiederherstellen von VMs oder Dateien und Ordnern finden Sie in [vSphere-Daten wiederherstellen](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore).
