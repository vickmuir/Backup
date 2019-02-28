---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-28"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}_
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:shortdesc: .shortdesc}

# Getting started tutorial
{: #gettingstarted}

Backups ensure that your data is safely stored outside of your device and protected if it gets lost. {{site.data.keyword.backup_full}} is an automated agent-based backup system that is managed through the {{site.data.keyword.backup_notm}} portal browser-based management utility. {{site.data.keyword.backup_notm}} provides users with a method to back up data between servers in one or more data centers on the {{site.data.keyword.BluSoftlayer_full}} network. Administrators can set backups to follow a daily, weekly, or custom schedule that targets full systems, specific directories, or even individual files. Extra plug-ins ensure compatibility with software like Microsoft Exchange and Microsoft SQL, other types of third-party software, and enable users to complete a Bare Metal Restore, when necessary.
{:shortdesc}

## Before you begin
{: #prereqs}

You must have a valid licence to use IBM Cloud Backup. You can purchase {{site.data.keyword.backup_notm}} service in two ways.

- [Purchase backups when you Order a Server](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingwithserver).
- [Purchase backups as an Upgrade](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingasupgrade).

For more information about ordering and pricing, see [Provisioning {{site.data.keyword.backup_notm}}](/docs/infrastructure/Backup?topic=Backup-ordering).

## Installing the {{site.data.keyword.backup_notm}} agent

{{site.data.keyword.backup_notm}} Agent is supported on the following OS.

**Windows**
 - Windows Server 2016
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

**Linux**
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - RHEL 7.x
 - RHEL 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

Follow the instructions appropriate for your OS,
- [Installing the Backup Client in Linux](/docs/infrastructure/Backup?topic=Backup-InstallinLinux)
- [Installing the Backup Client in Windows](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)
- [Installing the Backup Client in Windows 2016](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016)

## Accessing {{site.data.keyword.backup_notm}} portal (formerly WebCC)

{{site.data.keyword.backup_notm}} portal is used to interact with any {{site.data.keyword.backup_notm}} service that is offered by {{site.data.keyword.BluSoftlayer_full}}. {{site.data.keyword.backup_notm}} portal is a browser-based client that runs on the {{site.data.keyword.BluSoftlayer_full}} private network and allows full control of any {{site.data.keyword.backup_notm}} service, including configuration and restores.

1. Access the Private Network over VPN.

   {{site.data.keyword.backup_notm}} portal can't be accessed over the public network. A VPN connection must be established first.
   {:important}
2. Access the Backup storage screen in the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
3. Click anywhere on the row of the {{site.data.keyword.backup_notm}} service that you want to see to expand the view.
4. Click **{{site.data.keyword.backup_notm}} portal Login** to start the portal client in your browser.

## Configuring the Backup agent and the backup schedule

After you ordered your {{site.data.keyword.backup_notm}} and the agent is installed on the server, you can start creating backups of your data. Follow these steps to configure your agent and retention schedule.

1. Log in to the {{site.data.keyword.backup_notm}} portal.
2. Click **All Agents**> **Unconfigured Agents**.
3. Click **This is a new Agent I would like to configure** link. Step through the process and enter the following information:
   1. Agent configuration - provide agent description, click **Next**.
   2. Job type selection - enter job name, job description, and backup source type, click **Next**.
   3. Selection - select directories and click **Include...**
   4. Options - provide passwords
   5. Schedule - click **Add** to create a schedule, click **Next**.
   6. Select the default vault, click **OK**.
   7. Click **Save**.
4. Create a retention schedule.
   1. Select **Edit** > **Agent Settings**.
   2. Click **Add**.
   3. Complete your retention details.
   4. Click **OK**.
   5. Click **Save**.

      For more information about Retention Schemes, see the [FAQ](faqs.html).
      {:tip}

## Running your first backup job

1. Log in to the {{site.data.keyword.backup_notm}} portal.
2. Click **All Agents**, then select the agent that you configured.
3. Click **Run Backup**.
4. Confirm Destination and select a retention scheme.
5. Click **Start Backup**. You can view the backup details while the process is running.
6. When the backup is complete, click **Close**.

For more information, see [Configuring simple file-level backup on Linux](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup).
{:tip}

## Accessing and viewing {{site.data.keyword.backup_notm}} storage details in the Console

The storage details of your service can be viewed in the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}/){:new_window} and the {{site.data.keyword.slportal}} at any time. Details that can be viewed include the password, storage address, and usage that is associated with the selected {{site.data.keyword.backup_notm}} service.

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}){:new_window} and click the **menu** icon on the upper left. Select **Classic Infrastructure**.</br>
   Alternatively, you can log in to the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Click **Storage**, and select **Backup** from the list.
2. Click anywhere on the row of the vault you want to view its storage details. From this view, the Password is not visible.
3. Click the **Show** check box next to the **Password** field to view the password for the selected {{site.data.keyword.backup_notm}} service.

Changes that are made to the {{site.data.keyword.backup_notm}} password within the {{site.data.keyword.slportal}} are made to the service itself. To reset your password, follow the steps in [Changing the password for the backup service](/docs/infrastructure/Backup?topic=Backup-changePassword).
{:important}

## Getting more online help

{{site.data.keyword.backup_notm}} portal's systems are fully documented and support for the application is accessible within {{site.data.keyword.backup_notm}} portal. Click the white question mark in a blue circle that is located in the upper right for **Help**. Click any article or topic in the navigation bar on the left side to view more information.
