---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:new_window: target="_blank"}

# Configuring BMR Backup Job on Windows

## Prerequisite

You need to purchase BMR Plugin to perform a BMR backup. BMR is available only for Windows Bare Metal Servers. No BMR option is available for VSI.

## Launch WebCC
**Note**: You need to be connected to the {{site.data.keyword.BluSoftlayer_full}} private network to be able to start WebCC.
1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} and click **Storage** > **Backup** from the main menu to display the servers with EVault backup service. 
2. Select the server where the files to be backed up reside. Click the right-pointing expansion arrow to reveal the WebCC link.
4. Click **WebCC Login** to start the WebCC client in your browser.
  **Note**: If WebCC doesn't start, there may be a problem with your VPN connection. You may also see a message saying the form you’re sending isn’t secure. It’s expected - proceed by sending the form.
  
## Configure a BMR backup Job

1. In the left navigation pane, click **All Agents** to display current EVault Agents
2. Click **This is a new Agent I would like to configure**.
3. Enter a Job Name and a Job Description for the job you're configuring/creating.
4. For **Backup Source Type**, select the file system type you want to back up from the pull-down menu, then click **Next**
5. The **Job Type Selection** menu is displayed. Check the box next to **Bare Metal Restore** and click **Next** to continue.
6. Click **Yes** on the Confirmation windows.
7. The screen shows that the new job is now in the Backup set. Click **Next**.
8. The screen displays encryption options and advanced backup options. Normally these aren't needed. Click **Next** to proceed to the **Create a schedule** screen.   
9. On the **Create a schedule** page, click **Add** to schedule a time-based backup job or click **Next** to create a manual job.
  - If you choose to create a manual job, proceed to running your new job.
  - If you choose to schedule a time-based job, select the days and the time of day to run your backups.
  - Select your Retention Scheme. Read more about Retention Schemes [here](evault-backup-faq.html#how-do-the-retention-schemes-work-)
  - After you have configured your backup schedule, click **Ok** to save it. Your scheduled job is added to the list of scheduled jobs. 
10. Select a vault for your backup job, and click **Save Changes**.


## Run a BMR Backup Job
  - If you scheduled a time-based backup job, there are no further steps.  Your job will run automatically as scheduled.
  - If you set up a manual job (without a time-based schedule), you can run it by selecting its row in the job list and click **Run Backup**. <br/> As with time-based jobs, you can choose the **Retention Scheme** and the **Advanced Backup Options**. After completing your configuration choices, click **Start Backup** to start the job.
