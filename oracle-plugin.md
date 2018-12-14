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

# Installing the Oracle plug-in

The Oracle plug-in is an add-on and is installed with the Windows Agent or the Linux Agent on the Oracle database host. Through the {{site.data.keyword.backup_notm}} portal, you can configure jobs, back up Oracle databases to a secure, remote vault, and restore Oracle databases. The Oracle plug-in integrates into the existing architecture.

**Capabilities provided**

- Support for Oracle database backup and recovery.
- The Oracle plug-in provides ARCHIVELOG-based, non-RMAN backups of whole online database instances. All non-temporary table spaces and instance parameter files are automatically backed up. Oracle Corporation recommends that backups take place in periods of low database activity.
- Full and partial databases are restored through normal user-managed Oracle recovery mechanisms.

**Limitations**
- Only local, single-instance, disk-based databases are backed up.
- Database clusters are not backed up.
- Raw devices are not backed up.
- Remote databases are not backed up.
- The database must run in ARCHIVELOG mode, and the user under which the backup is configured must have SYSDBA privileges.
- Database passwords are encrypted for enhanced security over script-based methods.

## Ordering the plug-in

1. Log in to the [{{site.data.keyword.cloud_notm}} console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://{DomainName}/){:new_window} and click the **menu** icon on the upper left. Select **Classic Infrastructure**. <br/>
   Alternatively, you can log in to the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Click **Storage** > **Backup** to display the servers with backup service.
3. Select your account, and click **Order plug-ins**.
4. Select **{{site.data.keyword.backup_notm}} plug-in - Oracle**, and click **Continue**.
5. Enter your Promo Code if you have one, and click **Recalculate**.
6. The updated charges are displayed. Review your order.
7. Check the box to indicate that you read and accept the Third-party Service Agreements.
8. Click **Place Order**.

## Installing the Oracle plug-in for Windows

The Oracle plug-in for Windows is installed with the 32-bit or 64-bit Windows Agent. To install the Oracle plug-in, run the Agent installation kit. The Oracle plug-in appears as an option on the **Custom Setup** page.

Before you install the plug-in for your Microsoft Windows server, stop both {{site.data.keyword.backup_notm}} services in `services.msc`.
{:tip}

1. Browse to `c:\installs\evault` folder and run the .exe file with the higher revision number.
2. At the language screen, click **OK**
3. At the welcome screen, click **Next**
4. Select the **Modify installation**, and click **Next**.
5. Select the **Leave Unchanged**, and click **Next**.
6. At the custom setup screen, select each plug-in that you purchased, and select **This feature will be installed on ...**, then click **Next**.
7. Select **Keep my current registration**, and click **Next**.
8. Click **Install**.
9. When the installation is complete, check to ensure that both services are enabled and running.
10. If {{site.data.keyword.backup_notm}} portal is able to access/view the database, then the installation was successful.

## Installing the Oracle plug-in for Linux

The Oracle plug-in is an add-on to the Linux Agent and is installed with the Agent on the database host. The Linux Agent application must be installed before the Oracle plug-in installation occurs. The agent is available as a 32-bit application and a 64-bit application. For more information, see [Installing the {{site.data.keyword.backup_notm}} Client in Linux](install-backup-client-linux.html).

The Oracle plug-in installation kit is available in a tar.gz file.

1. On the host, download the installation package.
   ```
   http://downloads.softlayer.com/evault/Oracle-Plugin-Linux-x64-8.10.5249.tar.gz
   ```
   {: pre}

2. Extract the files from the package.
   ```
   # cd /tmp
   # tar xvf Oracle-Plugin-Linux-x64-8.10.5249.tar
   ```
   {: pre}

3. Go to the folder.
   ```
   # cd Oracle-Plugin-Linux-x64-8.10.5249.xxxx
   ```
   {: pre}

4. Run the installation script.
   ```
   # ./install.sh
   ```
   {: pre}

5. Follow the installation instructions on the screen.

The Oracle plug-in performs an "inconsistent" whole database backup that requires that the database runs in ARCHIVELOG mode. The DBA needs to ensure that the database is in ARCHIVELOG mode before the backups are started. For more information, see the User Guide.
{:important}


## Downloading the user guide

Connect to the {{site.data.keyword.BluSoftlayer_full}} network with {{site.data.keyword.BluVPN}} so that you can download the user guides from [Downloadable {{site.data.keyword.backup_notm}} Documentation ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}
