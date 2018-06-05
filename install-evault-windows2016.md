---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-05"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configure EVault on Windows 2016

Currently, EVault WebCC isn't officially supported on Windows 2016. Servers that are running on Windows 2016 have to use the Windows Central Control software.

## Installing the EVault backup agent

1. On the target server, open a browser session and enter the following URL to download the executable file
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
2. Double-click the downloaded file and click **Run** in the pop-up box that appears.
3. Select your language for the installation and click **OK**.
4. Select **Typical** for the Setup Type. Click **Next**.
5. At the Register Agent with Portal screen, select **Skip Registration**. 
6. Click **Next**, then, click **Finish**.

## Installing the EVault Software CentralControl

1. On the target server, open a browser session and enter the following URL to download the executable file.

   ```
   http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. Double-click the downloaded file and click **Run** in the pop-up box that appears.
3. Follow the installation steps for a Typical setup.

## Configuring CentralControl

This task is completed through a series of interactions while logged in to the server designated for the EVault backup service.

1. Remote control your server through RDP.
2. Start CentralControl.
3. In the workspace, right-click **Agent** and select **Agent Configuration**.
4. Click **New**.
5. Select **Register as a new computer** and click **Next**.
6. Enter network address and click **Add**, then click **Next**.
7. Enter the new port values and click **Add**, then **Next**.
8. In the Connection Settings screen, enter the number of seconds/minutes you want. 
9. In the Authentication screen, enter your credentials and click **Next**.
10. Registered Computers window displays the host name of your server. Click **Next**.
11.	The Vault Configuration Wizard has finished collecting your information, click **Finish** to complete the registration.


