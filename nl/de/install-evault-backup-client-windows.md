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

# EVault Backup-Client unter Windows installieren

Die Installation des EVault Backup-Clients unter Windows erfolgt durch eine Reihe von Interaktionen, während Sie bei dem Server angemeldet sind, der für den EVault Backup-Service bestimmt ist. Führen Sie die folgenden Schritte aus, um den EVault Backup-Client unter Windows zu installieren.

**Hinweis**: Windows 2016 wird gegenwärtig nicht unterstützt.

## Beim Zielgeräteserver anmelden

1. Melden Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an und wählen Sie im Hauptmenü die Optionen **Geräte** > **Geräteliste** aus, um die Liste der verfügbaren Servereinheiten anzuzeigen.
2. Suchen Sie nach dem Gerät, für das Sie den EVault-Service gekauft haben, und notieren Sie sich seine öffentliche IP-Adresse. 
3. Klicken Sie auf den nach rechts zeigenden Erweiterungspfeil, um zusätzliche Informationen zum Gerät sichtbar zu machen, inklusive Benutzername und Kennwort. Falls das Kennwort nicht angezeigt wird, klicken Sie auf das Kontrollkästchen **Kennwort anzeigen**, damit das Kennwort sichtbar wird.  
4. Melden Sie sich beim Zielgerät unter Verwendung einer Remote-Desktop-Verbindung an.

## EVault-Client herunterladen

1. Öffnen Sie auf dem Zielserver eine Browsersitzung und geben Sie die folgende URL ein, um die ausführbare Datei für den EVault Backup-Client herunterzuladen. <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}
  
2. Doppelklicken Sie auf die heruntergeladene Datei und klicken Sie im angezeigten Popup-Fenster auf **Ausführen**. 


## EVault-Agenten installieren und registrieren
 
1. Geben Sie die Netzadresse ein:<br />
  ```
  ev-webcc01.service.softlayer.com
  ```
  {: pre}
  
2. Geben Sie im Feld **Benutzername** den Benutzernamen für EVault Backup ein. 
3. Geben Sie im Feld **Kennwort** das Kennwort für EVault Backup ein. 
6. Klicken Sie auf **Weiter**. 
7. Klicken Sie auf **Installieren**, um die Installation auszuführen.

## Nächste Schritte

Melden Sie sich bei WebCC an, um Ihre Sicherungsagenten zu konfigurieren und zu verwalten. Anweisungen erhalten Sie im [Lernprogramm 'Einführung'](index.html#configuring-evault-agent-in-webcc).
