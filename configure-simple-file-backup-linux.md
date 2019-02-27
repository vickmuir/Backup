---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configuring simple file-level backup on Linux
{: #configureLinuxBackup}

After you ordered your {{site.data.keyword.backup_full}} and the agent is installed on the server, you can start creating backups of your data. The article provides the steps to configure your agent, retention schedule and start your first backup job.

## Starting {{site.data.keyword.backup_notm}} portal
{: #startWebCCconfigLin}

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}/){:new_window} and click the **menu** icon on the upper left. Select **Classic Infrastructure**. <br>
   Alternatively, you can log in to the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Click **Storage** > **Backup** to display the servers with backup service.
2. Select the server where the files to be backed up are located. Click the right-pointing expansion arrow to reveal the {{site.data.keyword.backup_notm}} portal link.
3. Start your VPN connection to get access to the IBM private network.
4. Click the {{site.data.keyword.backup_notm}} portal Login link to start the portal client in your browser.<br/>

  If {{site.data.keyword.backup_notm}} portal doesn't start, you might have a problem with your VPN connection. You might also see a message that says the form you're sending isn't secure. It is expected - proceed by sending the form.
  {:tip}

## Configuring a backup job

1. In the navigation pane, click **All Agents** to display current {{site.data.keyword.backup_notm}} Agents
2. Click **This is a new Agent I would like to configure**.
3. Enter a Job Name and a Job Description for the job that you're creating.
4. For **Backup Source Type**, select the file system type that you want to back up.
5. Click **Next** to continue.
6. In the data files pane, go to the files and directories that you want to include in your backup by clicking the **+** and **-** symbols next to the folder icons.
7. Select the check boxes next to the files and directories that you want to include, then click **Include** to save your choices.
8. You can further filter your selections by using the pop-up screen that appears, or click **OK** to use the selections you made as-is. After you included your file and directory choices, your chosen files, and directories are displayed in the backup set pane on the right-hand-side of the screen. Click **Next** to continue.

   You can repeat steps 6 - 8 to add more files or to remove files you previously added (by using the **Exclude**). You can also use **Remove** to delete any line item from the backup set pane. After your backup set is configured the way that you want it,
   {:tip}
9. Select the Encryption type that you want.
  - If you don't want to encrypt your backup, select **None**.
  - If you want encryption, select **AES 256 bit** and enter a password into the Password and Verify Password fields. You can also add a Password Hint.

    You need this password to restore files from the backup. Without the password, you can't restore an encrypted back and there's no way to recover a lost password.
    {:important}
10. You can use any of the **Advanced Options**.
  - **Retention** - You can manage your data usage with this option. The retention period determines how long your backup is retained. After the retention period is reached, the backup is automatically removed. The built-in choices are Daily, Weekly, or Monthly.
  - **Compression** - You can use this option to reduce the capacity that is used for saving backups.
  - **Backup files that are opened for write** - This option allows files to be backed up, even if they are opened by an application when the backup job runs.
  - **Create log file** - You to create and manage the content and retention of log files that are generated during the backup process with this option.
  - **Back up a single instance of all selected hard linked files**. This option applies only to UNIX style systems. If you're using hard links to create multiple file names for some content, this option causes only one copy of the content to be saved. Upon restoration, all of the hard links are restored. This option requires a pre-scan pass through the file selection, which can take a significant amount of time and memory.
11. After you made your encryption choice, click **Next** to proceed to the **Create a schedule** screen.
12. On the Create a schedule page, click **Add** to schedule a time-based backup job, or click **Next** to create a manual job.
  - If you choose to create a manual job, proceed to Step 15.
  - If you choose to schedule a time-based job, select the days and the time of day to run your backups.
  - Select your Retention Scheme. For more information about Retention Schemes, see the [FAQ](/docs/infrastructure/Backup?topic=Backup-faqs).
  - Click **Advanced Schedule Options** for more configuration choices. You can select **Use Deferring** to prevent large backups from running at peak network times.

    When the deferring option is enabled, the backup job doesn't back up any new data after the specified amount of time. It commits the safeset to the vault, even if some data in the job isn't backed up. Changes to data that was previously saved are backed up, regardless of the specified amount of time. <br/> When the job runs again, the Agent checks for changes in data that was previously backed up, backs up those changes, and then backs up the remaining data. If a backup job is deferred while an item is being backed up, the backup for that item is incomplete and data from that item can't be restored. However, you can restore items that were backed up in the job before the job was deferred.
    {:note}
13. After you configured your backup schedule, click **Ok** to save it. Your scheduled job is added to the list of scheduled jobs.
  - You can repeat step 12 to schedule more backups.
  - To update to an existing backup job, select the job by clicking its row, then click **Edit** and make your changes.
14. Select a vault for your backup job, and click **Save Changes**.
15. Run a backup job
  - If you scheduled a time-based backup job, you don't need to do anything else. Your job runs automatically as scheduled.
  - If you set up a manual job (without a time-based schedule), you can run it now by selecting its row in the job list and clicking **Run backup**. As with time-based jobs, you can choose the **Retention Scheme** and the **Advanced Backup Options**. After you made your configuration choices, click **Start backup** to start the job.
