---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-12"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Restoring from a Backup

Use these steps to complete a File restore with EVault. To restore a system image, follow the [Windows BMR](restoring-evault-bmr-system-volume-image.html) instructions.

## Starting WebCC

Remember to start your {{site.data.keyword.BluVPN}} connection to get access to the {{site.data.keyword.BluSoftlayer_full}} private network. The WebCC link doesn't work otherwise.
{:important}

1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} and click **Storage** > **Backup** from the main menu to display the servers with EVault backup service.
2. Select the server where the files to be restored are located. Click the arrow to reveal the WebCC link.
3. Click **WebCC** to start the WebCC client in your browser.

## Restoring your data

1. In the navigational pane on the left, click **All Agents**.
2. Click the Agent to display the Jobs.
3. Click the Job containing the backup that you want.
4. Click **Run Restore**.
5. Select a restore source.
6. Select a backup version.
7. Enter the encryption password.
8. Click **Next** to continue.
9. Select the check boxes next to the files and directories that you want to include, then click **Include** to save your choices.
10. You can further filter your selections by using the window that appears, or click **OK** to use the selections you made as-is. <br/>
After you included your file and directory choices, the files can no longer be selected in the **Data Files** pane. They are displayed in the **Backup Set** pane on the right.  

   You can repeat step 10 to add more files or to remove files you added previously (by using **Exclude**). <br/>You can also use **Remove** to delete any line item from the **Backup Set** pane.
   {:tip}
11. When your backup set is configured the way that you want it, click **Next** to continue.
12. Leave the default settings in the next pane or customize the restore to your preference, then click **Run Restore**.
13. The files are restored when the Status displays **Restore completed** on the **Process Details** screen.
