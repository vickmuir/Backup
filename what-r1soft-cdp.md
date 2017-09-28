---

copyright:
  years: 1994, 2017
lastupdated: "2017-09-28"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# About R1Soft CDP

## About R1Soft Continuous Data Protection (CDP)

R1Soft Continuous Data Protection (CDP) Server Backup is fast, affordable server backup software for Windows and Linux, in both physical and virtual environments. It offers a unique solution - Virtual Full Backup, which leverages block-level backup technology that reduces backup windows from hours to minutes. Block-level backup assures unique disk blocks are stored only one time in backup storage, even across thousands of recovery points. The one-time storage allows users to keep recovery points longer and save space over existing full or incremental backups. Users can back up data as frequently as every 5 minutes with minimal impact to production systems.

Idera CDP consists of three main components: the CDP server, the agent and the database plugins, which are available for purchase separately from the first two components.  Because R1Soft CDP is a third-party backup solution, interactions with CDP take place entirely outside of {{site.data.keyword.BluSoftlayer_full}}'s proprietary interfaces; however, R1Soft CDP passwords may be tracked and stored within [{{site.data.keyword.slportal}}](https://control.softlayer.com/).  All other interactions with R1Soft CDP are documented on R1Soft's website.

## Backup Performance and Options

- High Performance Backups: Perform an initial replica of your data the first time your continuous data protection (CDP) policy runs. After the initial replica, R1Soft stores block level deltas, leading to shorter backup windows and reduced disk I/O.

- Bare-Metal Restore: Restores of large file systems can be performed significantly faster by bypassing the file system and streaming blocks directly to disk, making it a faster alternative to file-by-file restore in the event of disaster.

- Innovative Web Interface: Browse, download, and restore files from your recovery points using a Windows Explorer-style interface. You can also perform policy management and reporting and see the detailed progress of replication and restore jobs as they run.

- Data Retention Policy: Define a replication goal (e.g., every 15 minutes) and how many recovery points you will retain. Old recovery points are automatically merged and their storage is recycled.
