---

copyright:
  years: 1994, 2017
lastupdated: "2017-07-12"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Restoring an Evault BMR System Volume Image 

In the event that you need to restore a Bare Metal image backup from Evault, you can quickly restore this from our Evault BMR Rescue Kernel system. This allows you to restore the system without the need of a bootable operating system. This is very useful in the event that the operating system is no longer usable or the drives in the system have been replaced.

## Initiating the Evault BMR Rescue Kernel system

You can access the Evault BMR Rescue Kernel system by logging into the control.softlayer.com portal and going to Storage, Backup, clicking the "Arrow" next to the vault, and then clicking "Initiate Bare Metal Restore". This will start a transaction that will take a few minutes to complete at which time you can access it by following the steps detailed below. You will be emailed once the system completes the boot process.


## Restoring from the Evault BMR Rescue Kernel

Once the Evault BMR Rescue Kernel transaction has loaded you can chose to access it in 2 different ways. One way being a vnc client and the private/public ip address of your server and the password that is listed in the portal and the other way being the KVM console of your ipmi card. Either of these ways will work out well. Upon logging into the Evault BMR Rescue Kernel for the first time, you will be greeted with the language selection screen as shown below. Once you have selected the language of your choice select **OK**.
<br/>![Figure 1: BMR Language selection](/images/bmr1.png)

This will bring you to the license agreement for the software. If you accept the terms select the check box and select **Next** to continue.

This will bring up the main Evault system restore menu. For this operation select **Restore My System**.
<br/>![Figure 2: BMR Main menu](/images/bmr2.png)

Next the Evault system restore wizard will appear. It gives a general overview of what will be done and the steps needed. Select **Next** to continue
<br/>![Figure 3: BMR Wizard](/images/bmr3.png)

In the next screen you will select a backup type to restore from. Select **Evault software** then select **Next** to continue.

Next you will see the Backup location screen. For this operation we will select the vault and enter in the vault address, Evault Account number, the Evault account login and the password for the account. The click **Next** to continue.
<br/>![Figure 4: Choose Backup Location](/images/bmr4.png)

You should now see your system listed in this screen. Make sure it is highlighted and click **Next** to continue.
<br/>![Figure 5: Choose your system](/images/bmr5.png)

The next screen to appear will be the backup job selection screen. Select the desired Job to restore from and hit **Next** to continue.
<br/>![Figure 6: Choose your Restore point](/images/bmr6.png)

You should now see the **Select Restore Point** menu. From here select the desired restore point and select **Next**
<br/>![Figure 8: Choose Restore Point](/images/bmr8.png)

On the next screen, you will select the source and destination volumes. To restore the source to the destination drag and drop the source volume onto the destination volume.
<br/>![Figure 9: Select Source and Destination Volumes](/images/bmr9.png)

This will bring up a format or merge data confirmation box. For this article we will select **Format** for a clean restore that formats the disk. In the event you want to merge the data on the destination volume select **Merge**.
<br/>![Figure 10: Choose Merge](/images/bmr10.png)

This will bring you back to the main source and destination volume screen . Select **Next** to continue.

Next you will see the restore plan summary screen. Check the box to accept the plan and select **Next** to continue.
<br/>![Figure 11: Start the restore](/images/bmr11.png)

This will bring up the restore progress screen. I will show you the progress of the restoration as it happens.
<br/>![Figure 12: Restore Progress](/images/bmr12.png)

Once complete, you will receive a notification pop up from that states that the Restore was completed successfully. Select **OK**.

This will bring you back to the restore progress screen. Select **Next** to continue.

The next screen is the final screen. Check the box for reboot system and select **Finish** and the server will boot into your restored volume image. The restoration is now complete.

## Notes:

The first time this happens you will see the unexpected shutdown message. This is completely normal with this backup type and will go away after the first boot. 
