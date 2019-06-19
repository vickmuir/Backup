---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-10"

keywords: IBM Cloud backup, EVault, Carbonite, backup, expanding vault

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}


# Vault-Kapazität erhöhen
{: #expandcapacity}

Die aktuellen Benutzer von {{site.data.keyword.cloud}} können ihre Vault auf bis zu 4000 GB vergrößern. Dazu müssen sie keine Duplikate erstellen und die Daten auch nicht manuell auf einen größeren Datenträger migrieren. Der Prozess zur Erhöhung des Grenzwerts verursacht keinen Ausfall oder keinen Verlust des Zugriffs.

## Erhöhung anfordern

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}){: external} an und klicken Sie auf das **Menüsymbol** links oben. Wählen Sie **Klassische Infrastruktur** aus.
2. Klicken Sie auf **Speicher** > **Sicherung**, um die Server mit Backup-Service anzuzeigen.
3. Wählen Sie die Vault aus, die Sie erweitern möchten.
4. Klicken Sie auf **Aktionen** und wählen Sie **{{site.data.keyword.backup_notm}} ändern** aus.
5. Wählen Sie in der nächsten Anzeige die neue Größe aus und klicken Sie auf **Upgrade**.

## Abrechnung

Die Abrechnung für den Datenträger wird automatisch aktualisiert, um die anteilmäßige Differenz des neuen Preises zum aktuellen Abrechnungszyklus hinzuzufügen. Anschließend wird der vollständige neue Betrag im nächsten Abrechnungszyklus berechnet.

Mit dem gleichen Prozess kann die {{site.data.keyword.backup_notm}}-Größe auch reduziert werden.
{:tip}
