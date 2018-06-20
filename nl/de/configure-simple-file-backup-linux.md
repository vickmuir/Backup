---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-14"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Einfache Sicherung auf Dateiebene unter Linux konfigurieren

Nachdem Sie Ihren EVault-Service bestellt haben und der Agent auf dem Server installiert wurde, können Sie mit dem Erstellen von Sicherungen Ihrer Daten beginnen. In diesem Artikel sind die Schritte beschrieben, mit denen Sie den Agenten sowie den Aufbewahrungszeitplan konfigurieren und Ihren ersten Sicherungsjob starten.

## WebCC starten

1. Melden Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an und klicken Sie im Hauptmenü auf **Speicher** > **Sicherung**, um die Server mit EVault Backup-Service anzuzeigen. 
2. Wählen Sie den Server aus, auf dem sich die zu sichernden Dateien befinden. Klicken Sie auf den nach rechts zeigenden Erweiterungspfeil, um den Link zu WebCC sichtbar zu machen.
3. Starten Sie Ihre VPN-Verbindung, um Zugang zum privaten IBM Netz zu erhalten.
4. Klicken Sie auf den Anmeldelink für WebCC, um den WebCC-Client in Ihrem Browser zu starten.<br/>
  **Hinweis**: Falls WebCC nicht gestartet wird, liegt möglicherweise ein Problem mit Ihrer VPN-Verbindung vor. Außerdem wird möglicherweise die Nachricht ausgegeben, dass das Formular, das Sie senden, nicht sicher ist. Dies entspricht dem erwarteten Verhalten; fahren Sie mit dem Senden des Formulars fort.
  
## Sicherungsjob konfigurieren

1. Klicken Sie auf der linken Seite im Navigationsbereich auf **Alle Agenten**, um die aktuellen EVault-Agenten anzuzeigen.
2. Klicken Sie auf **Neuer Agent, der konfiguriert werden soll**.
3. Geben Sie einen Jobnamen und eine Jobbeschreibung für den Job ein, den Sie konfigurieren bzw. erstellen.
4. Wählen Sie bei **Sicherungsquellentyp** im Dropdown-Menü den Typ des Dateisystems aus, aus dem die Sicherung ausgeführt werden soll.
5. Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen. 
6. Navigieren Sie im Fenster **Datendateien** zu den Dateien und Verzeichnissen, die Sie in Ihre Sicherung einbeziehen wollen, indem Sie auf die Zeichen **+** und **-** neben den Ordnersymbolen klicken.
7. Wählen Sie die Kontrollkästchen neben den Dateien und Verzeichnissen aus, die Sie einbeziehen wollen, und klicken Sie anschließend auf **Einschließen**, um Ihre Auswahl zu speichern.
8. Sie können Ihre Auswahl mit dem aufgerufenen Popup-Fenster weiter filtern oder auf **OK** klicken, um die getroffene Auswahl unverändert zu verwenden.<br /> Nachdem Sie Ihre Datei- und Verzeichnisauswahl einbezogen haben, werden Ihre ausgewählten Dateien und Verzeichnisse im Fenster **Sicherungsgruppe** rechts in der Anzeige angezeigt. Sie können die Schritte 6 bis 8 wiederholen, um weitere Dateien hinzuzufügen oder um bereits hinzugefügte Dateien (mithilfe der Schaltfläche **Ausschließen**) zu entfernen. Mit der Schaltfläche **Entfernen** können Sie außerdem jede Position im Fenster **Sicherungsgruppe** löschen. Sobald Ihre Sicherungsgruppe wie von Ihnen gewünscht konfiguriert ist, klicken Sie auf **Weiter**, um fortzufahren.
9. Wählen Sie den gewünschten Verschlüsselungstyp aus. 
  - Wählen Sie **Ohne** aus, wenn Ihre Sicherung nicht verschlüsselt werden soll.   
  - Falls Ihre Sicherung verschlüsselt werden soll, wählen Sie **AES 256-Bit** aus und geben Sie in den Feldern 'Kennwort' und 'Kennwort überprüfen' ein Kennwort ein. Auf Wunsch können Sie einen Kennworthinweis hinzufügen.<br/> **Hinweis**: Sie benötigen dieses Kennwort, um Dateien aus der Sicherung wiederherzustellen. Ein vergessenes Kennwort kann ebensowenig wiederhergestellt werden wie eine verschlüsselte Sicherung, deren Kennwort nicht bekannt ist.   
10. Unter **Erweiterte Optionen** sind die folgenden Optionen verfügbar:
  - **Aufbewahrung**: Diese Option hilft Ihnen bei der Verwaltung Ihrer Datennutzung. Die Aufbewahrungsdauer legt fest, wie lange Ihre Sicherung aufbewahrt wird. Nach Ablauf der Aufbewahrungsdauer wird die Sicherung automatisch gelöscht. Die integrierten Auswahlmöglichkeiten sind 'Täglich', 'Wöchentlich' und 'Monatlich'.
  - **Komprimierung**: Mit dieser Option kann der Umfang der Kapazität reduziert werden, die für die Speicherung von Sicherungen verwendet wird.
