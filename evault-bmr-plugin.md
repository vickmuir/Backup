---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Installing the  Bare Metal Restore plug-in

EVault BMR is a disaster recovery solution for Microsoft Windows. You can use BMR to restore your server from a bare metal state after a disaster, such as an operating system or hardware failure, occurred. With EVault BMR, you can quickly restore the system image from a safe, secure location that is managed by {{site.data.keyword.BluSoftlayer_full}}.

BMR is a Microsoft Windows only product on physical servers. It is not available for virtual servers. Bare Metal Restores for Linux distributions aren't supported. BMR is only supported by EVault Agent 8.30 or earlier versions. (30 June 2018).
{:important}

**Capabilities provided**

- Restore your system to a select point-in-time.
- Restore your system from image or file-based backups.
- Restore your system from backups that are stored on the EVault.
- A launchable recovery transaction that you can use to restore your data without a bootable system.

## Ordering the plug-in

1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Click **Storage** > **Backup**.
3. Select your EVault account and click **Order plug-ins**.
4. Select **EVault plug-in - BMR (Bare Metal Restore)** and click **Continue**.
5. Enter your Promo Code if you have one, and click **Recalculate**.
6. The updated charges are displayed. Review your order.
7. Check the box to indicate that you read and accept the Third-party Service Agreements.
8. Click **Place Order**.

## Downloading the user guide

Connect to the {{site.data.keyword.BluSoftlayer_full}} network with {{site.data.keyword.BluVPN}} so that you can download the EVault System Restore v8.3 - User Guide.pdf from [Downloadable EVault Documentation](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.

## Frequently Asked Questions

**Can I move from a single disk to a raid array?**

Yes, that works. However, you need to select a large capacity device due to the size decrease the raid array causes.

**What happens when the image is restored to a larger disk than the original volume?**

If you restore the image to a larger disk than the original volume, the left over space is deallocated. So for example - when you have a 500 GB drive and restore its data to a 1 TB disk, you end up with 500 GB of deallocated disk space. With windows 2008, you can use the built-in disk utility to grow the primary partition. However, there is no similar built-in capability in windows 2003, so you must allocate the space another way.

**Can BMR be used for regular backup?**

BMR backup isn't a disk image, but a system volume image backup system. The system isn't intended to be used for regular backups, but along with them.  

**Can BMR be used for Database backups?**

Database backups must be made separately with the normal EVault backup methods. BMR doesn't replace the need for SQL or Oracle plug-ins. Though BMR uses the VSS technology to backup open files, it can't always be guaranteed that the backed-up files are transaction consistent. The recommendation for these types of specialized applications is that you create two backup jobs: one to back up OS and application binary files and another one for application data. There's a note to this effect at the end of the BMR user guide.

**What kind of restore jobs can be run with BMR?**

You can either do a whole system restore, or you can pick individual files from the backup to restore. The BMR backup job can replace your current files backup job. The restore process is done inside the OS, just like a traditional backup job.

**Does BMR have open file Back up capabilities?**

BMR has open file back up capabilities. However, BMR doesn't replace the need for SQL or Oracle plug-ins. Click [here](evault-mssql-plugin.html) for the MSSQL plug-in installation instructions.

**How much disk space and time does a BMR restore take?**

A backup that is made from a default installation uses about 6 GB. Such a restore takes around 15 minutes on a 1 GB port. This process is also affected by private port speed. If you need faster backups/restores, a port speed increase might be needed.
