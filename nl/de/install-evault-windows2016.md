---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-05"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# EVault unter Windows 2016 konfigurieren

Gegenwärtig wird EVault WebCC unter Windows 2016 offiziell nicht unterstützt. Server, auf denen Windows 2016 ausgeführt wird, müssen die Software 'Windows CentralControl' verwenden.

## EVault Backup-Agenten installieren

1. Öffnen Sie auf dem Zielserver eine Browsersitzung und geben Sie die folgende URL ein, um die ausführbare Datei herunterzuladen:
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
2. Doppelklicken Sie auf die heruntergeladene Datei und klicken Sie im angezeigten Popup-Fenster auf **Ausführen**. 
3. Wählen Sie die Sprache für Ihre Installation aus und klicken Sie auf **OK**.
4. Wählen Sie den Installationstyp **Standard** aus. Klicken Sie auf **Weiter**.
5. Wählen Sie in der Anzeige 'Agenten beim Portal registrieren' die Option **Registrierung überspringen** aus. 
6. Klicken Sie auf **Weiter** und danach auf **Fertigstellen**.

## EVault-Software 'CentralControl' installieren

1. Öffnen Sie auf dem Zielserver eine Browsersitzung und geben Sie die folgende URL ein, um die ausführbare Datei herunterzuladen:

   ```
   http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. Doppelklicken Sie auf die heruntergeladene Datei und klicken Sie im angezeigten Popup-Fenster auf **Ausführen**. 
3. Befolgen Sie die Installationsschritte für eine Standardinstallation.

## CentralControl konfigurieren

Diese Task erfolgt durch eine Reihe von Interaktionen, während Sie bei dem Server angemeldet sind, der für den EVault Backup-Service bestimmt ist. 

1. Aktivieren Sie die Fernsteuerung Ihres Servers über RDP.
2. Starten Sie CentralControl.
3. Klicken Sie im Arbeitsbereich mit der rechten Maustaste auf **Agent** und wählen Sie die Option **Agentenkonfiguration** aus.
4. Klicken Sie auf **Neu**.
5. Wählen Sie **Als neuer Computer registrieren** aus und klicken Sie auf **Weiter**.
6. Geben Sie die Netzadresse ein, klicken Sie auf **Hinzufügen** und klicken Sie dann auf **Weiter**.
7. Geben Sie die neuen Portwerte ein, klicken Sie auf **Hinzufügen** und klicken Sie dann auf **Weiter**.
8. Geben Sie in der Anzeige 'Verbindungseinstellungen' die gewünschte Anzahl der Sekunden/Minuten ein. 
9. Geben Sie in der Anzeige 'Authentifizierung' Ihre Berechtigungsnachweise ein und klicken Sie auf **Weiter**.
10. Im Fenster 'Registrierte Computer' wird nun der Hostname Ihres Servers angezeigt. Klicken Sie auf **Weiter**.
11.	Der Assistent für die Vaultkonfiguration hat hiermit alle Informationen von Ihnen erfasst. Klicken Sie auf **Fertigstellen**, um die Registrierung abzuschließen.


