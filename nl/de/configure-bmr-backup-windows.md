---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# BMR-Sicherungsjob unter Windows konfigurieren

**Voraussetzung**

Sie müssen das Plug-in für BMR (Bare Metal Restore, Bare-Metal-Wiederherstellung) erwerben, um eine BMR-Sicherung durchführen zu können. BMR ist nur für Bare Metal Server-Systeme  unter Windows verfügbar. Bei einer virtuellen Serverinstanz (VSI) gibt es keine BMR-Option.

## WebCC starten
**Hinweis**: Sie müssen mit dem privaten {{site.data.keyword.BluSoftlayer_full}}-Netz verbunden sein, um WebCC starten zu können.
1. Melden Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an und klicken Sie im Hauptmenü auf **Speicher** > **Sicherung**, um die Server mit EVault Backup-Service anzuzeigen. 
2. Wählen Sie den Server aus, auf dem sich die zu sichernden Dateien befinden. Klicken Sie auf den nach rechts zeigenden Erweiterungspfeil, um den Link zu WebCC sichtbar zu machen.
4. Klicken Sie auf **WebCC-Anmeldung**, um den WebCC-Client in Ihrem Browser zu starten.
  **Hinweis**: Falls WebCC nicht gestartet wird, liegt möglicherweise ein Problem mit Ihrer VPN-Verbindung vor. Außerdem wird möglicherweise die Nachricht ausgegeben, dass das Formular, das Sie senden, nicht sicher ist. Dies entspricht dem erwarteten Verhalten; fahren Sie mit dem Senden des Formulars fort.
  
## BMR-Sicherungsjob konfigurieren

1. Klicken Sie im linken Navigationsbereich auf **Alle Agenten**, um die aktuellen EVault-Agenten anzuzeigen.
2. Klicken Sie auf **Neuer Agent, der konfiguriert werden soll**.
3. Geben Sie einen Jobnamen und eine Jobbeschreibung für den Job ein, den Sie konfigurieren bzw. erstellen.
4. Wählen Sie bei **Sicherungsquellentyp** in der Liste den Typ des Dateisystems aus, für den die Sicherung ausgeführt werden soll, und klicken Sie dann auf **Weiter**.
5. Das Menü **Jobtypauswahl** wird angezeigt. Wählen Sie das Feld neben **Bare-Metal-Wiederherstellung** aus und klicken Sie auf **Weiter**, um fortzufahren.
6. Klicken Sie im Bestätigungsfenster auf **Ja**.
7. In der Anzeige ist angegeben, dass der neue Job jetzt in der Sicherungsgruppe enthalten ist. Klicken Sie auf **Weiter**.
8. In der Anzeige werden Verschlüsselungsoptionen und erweiterte Sicherungsoptionen angezeigt. Normalerweise werden diese Optionen nicht benötigt. Klicken Sie auf **Weiter**.   
9. Auf der Seite **Zeitplan erstellen** stehen Ihnen zwei Optionen zur Verfügung. 
   - Klicken Sie auf **Weiter**, um einen manuellen Job zu erstellen, und fahren Sie mit der Ausführung Ihres neuen Jobs fort.
   - Klicken Sie auf **Hinzufügen**, um einen zeitbasierten Sicherungsjob zu planen. 
     1. Wählen Sie die Tage und die Uhrzeit für die Ausführung der Sicherungen aus.
     2. Wählen Sie das Aufbewahrungsschema aus. Weitere Informationen zu Aufbewahrungsschemas finden Sie [hier](evault-backup-faq.html).
     3. Nachdem Sie den Sicherungszeitplan konfiguriert haben, klicken Sie auf **OK**, um ihn zu speichern. Ihr geplanter Job wird zur Liste der geplanten Jobs hinzugefügt. 
10. Wählen Sie eine Vault für Ihren Sicherungsjob aus und klicken Sie auf **Änderungen speichern**.


## BMR-Sicherungsjob ausführen

  - Falls Sie einen zeitbasierten Sicherungsjob geplant haben, sind keine weiteren Schritte erforderlich. Ihr Job wird wie geplant automatisch ausgeführt.
  - Falls Sie einen manuellen Job (ohne zeitbasierten Zeitplan) konfiguriert haben, können Sie ihn ausführen, indem Sie seine Zeile in der Jobliste auswählen und auf **Sicherung ausführen** klicken. <br/> Wie bei zeitbasierten Jobs können Sie auch hier das **Aufbewahrungsschema** und **erweiterte Sicherungsoptionen** auswählen. Nachdem Sie die Konfigurationseinstellungen festgelegt haben, klicken Sie auf **Sicherung starten**, um den Job zu starten.
