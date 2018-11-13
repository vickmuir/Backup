---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-05"

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:new_window: target="_blank"}

# Creating a Backup and Restoring Data from one VSI to another in a different Data Center

Sometimes you want to restore data to a different server. This procedure applies to file-level restores of non-OS files only. To restore a system image, follow the [Windows BMR](restoring-evault-bmr-system-volume-image.html) instructions.

The process includes reregistering the EVault agent on the second server to access the EVault location of the first server and completing a **Restore from another Computer**.

**Pre-requisites**

- Server1 and Server2 must have the same OS. Cross-platform restores aren't supported.
- Server1 and Server2 must have EVault agents that were configured previously. To learn how to configure the EVault agents, click [here](index.html#configuring-backup-agent-in-webcc).
- A backup job for Server1 that produced a backup to the Server1 EVault location.

Disable all Schedule tasks on both servers to avoid any conflicts.
{:important}

## Starting WebCC of Server2

Remember to start your {{site.data.keyword.BluVPN}} connection to get access to the {{site.data.keyword.BluSoftlayer_full}} private network or the WebCC link doesn't work.
{:tip}

1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} and click **Storage** > **Backup** from the main menu to display the servers with EVault backup service.
2. Select Server2. Click the right-pointing expansion arrow to reveal the WebCC link.
3. Click **WebCC Login** to start the WebCC client in your browser.

## Reregistering the EVault

1. Click **All Agents** and open the specific agent that you want to modify.
2. Click **Edit** and select **Vault Settings**.
3. Click **Reregister** to connect Server1 to Server2.
4. On the **Re-register Vault** screen for the **Use a Vault Profile** entry, select **Enter Vault Settings**.
5. Enter the Vault Name, which is the same as the EVault name of Server1.
6. Enter credentials for Server1 to log in to the EVault for Server1.
7. Click **Load Computers**, this action displays the servers that are attached to the vault location.
8. Click **Save Changes**.
9. When prompted, click **Yes** to confirm the reregistration of the EVault.

## Running the Backup Job from Server1 as the Restore Job on Server2

1. Click **All Agents**.

   You might need to refresh the page to see the jobs that are defined on Server1 as accessible/synchronized under the Server2 **Jobs** tab.
   {:tip}
2. Hover over **Advanced** and select **Restore from another Computer**.
3. On the **Restore From Another Computer** screen, click **Add**. The fields are autopopulated with default values, so change them.
4. Click the Vault field, and select **Enter Vault Settings**, and type in the IP address of Server1's vault. Click **Add**.
5. Update the credentials to the credentials of Server1.
6. Click **Save Changes**. This action connects you to Server1's vault.
7. Back on the **Restore From Another Computer** screen, update the Computer and Job fields.
  - Computer - Select Server1 as the backup computer to restore from.
  - Job - Select the backup job from Server1.
8. Click **Next** start the restore process to the server2 in another Datacenter.
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

1. Connect to the root of Server2 through SSH.
2. List the files and all directory entries in a long format.
  ```
  ls -la
  ```
  {: pre}

3. Compare the output.

## Resuming normal Backup schedule.

1. When the restore is complete, remove the registration information of server1, where the data was restored from.
2. Enter the current server2 registration and enable Schedule tasks.
