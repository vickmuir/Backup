---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: EVault, Carbonite, Backup, expanding vault

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}


# Expanding vault capacity
{: #expandcapacity}

Current {{site.data.keyword.BluSoftlayer_full}} users are able to expand the size of their vault up to 4000 GB. They don't need to create a duplicate or manually migrate data to a larger volume. The limit increase process does not cause any outage or lack of access.

## Ordering an increase

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}/){:new_window} and click the **Menu** icon on the upper left. Select **Classic Infrastructure**.<br/>
   Alternatively, you can log in to the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Click **Storage** > **Backup** to display the servers with backup service.
3. Select the vault you want to extend.
4. Click **Actions**, and select **Modify {{site.data.keyword.backup_notm}}**.
5. On the next screen, select the new size and click **Upgrade**.

## Billing

Billing for the volume is automatically updated to add the pro-rated difference of the new price to the current billing cycle. Then, the full new amount is billed in the next billing cycle.

The same process can be used to downsize your {{site.data.keyword.backup_notm}}.
{:tip}
