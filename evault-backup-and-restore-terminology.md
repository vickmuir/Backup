---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-04"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# EVault Backup and Restore Terminology 

## Delta Technology:
The first Backup is a “seed” (a complete, full Backup), the next and subsequent ones are deltas (i.e. changes only), but they are equivalent to, and still considered a “full” Backup. That is, you are able to restore all or any files from it. This technology allows for “Full Backups” to be made each session, but saves enormous amounts of space on the Vault and decreases the amount of time each subsequent backups take to complete.

## Retention Schemes: 
EVault allows for Data retention depending on how long you wish to roll back to. Daily Retention schemes will hold data for 7 days, while Weekly will hold data for 1 month and Monthly will hold data for 1 year. At the end of each period, the oldest dataset gets rotated out and the first delta made becomes the oldest available restore point. 

## Compression: 
EVault offers 6 types of encryption solutions for your data: DES 56bit, Blowfish 56 bit, Triple DES 112bit, Blowfish 128 bit, AES 128 bit and AES 256 bit. Compression ratios allows for zero compression to a maximum ratios compression that, depending on file type, may be compressed anywhere from 20% to 30%.

## Encryption:
By default all encryption over the wire (OTW) is encrypted with AES 128bit encryption. If you want data stored in an encrypted format you have several options as part of the backup process. Note that if you lose your password you will NOT be able to get your data back. 

## Special Backups: 
The system state backups include, but are not limited to COM + Class Registration Database, Registry, Boot Files, System Files, Performance Counter all dependent on your System. System files vary by system O/S and service packs. Usually there are several thousand of them. MS Windows makes a dynamic list of these DLLs when you include them in the backup. Including the system files allows you to recover from corrupted system files, or if you accidentally uninstall some service packs, or want to recover with a bare-metal restore. It allows you to return to the state of the backup without having to reinstall the O/S from the installation kit, and then installing each service pack separately. 

## Open Files: 
By default the base client has state of the art technology to handle most open files running on the OS. In rare cases if backups fail because of open file limitation there are secondary plugins you can purchase to get improved open files handling. The rule of thumb is you do not need the open file plugin unless you see errors in your backups for open files in which case you can order the plugins.
