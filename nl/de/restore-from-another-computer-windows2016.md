---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---

# Job aus einem anderen Computer unter Windows 2016 wiederherstellen 

In diesem Artikel sind die Schritte beschrieben, die Sie ausführen müssen, um eine Dateiwiederherstellung mit Evault Windows Central Control unter Windows 2016 vorzunehmen.  

1. Aktivieren Sie die Fernsteuerung Ihres Servers über RDP.
2. Öffnen Sie CentralControl.
3. Klicken Sie mit der rechten Maustaste auf **Agent** und klicken Sie auf **Agentenkonfiguration**.
4. Entfernen Sie die aktuellen Vaulteinstellungen aus CentralControl, indem Sie den Eintrag auswählen und auf **Löschen** klicken.
5. Klicken Sie auf **Neu** und wählen Sie in der nächsten Anzeige die Option **Zuvor registrierten Computer erneut registrieren** aus. Klicken Sie auf **Weiter**.
6. Geben Sie die Netzadresse ein, klicken Sie auf **Hinzufügen** und klicken Sie dann auf **Weiter**.
7. Geben Sie die neuen Portwerte ein, klicken Sie auf **Hinzufügen** und klicken Sie dann auf **Weiter**.
8. Geben Sie in der Anzeige 'Verbindungseinstellungen' die gewünschte Anzahl der Sekunden/Minuten ein. 
9. Geben Sie in der Anzeige 'Authentifizierung' Ihre Berechtigungsnachweise ein und klicken Sie auf **Weiter**.
10. Im Fenster 'Registrierte Computer' wird nun der Hostname Ihres Servers angezeigt. Klicken Sie auf **Weiter**.
11.	Der Assistent für die Vaultkonfiguration hat hiermit alle Informationen von Ihnen erfasst. Klicken Sie auf **Fertigstellen**, um die Registrierung abzuschließen.
12. Bestätigen Sie bei der entsprechenden Eingabeaufforderung, dass Sie die erneute Registrierung fortsetzen wollen.
13. Klicken Sie nach Abschluss der Registrierung in der Menüleiste auf **Wiederherstellung**. 
9.	Wählen Sie die entsprechende Sicherungsgruppe aus und geben Sie das Verschlüsselungskennwort ein. Klicken Sie auf **Weiter**.
10.	Wählen Sie die Dateien aus, die Sie wiederherstellen wollen, wählen Sie die Standardoptionen aus und klicken Sie auf **Fertigstellen**. 
11.	Entfernen Sie nach Abschluss der Wiederherstellung die Vaultregistrierung und nehmen Sie eine erneute Registrierung mit den aktuellen Kontoinformationen für die Vault vor. 
