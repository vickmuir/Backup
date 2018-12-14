---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Mise à niveau de l'agent de logiciel de sauvegarde pour Windows

Utilisez les instructions détaillées décrites ci-après pour mettre à niveau l'agent {{site.data.keyword.backup_notm}} sur un serveur Windows.

1. Prenez le contrôle à distance via RDP de votre serveur {{site.data.keyword.BluSoftlayer_full}} ayant besoin d'une mise à niveau d'{{site.data.keyword.backup_notm}}.
2. Ouvrez un navigateur et accédez à l'adresse suivante :
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
3. Cliquez sur le fichier souhaité. (Par exemple, Agent-Windows-x64-6-72-1072a.exe.)

   Le numéro de version figure dans le nom de fichier. Sélectionnez le plus récent. <br/>Il existe des programmes d'installation 32 bits et 64 bits distincts. Si vous utilisez un système d'exploitation 64 bits, téléchargez le fichier dont le nom contient x64.
   {:tip}
4. Cliquez sur **Exécuter** sur l'écran de téléchargement, puis à nouveau après son téléchargement.
5. Cliquez sur **Oui** pour mettre à niveau l'**agent de logiciel EVault**.

   Le programme d'installation peut disparaître pendant une minute lors de son téléchargement.{:note}
6. Sélectionnez **Conserver mon enregistrement actuel** et cliquez sur **Suivant**.
7. Cliquez sur **Suivant**. L'agent entame la mise à niveau. Cette opération peut prendre quelques minutes.
8. Sur l'écran de fin, cliquez sur **Terminer**.