Die Option 'Zum Schreiben geöffnete Sicherungsdateien' ermöglicht die Sicherung von Dateien auch dann, wenn die Dateien bei Ausführung des Sicherungsjobs gerade von einer Anwendung geöffnet sind.
  - **Protokolldatei erstellen**: Mit dieser Option können Sie den Inhalt und die Aufbewahrung von Protokolldateien erstellen und verwalten, die während des Sicherungsprozesses generiert werden. 
  - **Nur eine Instanz aller ausgewählten Dateien mit fester Verbindung sichern**: Diese Option ist nur für UNIX-Systeme maßgeblich. Falls Sie feste Verbindungen verwenden, um mehrere Dateinamen für bestimmten Inhalt zu erstellen, bewirkt diese Option, dass nur eine einzige Kopie des Inhalts gesichert wird. Bei einer Wiederherstellung werden alle festen Verbindungen wiederhergestellt. Diese Option macht einen Vorabsuchlauf durch die Dateiauswahl erforderlich, was erheblich Zeit und Speicher beanspruchen kann.
11. Nachdem Sie Ihre Auswahl für die Verschlüsselung getroffen haben, klicken Sie auf **Weiter**, um zur Anzeige **Zeitplan erstellen** zu wechseln.   
12. Klicken Sie auf der Seite 'Zeitplan erstellen' auf **Hinzufügen**, um einen zeitbasierten Sicherungsjob zu planen, oder klicken Sie auf **Weiter**, um einen manuellen Job zu erstellen.
  - Falls Sie einen manuellen Job erstellen wollen, fahren Sie mit Schritt 15 fort.
  - Falls Sie einen zeitbasierten Job planen wollen, wählen Sie die Tage und die Uhrzeit für die Ausführung der Sicherungen aus.
  - Wählen Sie das Aufbewahrungsschema aus. Weitere Informationen zu Aufbewahrungsschemas finden Sie [hier](evault-backup-faq.html#how-do-the-retention-schemes-work-).
  - Klicken Sie auf **Erweiterte Zeitplanoptionen**, um bei Bedarf zusätzliche Konfigurationseinstellungen anzuzeigen. Durch Auswahl von 'Verzögerung verwenden' können Sie verhindern, dass umfangreiche Sicherungen zu Zeiten mit einer hohen Netzauslastung ausgeführt werden. Wenn die Verzögerung aktiviert ist, sichert der Sicherungsjob keine neuen Daten nach dem angegebenen Zeitraum und schreibt die Sicherungsgruppe in der Vault fest, auch wenn einige Daten im Job nicht gesichert wurden. Änderungen an zuvor gesicherten Daten werden unabhängig vom angegebenen Zeitraum gesichert.<br/> Wenn der Job erneut ausgeführt wird, prüft der Agent die zuvor gesicherten Daten auf Änderungen, sichert diese Änderungen und sichert anschließend die übrigen Daten. Falls ein Sicherungsjob verzögert wird, während ein Element (z. B. Datei, Datenbank, Datenträger, vSphere VMDK oder Hyper-V VM) gesichert wird, ist die Sicherung für dieses Element unvollständig und Daten aus dem Element können nicht wiederhergestellt werden. Elemente, die im Job vor seiner Verzögerung vollständig gesichert wurden, können Sie jedoch wiederherstellen.
13. Nachdem Sie den Sicherungszeitplan konfiguriert haben, klicken Sie auf **OK**, um ihn zu speichern. Ihr geplanter Job wird zur Liste der geplanten Jobs hinzugefügt. 
  - Sie können Schritt 12 wiederholen, um weitere Sicherungen zu planen. 
  - Wenn Sie einen vorhanden Sicherungsjob ändern möchten, wählen Sie den Job aus, indem Sie auf seine Zeile klicken, klicken Sie anschließend auf **Bearbeiten** und nehmen Sie die Änderungen vor.
14. Wählen Sie eine Vault für Ihren Sicherungsjob aus und klicken Sie auf **Änderungen speichern**.
15. Führen Sie einen Sicherungsjob aus.
  - Falls Sie einen zeitbasierten Sicherungsjob geplant haben, sind keine weiteren Schritte erforderlich. Ihr Job wird wie geplant automatisch ausgeführt.
  - Falls Sie einen manuellen Job (also ohne zeitbasierten Zeitplan) konfiguriert haben, können Sie ihn ausführen, indem Sie seine Zeile in der Jobliste auswählen und auf **Sicherung ausführen** klicken. <br/> Wie bei zeitbasierten Jobs können Sie auch hier das Aufbewahrungsschema und erweiterte Optionen für die Sicherung auswählen. Nachdem Sie die Konfigurationseinstellungen festgelegt haben, klicken Sie auf **Sicherung starten**, um den Job zu starten.
