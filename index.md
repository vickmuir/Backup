---

copyright:
  years: 2014, 2018
lastupdated: "2018-06-05"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Getting started with EVault backup services

Backups ensure that your data is safely stored outside of your device and protected if it's lost. EVault Backup is an automated agent-based backup system that is managed through the EVault WebCC browser-based management utility, providing users with a method to back up data between servers in one or more data centers on the {{site.data.keyword.BluSoftlayer_full}} Network. Administrators can set backups to follow an hourly, daily, weekly, or custom schedule that targets full systems, specific directories, or even individual files. Additional plug-ins allow for compatibility with software like Microsoft Exchange and Microsoft SQL, as well as other types of third-party software and enables users to perform a Bare Metal Restore, when necessary.

## Ordering EVault 

There are two ways to purchase EVault backup service:

- Purchase EVault when Ordering a Server
- Purchase EVault as an Upgrade

### Purchase EVault when ordering a server

1. Log in to [The IBM Cloud catalog](https://console.bluemix.net/catalog/){:new_window} or the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Order a monthly bare metal server. You can learn more about ordering bare metal servers [here](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html){:new_window}.
3. You are redirected to the manage portal to complete the order. <br/>
  **Note**: EVault backup service isn't available when ordering an hourly billed server. However, the service can be added later as an upgrade. 
4. Under **Add-ons** section, choose one of the EVault options (other than "None").
6. At the bottom of the page, click **Add to Order**. The Checkout page is displayed.
7. On the **CHECKOUT** page, find the Host and Domain Names section and enter host and domain names. You can choose any host name and Domain you like.
8. On the right-hand-side of the **CHECKOUT** page, click the **Cloud Service terms** and the **Third-Party Service Agreement** check boxes.
9. Confirm or enter your payment information and click **Submit Order**. You are redirected to a screen with your provisioning order number. You can print the screen because it's also your provisioning order receipt. <br/>**Note**: You can also save this order without purchasing by clicking **Save as Quote**.

A series of emails are sent to your administrator: acknowledgment of the provisioning order, provisioning order approval and processing, and provisioning complete. The provisioning complete email includes a link to your *Device Details* page after you login to {{site.data.keyword.cloud_notm}}. You can also log directly in to the {{site.data.keyword.slportal}}.

**Confirm the EVault service purchase**
1. In the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}, select **Devices** > **Device List** from the main menu. 
2. Locate the new server you ordered.
  - If there's clock icon next to the url, you'll need to wait to continue with the EVault purchase confirmation. You can refresh the page to see an updated status on your new server. When the clock icon is no longer present, you can proceed with the next steps to confirm the EVault service purchase.
  - When the clock icon is no longer showing for your server, click the link (the server's url) to go to the **Device Details** page. 
3. Click the **Storage** tab to display the EVault information.
4. Inspect the EVault section and verify that the size selected during the EVault purchase process is displayed next to the EVault link.

### Purchase EVault as an upgrade

**Select a server on which to install EVault**
1. Log in to [The IBM Cloud catalog](https://console.bluemix.net/catalog/){:new_window} or the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Select **Devices** > **Device List** from the main menu. Find the device for which you want to add EVault service.
3. Click on the Device name to go to the Device Details page.

**Add (purchase) EVault service**
1. Click on the **Storage** tab and locate the EVault section near the bottom of the page.
2. Click the **Add** link.
3. In the popup, select a location or accept the default and select a size.
4. click **Continue**
5. Click the check box if you agree with the terms and conditions.
6. Click **Place Order**.

**Confirm the EVault service purchase**
1. Refresh the **Device Details** page, and ensure that the **Storage** tab is selected.
2. Inspect the EVault section and verify that the size selected during the EVault purchase process is displayed next to the EVault link. <br /> **Note**: If the EVault storage size continues to show a capacity of zero, a second page refresh may be needed. 

## Accessing and viewing EVault backup storage details in {{site.data.keyword.slportal}}

Storage details regarding your EVault backup service may be viewed using the {{site.data.keyword.slportal}} at any time. Details that may be viewed include the password, storage address and usage associated with the selected EVault backup service. 

1. To access the **EVault Backup Storage** screen in the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} log in using your unique credentials.
2. Click on **Storage** and select **Backup** from the drop-down list.
2. Click anywhere on the row for the desired EVault Backup to view its storage details. From this view, the Password is not visible. Proceed to the next step to view the password associated with your EVault Backup service.
3. Click the **Show** check box next to the **Password** field to view the password for the selected EVault Backup service.

For many {{site.data.keyword.BluSoftlayer_full}} products and services, the password storage feature within the {{site.data.keyword.slportal}} is used solely for storage or tracking of the password and changes made to it within the {{site.data.keyword.slportal}} aren't applied to the product or service. This is _not_ the case for EVault Backup. Changes made to the EVault Backup password within the {{site.data.keyword.slportal}} will be made to the service itself. Make changes while keeping in mind that they will impact your service directly. To reset your password, follow the steps in [How to Change an EVault Backup password in the {{site.data.keyword.slportal}}](/docs/infrastructure/Backup/change-password-evault-backup-service.html).

## Installing the EVault agent

EVault Agent is supported on the following OS:

### Windows
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

### Linux
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - Red Hat Enterprise Linux 7.x
 - Red Hat Enterprise Linux 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

Please follow the instructions appropriate for your OS:
- [Installing the EVault Backup Client in Linux](install-evault-backup-client-linux.html)
- [Installing the EVault Backup Client in Windows](install-evault-backup-client-windows.html)
- [Installing the EVault Backup Client for Windows 2016](install-evault-windows2016.html)

## Accessing WebCentralControl (WebCC) for EVault backup

WebCentralControl (WebCC) is the client used when interacting with any EVault Backup service offered by  {{site.data.keyword.BluSoftlayer_full}}. WebCC is a browser-based client run on our private network that allows for full control of any EVault Backup service, including configuration and restores. Follow these steps to access WebCC for EVault Backup.

1. Access the Private Network over VPN. <br/>
    **Note**: WebCC can't be accessed over the public network. A VPN connection must be established in order to access WebCC.
2. Access the EVault Backup Storage screen in the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
3. Click anywhere on the row for the wanted EVault Backup to expand the view.
3. Click **WebCC Login** to start the WebCC client in your browser.

## Configuring EVault agent in WebCC

Once you have ordered your EVault service and the agent is installed on the server, you can start creating backups of your data. Follow these steps to configure your agent, retention schedule and start your first backup job.

1. Log in to WebCc.
2. Click **All Agents**> **Unconfigured Agents**.
3. Click **This is a new Agent I would like to configure** link. Step through the process and specify the following:
   1. Agent configuration - provide agent description, click **Next**.
   2. Job type selection - enter job name, job descrption, and backup source type, click **Next**.
   3. Selection - select directories and click **Include...**
   4. Options - provide passwords
   5. Schedule - click **Add** to create a schedule, click **Next**.
   6. Select the default vault, click **OK**.
   7. Click **Save**.
4. Create a retention schedule:
   1. Select **Edit** > **Agent Settings**.
   2. Click **Add**.
   3. Fill in your retention details.
   4. Click **OK**.
   5. Click **Save**.
   **Note** - Read more about how Retention Schemes work [here](evault-backup-faq.html#how-do-the-retention-schemes-work-)
5. Run the agent and start a backup.
   1. Click **All Agents**, then select the agent you have just configured.
   2. Click **Run Backup**.
   3. Confirm Destination and select a retention scheme.
   4. Click **Start Backup**. You can view the backup details while the process is running.
   5. When the backup is complete, click **Close**.
   
**Note**: Read more about how you can configure simple File-level backups on Linux [here](configure-simple-file-backup-linux.html).

## What happens next

WebCC's systems are fully documented and support for the application is accessible within WebCC. Click **Help** in the upper right corner, indicated by a white question mark in a blue circle. Click any article or topic in the navigation bar on the left side of the pop-up box to view more information.


