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

# Installing the backup client in Windows

Installing the {{site.data.keyword.backup_full}} client in Windows is completed through a series of interactions on the server that is designated for the {{site.data.keyword.backup_notm}} service.

For information about backups for Windows 2016 servers, see [Configuring {{site.data.keyword.backup_notm}} on Windows 2016](install-backup-client-windows2016.html).
{:tip}

## Logging in to the target device server

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}/catalog/){:new_window} and click the **menu** icon on the upper left. Select **Classic Infrastructure**. <br/>
   Alternatively, you can log in to the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Select **Devices** > **Device List** from the main menu to see the list of available servers.
3. Find the device for which you purchased the {{site.data.keyword.backup_notm}} service, and make note of its public IP address.
4. Click the right-pointing arrow to expand and show more information about the device, including the user name and password. If the password isn't displayed, clicking **Show Password** reveals it.
5. Log in to the target device by using Remote Desktop Connection.

## Downloading the backup client

1. On the target server, open a browser session and enter the following URL to download the executable file for the {{site.data.keyword.backup_notm}} client. <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}

2. Double-click the downloaded file.
3. Click **Run**.


## Installing and Registering the Backup Agent

1. Enter the Network address: <br />
  ```
  https://ev-webcc01.service.softlayer.com
  ```
  {: pre}

2. Enter the user name in the **user name** field.
3. Enter the password in the **password** field.
6. Click **Next**
7. Click **Install** to complete the installation.

## Configuring backup agents

Log in to {{site.data.keyword.backup_notm}} portal to configure and manage your backup agents. For more information, see the [Getting started tutorial](index.html#configuring-the-backup-agent-and-the-backup-schedule).
