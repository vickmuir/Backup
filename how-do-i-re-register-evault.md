---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-26"

---
{:new_window: target="_blank"}

# Reregistering an EVault

This task is most commonly used after the Operating System of a server is reloaded. You can also use these steps to [use backups of one server to restore data on another server](restore-from-another-computer.html).

1. Start WebCC and log in. Refer to the [Getting started with backup services](/docs/infrastructure/Backup/index.html) for instructions. <br/>Remember, WebCC is only accessible through {{site.data.keyword.BluVPN}}.

2. On the left, click **All Agents**.

3. In the upper right, mouse-over **Edit**.

4. Select **Vault Settings**.

5. Click **Reregister**.
 
6. Complete the form.
  - Vault name
  - Vault address
  - Account <br/>**Note**: "Account" is the equivalent of the "Account Name" in the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}. Typically, it looks like "SLE[account ID]"
  - User name
  - Password

7. Click **Load Computers**, and select the computers that you want to load.

8. Click **Save Changes**.

9. Refresh the website to restore previous backup jobs.

10. Synchronize each backup job to restore safeset history.

11. If the backup jobs were created with an encryption password, you must enter the encryption password to restore data, or continue with backups.

12. Click **Close**.
