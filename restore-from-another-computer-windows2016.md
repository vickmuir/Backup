---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---

# Restore a job from another computer on Windows 2016 

This article provides the steps needed to perform a file restore using Evault Windows Central Control in Windows 2016 from another computer. 

1. Remote control your server through RDP.
2. Open CentralControl.
3. Right click on **Agent** and click **Agent Configuration**.
4. Remove current Vault settings from CentralControl by selecting the entry and clicking **Delete**.
5. Click **New** and on the next screen, select **Re-register previously registered computer**. Click **Next**
6. Enter network address and click **Add**, then click **Next**.
7. Enter the new port values and click **Add**, then **Next**.
8. In the Connection Settings screen, enter the number of seconds/minutes you want. 
9. In the Authentication screen, enter your credentials and click **Next**.
10. Registered Computers window displays the host name of your server. Click **Next**.
11.	The Vault Configuration Wizard has finished collecting your information, click **Finish** to complete the registration.
12. When prompted, confirm that you want to proceed with the reregistartion.
13. When registration is complete, click **Restore** from the menu bar. 
9.	Select appropriate safe set and enter encryption password. Click **Next**.
10.	Select the files you want to restore and select default options and click **Finish**. 
11.	When the restore is complete, remove the vault registration and re-register with current vault account information. 
