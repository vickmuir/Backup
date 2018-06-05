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

# Installing the EVault Backup Client in Linux 

Installing the EVault backup client on a Linux-based operating system can be done through a series of commands in the shell or terminal within the OS. This procedure outlines the steps required to install the EVault backup client on any of the following Linux-based operating systems:

- RedHat Enterprise Linux
- CentOS
- CloudLinux

After completing the procedure, the automated process will register the Agent service with WebCC, then download and install the files needed to run the service. Follow the steps below to install the EVault Backup client to your Linux-based OS.

**Note**: If you purchased EVault when Ordering a Server in the {{site.data.keyword.slportal}}, then the software is automatically installed for you and you don't need to use the procedures described in this document.

If you purchased EVault as an Upgrade in the {{site.data.keyword.slportal}}, follow these steps to install the software.

## Log in to the target device server

1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} and select **Devices** > **Device List** from the main menu to see the list of available server devices.
2. Find the device for which you purchased the EVault service, and make note of its public IP address. It's to be used in following steps when logging in to the device from a UNIX or Linux command line. Replace <publicIpAddress> with the actual public IP address in the commands that follow. 
3. Click the right-pointing expansion arrow to reveal additional information about the device, including the user name and password.  If the password is not displayed, clicking the **Show Password** check box will reveal it. The user name and password will be used in the next step to log in to the test device.  Replace `<user name>` with the actual user name in the commands that follow.
4. Log into the target device using ssh by executing the following command from a unix or linux command line:
  ```
  ssh <user name>@<publicIpAddress>
  ```
  {: pre}
  
 **Note**: If you haven't logged into this server with this user name before, you'll be presented a message about the authenticity of the host, and you'll be asked if you want to continue.  Reply with **yes** to continue.
5. You'll be prompted to enter the password unless you have previously set up ssh keys for accessing this server.

## Update Linux to prepare for installing the EVault client (RedHat Linux only)
**Note**: This step is required for RedHat Linux, but optional for other Linux distributions.

- Execute the following command at the server prompt:
  ```
  yum update
  ```
  {: pre}
   
  If asked, confirm that the download size is okay. The update will proceed and displays a "Complete!" message when finished.

## Get the EVault Install Script
- Execute the following command at the server prompt:
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}
   
## Run the EVault Install Script
1. Run the following command at the server prompt:
  ```
  sh ./evault_manual.sh
  ```
  {: pre}

2. Enter your WebCC user name and password.     
  **Note**: Refer to the [Getting Started with Backup Services](/docs/infrastructure/Backup/index.html) article for instructions to view the EVaultbackup user name and Password.
3. After the user name and password, no further input is required, even though you will see some prompts written to the screen as the install proceeds. These prompts can be safely ignored. They are being produced by a sub-script which is invoked by the *evault_manual.sh* script.  The *evault_manual.sh* script provides the input for these prompts.
4. When messages similar to the following appear, the installation is complete:
  ```
  Starting VVAgent: [  OK  ]
  Starting buagent: [  OK  ]
  ```
  {: codeblock}
   
## Verify that the Installation Succeeded
1. Verify that the message "Registered to The Portal." appears in the installation output. This can be done by looking for the message on screen or by inspecting the output of the following command:
  ```
  grep 'Registered'  /opt/BUAgent/Install.log
  ```
  {: pre}

2. Execute the following command and observe the output: 
  ```
  service vvagent status
  ```
  {: pre}
   
  The following messages should be displayed:
  ```
  VVAgent is running (PID xxxxx).
  buagent is running (PID xxxxx).
  ```
  {: codeblock}
   
  **Note**: The process ids represented above by 'xxxxx' will vary with each installation. 
  
## Next steps

Log into WebCC to configure and manage your backup agents. Refer to the [Getting Started Tutorial](index.html#configuring-evault-agent-in-webcc) for instructions.
