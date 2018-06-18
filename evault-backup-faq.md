---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# EVault backup - frequently asked questions

## What kind of applications can I backup with EVault?

EVault allows for backups of a various applications. However, {{site.data.keyword.BluSoftlayer_full}} offers software agents for some of the more common software systems that are backed up, which include:

- Bare Metal Restore
- Microsoft SQL
- Oracle

Each agent is available as an add-on to your EVault backup service. To add an agent to your service, contact a member of our Sales team today. Note that the plug-ins that are listed here are only compatible with Windows servers. 

## How frequently can I back up my data with EVault backup?

You can back up your data as frequently as you like. Within WebCC, backups can be made manually or can be scheduled as a single instance or to be recurring. Recurring backups can be made daily, weekly, monthly or on a custom schedule and can be updated or canceled at any time.

**Note**: Highly frequent backups that run several times daily or hourly can cause backup jobs to become corrupt. This occurs because the vault might not be able to remove old safesets or perform other required background tasks.

## How do the retention schemes work?

EVault allows for data-retention depending on how long you want to roll back to. **Daily** retention schemes hold data for seven days, while **weekly** schemes hold data for one month and **monthly** schemes hold data for one year. At the end of each period, the oldest data set gets rotated out and the first "delta backup" that was made becomes the oldest available restore point. 

## What is Delta Technology?

The first backup is a "seed" (a complete, full backup), the next and subsequent ones are "deltas" (that is, changes only), but they are equivalent to, and still considered a "full backup". That is, you're able to restore all or any files from it. This technology allows for "full backups" to be made each session, but saves enormous amounts of space on the Vault and decreases the amount of time each subsequent backup takes to complete.

## Are my backups secure?

By default all encryption over the wire (OTW) is encrypted with AES 256-bit encryption. You can also choose to store data in encrypted 
format using AES 256-bit. 

**Note**: You must remember your encryption password. Your data can't be restored without your password. If you lose your password you won't be able to get your data back. 

Compression ratios allow for zero compression to a maximum ratios compression that, depending on file type, might be compressed anywhere from 20 percent to 30 percent.

## What information is stored with system state backups?

The system state backups include, but aren't limited to COM + class registration database, registry, boot files, system files, performance counter. It's all dependent on your system. System files vary by system O/S and service packs. Usually there are several thousand of them. MS Windows makes a dynamic list of these DLLs when you include them in the backup. Including the system files allows you to recover from corrupted system files, or if you accidentally uninstall some service packs, or want to recover with a bare-metal restore. It allows you to return to the state of the backup without having to reinstall the O/S from the installation kit, and then installing each service pack separately.

**Note**: No user data file is included in System state backup. A system state backup job should be configured as a standalone job. There should be no other data source included in System State backup job.

## What happens to open files?

By default the base client has state-of-the-art technology to handle most open files running on the OS. In rare cases, if backups fail because of open file limitation there are secondary plug-ins you can purchase to get improved open files handling. Generally, you don’t need the open-file plug-in unless you see errors in your backups for open files in which case you can order the plug-ins.
