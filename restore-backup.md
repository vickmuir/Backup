---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-22"

---
{:new_window: target="_blank"}

# Restore from a Backup

This article provides the steps that are needed to complete a File restore by using EVault. To restore a system image, follow the [Windows BMR](restoring-evault-bmr-system-volume-image.html) instructions.

## Start WebCC

**Note**: Remember to start your {{site.data.keyword.BluVPN}} connection to get access to the {{site.data.keyword.BluSoftlayer_full}} private network or the WebCC link won't work.

1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} and click **Storage** > **Backup** from the main menu to display the servers with EVault backup service.
2. Select the server where the files to be restored are located. Click the arrow to reveal the WebCC link.
3. Click **WebCC** to start the WebCC client in your browser.

## Restore your data

1. In the navigational pane on the left, click **All Agents**.
2. Click the Agent to display the Jobs.
3. Click the Job containing the backup that you want.
4. Click **Run Restore**.
5. Select a restore source.
6. Select **Restore from a single safeset** or **Restore from the safeset entered in the textbox below**. Both options have the same effect.
7. Select a backup version or enter the safeset number (The safeset number is the first number in the drop-down selection)
8. Enter the encryption password.
9. Click **Next** to continue.
10. Select the check boxes next to the files and directories that you want to include, then click **Include** to save your choices.
11. You can further filter your selections by using the window that appears, or click **OK** to use the selections you made as-is. <br/>
After you included your file and directory choices, the files can no longer be selected in the **Data Files** pane. They are displayed in the **Backup Set** pane on the right-hand-side of the screen. <br/>**Note**: You can repeat step 10 to add more files or to remove files you added previously (by using **Exclude**). <br/>You can also use **Remove** to delete any line item from the **Backup Set** pane.
12. When your backup set is configured the way that you want it, click **Next** to continue.
13. Leave the default settings in the next pane or customize the restore to your preference, then click **Run Restore**.
14. The files are fully restored when the Status displays **Restore completed** on the **Process Details** screen.
