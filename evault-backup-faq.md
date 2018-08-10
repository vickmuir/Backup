---

copyright:
  years: 1994, 2018
lastupdated: "2018-08-10"

---
{:new_window: target="_blank"}


# FAQs

## **What kind of applications can be backed up with EVault?**

EVault can be used to back up various applications. However, {{site.data.keyword.BluSoftlayer_full}} offers software agents for some of the more common software systems that are backed up, which include:

- Bare Metal Restore
- Microsoft SQL
- Oracle

The plug-ins that are listed here are only compatible with Windows servers, with the exception of the Oracle plug-in. Each agent is available as an add-on to your EVault backup service. To add an agent to your service, contact a member of the Sales team today. 

<hr>

## **How frequently can the data be backed up with EVault?**

You can back up your data as frequently as you like. Within WebCC, backups can be made manually or can be scheduled as a single instance or to be recurring. Recurring backups can be made daily, weekly, monthly or on a custom schedule and can be updated or canceled at any time.

>**Note** - Highly frequent backups that run several times daily or hourly can cause backup jobs to become corrupted. This corruption occurs because the vault might not be able to remove old safesets or complete other required background tasks in between runs.

<hr>

## **How do the retention schemes work?**

EVault allows for data-retention depending on how long you want to roll back to. **Daily** retention schemes hold data for seven days, while **weekly** schemes hold data for one month and **monthly** schemes hold data for one year. At the end of each period, the oldest data set gets rotated out, and the first "delta backup" that was made becomes the oldest available restore point. 

<hr>

## **What is Delta Technology?**

The first backup is a "seed" (a complete, full backup), the next and subsequent ones are "deltas" (that is, changes only), but they are equivalent to, and still considered a "full backup". That is, you're able to restore all or any files from it. This technology allows for "full backups" to be made each session, but saves enormous amounts of space on the Vault and decreases the amount of time each subsequent backup takes to complete.

<hr>

## **Are the backups secure?**

By default all encryption over the wire (OTW) is encrypted with AES 256-bit encryption. You can also choose to store data in encrypted 
format by using AES 256-bit. 

>**Note** - You must remember your encryption password. Your data can't be restored without your password. If you lose your password, you can't get your data back. 

Compression ratios allow for zero compression to a maximum ratios compression that, depending on file type, might be compressed anywhere from 20 percent to 30 percent.

<hr>

## **What information is stored with system state backups?**

The system state backups include, but aren't limited to COM + class registration database, registry, boot files, system files, performance counter. It's all dependent on your system. System files vary by system O/S and service packs. Usually there are several thousand of them. MS Windows makes a dynamic list of these DLLs when you include them in the backup. By including the system files, you can recover from corrupted system files, or if you accidentally uninstall some service packs, or want to recover with a bare-metal restore. You can return to the state of the backup without having to reinstall the O/S from the installation kit, and then installing each service pack separately.

>**Note** - No user data file is included in System state backup. A system state backup job must be configured as a stand-alone job. There mustn't be any other data source that is included in the System State backup job.

<hr>

## **What happens to open files?**

By default the base client has a state-of-the-art technology to handle most open files that are running on the OS.

<hr>

## **Where can I find information about pricing?**

For more information, see [Backup storage](https://www.ibm.com/cloud/backup-and-restore){:new_window} and [EVault on IBM Cloud: Pricing](https://www.ibm.com/cloud/evault/pricing){:new_window}.

<hr>

## **Can the EVault capacity be increase/decrease without compromising the backups?**

You can increase or decrease the size of your EVault through the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}. The modification to the EVault capacity does not affect the integrity of the data that is stored in the vault. For more information, see [Expanding EVault Capacity](expanding-evault-capacity.html).

<hr>

## **What happens when the EVault capacity is exceeded?**

You can still save and retrieve your backups even if you reached the limit of the capacity that you purchased previously. However, please note that there is going to be an extra charge for every additional GB used in the billing statement.

<hr>

## **How can I set up notifications in WebCC to let me know if my backups fail?**

Notifications can be set up on the Advanced tab. Follow the instructions that you can find in **Quick Links** in WebCC.
