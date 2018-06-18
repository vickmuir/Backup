---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-18"

---
{:new_window: target="_blank"}

# Installing the EVault Bare Metal Restore plug-in

EVault BMR is a disaster recovery solution for Microsoft Windows that enables you to completely restore your server from a bare metal state when a disaster such as an operating system or hardware failure occurred. This system allows you to quickly restore the system image from a safe, secure location that is managed by {{site.data.keyword.BluSoftlayer_full}}.

**Note**: BMR is a Microsoft Windows only product on physical servers. It is not available for virtual servers. Bare Metal Restores for Linux distributions aren't supported. BMR is only supported by EVault Agent 8.30 or lower. (30 June 2018).

## Capabilities provided

- Restore your system to a select point-in-time.
- Restore your system from image or file-based backups.
- Restore your system from backups that are stored on the EVault.
- A launchable recovery transaction that will allow you to restore your data without a bootable system.

## Order the plug-in

1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Click **Storage** > **Backup**.
3. Select your EVault account and click **Order Plugins**.
4. Select **EVault Plugin - BMR (Bare Metal Restore)** and click **Continue**.
5. Enter your Promo Code if you have one and click **Recalculate**.
6. The updated charges are displayed. Review your order.
7. Check the boxes to indicate that you read the Master Service Agreement and accept the 3rd Party Software Terms. 
8. Click **Place Order**.

## User guide

Connect to the {{site.data.keyword.BluSoftlayer_full}} network with {{site.data.keyword.BluVPN}} so that you can download the EVault System Restore v8.3 - User Guide.pdf from [Downloadable EVault Documentation](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.

## Frequently asked questions

### Can I migrate from a single disk to a raid array?

Yes, it will work. However, you need to select a large capacity device due to the size decrease the raid array will cause.

### What happens if I restore the image to a larger disk than the original volume?

If you restore the image to a larger disk than the original volume, the left over space is deallocated. So for example - if you have a 500 GB drive and restore its data to a 1 TB disk, there will be 500 GB of deallocated disk space. With windows 2008, you can use the native disk utility to grow the primary partition. However, in windows 2003 there isn’t a native capability for this so simply allocating the space is recommended.

### Can I use BMR for my regular backup?

This isn't a disk image, but a system volume image backup system. This system isn't intended to be used for regular backups, but along with them.  

### Can I use BMR for my database backups?

Database backups should be made separately with the normal EVault backup methods. BMR doesn't replace the need for SQL or Oracle plug-ins. Though BMR uses the VSS technology to backup open files, we can't always guarantee that the backed-up files will be transaction consistent. Our recommendation for these types of specialized applications is that you create two backup jobs: one to back up OS and application binary files and another one for application data. There's a note to this effect at the far end of the BMR user guide.

### What kind of restore jobs can I perform with BMR?

You can either do a whole system restore, or you can pick individual files from the backup to restore. This means that this job can replace your current files backup job. The restore process can be done inside the OS, just like a traditional backup job.

### Does BMR have open file backup capabilities?

BMR has open file back up capabilities. However, BMR doesn't replace the need for SQL or Oracle plug-ins. Click [here](evault-mssql-plugin.html) for the MSSQL plug-in installation instructions.

### How much disk space and time does a BMR restore take?

A backup made from a default install will use about 6 GB. Such a restore would take around 15 minutes on a 1 GB port. This process is also affected by private port speed. If you need faster backups/restores a port speed increase may be needed.
