---

copyright:
  years: 2014, 2018
lastupdated: "2018-04-06"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Getting Started with eVault Backup Services

Backups ensure that your data is safely stored outside of your device and protected if it is lost. EVault Backup is an automated agent-based backup system that is managed through the EVault WebCC browser-based management utility, providing users with a method to back up data between servers in one or more data centers on the {{site.data.keyword.BluSoftlayer_full}} Network. Administrators can set backups to follow an hourly, daily, weekly, or custom schedule that targets full systems, specific directories, or even individual files.  Additional plug-ins allow for compatibility with software like Microsoft Exchange and Microsoft SQL, as well as other types of third-party software and enables users to perform a Bare Metal Restore, when necessary.

## Accessing and Viewing EVault Backup Storage Details in {{site.data.keyword.slportal}}

Storage details regarding your EVault Backup service may be viewed using the {{site.data.keyword.slportal}} at any time. Details that may be viewed include the password, storage address and usage associated with the selected EVault Backup service. 

1. To access the **EVault Backup Storage** screen in the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} log in using your unique credentials.
2. Click on **Storage** and select **Backup** from the drop-down list.
2. Click anywhere on the row for the desired EVault Backup to view its storage details. From this view, the Password is not visible. Proceed to the next step to view the password associated with your EVault Backup service.
3. Click the **Show** check box next to the **Password** field to view the password for the selected EVault Backup service.

For many {{site.data.keyword.BluSoftlayer_full}} products and services, the password storage feature within the {{site.data.keyword.slportal}} is used solely for storage or tracking of the password and changes made to it within the {{site.data.keyword.slportal}} are not applied to the product or service. This is _not_ the case for EVault Backup. Changes made to the EVault Backup password within the {{site.data.keyword.slportal}} will be made to the service itself. Please make changes while keeping in mind that they will impact your service directly. To reset your password, follow the steps in [How to Change an EVault Backup password in the {{site.data.keyword.slportal}}](/docs/infrastructure/Backup/change-password-evault-backup-service.html).

## Accessing WebCentralControl (WebCC) for EVault Backup

WebCentralControl (WebCC) is the client used when interacting with any EVault Backup service offered by  {{site.data.keyword.BluSoftlayer_full}}. WebCC is a browser-based client run on our private network that allows for full control of any EVault Backup service, including configuration and restores. Follow the steps below to access WebCC for EVault Backup.

1. Access the Private Network over VPN. <br/>
    **Note**: WebCC cannot be accessed over the public network. A VPN connection must be established in order to access WebCC.
2. Access the EVault Backup Storage screen in the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
3. Click anywhere on the row for the desired EVault Backup to expand the view.
3. Click **WebCC Login** to launch the WebCC client in your browser.

## What Happens Next

After accessing WebCC over the private network, actions may be taken on the EVault Backup service. WebCC's systems are fully documented and support for the application is accessible within WebCC. Refer to [Find Instructions to Interact with EVault Backup in WebCC](/docs/infrastructure/Backup/find-instructions-interact-evault-backup-webcc.html) for more information on accessing WebCC's support documentation.


