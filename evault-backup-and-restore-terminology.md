---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# EVault Backup and Restore Terminology 

**Delta technology**

The first backup is a “seed” (a complete, full backup). The next and subsequent ones are deltas (meaning changes only), but they are equivalent to, and still considered to be a full backup. You can restore all or any files from a delta backup. 

This technology makes full backups at each session. It saves enormous amounts of space on the Vault, and decreases the amount of time each subsequent backup takes to complete.


**Retention schemes**

EVault's Data retention schemes depend on how long you want to roll back to. Daily Retention schemes hold data for seven days, while Weekly schemes hold data for one month and Monthly schemes hold data for one year. At the end of each period, the oldest data set gets rotated out and the first delta that was made becomes the oldest available restore point.


**Compression**

EVault offers six types of encryption solutions for your data: DES 56-bit, Blowfish 56-bit, Triple DES 112-bit, Blowfish 128-bit, AES 128-bit, and AES 256-bit. Compression ratios allow for zero compression to a maximum ratios compression that, depending on file type, can be compressed anywhere from 20% to 30%.


**Encryption**

By default all encryption over the wire (OTW) is encrypted with AES 128-bit encryption. If you want to store your data in an encrypted format, you have several options as part of the backup process. If you lose your password, you can't get your data back.


**Special backups**

The system state backups include, but are not limited to COM + class registration database, registry, boot files, system files, performance counter, all dependent on your System. System files vary by server O/S and service packs. Usually there are several thousand of them. MS Windows makes a dynamic list of these DLLs when you include them in the backup. Including the system files allows you to recover from corrupted system files, or if you accidentally uninstall some service packs, or want to recover with a bare-metal restore. It allows you to return to the state of the backup without having to reinstall the O/S from the installation kit, and then installing each service pack separately.


**Open files**

By default the base client has state-of-the-art technology to handle most open files that are running on the OS.
