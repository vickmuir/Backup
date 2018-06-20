---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Multi-Vaulting

Beim Multi-Vaulting kann ein Client/Server eine Verbindung zu mehreren EVault-Positionen herstellen. Eine solche Umgebung bietet Redundanz; Sie können somit unbesorgt sein, weil Sicherungen selbst dann verfügbar sind, wenn einer der Standorte ausfällt. 

## Schlüsselpunkte

1. Mehrere EVault-Instanzen können über dieselbe WebCC-Instanz verwaltet und auf gleiche Weise behandelt werden. Der einzige Unterschied besteht darin, dass andere Auswahlmöglichkeiten für die Vault verfügbar sind.
2. Die Plug-in-Lizenzierung erfolgt vaultabhängig; falls Sie beispielsweise eine EVault-Instanz für das Plug-in für MS SQL in Washington DC lizenziert haben, kann diese Lizenz in der Vault 'Seattle' nicht verwendet werden.
3. Die neue EVault-Lizenz muss nach jeder Bestellung manuell zu WebCC hinzugefügt werden.

## Ferne Vault zu einem Konto hinzufügen

Sie müssen die neue ferne EVault-Speichervault zum Konto hinzufügen, bevor Sie in WebCC eine neue Sicherungsposition hinzufügen können. 

1. Melden Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an.
2. Klicken Sie auf **Geräte**.
3. Suchen Sie den Link für den betreffenden Server und klicken Sie auf den Link.
4. Klicken Sie unter **Gerätedetails** auf **Speicher**.
5. Blättern Sie nach dem Öffnen des Abschnitts 'Speicher' bis zu **EVault** vor und klicken Sie auf **Hinzufügen**.
6. Wählen Sie im aufgerufenen Dialogfenster **EVault bestellen** die ferne Vaultposition aus, indem Sie auf das Pulldown-Menü klicken.
7. Wählen Sie die Größe des Speichervolumens aus und klicken Sie auf **Weiter**.
8. Wählen Sie das Kontrollkästchen **Rahmenvereinbarung gelesen...** aus und klicken Sie auf **Bestellung aufgeben**.

Die neu bestellte Vault wird automatisch zum Konto hinzugefügt. Sollte dies nicht der Fall sein, bitten Sie den Vertrieb um Hilfe.
Nachdem Sie den Bestellprozess abgeschlossen haben, navigieren Sie zu **Speicher** > **Sicherung**, um die aufgelistete neue Vault anzuzeigen.

## Zusätzliche Vault zu WebCC hinzufügen

1. Melden Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an und klicken Sie im Hauptmenü auf **Speicher** > **Sicherung**, um die Server mit EVault Backup-Service anzuzeigen. 
2. Wählen Sie den Server aus, auf dem sich die wiederherzustellenden Dateien befinden. Klicken Sie auf den nach rechts zeigenden Erweiterungspfeil, um den Link zu WebCC sichtbar zu machen.
3. Klicken Sie auf den Anmeldelink für WebCC, um den WebCC-Client in Ihrem Browser zu starten.<br/>**Hinweis**: WebCC ist nur über {{site.data.keyword.BluVPN}} zugänglich ist.
4. Klicken Sie im linken Navigationsbereich auf **Alle Agenten**.
5. Klicken Sie in der rechten oberen Ecke auf **Bearbeiten** und wählen Sie **Vaulteinstellungen** aus.
6. Klicken Sie im Fenster 'Vaulteinstellungen' auf **Hinzufügen**.
7. Führen Sie im Dialogfenster **Neue Vault** Folgendes aus:
  1. Wählen Sie in der Dropdown-Liste 'Vaultprofil' den Eintrag **Vaulteinstellungen eingeben** aus, um einen neuen Eintrag zu erstellen. Aktualisieren Sie nicht den vorhandenen Eintrag.
  2. Der Vaultname darf nicht mit dem Namen der anderen Vault identisch sein. Es empfiehlt sich, die Kennzeichnung '-2' am Ende des Namens hinzuzufügen.<br/> **Hinweis**: Die Länge dieses Feldes ist auf 15 Zeichen begrenzt.
  3. Im IP-Adressfeld sollten Standortinformationen für EVault Director angegeben werden. Beispielsweise hat 'ev-director301.service.softlayer.com' die IP-Adresse 10.1.114.46 und befindet sich in Washington DC. Andere Standorte und Adressen für EVault Director sind am Ende der Seite aufgeführt.
  4. Unter dem Feld 'Berechtigungsnachweise' ist das Konto die Konto-ID des Kunden, der Benutzername ist der EVault-Benutzername für die ausgewählte Vault und das Kennwort ist das Kennwort für die ausgewählte Vault.
  5. Klicken Sie auf **Änderungen speichern**.

Nach einigen Sekunden ist die neue Vault verwendbar. Falls Sie einen Verbindungsfehler empfangen, überprüfen Sie Ihre Einstellungen und wiederholen Sie die Aktion. Denken Sie daran, dass Sie beim Hinzufügen einer zusätzlichen Vault lediglich die Möglichkeit erhalten, ein zusätzliches Ziel für einen Job auszuwählen und Jobs nicht automatisch für beide Vaults ausgeführt werden. Sie müssen Jobs entsprechend konfigurieren, damit sie die zusätzliche Vault nutzen. Anweisungen hierzu erhalten Sie im [Lernprogramm 'Einführung'](index.html#getting-started-with-evault-backup-services).

## Standorte für EVault Director

Das Multi-Vaulting ist in allen Rechenzentren verfügbar und bei der Auswahl einer fernen Vault bestehen keine geografischen Einschränkungen. Wenn Vaults durch die Schritte in diesem Dokument konfiguriert werden, werden alle konfigurierten Vaults in den Vaulteinstellungen angezeigt.

**Hinweis**: Die Sicherung an fernen Rechenzentrenstandorten kann länger dauern als Sicherungen in demjenigen Rechenzentrum, in dem sich Ihr Server befindet.

