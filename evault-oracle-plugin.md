---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# Installing the EVault Oracle Plug-in

The Oracle plug-in is installed with the Windows Agent on the Oracle database host. Through the WebCC portal, you can configure jobs, back up Oracle databases to a secure, remote vault, and restore Oracle databases. The Oracle plug-in integrates into the existing architecture.

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

## Ordering the Plug-in

1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Click **Storage** > **Backup**.
3. Select your EVault account, and click **Order plug-ins**.
4. Select **EVault plug-in - Oracle**, and click **Continue**.
5. Enter your Promo Code if you have one, and click **Recalculate**.
6. The updated charges are displayed. Review your order.
7. Check the box to indicate that you read and accept the Third-party Service Agreements. 
8. Click **Place Order**.

## Installing the Oracle Plug-in

The Oracle plug-in for Windows is installed with the 32-bit or 64-bit Windows Agent. To install the Oracle plug-in for Windows, run the Agent installation kit. The Oracle plug-in appears as an option on the **Custom Setup** page.

>**Note** - Before you install the plug-in for your Microsoft Windows server, stop both EVault services in `services.msc`.  

1. Browse to `c:\installs\evault` folder and run the .exe file with the higher revision number.
2. At the language screen, click **OK**
3. At the welcome screen, click **Next**
4. Select the **Modify installation**, and click **Next**.
5. Select the **Leave Unchanged**, and click **Next**.
6. At the custom setup screen, select each plug-in that you purchased, and select **This feature will be installed on ...**, then click **Next**.
7. Select **Keep my current registration**, and click **Next**.
8. Click **Install**.
9. When the installation is complete, check to ensure that both services are enabled and running.
10. If WebCC is able to access/view the database, then the installation was successful. 

## Downloading user guide

Connect to the {{site.data.keyword.BluSoftlayer_full}} network with {{site.data.keyword.BluVPN}} so that you can download the EVault Agent v8.0 for Microsoft Windows - Oracle plug-in Guide.pdf from [Downloadable EVault Documentation](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.




