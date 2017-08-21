---

copyright:
  years: 2017
lastupdated: "2017-07-07"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# R1Soft CDP Bare Metal Restore Procedures

Below is the process for completing a bare metal restore to a IBM Bluemix public/private VM or bare metal server. This process would be followed in the case of a server failure that causes data/OS loss. This process will restore all file system blocks backed up (including the OS and any files that were not excluded from backups). This process should not be followed if the restoration of a subset of files is the objective (Refer to http://wiki.r1soft.com/display/CDP/Restoring+Files for restotration of the files only).

## R1Soft Server Tasks 

1. Log into R1Soft server via browser (IP and admin password available via the [Control portal](https://control.softlayer.com/)).
2. Click on **Recovery Points** on the bottom left-hand side of the R1Soft management portal.
3. Select the server you wish to restore and the **Disk Safe** you wish to you restore from.
4. Locate in the list of recovery points the point from which you want to restore.
5. Click the **shield** icon (MouseOver text reads Bare Metal Restore).
 
 
## Restore Device Tasks 

1. Click into the device you wish you restore in the [Control panel](https://control.softlayer.com/).
2. Click the **Actions** menu and choose **Boot from image** you will get a list of private images.
3. Choose **Public Images** from the drop down menu at the top of the list.
4. Choose the appropriate R1Soft agent boot image for your version of R1Soft server (serverbackup-centos-bootcd-agent.iso) and click **Boot From This Image** link on the right.
5. From the **Device Details** page for the server being restored, click **Actions** > **KVM Console**.
6. Once the console is up and the image has booted, you should see a Debian bootloader screen with some options.  Simply press the Enter key to boot from the default option.
7. Once the OS is booted, type `netconfig` and press **Enter**.
8. Choose **Yes** to configure the networking.
9. Enter networking configuration details from device details in the Control portal.
10. Choose **Yes** when prompted to restart networking.
11. **OPTIONAL** type `passwd root` to set a root password for SSH logins and type service ssh start to allow SSH login, which may be useful if your KVM console is very slow.
12. Type `service cdp-agent restart` (This should start the CDP agent if it isn't already running).


## R1Soft Server Tasks 

1. Click **Next** on the wizard.
2. Select filesystems to be restored and click **Next**.
3. Select host to restore to - This can be the original host, or an alternate one as designated by you (for these instructions, we are going for recovering to the same server).
4. Click **Next**.
5. Choose the storage configuration to use (Use what's in place on the server, or choose one based on backups).
6. Select **Partition Tables** you wish to use (If you elected to choose the filesystem layout).
7. Map your filesystem to the correct block devices (C:\ == /dev/sda1, etc.) and click **Next**.
8. Check any restore options you wish (Reboot after restore, Check filesystem after restore) and click **Next**.
9. Verify options chosen and click **Restore** if appropriate; else go back to change restoration options.
10. You should then get a window showing you the status of the current restoration.


## Restore Device Tasks 

1. Once restore is complete, in the **Device Details** page on the [Control portal](https://control.softlayer.com/), choose **Boot From Image** again.
2. A frame will appear mentioning that this device is currently configured to boot from the r1soft-cdp-bootcd-agent-4.0.0.iso image and it will ask you if you want to unload the image and return ot normal booting.
3. Click Yes and the server will reboot from the system disk.
4. The server should run through a `chkdsk` or `fsck` process to verify the disk and may reboot itself again.
5. Your server or VM should now be operational with data restored from the chosen restore point.


Bare Metal restore steps - Reference: http://wiki.r1soft.com/display/CDP/Bare-Metal+Restore
