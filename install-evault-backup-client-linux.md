---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:codeblock: .codeblock}
{:pre: .pre}
{:new_window: target="_blank"}

# Installing the EVault Backup Client in Linux 

Installing the EVault backup client on a Linux-based operating system can be done through a series of commands in the shell or the terminal within the OS. This procedure outlines the steps that are required to install the EVault backup client on any of the following Linux-based operating systems:

- RedHat Enterprise Linux
- CentOS
- CloudLinux

After you completed the procedure, the automated process registers the Agent service with WebCC, then download and install the files that are needed to run the service.

>**Note** - If you purchased EVault when Ordering a Server in the {{site.data.keyword.slportal}}, then the software is automatically installed for you. You don't need to use the procedures that are described in this document.

If you purchased EVault as an Upgrade in the {{site.data.keyword.slportal}}, follow these steps to install the software.

## Logging in to the target device server

1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} and select **Devices** > **Device List** from the main menu to see the list of available server devices.
2. Find the device for which you purchased the EVault service, and make a note of its public IP address. 
  - This IP address is to be used in following steps when you log in to the device from a UNIX or Linux command line. Replace <publicIpAddress> with the actual public IP address in the command that is shown in Step 4. 
3. Click the right-pointing arrow to display more information about the device, including the user name and password. 
  - If the password is not displayed, you can reveal it by clicking the **Show Password**. The user name and password are used in the next step to log in to the test device.  Replace `<user name>` with the actual user name.
4. Log in to the target device by entering the following command from a UNIX or Linux command line:
   ```
   ssh <user name>@<publicIpAddress>
   ```
   {: pre}
   
   >**Note** - If you didn't log in to this server with this user name before, you are presented a message about the authenticity of the host. You are also asked whether you want to continue. Reply with **yes** to continue.
5. You are prompted to enter the password unless you set up ssh keys for accessing this server before.

## Updating Linux to prepare for installing the EVault client (RedHat Linux only)
>**Note** - This step is required for RedHat Linux, but optional for other Linux distributions.

- Run the following command at the server prompt:
  ```
  yum update
  ```
  {: pre}
   
  If you're prompted, confirm that the download size is okay. The update proceeds and displays a "Complete!" message when it finishes.

## Getting the EVault Install Script

- Run the following command at the server prompt:
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}
   
## Running the EVault Install Script

1. Run the following command at the server prompt.
   ```
   sh ./evault_manual.sh
   ```
   {: pre}

2. Enter your WebCC user name and password.     
   >**Note** - Refer to the [Getting started with backup services](/docs/infrastructure/Backup/index.html) article for instructions to view the EVault backup user name and Password.
3. After the user name and password, no further input is required, even though there are some prompts that are written to the screen as the installation proceeds. These prompts can be safely ignored. They are being produced by a subscript, which is started by the `evault_manual.sh` script. The `evault_manual.sh` script provides the input for these prompts.
4. When messages similar to the following appear, the installation is complete:
   ```
   Starting VVAgent: [  OK  ]
   Starting buagent: [  OK  ]
   ```
   {: codeblock}
   
## Verifying that the Installation Succeeded

1. Verify that the message "Registered to The Portal." appears in the installation output. The verification can be done by looking for the message on screen or by inspecting the output of the following command:
   ```
   grep 'Registered'  /opt/BUAgent/Install.log
   ```
   {: pre}

2. Run the following command and observe the output.
   ```
   service vvagent status
   ```
   {: pre}
   
   The following messages are displayed.
   ```
   VVAgent is running (PID xxxxx).
   buagent is running (PID xxxxx).
   ```
   {: codeblock}
   
  >**Note** - The process IDs represented by `xxxxx` varies with each installation. 
  
**Next steps**

Log in to WebCC to configure and manage your backup agents. Refer to the [Getting Started Tutorial](index.html#configuring-evault-agent-in-webcc) for instructions.
