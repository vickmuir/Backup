---

copyright:
  years: 1994, 2019
lastupdated: "2019-10-31"

keywords: IBM Cloud backup, EVault, Carbonite, backup, backup frequency, backup types, backup retention scheme, plugins, delta technology, open files, pricing

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:faq: data-hd-content-type='faq'}


# FAQs
{: #faqs}

## What kind of applications can be backed up?
{: faq}

{{site.data.keyword.backup_full}} can be used to back up various applications. {{site.data.keyword.cloud}} also offers software agents for some of the more common software systems that are backed up, which include

- [Bare Metal Restore](/docs/infrastructure/Backup?topic=Backup-BMRplugin)
- [Microsoft Exchange](/docs/infrastructure/Backup?topic=Backup-Exchangeplugin)
- [Microsoft SQL](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin#MSSQLplugin)
- [Oracle](/docs/infrastructure/Backup?topic=Backup-Oracleplugin#Oracleplugin)
- [VMware VRA](/docs/infrastructure/Backup?topic=Backup-VRA#VRA)

The plug-ins that are listed here are only compatible with Windows servers, except for the Oracle or VMware plug-ins. Each agent is available as an add-on to your backup service for free.

<hr>

## How frequently can we back up the data?
{: faq}

Within Cloud Backup Portal, backups can be made manually, or can be scheduled as a single instance, or to be recurring. Recurring backups can be made daily, weekly, monthly or on a custom schedule and can be updated or canceled at any time.

Highly frequent backups that run several times daily or hourly can cause backup jobs to become corrupted. This corruption occurs because backup vault does not get enough time to run required background maintenance tasks. Backup Jobs take precedence over maintenance tasks. So when backups are done with high frequency, the vault continues to run the backup jobs and cause the number of safe-sets to grow.
{:note}

<hr>

## How do the retention schemes work?
{: faq}

{{site.data.keyword.backup_notm}} allows for data-retention depending on how long you want to roll back to. **Daily** retention schemes hold data for seven days, while **weekly** schemes hold data for one month and **monthly** schemes hold data for one year. At the end of each period, the oldest data set gets rotated out, and the first "delta backup" that was made becomes the oldest available restore point.

You can modify default retention schemes and can create custom retention schemes. However, IBM recommends that you use the default retentions as a starting point. When you create a new retention scheme or modify an existing retention, make sure that the Archiving option is not selected. Archiving is not supported.
{:tip}

<hr>

## What is Delta Technology?
{: faq}

The first backup is a "seed" (a complete, full backup), the next and subsequent ones are "deltas" (that is, changes only), but they are equivalent to, and still considered a "full backup". That is, you're able to restore all or any files from it. With this technology, "full backups" are created at each session, but it saves enormous amounts of space on the vault and decreases the amount of time each subsequent backup takes to complete.

<hr>

## Are the backups secure?
{: faq}

By default all encryption over the wire (OTW) is encrypted with AES 256-bit encryption. You can also choose to store data in encrypted format by using AES 256-bit.

You must remember your encryption password. Your data can't be restored without your password. If you lose your password, you can't get your data back.
{:important}

Compression ratios allow for zero compression to a maximum ratios compression that, depending on file type, might be compressed anywhere from 20 percent to 30 percent.

<hr>

## What information is stored with system state backups?
{: faq}

The system state backups include, but aren't limited to COM + class registration database, registry, boot files, system files, performance counter. It's all dependent on your system. System files vary by system O/S and service packs. Usually there are several thousand of them. MS Windows makes a dynamic list of these DLLs when you include them in the backup. By including the system files, you can recover from corrupted system files, or if you accidentally remove some service packs, or want to recover with a bare-metal restore. You can return to the state of the backup without having to reinstall the O/S from the installation kit, and then installing each service pack separately.

No user data file is included in System state backup. A system state backup job must be configured as a stand-alone job. There mustn't be any other data source that is included in the System State backup job
{:important}

<hr>

## What happens to open files?
{: faq}

By default, the base client has a state-of-the-art technology to handle most open files that are running on the OS.

<hr>

## Where can I find information about pricing?
{: #pricing}
{: faq}

For more information, see [Backup storage](https://www.ibm.com/cloud/backup-and-restore){: external} and [IBM Cloud Backup: Pricing](https://www.ibm.com/cloud/backup/pricing){: external}.

<hr>

## Can the {{site.data.keyword.backup_notm}} capacity be increased or decreased without compromising the backups?
{: faq}

You can increase or decrease the size of your vault through the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}){: external}. The modification to the capacity does not affect the integrity of the data that is stored in the vault. For more information, see [Expanding Capacity](/docs/infrastructure/Backup?topic=Backup-expandcapacity#expandcapacity).

<hr>

## What happens when the {{site.data.keyword.backup_notm}} capacity is exceeded?
{: faq}

You can still save and retrieve your backups even if you reached the limit of the capacity that you purchased previously. However, you are going to receive an extra charge for every additional GB that was used in the next billing statement.

<hr>

## How can I set up notifications in the Cloud Backup Portal that can alert me if a backup fails?
{: faq}

Notifications can be set up on the Advanced tab. Follow the instructions that you can find in **Quick Links** in Cloud Backup Portal.

<hr>

## When we use the BMR plug-in, can we move from a single disk to a raid array?

Yes, that works. However, you need to select a large capacity device due to the size decrease that the raid array causes.

<hr>

## When we use the BMR plug-in, what happens when the image is restored to a larger disk than the original volume?
{: faq}

If you restore the image to a larger disk than the original volume, the leftover space is deallocated. So for example - when you have a 500-GB drive and restore its data to a 1-TB disk, you end up with 500 GB of deallocated disk space. With windows 2008, you can use the built-in disk utility to grow the primary partition. However, Windows 2003 does not have a similar built-in capability, so you must allocate the space another way.

<hr>

## Can BMR be used for regular backup?
{: faq}

BMR backup isn't a disk image, but a system volume image backup system. The system isn't intended to be used for regular backups, but along with them.

<hr>

##Can BMR be used for database backups?
{: faq}

Database backups must be made separately with the normal {{site.data.keyword.backup_notm}} methods. BMR doesn't replace the need for SQL or Oracle plug-ins. Though BMR uses the VSS technology to backup open files, it can't always be guaranteed that the backed-up files are transaction consistent. The recommendation for these types of specialized applications is that you create two backup jobs: one to back up OS and application binary files and another one for application data.

<hr>

## What kind of restore jobs can be run with BMR?

You can either do a whole system restore, or you can pick individual files from the backup to restore. The BMR backup job can replace your current files backup job. The restore process is done inside the OS, just like a traditional backup job.

<hr>

## Does BMR have open file back up capabilities?
{: faq}

BMR has open file back up capabilities. However, BMR doesn't replace the need for SQL or Oracle plug-ins. Click [here](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin) for the MSSQL plug-in installation instructions.

<hr>

## How much disk space and time does a BMR restore take?
{: faq}

A backup that is made from a default installation uses about 6 GB. Such a restore takes around 15 minutes on a 1-GB port. This process is also affected by private port speed. If you need faster backups and restore, a port speed increase might be needed.

<hr>

## What does VSS (Volume Shadow Copy Services) do?
{: faq}

The current version of the SQL Server plug-in uses VSS (Volume Shadow Copy Services) to complete backups. By using VSS, the SQL Server plug-in effectively backs up SQL databases, even SQL databases that span volumes. Backups can be completed while applications continue to write to a volume. The SQL Server plug-in provides data consistency within and across databases. VSS allows multiple backups to run at the same time.

<hr>

## Is the 32-bit version of EVault for Windows 8 still supported?
{: faq}

No. The 32-bit version of the backup software agent was retired along with Windows Server 2008 Standard and Datacenter Editions in March 2017.
