---

copyright:
  years: 1994, 2018
lastupdated: "2018-11-12"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Configuring BMR backup job on Windows

**Prerequisite**

You need to purchase BMR plug-in to create a BMR backup. BMR is available only for Windows Bare Metal Servers. No BMR option is available for VSI.
{:important}

## Starting WebCC

You need to be connected to the {{site.data.keyword.BluSoftlayer_full}} private network to be able to start WebCC.
{:important}

1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} and click **Storage** > **Backup** from the main menu to display the servers with EVault backup service.
2. Select the server where the files to be backed up are located. Click the right-pointing expansion arrow to reveal the WebCC link.
4. Click **WebCC Login** to start the WebCC client in your browser.


  If WebCC doesn't start, you might have a problem with your VPN connection. You might also see a message that says the form you’re sending isn’t secure. It is expected - proceed by sending the form.
  {:tip}

## Configuring a BMR backup job

1. In the left navigation pane, click **All Agents** to display current backup agents.
2. Click **This is a new Agent I would like to configure**.
3. Enter a Job Name and a Job Description for the job you're configuring/creating.
4. For **Backup Source Type**, select the file system type you want to back up from the list, then click **Next**
5. The **Job Type Selection** menu is displayed. Check the box next to **Bare Metal Restore** and click **Next** to continue.
6. Click **Yes** on the Confirmation windows.
7. The screen shows that the new job is now in the backup set. Click **Next**.
8. The screen displays encryption options and advanced backup options. Normally these options aren't needed. Click **Next**.   
9. On the **Create a schedule** page, you have two choices.
   - Click **Next** to create a manual job, and proceed to running your new job
   - Click **Add** to schedule a time-based backup job.
     1. Select the days and the time of day to run your backups.
     2. Select your Retention Scheme. For more information about Retention Schemes, see [the FAQ](faqs.html).
     3. After you configured your backup schedule, click **Ok** to save it. Your scheduled job is added to the list of scheduled jobs.
10. Select a vault for your backup job, and click **Save Changes**.


## Running a BMR backup job

  - If you scheduled a time-based backup job, you don't need to do anything else. Your job runs automatically as scheduled.
  - If you set up a manual job (without a time-based schedule), you can run it by selecting its row in the job list and click **Run backup**. <br/> As with time-based jobs, you can choose the **Retention Scheme** and the **Advanced backup options**. After you made your configuration choices, click **Start backup** to start the job.
