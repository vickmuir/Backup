---

copyright:
  years: 2014, 2017
lastupdated: "2017-10-04"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Getting Started with Backup Services

## EVault Backup

EVault Backup is an automated agent-based backup system that is managed through the EVault WebCC browser-based management utility, providing users with a method to back up data between servers in one or more data centers on the {{site.data.keyword.BluSoftlayer_full}} Network. Administrators can set backups to follow an hourly, daily, weekly, or custom schedule that targets full systems, specific directories, or even individual files.  Additional plug-ins allow for compatibility with software like Microsoft Exchange and Microsoft SQL, as well as other types of third-party software and enables users to perform a Bare Metal Restore, when necessary.

### Accessing the EVault Backup Storage Screen in the {{site.data.keyword.slportal}}

You can interact with your EVault Backup service within the [{{site.data.keyword.slportal}}](https://control.softlayer.com//){:new_window}, through the Storage screen. Follow the steps below to access the Storage screen for EVault.

1. Access the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} using your unique credentials.
2. Select **Storage** > **Backup** from the navigation bar to access the EVault Backup screen.

### Viewing EVault Backup Storage Details in {{site.data.keyword.slportal}}

Storage details regarding your EVault Backup service may be viewed using the {{site.data.keyword.slportal}} at any time. Details that may be viewed include the password, storage address and usage associated with the selected EVault Backup service. Follow the steps below to view the storage details for your EVault Backup service.

1. Access the **EVault Backup Storage** screen in the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Click anywhere on the row for the desired EVault Backup to view its storage details. From this view, the Password is not viewable. Proceed to the next step to view the password associated with your EVault Backup service.
3. Click the **Show** check box next to the **Password** field to view the password for the selected EVault Backup service.

For many {{site.data.keyword.BluSoftlayer_full}} products and services, the password storage feature within the {{site.data.keyword.slportal}} is used solely for storage or tracking of the password and changes made to it within the {{site.data.keyword.slportal}} are not applied to the product or service. This is _not_ the case for EVault Backup. Changes made to the EVault Backup password within the {{site.data.keyword.slportal}} will be made to the service itself. Please make changes while keeping in mind that they will impact your service directly. To reset your password, follow the steps in [How to Change an EVault Backup password in the {{site.data.keyword.slportal}}](/docs/infrastructure/Backup/change-password-evault-backup-service.html).

### Accessing WebCentralControl (WebCC) for EVault Backup

WebCentralControl (WebCC) is the client used when interacting with any EVault Backup service offered by  {{site.data.keyword.BluSoftlayer_full}}. WebCC is a browser-based client run on our private network that allows for full control of any EVault Backup service, including configuration and restores. Follow the steps below to access WebCC for EVault Backup.

1. Access the Private Network over VPN. <br/>
    **Note**: WebCC cannot be accessed over the public network. A VPN connection must be established in order to access WebCC.
2. Access the EVault Backup Storage screen in the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
3. Click anywhere on the row for the desired EVault Backup to expand the view.
3. Click **WebCC Login** to launch the WebCC client in your browser.

### What Happens Next

After accessing WebCC over the private network, actions may be taken on the EVault Backup service. WebCC's systems are fully documented and support for the application is accessible within WebCC. Refer to [Find Instructions to Interact with EVault Backup in WebCC](/docs/infrastructure/Backup/find-instructions-interact-evault-backup-webcc.html) for more information on accessing WebCC's support documentation.

## R1Soft CDP

Continuous Data Protection (CDP) is a high-performance backup software created by R1Soft that allows for backup of both physical and virtual devices.

### About R1Soft Continuous Data Protection (CDP)

R1Soft Continuous Data Protection (CDP) Server Backup is fast, affordable server backup software for Windows and Linux, in both physical and virtual environments. It offers a unique solution - Virtual Full Backup, which leverages block-level backup technology that reduces backup windows from hours to minutes. Block-level backup assures unique disk blocks are stored only one time in backup storage, even across thousands of recovery points. The one-time storage allows users to keep recovery points longer and save space over existing full or incremental backups. Users can back up data as frequently as every 5 minutes with minimal impact to production systems.

Idera CDP consists of three main components: the CDP server, the agent and the database plugins, which are available for purchase separately from the first two components.  Because R1Soft CDP is a third-party backup solution, interactions with CDP take place entirely outside of {{site.data.keyword.BluSoftlayer_full}}'s proprietary interfaces; however, R1Soft CDP passwords may be tracked and stored within [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}. All other interactions with R1Soft CDP are documented on R1Soft's website.

### Backup Performance and Options

- High Performance Backups: Perform an initial replica of your data the first time your continuous data protection (CDP) policy runs. After the initial replica, R1Soft stores block level deltas, leading to shorter backup windows and reduced disk I/O.

- Bare-Metal Restore: Restores of large file systems can be performed significantly faster by bypassing the file system and streaming blocks directly to disk, making it a faster alternative to file-by-file restore in the event of disaster.

- Innovative Web Interface: Browse, download, and restore files from your recovery points using a Windows Explorer-style interface. You can also perform policy management and reporting and see the detailed progress of replication and restore jobs as they run.

- Data Retention Policy: Define a replication goal (e.g., every 15 minutes) and how many recovery points you will retain. Old recovery points are automatically merged and their storage is recycled.

### Retrieving an R1Soft CDP Username and Password

R1Soft Continuous Data Protection (CDP) credentials are found in one of two locations, based on how long the CDP has been active on the device and/or whether or not the CDP credentials were saved manually within the {{site.data.keyword.slportal}}. The CDP credentials default to the root username and credentials may be stored and tracked within the {{site.data.keyword.slportal}}, however, updates to the CDP password will not sync with the credentials stored in the {{site.data.keyword.slportal}}. Therefore, any changes to the CDP password must be manually entered within the {{site.data.keyword.slportal}}.

Follow these steps to retrieve the CDP credentials for a device.

1. Access the Device List in the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Determine if the CDP credentials have been manually changed. <br/>
   **Note**: CDP credentials can only be changed if CDP has been accessed.  If accessing CDP for the first time, the credentials have not been manually changed.
  - If the CDP credentials have been manually changed, then 
     - Click the Device Name to access the device.
     - Select the Passwords tab.
  - If the CDP credentials have **not** been manually changed, then
     - Proceed to Interact with a Device in the Snapshot View procedure and follow the instructions to **view the username and password** for a device.

**Note**:  Use the root username and password to log in to CDP unless the credentials have been manually changed.

### What Happens Next

Use the credentials for R1Soft CDP to log in to CDP on the device. If the credentials retrieved from the {{site.data.keyword.slportal}} do not allow for login, it is possible that the password was updated in R1Soft CDP but not recorded using the Password Tracking tool. To reset a lost password, use the KVM functionality for your device to access the CDP server remotely and manually reset the password. For more information on interacting with R1Soft CDP, we recommend using [R1Soft's Support Wiki](http://wiki.r1soft.com/display/CDP3/Enterprise+Edition){:new_window}.


