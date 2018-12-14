---

copyright:
  years: 2014, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Getting started with {{site.data.keyword.backup_notm}} services

Backups ensure that your data is safely stored outside of your device and protected if it gets lost. {{site.data.keyword.backup_full}} is an automated agent-based backup system that is managed through the {{site.data.keyword.backup_notm}} portal browser-based management utility. {{site.data.keyword.backup_notm}} provides users with a method to back up data between servers in one or more data centers on the {{site.data.keyword.BluSoftlayer_full}} network. Administrators can set backups to follow a daily, weekly, or custom schedule that targets full systems, specific directories, or even individual files. Extra plug-ins ensure compatibility with software like Microsoft Exchange and Microsoft SQL, other types of third-party software, and enable users to complete a Bare Metal Restore, when necessary.

## Ordering {{site.data.keyword.backup_notm}}

You can purchase {{site.data.keyword.backup_notm}} service in two ways.

- [Purchase {{site.data.keyword.backup_notm}} when you Order a Server](#purchasing-ibm-cloud-backup-when-you-order-a-server).
- [Purchase {{site.data.keyword.backup_notm}} as an Upgrade](#purchasing-ibm-cloud-backup-as-an-upgrade).

For more information about pricing, see [{{site.data.keyword.backup_notm}} storage ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/cloud/backup-and-restore){:new_window} and [{{site.data.keyword.backup_notm}} on IBM Cloud ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/cloud/evault/pricing){:new_window}.

### Purchasing {{site.data.keyword.backup_notm}} when you order a server

1. Log in to the [IBM Cloud catalog ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://{DomainName}/catalog/){:new_window} or the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}
2. Order a monthly bare metal server. For more information about ordering bare metal servers, see [Building a custom Bare Metal Servers](https://{DomainName}/docs/infrastructure/bare-metal/baremetal-provision.html){:new_window}.
   1. Select quantity, billing option. Enter host and domain names. You can choose any host name and domain that you like.

      {{site.data.keyword.backup_notm}} service isn't available when you're ordering an hourly billed server. However, the service can be added later as an upgrade.
      {:tip}
   2. Select location.
   3. Select Server configuration and OS Image type. You can also choose multiple add-ons.
   4. Under the **Storage Disks** section, click on **Add-ons** and select **{{site.data.keyword.backup_notm}} Backup**. Choose the option that matches what you need.
   5. Under **Network Interface**, select the Uplink Port Speed and any add-ons that you want.
3. On the right, review your order summary.
4. After you reviewed the terms and conditions, check the **I have read and agree to the Third-Party Service Agreements** box.
5. Click **Provision**. You are redirected to a screen with your provisioning order number. You can print the screen because it's also your provisioning order receipt.

   You can also save this order without purchasing by clicking **Save as Quote**.
   {:tip}

A series of emails is sent to your administrator: Acknowledgment of the provisioning order, Provisioning order approval and processing, and Provisioning complete. The Provisioning complete email includes a link to your *Device Details* page, that you can access after you log in to {{site.data.keyword.cloud_notm}}. You can also log directly in to the {{site.data.keyword.slportal}}.

#### Confirming the {{site.data.keyword.backup_notm}} purchase
1. In the [{{site.data.keyword.cloud_notm}} console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://{DomainName}/){:new_window}, click the **Menu** icon on the upper left. Select **Classic Infrastructure**.</br>
   Alternatively, you can log in to the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Click **Device** > **Device List**.
2. Locate the new server that you ordered.
  - If you see a clock icon next to the url, you need to wait to continue with the {{site.data.keyword.backup_notm}} purchase confirmation. You can refresh the page to see an updated status on your new server. When the clock icon is no longer present, you can proceed with the next steps to confirm the {{site.data.keyword.backup_notm}} service purchase.
  - When the clock icon is no longer showing for your server, click the link (the server's url) to go to the **Device Details** page.
3. Click the **Storage** tab to display the {{site.data.keyword.backup_notm}} information.
4. Inspect the {{site.data.keyword.backup_notm}} section, and verify that the size that was selected during the purchase process is displayed.

### Purchasing {{site.data.keyword.backup_notm}} as an upgrade

#### Select a server on which to install {{site.data.keyword.backup_notm}}

1. Log in to the [{{site.data.keyword.cloud_notm}} console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://{DomainName}){:new_window} and click the **Menu** icon on the top left. Select **Classic Infrastructure**.</br>
   Alternatively, you can log into the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Select **Devices** > **Device List** from the main menu. Find the device for which you want to add {{site.data.keyword.cloud_notm}} Backup service.
3. Click the Device name to go to the **Device Details** page.

#### Adding (purchasing) {{site.data.keyword.backup_notm}} service
1. Click the **Storage** tab, and scroll down to locate the {{site.data.keyword.backup_notm}} section.
2. Click the **Add** link.
3. In the window, select a location, and select a size.
4. Select Payment type, and click **Continue**
5. Enter the **Promo Code** if you have one, and click **Recalculate**.
6. Review your order, and click the link to read the terms and conditions.
7. Click the check box if you agree with the terms and conditions.
7. Click **Place Order**.

#### Confirming the {{site.data.keyword.backup_notm}} upgrade purchase
1. Refresh the **Device Details** page, and ensure that the **Storage** tab is selected.
2. Inspect the {{site.data.keyword.backup_notm}} section and verify that the size that was selected during the purchase process is displayed.

   If the backup storage size continues to show a capacity of zero, a second page refresh might be needed.
   {:tip}

## Accessing and viewing {{site.data.keyword.backup_notm}} storage details

The storage details of your {{site.data.keyword.backup_notm}} service can be viewed in the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}/catalog/){:new_window} and the {{site.data.keyword.slportal}} at any time. Details that can be viewed include the password, storage address, and usage that is associated with the selected {{site.data.keyword.backup_notm}} service.

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}){:new_window} and click the **Menu** icon on the top left. Select **Classic Infrastructure**.</br>
   Alternatively, you can log into the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Click **Storage**, and select **Backup** from the list.
2. Click anywhere on the row of the vault you want to view its storage details. From this view, the Password is not visible. Proceed to the next step to view the password that is associated with your {{site.data.keyword.backup_notm}} service.
3. Click the **Show** check box next to the **Password** field to view the password for the selected {{site.data.keyword.backup_notm}} service.

For many {{site.data.keyword.BluSoftlayer_full}} products and services, the password storage feature within the {{site.data.keyword.slportal}} is used solely for storage or tracking of the password. For those offerings, the changes that are made to them within the {{site.data.keyword.slportal}} aren't applied to the product or service.

It is _not_ the case for {{site.data.keyword.backup_notm}}. Changes that are made to the {{site.data.keyword.backup_notm}} password within the {{site.data.keyword.slportal}} are made to the service itself. When you change your password, keep in mind that it impacts your service directly. To reset your password, follow the steps in [How to Change an {{site.data.keyword.backup_notm}} password in the {{site.data.keyword.slportal}}](change-password.html).
{:important}

## Installing the {{site.data.keyword.backup_notm}} agent

{{site.data.keyword.backup_notm}} Agent is supported on the following OS.

**Windows**
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

**Linux**
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - RHEL 7.x
 - RHEL 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

Follow the instructions appropriate for your OS,
- [Installing the Backup Client in Linux](install-backup-client-linux.html)
- [Installing the Backup Client in Windows](install-backup-client-windows.html)
- [Installing the Backup Client in Windows 2016](install-backup-client-windows2016.html)
- [Installing the Backup Client in VMware](https://{DomainName}/docs/infrastructure/vmware/install-backup-client-vmware.html)

## Accessing {{site.data.keyword.backup_notm}} portal (formerly WebCC)

{{site.data.keyword.backup_notm}} portal is used to interact with any {{site.data.keyword.backup_notm}} service that is offered by {{site.data.keyword.BluSoftlayer_full}}. {{site.data.keyword.backup_notm}} portal is a browser-based client that runs on the {{site.data.keyword.BluSoftlayer_full}} private network and allows full control of any {{site.data.keyword.backup_notm}} service, including configuration and restores.

1. Access the Private Network over VPN.

   {{site.data.keyword.backup_notm}} portal can't be accessed over the public network. A VPN connection must be established first.
   {:important}
2. Access the Backup storage screen in the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
3. Click anywhere on the row of the {{site.data.keyword.backup_notm}} service that you want see to expand the view.
4. Click **{{site.data.keyword.backup_notm}} portal Login** to start the {{site.data.keyword.backup_notm}} portal client in your browser.

## Configuring the Backup agent and the backup schedule

After you ordered your {{site.data.keyword.backup_notm}} and the agent is installed on the server, you can start creating backups of your data. You can follow these steps to configure your agent, retention schedule and start your first backup job.

1. Log in to WebCc.
2. Click **All Agents**> **Unconfigured Agents**.
3. Click **This is a new Agent I would like to configure** link. Step through the process and enter the following information:
   1. Agent configuration - provide agent description, click **Next**.
   2. Job type selection - enter job name, job description, and backup source type, click **Next**.
   3. Selection - select directories and click **Include...**
   4. Options - provide passwords
   5. Schedule - click **Add** to create a schedule, click **Next**.
   6. Select the default vault, click **OK**.
   7. Click **Save**.
4. Create a retention schedule.
   1. Select **Edit** > **Agent Settings**.
   2. Click **Add**.
   3. Complete your retention details.
   4. Click **OK**.
   5. Click **Save**.

      For more information about Retention Schemes, see the [FAQ](faqs.html).
      {:tip}
5. Run the agent and start a backup.
   1. Click **All Agents**, then select the agent that you configured.
   2. Click **Run Backup**.
   3. Confirm Destination and select a retention scheme.
   4. Click **Start Backup**. You can view the backup details while the process is running.
   5. When the backup is complete, click **Close**.

For more information about File-level backups on Linux, see [Configuring Simple File-level Backup on Linux](configure-simple-file-backup-linux.html).
{:tip}

## Getting online help

{{site.data.keyword.backup_notm}} portal's systems are fully documented and support for the application is accessible within {{site.data.keyword.backup_notm}} portal. Click the white question mark in a blue circle that is located in the upper right for **Help**. Click any article or topic in the navigation bar on the left side to view more information.
