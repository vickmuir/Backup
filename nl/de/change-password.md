---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, password, password reset

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Kennwort für den Backup-Service ändern
{: #changePassword}

Jedem {{site.data.keyword.backup_full}}-Service ist ein Kennwort zugeordnet, das für den Zugriff auf die Vault im {{site.data.keyword.backup_notm}}-Portal verwendet wird.

Für viele Produkte und Services von {{site.data.keyword.cloud}} wird die Kennwortspeicherfunktion im {{site.data.keyword.slportal}} ausschließlich zur Protokollierung des Kennworts verwendet. Für diese Produkte und Services werden Änderungen, die im {{site.data.keyword.slportal}} am Kennwort vorgenommen werden, nicht auf das jeweilige Produkt oder den jeweiligen Service angewendet. Dies gilt **nicht** für {{site.data.keyword.backup_notm}}.

Änderungen, die Sie am Kennwort für {{site.data.keyword.backup_notm}} im {{site.data.keyword.slportal}} vornehmen, werden auf den Service selbst angewendet. Wenn Sie Ihr Kennwort ändern, müssen Sie bedenken, dass sich dieser Schritt direkt auf Ihren Service auswirkt.
{:important}

## Kennwort ändern

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}/catalog){: external} an und klicken Sie oben links auf das **Menüsymbol**. Wählen Sie **Klassische Infrastruktur** aus. <br/>
   Alternativ können Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external} anmelden.
2. Klicken Sie auf **Speicher** > **Sicherung**, um die Server mit Backup-Service anzuzeigen.
3. Klicken Sie auf eine beliebige Stelle in der Zeile der Vault, um die Ansicht zu erweitern.
4. Klicken Sie auf **Anzeigen**, damit das aktuelle Kennwort angezeigt wird.
5. Geben Sie das neue Kennwort im Feld **Kennwort** ein.
6. Klicken Sie auf **Aktualisieren**.
