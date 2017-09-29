---

copyright:
  years: 1994, 2017
lastupdated: "2017-09-28"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Restoring a Server with R1Soft CDP

Use this process to perform a [bare metal restore](http://wiki.r1soft.com/display/CDP/Bare-Metal+Restore){:new_window} to a {{site.data.keyword.BluSoftlayer_full}} public or private virtual server (VSI) in the case of a server failure that causes data or OS loss.

All file system blocks that have been backed up will be restored, including the OS and any files that were not excluded from backups. Do not follow this process if restoration of a subset of files is the objective; click [here](http://wiki.r1soft.com/display/CDP/Restoring+Files){:new_window} for the steps on how to restore files only.

## Preparing the R1Soft CDP Server

### Perform the following tasks on the R1Soft CDP server:

1. Open a browser window and log into R1Soft CDP server (the IP and admin passwords are available via the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}).
2. Click **Recovery Points** on the bottom left-hand side of the R1Soft CDP management portal.
3. Select the **Server** you wish to restore and the **Disk Safe** from which you wish to restore.
4. Locate the point from which you want to restore from the recovery points list.
5. Click **Bare Metal Restore** (the shield icon) to bring up the **Restoration Wizard**.
6. Click **Next** on the **Restoration Wizard**.
7. Select the filesystems to be restored and click **Next**.
8. Select the host to be restored to; this can be the original host, or an alternate one as designated by you. (Note that the steps within this procedure recover the same server.)
9. Click **Next**.
10. Chose the storage configuration to use (use what is in place on the server or choose one based on backups).
11. Select the **Partition Tables** you wish to use if you elected to choose the filesystem layout.
12. Map your filesystems to the correct block devices (C:\ = /dev/sda1, and so on) and click **Next**.
13. Check any restore options you wish - Reboot after restore, Check filesystem after restore - and click **Next**,
14. Verify you options and click **Restore** or go back to change your restoration options.

You should see a window with the status of the current restoration

## Preparing the device for restoration

### Perform the following steps to prepare the device to be restored:

1. Open a browser window and access [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Click **Devices**, **Device List** and select the device to be restored.
3. Click **Actions** and choose **Boot from image** to display a list of private images; choose **Public Images** from the drop-down menu at the top of the list.
4. Choose the appropriate R1Soft agent boot image for your version of R1Soft server (*r1soft-cdp-bootcd-server-4.0.0.iso*) and click **Boot From This Image**.
5. Click **Actions**, **KVM Console** from the Device Details page for the server being restored. Once console is up and the image has booted, you should see a Debian bootloader screen with some options.
6. Press **Enter** to boot using the default option.
7. Type netconfig from the r1soft-recovery prompt after the OS has booted up and press **Enter**.
8. Choose **Yes** to configure networking.
9. Enter the network configuration details from the **Device Details** page.
10. Click **Yes** when prompted to restart networking.
11. **Optional**: Type passwd root to set a root password for SSH logins and type service ssh start to allow SSH login, which may be useful if your KVM console is slow to respond.
12. Type service cdp-agent restart, which should start the CDP agent even if it is not already running.
13. Select **Boot From Image**. A frame will appear stating that the device is currently configured to boot from the *r1soft-cdp-bootcd-agent-4.0.0.iso* image. There will also be a question regarding unloading the image and returning to normal booting.
14. Click **Yes** and the server will reboot from the system disk

The server will run through a chkdsk or fsck process to verify the disk and may reboot itself again. Once the process is complete, your server or VM will now be operational with data restored from your chosen restore point.
