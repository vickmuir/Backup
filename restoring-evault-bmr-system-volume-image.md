---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-03"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Restoring an Evault BMR System Volume Image 

In the event that you need to restore a Bare Metal image backup from Evault, you can quickly restore this from our Evault BMR Rescue Kernel system. This allows you to restore the system without the need of a bootable operating system. This is very useful in the event that the operating system is no longer usable or the drives in the system have been replaced.

## Initiating the Evault BMR Rescue Kernel system

You can access the Evault BMR Rescue Kernel system via the {{site.data.keyword.slportal}}.
1. Log into the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Click **Storage** > **Backup** 
3. Click the **Arrow** next to the vault
4. Click **Initiate Bare Metal Restore**. This will start a transaction that will take a few minutes to complete at which time you can access it by following the steps detailed below. You will be emailed once the system completes the boot process.


## Restoring from the Evault BMR Rescue Kernel

Once the Evault BMR Rescue Kernel transaction has loaded you can chose to access it in 2 different ways. One way being a vnc client and the private/public ip address of your server and the password that is listed in the {{site.data.keyword.slportal}} and the other way being the KVM console of your IPMI card. Either of these ways will work out well. Upon logging into the Evault BMR Rescue Kernel for the first time, you are greeted with the language selection screen as shown below. 

1. Select the language of your choice and click **OK**.
<br/>![Figure 1: BMR Language selection](/images/bmr1.png)<br/> This brings you to the license agreement for the software. 
2. If you accept the terms select the check box and select **Next** to continue. <br/> This brings up the main Evault system restore menu. 
3. For this operation select **Restore My System**.
<br/>![Figure 2: BMR Main menu](/images/bmr2.png)
4. The Evault system restore wizard appears. It gives a general overview of what will be done and the steps needed. Select **Next** to continue
<br/>![Figure 3: BMR Wizard](/images/bmr3.png)
5. Select a backup type to restore from. Select **Evault software** then select **Next** to continue.
6. On the Backup location screen, select the vault and enter in the vault address, Evault Account number, the Evault account login and the password for the account. Then click **Next** to continue.
<br/>![Figure 4: Choose Backup Location](/images/bmr4.png)
7. You should now see your system listed in this screen. Make sure it is highlighted and click **Next** to continue.
<br/>![Figure 5: Choose your system](/images/bmr5.png)
8. On the backup job selection screen, select the desired Job to restore from and hit **Next** to continue.
<br/>![Figure 6: Choose your Restore point](/images/bmr6.png)
9. From the **Select Restore Point** menu, select the desired restore point and select **Next**
<br/>![Figure 8: Choose Restore Point](/images/bmr8.png)
10. Select the source and destination volumes. To restore the source to the destination drag and drop the source volume onto the destination volume.
<br/>![Figure 9: Select Source and Destination Volumes](/images/bmr9.png)
11. On the format or merge data confirmation box there are two options. For this article we select **Format** for a clean restore that formats the disk. In the event you want to merge the data on the destination volume select **Merge**.
<br/>![Figure 10: Choose Merge](/images/bmr10.png)
11. On the main source and destination volume screen. Select **Next** to continue.
12. On the restore plan summary screen, check the box to accept the plan and select **Next** to continue.
<br/>![Figure 11: Start the restore](/images/bmr11.png)
12. The restore progress screen appears and it shows you the progress of the restoration as it happens.
<br/>![Figure 12: Restore Progress](/images/bmr12.png)
13. Once complete, you receive a notification pop up from that states that the Restore was completed successfully. Select **OK**.
14. On the restore progress screen. Select **Next** to continue.
15. On the final screen, check the box for reboot system and select **Finish** and the server boots into your restored volume image. 
The restoration is now complete.

## Notes

The first time this happens you will see the unexpected shutdown message. This is completely normal with this backup type and will go away after the first boot. 
