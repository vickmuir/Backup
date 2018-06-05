---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-30"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Reregistering an EVault

This task is most commonly a step needed after reloading the OS of a server, but you can also use these steps to [use backups for one server, to restore on another server](restore-from-another-computer.html).

1. Log in as the user on WebCC. Refer to the [Getting Started with Backup Services](/docs/infrastructure/Backup/index.html) for instructions. Remember, WebCC is only accessible through {{site.data.keyword.BluVPN}}.

2. On the left, click **All Agents**.

3. In the upper right corner, mouse-over **Edit**.

4. Select **Vault Settings**.

5. Click **Reregister**.

6. Complete: 
  - Vault name
  - Vault address
  - Account
  - User name
  - Password. <br/>
  **Note**: "Account" is the equivalent of the "Account Name" in the [Getting Started with Backup Services](index.html) page. Typically, it looks like "SLE[account ID]"

7. Click **Load Computers** and select which computers you want to load.

8. Click **Save Changes**.

9. Refresh Website to restore previous backup jobs.

10. Synchronize each backup job to restore safeset history. 

11. If the the backup jobs were created using an encryption password, you must enter the encryption password to restore data or continue with backups.

12. Click **Close** and you're all done.
