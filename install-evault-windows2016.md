---

copyright:
  years: 1994, 2018
lastupdated: "2018-11-15"

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:new_window: target="_blank"}

# Configuring EVault on Windows 2016

## Installing the EVault Software agent

1. On the target server, open a browser session and enter the following URL to download the executable file
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}

   Install the agent of version 8.30 and later.
   {:note}
2. Double-click the downloaded file and click **Run** in the window that appears.
3. Select your language for the installation and click **OK**.
4. Click **Next** to begin.
5. Read the Terms and Conditions, and select **I accept the terms in the license agreement**. Then, click **Next**.
6. Select **Typical** for the Setup Type. Click **Next**.
7. At the Register Agent with Portal screen, select **Skip Registration**. Click **Next**
8. On the next screen, click **Install**.
9. When the installation is complete, click **Finish**.

## Installing the EVault Software CentralControl 8.30

1. On the target server, open a browser session and enter the following URL to download the executable file.

   ```
   http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. Double-click the downloaded file and click **Run** in the window that appears.
3. Follow the installation steps for a **Typical** setup.
   1. When you are prompted to add a desktop shortcut, select **Yes**. Click **Next**.
   2. After you read the Software license agreement, select **ACCEPT**. Click **Next**.
   3. Keep the default destination folder and click **Next**.
4. When the installation is complete, check **Launch EVault Software Central Control**. Click **Finish**.


## Configuring Central Control

This task is completed through a series of interactions while logged in to the server designated for the EVault backup service.

1. Remote control your server through RDP.
2. Start Central Control.
3. In the workspace, right-click **MyAgent** and select **Agent Configuration**.
4. On the Vaults tab, click **New**. The Vault Configuration Wizard appears. Click **Next**.
5. Select **Register as a new computer** and click **Next**.
6. Enter the vault name in the Profile name field. The vault name can be obtained from the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
6. Enter network address (the IP address of the assigned vault) and click **Add**. Then, click **Next**.
7. Enter the new port values and click **Add**, then **Next**.
8. In the Connection Settings screen, enter the number of seconds/minutes you want. Keep the **Enable over the wire encryption for transmissions to and from the vault** box checked. Click **Next**.
9. In the Authentication screen, enter your credentials and click **Next**.
10. Registered computers window displays the host name of your server. Click **Next**.
11.	Click **Finish** to complete the configuration.


## Creating the Retention Schemes

1. Remote control your server through RDP.
2. Start Central Control.
3. In the workspace, right-click **MyAgent** and select **Agent Configuration**.
4. Click the **Retentions** tab. The Retention Wizard appears, click **Next**.
5. Enter the retention name. Click **Next**.<br/>

   The entry can be a maximum of 32 alphanumeric characters. Spaces are not allowed, but underscores (`_`) and dashes (`-`) can be used.
   {:tip}
6. Enter the online retention days and copies for this retention type. Then, click **Next**.<br/>

   The combination of retention days and copies is used to ensure that a minimum duration and a number of backups are retained.
   {:note}
7. Select **I do not want to create any archive backup copies**. Click **Next**.
8. Click **Finish** to complete the configuration of the retention scheme.


## Setting up the backup job

1. Remote control your server through RDP.
2. Start Central Control.
3. In the workspace, right-click **MyAgent** and select **New Job**.
4. On the welcome screen, click **Next**.
5. Select the backup source type.
6. Select **Unicode** for encoding. Click **Next**.
7. Select the destination where this job is targeted. Click **Next**.
8. Enter the name for the job and its description.<br/>

   The name must be 1 - 30 characters long. The name can contain letters, numbers, underscores (`_`), hyphens (`-`), and dollar signs (`$`).
   {:important}
9. Select the data sources. Click **Add**.
10. Specify processing and backup time options. Check **Quick file scanning** and enter the hours or minutes you want as your backup time window. Then, click **Next**.
11. Select encryption type (default setting is AES 256-bit) and enter your encryption password. Click **Next**
12. Select log options for your job. Check **Create log file**, and select **Automatically purge expired log files only**. Then, click **Next**
13. Select **Just exit from this wizard**, and click **Finish** to complete the configuration. The new job now appears under MyAgent.


## Running the EVault job

1. Remote control your server through RDP.
2. Start Central Control.
3. In the workspace, right-click **MyAgent** and select the agent that you created.
4. On the welcome screen, click **Next**.
5. Select the backup destination or an alternative location to seed the backup job. Click **Next**.<br/>

   For more information about multiple vaults, see [Multi-vaulting](multivaulting.html)
   {:tip}
6. Select the Quick file scanning option to avoid reading files that were not changed. Click **Next**.
7. Click **Finish** to complete the configuration and start the backup. A process information window appears that shows the status of the backup jon. When the backup job is done, click **Close**.
