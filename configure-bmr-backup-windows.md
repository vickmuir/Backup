---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud backup, EVault, Carbonite, backup, configure BMR, bmr plug-in, bmr plugin, configuration

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configuring BMR backup job
{: #configureBMR}

You need to purchase the BMR plug-in to create a BMR backup. BMR is available only for Windows Bare Metal Servers. No BMR option is available for VSI. For more information, see [Learn about the Bare Metal Restore plug-in](/docs/infrastructure/Backup?topic=Backup-BMRplugin#BMRplugin)
{:important}

## Starting {{site.data.keyword.backup_notm}} portal
{: #startWebCCBMR}

You need to be connected to the {{site.data.keyword.cloud}} private network to be able to start {{site.data.keyword.backup_notm}} portal.
{:important}

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}){: external}. From the Navigational Menu, select **Classic Infrastructure**.
2. Click **Storage** > **Cloud Backup** to display the servers with backup services.
3. Select the server where the files to be backed up are located. Click the expansion arrow to reveal the {{site.data.keyword.backup_notm}} portal link.
4. Click **{{site.data.keyword.backup_notm}} portal Login** to start the portal client in your browser.

   If {{site.data.keyword.backup_notm}} portal doesn't start, you might have a problem with your VPN connection. You might also see a message that says the form you’re sending isn’t secure. It is expected - proceed by sending the form.
   {:tip}

## Configuring a BMR backup job

1. In the navigation, click **All Agents** to display current {{site.data.keyword.backup_notm}} Agents.
2. Click **This is a new Agent I would like to configure**.
3. Enter a Job Name and a Job Description for the job that you're creating.
4. For **Backup Source Type**, select the file system type, then click **Next**
5. The **Job Type Selection** menu is displayed. Check the box next to **Bare Metal Restore**, and click **Next** to continue.
6. Click **Yes** on the Confirmation windows.
7. The screen shows that the new job is now in the backup set. Click **Next**.
8. The screen displays encryption options and advanced backup options. Normally these options aren't needed. Click **Next**.
9. On the **Create a schedule** page, you have two choices.
   - Click **Next** to create a manual job, and proceed to running your new job.
   - Click **Add** to schedule a time-based backup job.
     1. Select the days and the time of day to run your backups.
     2. Select your Retention Scheme.

        For more information about Retention Schemes, see the [FAQ](/docs/infrastructure/Backup?topic=Backup-faqs).
        {:tip}
     3. After you configured your backup schedule, click **Ok** to save it. Your scheduled job is added to the list of scheduled jobs.
10. Select a vault for your backup job, and click **Save Changes**.


## Running a BMR backup job

  - If you scheduled a time-based backup job, you don't need to do anything else. Your job runs automatically as scheduled.
  - If you set up a manual job (without a time-based schedule), you can run it by selecting its row in the job list and click **Run backup**. <br/> As with time-based jobs, you can choose the **Retention Scheme** and the **Advanced backup options**. After you made your configuration choices, click **Start backup** to start the job.
