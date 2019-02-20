---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Reregistering a vault
{: #reregister}

This task is most commonly used after the Operating System of a server is reloaded. You can also use these steps to [use backups of one server to restore data on another server](/docs/infrastructure/Backup?topic=Backup-restorefromotherVSI).
{:tip}

1. Start {{site.data.keyword.backup_notm}} portal and log in. For more information, see the [Getting started tutorial](/docs/infrastructure/Backup?topic=Backup-GettingStarted).

   Remember, {{site.data.keyword.backup_notm}} portal is only accessible through {{site.data.keyword.BluVPN}}.
   {:tip}
2. On the left, click **All Agents**.
3. In the upper right, mouse-over **Edit**.
4. Select **Vault Settings**.
5. Click **Reregister**.
6. Complete the form.
  - Vault name
  - Vault address
  - Account

    "Account" is the equivalent of the "Account Name" in the [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}. Typically, it looks like "SLE[account ID]"
    {:tip}
  - User name
  - Password
7. Click **Load Computers**, and select the computers that you want to load.
8. Click **Save Changes**.
9. Refresh the website to restore previous backup jobs.
10. Synchronize each backup job to restore safeset history.
11. If the backup jobs were created with an encryption password, you must enter the encryption password to restore data, or continue with backups.
12. Click **Close**.
