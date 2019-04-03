---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Verwendung mehrerer Vaults (Multi-Vaulting)
{: #multivault}

Bei der Verwendung mehrerer Vaults (Multi-Vaulting) kann ein Client eine Server-Verbindung zu mehreren Vaultpositionen herstellen. Eine solche Umgebung bietet Redundanz und die Gewissheit, dass Ihre Sicherungen selbst dann noch verfügbar sind, wenn einer Ihrer Standorte ausfällt.

**Wesentliche Punkte**

1. Mehrere Vaults können über dasselbe {{site.data.keyword.backup_notm}}-Portal verwaltet werden und werden auf dieselbe Weise behandelt. Der einzige Unterschied besteht darin, dass andere Auswahlmöglichkeiten für die Vault verfügbar sind.
2. Die Plug-in-Lizenzierung erfolgt auf Vaultbasis. Wenn Sie beispielsweise das Plug-in für MS SQL für eine Vaultinstanz in Washington DC erworben haben, kann diese Lizenz in der Vault 'Seattle' nicht verwendet werden.
3. Die neue Vault muss nach jedem Kauf manuell zum {{site.data.keyword.backup_notm}}-Portal hinzugefügt werden.



**Positionen von {{site.data.keyword.backup_notm}} Vault Director**

Multi-Vaulting steht über alle Rechenzentren hinweg zur Verfügung und es gibt keine geografische Einschränkung bei der Auswahl eines fernen Vaults. Wenn Vaults konfiguriert werden, werden alle konfigurierten Vaults in den Vaulteinstellungen angezeigt.

Die Sicherung auf fernen Positionen von Rechenzentren kann mehr Zeit in Anspruch nehmen, als die Sicherung in demselben Rechenzentrum, in dem sich auch ihr Server befindet.
{:note}

## Ferne Vault zu einem Konto hinzufügen

Sie müssen den neuen fernen Vault zum Konto hinzufügen, bevor eine neue Sicherungsposition im {{site.data.keyword.backup_notm}}-Portal hinzugefügt werden kann.
{:important}

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}){:new_window} an und klicken Sie oben links auf das **Menüsymbol**. Wählen Sie **Klassische Infrastruktur** aus.<br/>
   Alternativ können Sie sich am [{{site.data.keyword.slportal}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){:new_window} anmelden.
2. Klicken Sie auf **Geräte**.
3. Suchen Sie den Link für den betreffenden Server und klicken Sie auf den Link.
4. Klicken Sie unter **Gerätedetails** auf **Speicher**.
5. Blättern Sie nach dem Öffnen des Abschnitts 'Speicher' bis zu **{{site.data.keyword.backup_notm}}** und klicken Sie dann auf **Hinzufügen**.
6. Wählen Sie im Fenster **{{site.data.keyword.backup_notm}} bestellen** die ferne Vaultposition aus, indem Sie in der Pulldown-Liste auf den zugehörigen Eintrag klicken.
7. Wählen Sie die Größe des Speichers aus und klicken Sie auf **Weiter**.
8. Wählen Sie das Kontrollkästchen **Rahmenvereinbarung gelesen...** aus und klicken Sie auf **Bestellung aufgeben**.

Die neu bestellte Vault wird automatisch zum Konto hinzugefügt. Sollte dies nicht der Fall sein, bitten Sie den Vertrieb um Hilfe.

Nachdem Sie den Bestellprozess abgeschlossen haben, navigieren Sie zu **Speicher** > **Sicherung**, um die aufgelistete neue Vault anzuzeigen.

## Zusätzliche Vault zum {{site.data.keyword.backup_notm}}-Portal hinzufügen

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}){:new_window} an und klicken Sie oben links auf das **Menüsymbol**. Wählen Sie **Klassische Infrastruktur** aus.<br/>
   Alternativ können Sie sich am [{{site.data.keyword.slportal}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){:new_window} anmelden.
2. Klicken Sie auf **Speicher** > **Sicherung**, um die Server mit Backup-Service anzuzeigen.
3. Wählen Sie den Server aus, für den Sicherungen mit mehreren Vaults möglich sein sollen. Klicken Sie auf den nach rechts zeigenden Pfeil, um den Link zum {{site.data.keyword.backup_notm}}-Portal sichtbar zu machen.
4. Klicken Sie auf den Link zur **{{site.data.keyword.backup_notm}}-Portalanmeldung**, um den Portalclient in Ihrem Browser zu starten.

   Das {{site.data.keyword.backup_notm}}-Portal ist nur über {{site.data.keyword.BluVPN}} zugänglich.
   {:tip}
5. Klicken Sie im linken Navigationsbereich auf **Alle Agenten**.
6. Klicken Sie in der rechten oberen Ecke auf **Bearbeiten** und wählen Sie **Vaulteinstellungen** aus.
7. Klicken Sie im Fenster **Vaulteinstellungen** auf **Hinzufügen**.
8. Führen Sie im Fenster **Neue Vault** folgende Schritte aus.
  1. Wählen Sie im Menü 'Vaultprofil' die Option **Vaulteinstellungen eingeben** aus, um einen neuen Eintrag zu erstellen. Aktualisieren Sie den vorhandenen Eintrag nicht.
  2. Der Vaultname darf nicht mit dem Namen des anderen Vaults identisch sein. Versuchen Sie, das Tag `-2` am Ende des Namens hinzuzufügen. <br/>

     Das Feld für den Vault-Namen hat eine Begrenzung von 15 Zeichen.
     {:important}
  3. Tragen Sie in das Feld 'IP-Adresse' die Position von {{site.data.keyword.backup_notm}} Director ein. Beispiel: `ev-director301.service.softlayer.com` hat die IP-Adresse 10.1.114.46 und befindet sich in WDC.
  4. Geben Sie im Feld 'Berechtigungsnachweise' die Konto-ID, den {{site.data.keyword.backup_notm}}-Benutzernamen und das zugehörige Kennwort für den ausgewählten Vault ein.
  5. Klicken Sie auf **Änderungen speichern**.

Nach einigen Sekunden ist die neue Vault verwendbar. Falls Sie einen Verbindungsfehler empfangen, überprüfen Sie Ihre Einstellungen und wiederholen Sie die Aktion. Bedenken Sie, dass Sie beim Hinzufügen einer zusätzlichen Vault die Möglichkeit erhalten, ein zusätzliches Ziel für einen Job auszuwählen. Es werden nicht automatisch Jobs für beide Vaults ausgeführt. Sie müssen entsprechende Jobs konfigurieren, um die zusätzliche Vault nutzen zu können. Weitere Informationen finden Sie im [Lernprogramm 'Einführung'](/docs/infrastructure/Backup?topic=Backup-gettingstarted#getting-started).
