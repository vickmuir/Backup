---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-14"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Installing the EVault Backup Client in Windows

Installing the EVault Backup client in Windows is completed through a series of interactions while logged in to the server designated for the EVault backup service. Follow the steps below to install the EVault backup client in Windows.

**Note**: Windows 2016 isn't supported currently.

## Log in to the target device server

1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} and select **Devices** > **Device List** from the main menu to see the list of available server devices.
2. Find the device for which you purchased the EVault service, and make note of its public IP address.
3. Click the right-pointing expansion arrow to reveal more information about the device, including the user name and password. If the password isn't displayed, clicking the **Show Password** check box reveals it. 
4. Log in to the target device using Remote Desktop Connection.

## Download the EVault Client

1. On the target server, open a browser session and enter the following URL to download the executable file for the EVault backup client. <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}
  
2. Double-click the downloaded file and click **Run** in the pop-up box that appears.


## Install and Register the EVault Agent
 
1. Enter the Network address: <br />
  ```
  ev-webcc01.service.softlayer.com
  ```
  {: pre}
  
2. Enter the EVault backup user name in the **User name** field. 
3. Enter the EVault backup password in the **Password** field. 
6. Click **Next** 
7. Click **Install** to complete the installation.

## Next steps

Log into WebCC to configure and manage your backup agents. Refer to the [Getting Started Tutorial](index.html#configuring-evault-agent-in-webcc) for instructions.
