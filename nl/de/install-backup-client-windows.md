---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Sicherungsclient unter Windows installieren

Die Installation des {{site.data.keyword.backup_full}}-Clients unter Windows erfolgt durch eine Reihe von Interaktionen auf dem Server, der für den {{site.data.keyword.backup_notm}}-Service vorgesehen ist.

Weitere Informationen zu Sicherungen für Windows 2016-Server finden Sie unter [{{site.data.keyword.backup_notm}} unter Windows 2016 konfigurieren](install-backup-client-windows2016.html).
{:tip}

## Beim Zielgeräteserver anmelden

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}/catalog/){:new_window} an und klicken Sie oben links auf das **Menüsymbol**. Wählen Sie **Klassische Infrastruktur** aus. <br/>
   Alternativ können Sie sich am [{{site.data.keyword.slportal}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){:new_window} anmelden.
2. Wählen Sie im Hauptmenü **Geräte** > **Geräteliste** aus, um eine Liste verfügbarer Server anzuzeigen.
3. Suchen Sie das Gerät, für das Sie den {{site.data.keyword.backup_notm}}-Service gekauft haben, und notieren Sie die zugehörige öffentliche IP-Adresse.
4. Klicken Sie auf den nach rechts zeigenden Pfeil, um zusätzliche Informationen zum Gerät (einschließlich Benutzername und Kennwort) anzuzeigen. Falls das Kennwort nicht angezeigt wird, klicken Sie auf **Kennwort anzeigen**, damit das Kennwort sichtbar wird.
5. Melden Sie sich beim Zielgerät unter Verwendung einer Remote-Desktop-Verbindung an.

## Backup-Client herunterladen

1. Öffnen Sie auf dem Zielserver eine Browsersitzung und geben Sie die folgende URL ein, um die ausführbare Datei für den {{site.data.keyword.backup_notm}}-Client herunterzuladen. <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}

2. Doppelklicken Sie auf die heruntergeladene Datei.
3. Klicken Sie auf **Ausführen**.


## Sicherungsagenten installieren und registrieren

1. Geben Sie die Netzadresse ein: <br />
  ```
  https://ev-webcc01.service.softlayer.com
  ```
  {: pre}

2. Geben Sie den Benutzernamen im Feld **Benutzername** ein.
3. Geben Sie das Kennwort im Feld **Kennwort** ein.
6. Klicken Sie auf **Weiter**.
7. Klicken Sie auf **Installieren**, um die Installation auszuführen.

## Sicherungsagenten konfigurieren

Melden Sie sich beim {{site.data.keyword.backup_notm}}-Portal an, um Ihre Sicherungsagenten zu konfigurieren und zu verwalten. Weitere Informationen enthält das [Lernprogramm - Einführung](index.html#configuring-the-backup-agent-and-the-backup-schedule).
