---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-21"

---
{:new_window: target="_blank"}

# Configuring Simple File-level Backup on Linux

After you ordered your EVault service and the agent is installed on the server, you can start creating backups of your data. The article provides the steps to configure your agent, retention schedule and start your first backup job.

## Launch WebCC

1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} and click **Storage** > **Backup** from the main menu to display the servers with EVault backup service. 
2. Select the server where the files to be backed up are located. Click the right-pointing expansion arrow to reveal the WebCC link.
3. Start your VPN connection to get access to the IBM private network.
4. Click the WebCC Login link to start the WebCC client in your browser.<br/>
  **Note**: If WebCC doesn't start, there might be a problem with your VPN connection. You might also see a message that says the form you're sending isn't secure. It is expected - proceed by sending the form.
  
## Configure a Backup Job

1. In the navigation pane on the left, click **All Agents** to display current EVault Agents
2. Click **This is a new Agent I would like to configure**.
3. Enter a Job Name and a Job Description for the job you're configuring/creating.
4. For **Backup Source Type**, select the file system type you want to back up from the menu.
5. Click **Next** to continue. 
6. In the **Data Files** pane, go to the files and directories you want included in your backup by clicking the **+** and **-** symbols next to the folder icons.
7. Select the check boxes next to the files and directories you want to include, then click **Include** to save your choices.
8. You can further filter your selections by using the pop-up screen that appears, or click **OK** to use the selections you made as-is. <br /> After you included your file and directory choices, your chosen files, and directories are displayed in the **Backup Set** pane on the right-hand-side of the screen. You can repeat steps 6 - 8 to add more files or to remove files you have already added (by using the **Exclude**). You can also use **Remove** to delete any line item from the **Backup Set** pane. After your Backup Set is configured the way that you want it, click **Next** to continue.
9. Select the Encryption type that you want. 
  - If you don't want to encrypt your backup, select **None**.   
  - If you want encryption, select **AES 256 bit** and enter a password into the Password and Verify Password fields. If wanted, you can add a Password Hint. <br/> **Note**: you need this password to restore files from the backup. There's no way to recover a lost password or to restore an encrypted backup without knowing the password.   
10. If you want to use any of the **Advanced Options**, here is an explanation of each option:
  - **Retention** helps to manage your data usage. The retention period determines how long your backup will be retained. After the retention period has been reached, the backup will be automatically removed. The built-in choices are Daily, Weekly, or Monthly.
  - **Compression** is used to reduce the amount of capacity used for saving backups.
The Backup files that are opened for write option allows files to be backed up, even if they are opened by an application when the backup job runs.
  - **Create log file** allows you to create and manage the content and retention of log files that are generated during the backup process. 
  - **Back up a single instance of all selected hard linked files**. This option applies only to unix style systems. If you're using hard links to create multiple file names for some content, this option causes only one copy of the content to be saved. Upon restoration, all of the hard links are restored. This option requires a pre-scan pass through the file selection, which can take a significant amount of time and memory.
11. After making your encryption choice, click **Next** to proceed to the **Create a schedule** screen.   
12. On the Create a schedule page, click **Add** to schedule a time-based backup job or click **Next** to create a manual job.
  - If you choose to create a manual job, proceed to Step 15.
  - If you choose to schedule a time-based job, select the days and the time of day to run your backups.
  - Select your Retention Scheme. Read more about Retention Schemes [here](evault-backup-faq.html#how-do-the-retention-schemes-work-)
  - Click **Advanced Schedule Options** for more configuration choices, if wanted. You can select **Use Deferring** to prevent large backups from running at peak network times. When deferring is enabled, the backup job doesn't back up any new data after the specified amount of time and commits the safeset to the vault, even if some data in the job isn't backed up. Changes to data that was previously backed up will be backed up, regardless of the specified amount of time. <br/> When the job runs again, the Agent checks for changes in data that was previously backed up, backs up those changes, and then backs up the remaining data.  If a backup job is deferred while an item (for example, file, database, volume, vSphere VMDK, or Hyper-V VM) is being backed up, the backup for that item is incomplete and data from the item can't be restored. However, you can restore items that were completely backed up in the job before the job was deferred.
13. After you have configured your backup schedule, click **Ok** to save it. Your scheduled job is added to the list of scheduled jobs. 
  - You can repeat step 12 to schedule more backups. 
  - To update to an existing backup job, select the job by clicking its row, then click **Edit** and make your changes.
14. Select a vault for your backup job, and click **Save Changes**.
15. Run a backup job
  - If you scheduled a time-based backup job, there are no further steps.  Your job will run automatically as scheduled.
  - If you set up a manual job (without a time-based schedule), you can run it by selecting its row in the job list and clicking **Run backup**. <br/> As with time-based jobs, you can choose the Retention Scheme and the Advanced Backup Options. After you made your configuration choices, click **Start backup** to start the job.
