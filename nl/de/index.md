---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-28"

keywords: EVault, Carbonite, IBM Cloud Backup, Enterprise Backup

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Bereitstellung von {{site.data.keyword.backup_notm}}
{: #ordering}

Sie können den {{site.data.keyword.backup_notm}}-Service auf zwei Arten erwerben.

- [Sicherungen bei der Bestellung eines Servers kaufen](#purchasingwithserver).
- [Sicherungen als Upgrade kaufen](#purchasingasupgrade).

Weitere Informationen zur Preisgestaltung finden Sie unter [{{site.data.keyword.backup_notm}}-Speicher ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/cloud/backup-and-restore){:new_window} und [{{site.data.keyword.backup_notm}} on IBM Cloud ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/cloud/backup/pricing){:new_window}.

## {{site.data.keyword.backup_notm}} bei der Bestellung eines Servers kaufen
{: #purchasingwithserver}

1. Melden Sie sich beim [IBM Cloud-Katalog ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/catalog){:new_window} oder beim [{{site.data.keyword.slportal}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){:new_window} an.
2. Bestellen Sie ein Bare Metal Server-System pro Monat. Weitere Informationen zum Bestellen von Bare-Metal-Servern finden Sie im Abschnitt zum Thema [Angepasste Bare-Metal-Server erstellen](https://{DomainName}/docs/bare-metal/baremetal-provision.html){:new_window}.
   1. Wählen Sie die Menge und die Abrechnungsoption aus. Geben Sie den Host- und Domänenname ein. Sie können jeden gewünschten Host- und Domänennamen auswählen.

      Der {{site.data.keyword.backup_notm}}-Service ist nicht verfügbar, wenn Sie einen Server bestellen, der auf Stundenbasis abgerechnet wird. Der Service kann jedoch später als Upgrade hinzugefügt werden.
      {:tip}
   2. Wählen Sie die Position aus.
   3. Wählen Sie die Serverkonfiguration und einen Betriebssystemimagetyp aus. Sie können auch mehrere Add-ons auswählen.
   4. Klicken Sie im Abschnitt **Speicherplatten** auf **Add-ons** und wählen Sie **{{site.data.keyword.backup_notm}}** aus. Wählen Sie die Option aus, die Ihren Anforderungen am besten entspricht.
   5. Wählen Sie unter **Netzschnittstelle** die Uplink-Port-Geschwindigkeit und alle gewünschten Add-ons aus.
3. Überprüfen Sie auf der rechten Seite Ihre Bestellübersicht.
4. Danach markieren Sie das Kontrollkästchen **Die im Folgenden aufgeführten Servicevereinbarungen anderer Anbieter habe ich gelesen und stimme ihnen zu:**.
5. Klicken Sie auf **Bereitstellung**. Sie werden zu einer Anzeige geführt, der Sie die Bestellnummer für Ihre Bereitstellung entnehmen können. Sie können die Anzeige ausdrucken, weil es sich hierbei auch um die Bestätigung des Bestelleingangs für Ihre Bereitstellung handelt.

   Sie können diese Bestellung auch ohne Einkauf speichern, indem Sie auf **Als Angebot speichern** klicken.
   {:tip}

An Ihren Administrator wird eine Reihe von E-Mails gesendet, nämlich zur Bestätigung der Bereitstellungsbestellung, zur Genehmigung und Verarbeitung der Bereitstellungsbestellung sowie zur Fertigstellung der Bereitstellung. Die E-Mail zur Fertigstellung der Bereitstellung enthält einen Link zu Ihrer Seite *Gerätedetails*, auf die Sie zugreifen können, nachdem Sie sich bei {{site.data.keyword.cloud_notm}} angemeldet haben. Sie können sich auch direkt beim {{site.data.keyword.slportal}} anmelden.

### {{site.data.keyword.backup_notm}}-Einkauf bestätigen
1. Klicken Sie in der [{{site.data.keyword.cloud_notm}}-Konsole ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/){:new_window} oben links auf das **Menüssymbol**. Wählen Sie **Klassische Infrastruktur** aus.</br>
   Alternativ können Sie sich am [{{site.data.keyword.slportal}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){:new_window} anmelden.
2. Klicken Sie auf **Gerät** > **Geräteliste**.
2. Suchen Sie nach dem neuen Server, den Sie bestellt haben.
  - Wenn das Uhrsymbol neben der URL angezeigt wird, müssen Sie warten, bevor Sie mit der Kaufbestätigung für {{site.data.keyword.backup_notm}} fortfahren können. Sie können die Seite aktualisieren und so einen aktualisierten Status Ihres neuen Servers anzeigen. Wenn das Uhrsymbol nicht mehr angezeigt wird, können Sie mit den nächsten Schritten fortfahren, um den Kauf des {{site.data.keyword.backup_notm}}-Service zu bestätigen.
  - Wenn das Uhrsymbol nicht mehr für Ihren Server angezeigt wird, klicken Sie auf den Link (die URL des Servers), um auf die Seite **Gerätedetails** zu wechseln.
3. Klicken Sie auf die Registerkarte **Speicher**, um die {{site.data.keyword.backup_notm}}-Informationen anzuzeigen.
4. Überprüfen Sie den Abschnitt {{site.data.keyword.backup_notm}} und vergewissern Sie sich, dass die Größe angezeigt wird, die Sie während des Kaufvorgangs ausgewählt haben.

## {{site.data.keyword.backup_notm}} als Upgrade kaufen
{: #purchasingasupgrade}

### Wählen Sie einen Server aus, auf dem Sie {{site.data.keyword.backup_notm}} installieren möchten.

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}-Konsole ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}){:new_window} an und klicken Sie oben links auf das **Menüsymbol**. Wählen Sie **Klassische Infrastruktur** aus.</br>
   Alternativ können Sie sich am [{{site.data.keyword.slportal}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){:new_window} anmelden.
2. Wählen Sie im Hauptmenü die Optionen **Geräte** > **Geräteliste** aus. Suchen Sie nach dem Gerät, für das Sie den Sicherungsservice hinzufügen möchten.
3. Klicken Sie auf den Gerätenamen, um zu der Seite **Gerätedetails** zu gelangen.

### {{site.data.keyword.backup_notm}}-Service hinzufügen (kaufen)
1. Klicken Sie auf die Registerkarte **Speicher** und blättern Sie nach unten zum Abschnitt {{site.data.keyword.backup_notm}}.
2. Klicken Sie auf den Link **Hinzufügen**.
3. Wählen Sie im Fenster einen Standort und anschließend eine Größe aus.
4. Wählen Sie den Zahlungstyp aus und klicken Sie dann auf **Weiter**.
5. Geben Sie (falls vorhanden) den **Werbeaktionscode** ein und klicken Sie auf **Neu berechnen**.
6. Prüfen Sie Ihre Bestellung und klicken Sie auf den Link, um die Bedingungen zu lesen.
7. Klicken Sie auf das Kontrollkästchen, wenn Sie den Bedingungen zustimmen.
7. Klicken Sie auf **Bestellung aufgeben**.

### Kauf des {{site.data.keyword.backup_notm}}-Upgrade bestätigen
1. Aktualisieren Sie die Seite **Gerätedetails** und achten Sie darauf, dass die Registerkarte **Speicher** ausgewählt ist.
2. Überprüfen Sie den Abschnitt {{site.data.keyword.backup_notm}} und vergewissern Sie sich, dass die Größe angezeigt wird, die Sie während des Kaufvorgangs ausgewählt haben.

   Falls für die Größe des Speichers weiterhin die Kapazität 0 angezeigt wird, müssen Sie die Seite möglicherweise ein zweites Mal aktualisieren.
   {:tip}
