---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud backup,  EVault, Carbonite, backup, restore

subcollection: Backup

---
{:pre: .pre}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:shortdesc: .shortdesc}

# Restoring data from one VSI to another within the same data center
{: #restorefromotherVSI}

Sometimes you want to restore data to a different server in the same data center. This procedure applies to file-level restores of non-OS files only. To restore a system image, follow the [Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR) instructions.
{:shortdesc}

The process includes reregistering the backup agent on the second server to access the vault location of the first server and completing a **Restore from another Computer**.

**Pre-requisites**

- Server1 and Server2 must have the same Operating System. Cross-platform restores aren't supported.
- Server1 and Server2 must have backup agents that were configured previously. For more information about configuring the backup agents, see [Configuring the backup agent in {{site.data.keyword.backup_notm}} portal](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).
- A backup job for Server1 that produced a backup to Server1's vault location.

Disable all Scheduled tasks on both servers to avoid any conflicts.
{:important}

## Starting {{site.data.keyword.backup_notm}} portal of Server2
{: #startWebCC}

Remember to start your {{site.data.keyword.BluVPN}} connection to get access to the {{site.data.keyword.cloud}} private network or the {{site.data.keyword.backup_notm}} portal link doesn't work.
{:tip}

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}){: external}. From the Navigational Menu, select **Classic Infrastructure**.
2. Click **Storage** > **Cloud Backup** to display the servers with backup service.
3. Select Server2. Click the expansion arrow to reveal the {{site.data.keyword.backup_notm}} portal link.
4. Click **{{site.data.keyword.backup_notm}} portal Login** to start the portal client in your browser.

## Reregistering the vault
{: #reregistervault}

1. Click **All Agents** and open the specific agent that you want to modify.
2. Click **Edit** and select **Vault Settings**.
3. Click **Reregister** to connect Server1 to Server2.
4. On the **Re-register Vault** screen for the **Use a Vault Profile** entry, select **Enter Vault Settings**.
5. Enter the Vault Name, which is the same as the vault name of Server1.
6. Enter credentials for Server1 to log in to the vault for Server1.
7. Click **Load Computers**, this action displays the servers that are attached to the vault location.
8. Click **Save Changes**.
9. When prompted, click **Yes** to confirm the reregistration of the vault.

## Running the backup job from Server1 as the restore job on Server2
{: #runbackuprestore}

1. Click **All Agents**.

   You might need to refresh the page to see the jobs that are defined on Server1 as accessible and synchronized under the Server2 **Jobs** tab.
   {:tip}
2. Hover over **Advanced** and select **Restore from another Computer**.
3. On the **Restore From Another Computer** screen, make the following selections.
  - Vault - This entry defaults to Server1's vault.
  - Computer - Select Server1 as the backup computer to restore from.
  - Job - Select the backup job from Server1.
4. Click **Next**
5. Confirm Source information
  - **Safeset location** is the Vault location for Server1.
  - In the **Select a Backup Version** section, specify your backup from Server1 as the backup version.
  - The encryption password is the password that you used when you created the backup of Server1.
6. Click **Next**
7. Select which files need to be restored from the Server1 backup. Check the boxes next to the files, and directories that you want to restore, then click **Include** to save your choices.
8. Click **Next** to move to the restore options.
9. In Options
  - Destination - Select **Restore to original location**
  - File Overwrite - Select **Overwrite existing files**
10. Click **Run Restore**.
11. The Process Detail screen displays the status of the restore job.


## Verifying the restore
{: #verifyrestore}

1. Connect to the root of Server2 through SSH.
2. List the files and all directory entries in a long format.
  ```
  ls -la
  ```
  {: pre}

3. Compare the output.

## Resuming normal backup schedule.
{: #resumeschedule}

1. When the restore is complete, remove the registration information of server1, where the data was restored from.
2. Enter the current server2 registration and enable Schedule tasks.
