---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:codeblock: .codeblock}
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Installing the Backup Client in Linux

Installing the {{site.data.keyword.backup_full}} client on a Linux-based operating system can be done through a series of commands in the shell or the terminal within the OS. This procedure outlines the steps that are required to install the {{site.data.keyword.backup_notm}} client on any of the following Linux-based operating systems:

- RHEL
- CentOS
- CloudLinux

After you completed the procedure, the automated process registers the Agent service with {{site.data.keyword.backup_notm}} portal, then download and install the files that are needed to run the service.

If you purchased {{site.data.keyword.backup_notm}} when you ordered a server through the the [{{site.data.keyword.cloud_notm}} catalog](https://{DomainName}/catalog/){:new_window} or the {{site.data.keyword.slportal}}, then the software is automatically installed for you. You don't need to use the procedures that are described in this document.
{:tip}

If you purchased {{site.data.keyword.backup_notm}} as an upgrade in the {{site.data.keyword.slportal}}, follow these steps to install the software.

## Logging in to the target device server

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}/){:new_window} and click the **menu** icon on the upper left. Select **Classic Infrastructure**.<br/>
   Alternatively, you can log in to the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Select **Devices** > **Device List** from the main menu to see the list of available server devices.
3. Find the device for which you purchased the {{site.data.keyword.backup_notm}} service, and make a note of its public IP address.
  - This IP address is to be used in following steps when you log in to the device from a UNIX or Linux command line. Replace <publicIpAddress> with the actual public IP address in the command that is shown in Step 4.
4. Click the right-pointing arrow to display more information about the device, including the user name and password.
  - If the password is not displayed, you can reveal it by clicking the **Show Password**. The user name and password are used in the next step to log in to the test device. Replace `<user name>` with the actual user name.
5. Log in to the target device by entering the following command from a UNIX or Linux command line.
   ```
   ssh <user name>@<publicIpAddress>
   ```
   {: pre}

   If you didn't log in to this server with this user name before, you are presented a message about the authenticity of the host. You are also asked whether you want to continue. Reply with **yes** to continue.
   {:note}

6. You are prompted to enter the password unless you set up ssh keys for accessing this server before.

## Updating the OS to prepare for the installation (RHEL only)

This step is required for RHEL, but optional for other Linux distributions.
{:tip}

- Run the following command at the server prompt.
  ```
  yum update
  ```
  {: pre}

  If you're prompted, confirm that the download size is okay. The update proceeds and displays a "Complete!" message when it finishes.

## Getting the Install Script

- Run the following command at the server prompt.
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}

## Running the Install Script

1. Run the following command at the server prompt.
   ```
   sh ./evault_manual.sh
   ```
   {: pre}

2. Enter your {{site.data.keyword.backup_notm}} portal user name and password.

   For more information about viewing the {{site.data.keyword.backup_notm}} user name and password, see [Getting started with backup services](index.html#accessing-and-viewing-ibm-cloud-backup-storage-details).
   {:tip}

3. After the user name and password, no further input is required. The prompts that are written to the screen as the installation proceeds can be safely ignored.

   They are being produced by a subscript, which is started by the `evault_manual.sh` script. The `evault_manual.sh` script provides the input for these prompts.
   {:note}

4. The installation is complete when the following messages appear.

   ```
   Starting VVAgent: [  OK  ]
   Starting buagent: [  OK  ]
   ```
   {: codeblock}

## Verifying that the Installation Succeeded

1. Verify that the message "Registered to The Portal" appears in the installation output. The verification can be done by looking for the message on screen or by inspecting the output of the following command.
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

  The process IDs that are represented by `xxxxx` varies with each installation.
  {:tip}

**Next steps**

Log in to {{site.data.keyword.backup_notm}} portal to configure and manage your backup agents. For more information, see the [Getting Started Tutorial](index.html#configuring-the-backup-agent-and-the-backup-schedule) and [Configuring simple file-level backup on Linux](configure-simple-file-backup-linux.html).
