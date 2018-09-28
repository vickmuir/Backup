---

copyright:
  years: 1994, 2018
lastupdated: "2018-08-15"

---
{:new_window: target="_blank"}

# Multi-Vaulting

Beim Multi-Vaulting kann ein Client/Server eine Verbindung zu mehreren EVault-Positionen herstellen. Eine solche Umgebung bietet Redundanz und die Gewissheit, dass Ihre Sicherungen selbst dann noch verfügbar sind, wenn einer Ihrer Standorte ausfällt. 

**Schlüsselpunkte**

1. Mehrere EVault-Instanzen können über dieselbe WebCC-Instanz verwaltet und auf die gleiche Weise behandelt werden. Der einzige Unterschied besteht darin, dass andere Auswahlmöglichkeiten für die Vault verfügbar sind.
2. Die Plug-in-Lizenzierung erfolgt auf Vaultbasis. Wenn Sie beispielsweise das Plug-in für MS SQL für eine Vaultinstanz in Washington DC erworben haben, kann diese Lizenz in der Vault 'Seattle' nicht verwendet werden.
3. Die neue Vault muss nach jedem Kauf manuell zu WebCC hinzugefügt werden.

**Standorte für EVault Director**

Das Multi-Vaulting ist in allen Rechenzentren verfügbar und bei der Auswahl einer fernen Vault bestehen keine geografischen Einschränkungen. Wenn Vaults anhand der Schritte in diesem Dokument konfiguriert werden, werden alle konfigurierten Vaults in den Vaulteinstellungen angezeigt.

>**Hinweis** - Die Sicherung an fernen Rechenzentrumsstandorten kann länger dauern als Sicherungen in demjenigen Rechenzentrum, in dem sich Ihr Server befindet.

## Ferne Vault zu einem Konto hinzufügen

Sie müssen die neue ferne EVault-Speichervault zum Konto hinzufügen, bevor Sie in WebCC eine neue Sicherungsposition hinzufügen können. 

1. Melden Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an.
2. Klicken Sie auf **Geräte**.
3. Suchen Sie den Link für den betreffenden Server und klicken Sie auf den Link.
4. Klicken Sie unter **Gerätedetails** auf **Speicher**.
5. Blättern Sie nach dem Öffnen des Abschnitts 'Speicher' bis zu **EVault** vor und klicken Sie dann auf **Hinzufügen**.
6. Wählen Sie im Fenster **EVault bestellen** die ferne Vaultposition aus, indem Sie in der Pulldown-Liste auf den entsprechenden Eintrag klicken.
7. Wählen Sie die Größe des Speichervolumens aus und klicken Sie auf **Weiter**.
8. Wählen Sie das Kontrollkästchen **Rahmenvereinbarung gelesen...** aus und klicken Sie auf **Bestellung aufgeben**.

Die neu bestellte Vault wird automatisch zum Konto hinzugefügt. Sollte dies nicht der Fall sein, bitten Sie den Vertrieb um Hilfe.
Nachdem Sie den Bestellprozess abgeschlossen haben, navigieren Sie zu **Speicher** > **Sicherung**, um die aufgelistete neue Vault anzuzeigen.

## Zusätzliche Vault zu WebCC hinzufügen

1. Melden Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an und klicken Sie im Hauptmenü auf **Speicher** > **Sicherung**, um die Server mit EVault Backup-Service anzuzeigen. 
2. Wählen Sie den Server aus, für den Sicherungen mit mehreren Vaults möglich sein sollen. Klicken Sie auf den nach rechts zeigenden Pfeil, um den Link zu WebCC sichtbar zu machen.
3. Klicken Sie auf den Link **WebCC-Anmeldung**, um den WebCC-Client in Ihrem Browser zu starten.
   >**Hinweis** - Auf WebCC kann nur über {{site.data.keyword.BluVPN}} zugegriffen werden.
4. Klicken Sie im linken Navigationsbereich auf **Alle Agenten**.
5. Klicken Sie in der rechten oberen Ecke auf **Bearbeiten** und wählen Sie **Vaulteinstellungen** aus.
6. Klicken Sie im Fenster **Vaulteinstellungen** auf **Hinzufügen**.
7. Führen Sie im Fenster **Neue Vault** folgende Schritte aus.
  1. Wählen Sie im Menü 'Vaultprofil' die Option **Vaulteinstellungen eingeben** aus, um einen neuen Eintrag zu erstellen. Aktualisieren Sie den vorhandenen Eintrag nicht.
  2. Der Vaultname darf nicht mit dem Namen des anderen Vaults identisch sein. Es empfiehlt sich, die Kennzeichnung '-2' am Ende des Namens hinzuzufügen. <br/> 
     >**Hinweis** - Die Länge dieses Feldes ist auf 15 Zeichen begrenzt.
  3. Das Feld für die IP-Adresse wird mit den EVault Director-Positionsinformationen gefüllt. Beispiel: `ev-director301.service.softlayer.com` hat die IP-Adresse 10.1.114.46 und befindet sich in WDC.
  4. Geben Sie im Feld 'Berechtigungsnachweise' die Konto-ID, den EVault-Benutzernamen für die ausgewählte Vault und das Kennwort für die ausgewählte Vault ein.
  5. Klicken Sie auf **Änderungen speichern**.

Nach einigen Sekunden ist die neue Vault verwendbar. Falls Sie einen Verbindungsfehler empfangen, überprüfen Sie Ihre Einstellungen und wiederholen Sie die Aktion. Bedenken Sie, dass Sie beim Hinzufügen einer zusätzlichen Vault lediglich die Möglichkeit erhalten, ein zusätzliches Ziel für einen Job auszuwählen. Es werden nicht automatisch Jobs für beide Vaults ausgeführt. Sie müssen entsprechende Jobs konfigurieren, um die zusätzliche Vault nutzen zu können. Anweisungen hierzu erhalten Sie im [Lernprogramm 'Einführung'](index.html#getting-started-with-evault-backup-services).
