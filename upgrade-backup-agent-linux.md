---

copyright:
  years: 1994, 2019
lastupdated: "2019-11-13"

keywords: IBM Cloud backup, EVault, Carbonite, backup, upgrade agent, Linux

subcollection: Backup

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:shortdesc: .shortdesc}

# Upgrading backup software agent for Linux
{: #UpgradeinLinux}

The most recent backup agent can be downloaded from your Cloud Backup Portal Dashboard quick links section.
{:tip}

Following the upgrade process ensures that you can upgrade your {{site.data.keyword.backup_notm}} agent without losing the registration.
{:shortdesc}

1. Log in to your host at root level.
2. Download the latest version of the agent.
   ```
   wget -N downloads.service.softlayer.com/evault/Agent-Linux-8.50.7245-x64.tar.gz
   ```
   {:pre}

3. Extract the contents of the downloaded file.

   ```
   tar -xzvf Agent-Linux-x64-8.50.7245.tar.gz
   ```
4. Go to the recent installation directory.
   ```
   cd Agent-Linux-x64-8.50.7245/
   ```

5. Run installation script.
   ```
   ./install.sh
   ```
   {:pre}

6. Answer the prompts by selecting your language, selecting `N` for not registering the computer as a new host, and `A` to encrypt data by using the Integrated encryption method.

7. If the installation is successful, it is recorded in `/opt/BUAgent/Install.log`.
