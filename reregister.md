---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud backup, EVault, Carbonite, backup, reregister

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:shortdesc: .shortdesc}

# Reregistering a vault
{: #reregister}

Reregistering a vault is a task that is most commonly used after the Operating System of a server is reloaded. You can also use these steps to [use backups of one server to restore data on another server](/docs/infrastructure/Backup?topic=Backup-restorefromotherVSI).
{:shortdesc}

1. Start {{site.data.keyword.backup_notm}} portal and log in. For more information, see the [Getting started tutorial](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).

   Remember, {{site.data.keyword.backup_notm}} portal is only accessible through {{site.data.keyword.BluVPN}}.
   {:tip}
2. Click **All Agents**.
3. Mouse-over **Edit**.
4. Select **Vault Settings**.
5. Click **Reregister**.
6. Complete the form.
  - Vault name
  - Vault address
  - Account

    "Account" is the equivalent of the "Account Name" in the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}/classic/storage/backup){: external}. Typically, it looks like "SLE[account ID]"
    {:tip}
  - User name
  - Password
7. Click **Load Computers**, and select the computers that you want to load.
8. Click **Save Changes**.
9. Refresh the website to restore previous backup jobs.
10. Synchronize each backup job to restore safe-set history.
11. If the backup jobs were created with an encryption password, you must enter the encryption password to restore data, or continue with backups.
12. Click **Close**.
