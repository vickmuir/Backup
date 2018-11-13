---

copyright:
  years: 1994, 2018
lastupdated: "2018-11-12"

---
{:pre: .pre}{:tip: .tip}
{:note: .note}
{:important: .important}
{:new_window: target="_blank"}

# Creating a Backup and Restoring Data from one VSI to another within the same data center

Sometimes you want to restore data to a different server in the same data center. This procedure applies to file-level restores of non-OS files only. To restore a system image, follow the [Windows BMR](restoring-evault-bmr-system-volume-image.html) instructions.

The process includes reregistering the EVault agent on the second server to access the EVault location of the first server and completing a **Restore from another Computer**.

**Pre-requisites**

- Server1 and Server2 must have the same OS. Cross-platform restores aren't supported.
- Server1 and Server2 must have EVault agents that were configured previously. To learn how to configure the EVault agents, click [here](index.html#configuring-evault-agent-in-webcc)
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
5. Enter the Vault Name, which is the same as the vault name of Server1.
6. Enter credentials for Server1 to log in to the vault for Server1.
7. Click **Load Computers**, this action displays the servers that are attached to the vault location.
8. Click **Save Changes**.
9. When prompted, click **Yes** to confirm the reregistration of the EVault.

## Running the Backup Job from Server1 as the Restore Job on Server2

1. Click **All Agents**.
   >**Note** - You might need to refresh the page to see the jobs that are defined on Server1 as accessible/synchronized under the Server2 **Jobs** tab
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
