---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Installing the Bare Metal Restore plug-in
{: #BMRplugin}

BMR is a disaster recovery solution for Microsoft Windows. You can use BMR to restore your server from a bare metal state after a disaster, such as an operating system or hardware failure, occurred. With BMR, you can quickly restore the system image from a safe, secure location that is managed by {{site.data.keyword.BluSoftlayer_full}}.

BMR is a Microsoft Windows only product on physical servers. It is not available for virtual servers. Bare Metal Restores for Linux distributions aren't supported. BMR is only supported by Backup Agent 8.30 or earlier versions. (30 June 2018).
{:important}

**Capabilities provided**

- Restore your system to a select point-in-time.
- Restore your system from image or file-based backups.
- Restore your system from backups that are stored on the {{site.data.keyword.backup_notm}}.
- A launchable recovery transaction that you can use to restore your data without a bootable system.

## Ordering the plug-in

1. Log in to the [{{site.data.keyword.cloud_notm}} console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://{DomainName}){:new_window} and click the **menu** icon on the upper left. Select **Classic Infrastructure**. <br/>
   Alternatively, you can log in to the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Click **Storage** > **Backup** to display the servers with backup service.
3. Select your account and click **Order plug-ins**.
4. Select **{{site.data.keyword.backup_notm}} plug-in - BMR (Bare Metal Restore)** and click **Continue**.
5. Enter your Promo Code if you have one, and click **Recalculate**.
6. The updated charges are displayed. Review your order.
7. Check the box to indicate that you read and accepted the Third-party Service Agreements.
8. Click **Place Order**.

## Downloading the user guide

Connect to the {{site.data.keyword.BluSoftlayer_full}} network with {{site.data.keyword.BluVPN}} so that you can access and download the user guide from the [Downloadable {{site.data.keyword.backup_notm}} Documentation ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}
