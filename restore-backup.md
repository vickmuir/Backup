---

copyright:
  years: 1994, 2019
lastupdated: "2019-09-16"

keywords: IBM Cloud backup, EVault, Carbonite, backup, restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:shortdesc: .shortdesc}

# Restoring from a backup
{: #simplerestore}

Use these steps to complete a File restore with {{site.data.keyword.backup_full}}. To restore a system image, follow the [Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR#restoreBMR) instructions.
{:shortdesc}

## Starting WebCC
{: #startWebCCsimple}

Remember to start your {{site.data.keyword.BluVPN}} connection to get access to the {{site.data.keyword.cloud}} private network. The WebCC link doesn't work otherwise.
{:important}

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}){: external}. From the Navigational Menu, select **Classic Infrastructure**.
2. Click **Storage** > **Cloud Backup** to display the servers with backup service.
3. Select the server where the files to be restored are located. Click the arrow to reveal the WebCC link.
4. Click **WebCC** to start the WebCC client in your browser.

## Restoring your data

1. On the navigation, click **Computers**. The computers page shows the registered computers and environments. Expand the server that you want to restore to a previous state.
2. To start the job, click **Select Actions** and click **Restore**.
3. 
9. Select the check boxes next to the files and directories that you want to include. Then, click **Include** to save your choices.
10. You can further filter your selections by using the window that appears, or click **OK** to use the selections you made as-is.
After you included your file and directory choices, the files can no longer be selected in the data files pane. They are displayed in the backup set pane.

   You can repeat step 10 to add more files or to remove files you added previously (by using **Exclude**). You can also use **Remove** to delete any line item from the **Backup Set** pane.
   {:tip}

11. When your backup set is configured the way that you want it, click **Next** to continue.
12. Leave the default settings in the next pane or customize the restore to your preference. Then, click **Run Restore**.
13. The files are restored when the Status displays **Restore completed** on the **Process Details** screen.
