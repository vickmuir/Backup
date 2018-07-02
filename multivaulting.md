---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# Multivaulting

Multivaulting is the ability for a client/server to connect to more than one EVault location. It provides redundancy and peace of mind that backups are available even if one site fails. 

## Keypoints

1. Multiple EVaults can be managed through the same WebCC and they are handled the same way. The only difference is that you have different vault choices.
2. Plug-in licensing is on a per vault basis - for example, if you purchased the MSSQL plug-in for a vault in Washington DC, it won't work on the Seattle vault.
3. The new vault needs to be manually added to the WebCC after each purchase.

## Adding a Remote Vault to an Account

You must add the new remote EVault storage vault to the account before a new backup location can be added in the WebCC. 

1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Click **Devices**
3. Locate and click the link for the server in question.
4. Under **Device Details**, click **Storage**
5. When the Storage section opens up, scroll down to **EVault**, and click **Add**
6. In the **Order EVault** dialog box that opens, select the remote vault location by clicking its entry in the pull-down list.
7. Select the size of the storage amount, then click **Continue**
8. Check the **I have read the Master...** box and click **Place Order**.

The newly ordered vault is automatically added to the account. If not, contact Sales for help.
When the ordering process is complete, go to the **Storage** > **Backup** to see the new vault listed.

## Adding an Additional Vault to WebCC

1. Log in to the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} and click **Storage** > **Backup** from the main menu to display the servers with EVault backup service. 
2. Select the server where the files to be restored are located. Click the right-pointing arrow to reveal the WebCC link.
3. Click the **WebCC Login** link to start the WebCC client in your browser. <br/>**Note**: WebCC is only accessible through {{site.data.keyword.BluVPN}}.
4. In the left navigational pane, click **All Agents**.
5. In the right upper corner, click **Edit** and select **Vault Settings**.
6. In the **Vault Settings" window click **Add**.
7. In the **New Vault** dialog box:
  1. In the Vault Profile menu, choose **Enter Vault Settings** to create a new entry. Don't update the existing entry, it won't work.
  2. The vault name can't be the same as the other vault name. We suggest adding a -2 tag to the end of it. <br/> 
     >**Note**: This field has a 15 character limit.
  3. The IP address field is populated with the EVault director location information. For example, `ev-director301.service.softlayer.com` has the IP address 10.1.114.46 and is located in WDC.
  4. In the credentials field, enter the account ID, the EVault user name for the selected vault, and the password for the selected vault.
  5. Click **Save Changes**.

In a few seconds, the new vault is usable. If you get a connection failure, check your settings, and try again. Keep in mind that adding an extra vault just presents you with an extra destination to choose for a job. It doesn't automatically run jobs against both vaults. You need to set up jobs to use the extra vault. Refer to the [Getting Started Tutorial](index.html#getting-started-with-evault-backup-services) for instructions.

## EVault Director locations

Multi Vaulting is available across all data centers and there's no geographical limitation in selecting a remote vault. When vaults are configured following steps that are mentioned in this document, all the configured vaults appear in vault settings.

**Note**: Backing up to remote data center locations can take longer than backups to the same data center your server is located.

