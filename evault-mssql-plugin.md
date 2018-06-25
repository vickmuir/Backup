---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-25"

---
{:new_window: target="_blank"}

# Installing the EVault SQL Server plug-in

The SQL Server plug-in is installed with the Windows Agent on the SQL database host. Through the WebCC portal, you can configure jobs, back up SQL databases to a secure, remote vault, and restore SQL databases.

## Capabilities provided

- You can run full database backups, full database with transaction logs backups, or transaction logs only backup.
- You can run multiple backups at the same time. 
- You can restore SQL databases to the same SQL instance or to a different SQL instance,
- You can restore databases with the original database names, overwrite existing databases, and restore by using the No Recovery option.

## Order the Plug-in

1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Click **Storage** > **Backup**.
3. Select your EVault account, and click **Order Plugins**.
4. Select **EVault Plugin - MSSQL** and click **Continue**.
5. Enter your Promo Code if you have one, and click **Recalculate**.
6. The updated charges are displayed. Review your order.
7. Check the boxes to indicate that you read the **Master Service Agreement** and accept the **3rd Party Software Terms**. 
8. Click **Place Order**.

## Install the MSSQL Plug-in

To install the SQL plug-in for Windows, run the Agent installation kit. The plug-in appears as an option on the **Custom Setup** page.

**Note**: Before you install the MSSQL EVault plug-in for your Microsoft Windows server, stop both EVault services in `services.msc`.  

1. Browse to `c:\installs\evault` folder and run the .exe file with the higher revision number.
2. At the language screen, click **OK**.
3. At the welcome screen, click **Next**.
4. Select the **Modify installation**, and click **Next**.
5. Select the **Leave Unchanged**, and click **Next**.
6. At the custom setup screen, select each plug-in that you purchased.
7. Select **This feature will be installed on ...**, then click **Next**.
8. Select **Keep my current registration** and click **Next**.
9. Click **Install**.
10. When installed, check to ensure that both services are enabled and running.
11. If WebCC is able to access/view the database, then the installation was successful. 

## User guide

Connect to the {{site.data.keyword.BluSoftlayer_full}} network with {{site.data.keyword.BluVPN}} so that you can download the EVault Agent for Microsoft Windows v8.0 - SQL Server plug-in Guide.pdf from [Downloadable EVault Documentation](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.

## Frequently Asked Questions

### What does VSS (Volume Shadow Copy Services) do?

The current version of the SQL Server plug-in uses VSS (Volume Shadow Copy Services) to complete backups. By using VSS, the SQL Server plug-in:
- Effectively backs up SQL databases, even SQL databases that span volumes, 
- Allows backups to be completed while applications continue to write to a volume, and 
- Provides data consistency within and across databases. 
VSS allows multiple backups to run at the same time.

### What are the main features of the SQL Plug-in?

- Ability to specify the names of databases to include and exclude in SQL Server backup jobs by using wildcard characters (asterisks and question marks). New databases with names that match a backup job's filters are automatically included or excluded when the job runs. 
- Ability to protect secondary databases in AlwaysOn Availability Groups by using the 64-bit Agent and SQL Server plug-in.
- Ability to share SQL safesets that contain SharePoint 2010/2013 content databases for use with the Granular Restore for Microsoft SharePoint application. Once a safeset is shared, the Granular Restore application can be used to restore site collections, websites, lists, libraries, folders, list items, or documents.
- Support for Delta-friendly backup of databases that are on spanned volumes.
Ability to protect databases in full recovery model with a single schedule entry. This option allows protecting databases and managing truncation of transaction logs in a single schedule entry.
- The SQL Server plug-in supports Full, Full with Include Transaction Logs, and Transaction Log backups (updated terminology to align with SQL Server terminology). EVault will continue to support the Single Pass Restore function that allows the customer to select a point in time “transaction log” backup. EVault will restore the full database and all transaction logs necessary to restore the database to the selected point in time.
- A backup job can contain one or more databases from the same single SQL Server instance. A separate Job can be created to back up other databases from a different SQL Server instance, which can be run simultaneously if wanted.
- Ability to restore databases with "No Recovery" to provide more recovery options through the SQL Server Management Studio.
- Alternate restore option supports restore to files, which allows the database administrator to mount the databases through the SQL System Manager.
- Alternate restore includes the ability to direct the restore of one database into another even when the logical database names are not matching. For mismatched objects, the plug-in will create databases in the default database location for the instance.
- Support for Transparent Data Encryption (TDE) with 64-bit SQL Server 2008 R2 (SP1) and SQL Server 2012.
- If an SQL Server host is completely lost, the SQL Server software can be installed, and the database completely restored. (The Master database must be restored first.)
- When the backup starts, the backup occurs with or without the database services running.
- Restores are supported to original database names (with or without overwrite existing databases), Restore over an existing database, or to files on disk.

