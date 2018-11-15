---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-27"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Installing the Exchange plug-in

The Exchange plug-in is installed with the Windows Agent on the host. Through the WebCC portal, you can configure jobs, back up Exchange databases to a secure, remote vault, and restore Exchange databases. The plug-in integrates into the existing architecture.

**Capabilities provided**

- Ability to back up and restore Microsoft Exchange databases.

## Ordering the plug-in

1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Click **Storage** > **Backup**.
3. Select your EVault account and click **Order plug-ins**.
4. Select **EVault plug-in - Exchange** and click **Continue**.
5. Enter your Promo Code if you have one, and click **Recalculate**.
6. The updated charges are displayed. Review your order.
7. Check the box to indicate that you read and accept the Third-party Service Agreements.
8. Click **Place Order**.

## Installing the Exchange plug-in

The Exchange plug-in is installed during the Windows Agent 64-bit installation. The plug-in can be installed at the same time as the Agent or it can be installed later, by rerunning the installation with the **Modify** selection.

Before you install the plug-in for your Microsoft Windows server, stop both EVault services in `services.msc`.
{:important}

1. Browse to `c:\installs\evault` folder and run the .exe file with the higher revision number.
2. At the language screen, click **OK**
3. At the welcome screen, click **Next**
4. Select the **Modify installation**, and click **Next**.
5. Select the **Leave Unchanged**, and click **Next**.
6. At the custom setup screen, select each plug-in that you purchased.
7. Select **This feature will be installed on ...**, then click **Next**.
8. Select **Keep my current registration**, and click **Next**.
9. Click **Install**.
10. When installed, check to ensure that both services are enabled and running.
11. If WebCC is able to access and view the database, then the installation was successful.

## Downloading the user guide

Connect to the {{site.data.keyword.BluSoftlayer_full}} network with {{site.data.keyword.BluVPN}} so that you can download the EVault Agent v8.0 for Microsoft Windows (64-bit) - Exchange plug-in Guide.pdf from [Downloadable Documentation](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}. The guide describes how to back up and restore Microsoft Exchange databases by using the Exchange plug-in. The guide also describes how to share a DR backup safeset. With a DR backup safeset, you can restore specific mailboxes, messages, or other objects to a .pst file by using the Granular Restore for Microsoft Exchange application.
