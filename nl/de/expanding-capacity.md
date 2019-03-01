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


# Vault-Kapazität erhöhen
{: #expandcapacity}

Die aktuellen Benutzer von {{site.data.keyword.BluSoftlayer_full}} können ihre Vault auf bis zu 4000 GB vergrößern. Dazu müssen sie keine Duplikate erstellen und die Daten auch nicht manuell auf einen größeren Datenträger migrieren. Der Prozess zur Erhöhung des Grenzwerts verursacht keinen Ausfall oder keinen Verlust des Zugriffs.

## Erhöhung anfordern

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}/){:new_window} an und klicken Sie auf das **Menüsymbol** links oben. Wählen Sie **Klassische Infrastruktur** aus.<br/>
   Alternativ können Sie sich am [{{site.data.keyword.slportal}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){:new_window} anmelden.
2. Klicken Sie auf **Speicher** > **Sicherung**, um die Server mit Backup-Service anzuzeigen.
3. Wählen Sie die Vault aus, die Sie erweitern möchten.
4. Klicken Sie auf **Aktionen** und wählen Sie **{{site.data.keyword.backup_notm}} ändern** aus.
5. Wählen Sie in der nächsten Anzeige die neue Größe aus und klicken Sie auf **Upgrade**.

## Abrechnung

Die Abrechnung für den Datenträger wird automatisch aktualisiert, um die anteilmäßige Differenz des neuen Preises zum aktuellen Abrechnungszyklus hinzuzufügen. Anschließend wird der vollständige neue Betrag im nächsten Abrechnungszyklus berechnet.

Mit dem gleichen Prozess kann die {{site.data.keyword.backup_notm}}-Größe auch reduziert werden.
{:tip}
