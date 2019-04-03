---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup,  EVault, Carbonite, backup, restore

subcollection: Backup

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restoring data from one VSI to another in a different Data Center
{: #restoreVSIotherlocation}

Sometimes you want to restore data to a different server. This procedure applies to file-level restores of non-OS files only. To restore a system image, follow the [Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR) instructions.

The process includes reregistering the backup agent on the second server to access the vault location of the first server and completing a **Restore from another Computer**.

**Pre-requisites**

- Server1 and Server2 must have the same OS. Cross-platform restores aren't supported.
- Server1 and Server2 must have backup agents that were configured previously. For more information about configuring the backup agents, see [Configuring the Backup agent in {{site.data.keyword.backup_notm}} portal](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).
- A backup job for Server1 that produced a backup to Server1's vault location.

Disable all Scheduled tasks on both servers to avoid any conflicts.
{:important}

## Starting {{site.data.keyword.backup_notm}} portal of Server2
{: #startWebCCotherDC}

Remember to start your {{site.data.keyword.BluVPN}} connection to get access to the {{site.data.keyword.BluSoftlayer_full}} private network or the {{site.data.keyword.backup_notm}} portal link doesn't work.
{:tip}

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}/){:new_window} and click the **menu** icon on the upper left. Select **Classic Infrastructure**. <br/>
   Alternatively, you can log in to the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Click **Storage** > **Backup** to display the servers with backup service.
3. Select Server2. Click the right-pointing expansion arrow to reveal the {{site.data.keyword.backup_notm}} portal link.
4. Click **{{site.data.keyword.backup_notm}} portal Login** to start the portal client in your browser.

## Reregistering the vault
{: #reregistervaultotherDC}

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
{: #runbackuprestoreotherDC}

1. Click **All Agents**.

   You might need to refresh the page to see the jobs that are defined on Server1 as accessible and synchronized under the Server2 **Jobs** tab.
   {:tip}
2. Hover over **Advanced** and select **Restore from another Computer**.
3. On the **Restore From Another Computer** screen, click **Add**. The fields are auto-populated with default values, so change them.
4. Click the Vault field, and select **Enter Vault Settings**, and type in the IP address of Server1's vault. Click **Add**.
5. Update the credentials to the credentials of Server1.
6. Click **Save Changes**. This action connects you to Server1's vault.
7. Back on the **Restore From Another Computer** screen, update the Computer and Job fields.
  - Computer - Select Server1 as the backup computer to restore from.
  - Job - Select the backup job from Server1.
8. Click **Next** start the restore process to the server2 in another data center.
9. At the prompt, enter the backup password and click **Next**.
10. Confirm that the right backup job is selected, and click **Next**. The restore job is now configured on server2.
11. Select the newly configured job, and click **Run Restore**.
12. Select the files that you want to restore.
13. Click the plus sign to expand file selection.
14. Click the check box of the individual files or folders to be restored from server1 to server2. Then, click **Include**.
15. The files populate the Backup Set window on the right. Click **Next**.
16. After you completed the data selection, proceed to select your options.
    - Select **Restore to the original location**.
    - Select **Overwrite existing files**.
17. Click **Run Restore**. The Process Details window provides the status of the running backup job. After the backup is complete, click **Close**.


## Verifying the restore
{: #verifyrestoreotherDC}

1. Connect to the root of Server2 through SSH.
2. List the files and all directory entries in a long format.
  ```
  ls -la
  ```
  {: pre}

3. Compare the output.

## Resuming normal backup schedule.
{: #resumescheduleotherCD}

1. When the restore is complete, remove the registration information of server1, where the data was restored from.
2. Enter the current server2 registration and enable Schedule tasks.
