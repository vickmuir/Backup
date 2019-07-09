---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-10"

keywords: IBM Cloud backup, EVault, Carbonite, backup, configure BMR, bmr plug-in, bmr plugin, configuration

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# BMR-Sicherungsjob konfigurieren
{: #configureBMR}

Sie müssen das Plug-in für BMR (Bare Metal Restore, Bare-Metal-Wiederherstellung) erwerben, um eine BMR-Sicherung durchführen zu können. BMR ist nur für Bare Metal Server-Systeme unter Windows verfügbar. Bei einer virtuellen Serverinstanz (VSI) gibt es keine BMR-Option. Weitere Informationen finden Sie in [Informationen zum Plug-in für Bare-Metal-Wiederherstellung](/docs/infrastructure/Backup?topic=Backup-BMRplugin#BMRplugin).
{:important}

## Das {{site.data.keyword.backup_notm}}-Portal starten
{: #startWebCCBMR}

Sie müssen mit dem privaten {{site.data.keyword.cloud}}-Netz verbunden sein, um das {{site.data.keyword.backup_notm}}-Portal starten zu können.
{:important}

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}){: external} an und klicken Sie oben links auf das **Menüsymbol**. Wählen Sie **Klassische Infrastruktur** aus.
2. Klicken Sie auf **Speicher** > **Sicherung**, um die Server mit Backup-Services anzuzeigen.
3. Wählen Sie den Server aus, auf dem sich die zu sichernden Dateien befinden. Klicken Sie auf den nach rechts zeigenden Erweiterungspfeil, um den Link zum {{site.data.keyword.backup_notm}}-Portal sichtbar zu machen.
4. Klicken Sie auf **{{site.data.keyword.backup_notm}}-Portalanmeldung**, um den Portalclient in Ihrem Browser zu starten.

   Falls das {{site.data.keyword.backup_notm}}-Portal nicht gestartet wird, liegt möglicherweise ein Problem mit Ihrer VPN-Verbindung vor. Außerdem wird möglicherweise die Nachricht ausgegeben, dass das Formular, das Sie senden, nicht sicher ist. Dies entspricht dem erwarteten Verhalten; fahren Sie mit dem Senden des Formulars fort.
   {:tip}

## BMR-Sicherungsjob konfigurieren

1. Klicken Sie im linken Navigationsbereich auf **Alle Agenten**, um die aktuellen {{site.data.keyword.backup_notm}}-Agenten anzuzeigen.
2. Klicken Sie auf **Neuer Agent, der konfiguriert werden soll**.
3. Geben Sie einen Jobnamen und eine Jobbeschreibung für den Job ein, den Sie erstellen.
4. Wählen Sie bei **Sicherungsquellentyp** in der Liste den Typ des Dateisystems aus und klicken Sie dann auf **Weiter**.
5. Das Menü **Jobtypauswahl** wird angezeigt. Wählen Sie das Feld neben **Bare-Metal-Wiederherstellung** aus und klicken Sie auf **Weiter**, um fortzufahren.
6. Klicken Sie im Bestätigungsfenster auf **Ja**.
7. In der Anzeige ist angegeben, dass der neue Job jetzt in der Sicherungsgruppe enthalten ist. Klicken Sie auf **Weiter**.
8. In der Anzeige werden Verschlüsselungsoptionen und erweiterte Sicherungsoptionen angezeigt. Normalerweise werden diese Optionen nicht benötigt. Klicken Sie auf **Weiter**.   
9. Auf der Seite **Zeitplan erstellen** stehen Ihnen zwei Optionen zur Verfügung.
   - Klicken Sie auf **Weiter**, um einen manuellen Job zu erstellen, und fahren Sie mit der Ausführung Ihres neuen Jobs fort.
   - Klicken Sie auf **Hinzufügen**, um einen zeitbasierten Sicherungsjob zu planen.
     1. Wählen Sie die Tage und die Uhrzeit für die Ausführung der Sicherungen aus.
     2. Wählen Sie das Aufbewahrungsschema aus.

        Weitere Informationen zu Aufbewahrungsschemas finden Sie im Abschnitt zu den [häufig gestellten Fragen](/docs/infrastructure/Backup?topic=Backup-faqs).
        {:tip}
     3. Nachdem Sie den Sicherungszeitplan konfiguriert haben, klicken Sie auf **OK**, um ihn zu speichern. Ihr geplanter Job wird zur Liste der geplanten Jobs hinzugefügt.
10. Wählen Sie eine Vault für Ihren Sicherungsjob aus und klicken Sie auf **Änderungen speichern**.


## BMR-Sicherungsjob ausführen

  - Falls Sie einen zeitbasierten Sicherungsjob geplant haben, sind keine weiteren Schritte erforderlich. Ihr Job wird wie geplant automatisch ausgeführt.
  - Falls Sie einen manuellen Job (ohne zeitbasierten Zeitplan) konfiguriert haben, können Sie ihn ausführen, indem Sie seine Zeile in der Jobliste auswählen und auf **Sicherung ausführen** klicken. <br/> Wie bei zeitbasierten Jobs können Sie auch hier das **Aufbewahrungsschema** und **erweiterte Sicherungsoptionen** auswählen. Nachdem Sie die Konfigurationseinstellungen festgelegt haben, klicken Sie auf **Sicherung starten**, um den Job zu starten.
