---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restoring from a backup

Use these steps to complete a File restore with {{site.data.keyword.backup_full}}. To restore a system image, follow the [Windows BMR](restore-bmr-system-volume-image.html) instructions.

## Starting {{site.data.keyword.backup_notm}} portal

Remember to start your {{site.data.keyword.BluVPN}} connection to get access to the {{site.data.keyword.BluSoftlayer_full}} private network. The {{site.data.keyword.backup_notm}} portal link doesn't work otherwise.
{:important}

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}/catalog/){:new_window} and click the **menu** icon on the upper left. Select **Classic Infrastructure**.

   Alternatively, you can log in to the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Click **Storage** > **Backup** to display the servers with backup service.
3. Select the server where the files to be restored are located. Click the arrow to reveal the {{site.data.keyword.backup_notm}} portal link.
4. Click **{{site.data.keyword.backup_notm}} portal** to start the {{site.data.keyword.backup_notm}} portal client in your browser.

## Restoring your data

1. In the navigational pane on the left, click **All Agents**.
2. Click the Agent to display the Jobs.
3. Click the Job that contains the data that you want.
4. Click **Run Restore**.
5. Select the restore source.
6. Select the backup version.
7. Enter the encryption password.
8. Click **Next** to continue.
9. Select the check boxes next to the files and directories that you want to include. Then, click **Include** to save your choices.
10. You can further filter your selections by using the window that appears, or click **OK** to use the selections you made as-is.
After you included your file and directory choices, the files can no longer be selected in the **Data Files** pane. They are displayed in the **Backup Set** pane on the right.

   You can repeat step 10 to add more files or to remove files you added previously (by using **Exclude**). You can also use **Remove** to delete any line item from the **Backup Set** pane.
   {:tip}

11. When your backup set is configured the way that you want it, click **Next** to continue.
12. Leave the default settings in the next pane or customize the restore to your preference. Then, click **Run Restore**.
13. The files are restored when the Status displays **Restore completed** on the **Process Details** screen.
