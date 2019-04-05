---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restauration des données vSphere
{: #VRARestore}
 
Lorsque des machines virtuelles sont protégées dans un environnement vSphere, vous pouvez restaurer les [machines virtuelles vSphere](#restoreVMs) et les [fichiers et dossiers](#restoreFFVRA) avec vSphere Recovery Agent.

## Restauration des machines virtuelles vSphere
{: #restoreVMs}

1.	Sur la barre de navigation, cliquez sur **Computers**. Une grille affiche les ordinateurs disponibles. 
2.	Localisez l'environnement vSphere contenant la machine virtuelle que vous souhaitez restaurer et développez sa vue en cliquant sur la ligne. 
3.	Cliquez sur **Jobs**. 
4.	Localisez le travail de sauvegarde contenant la machine virtuelle que vous souhaitez restaurer et cliquez sur **Restore** dans le menu **Select Action** du travail. 
5.	Dans la boîte de dialogue **Choose What you Want to Restore**, sélectionnez **Virtual machines**. 
6.	Cliquez sur **Continue**. La boîte de dialogue Restore affiche le jeu sécurisé le plus récent du travail. 
    * Pour restaurer des données d'une autre source, cliquez sur une source (coffre) dans la liste **Source Device**. 
    *	Pour restaurer des données d'un jeu sécurisé plus ancien, cliquez sur le bouton **Browse Safesets**. Dans le calendrier qui s'affiche, cliquez sur la date des jeux sécurisés à partir de laquelle vous souhaitez effectuer la restauration. 
7.	Dans le panneau **Items to Restore**, sélectionnez chaque machine virtuelle que vous souhaitez restaurer. 
8.	Dans la zone **Encryption Password**, entrez le mot de passe de chiffrement des données. 
9.	Dans la liste **Destination Datastore**, cliquez sur le magasin de données des machines virtuelles restaurées. 
10.	Sélectionnez l'une des options suivantes pour restaurer les machines virtuelles dans le magasin de données que vous avez sélectionné :
  * **Restore all selected Virtual Machines to the selected datastore only.**
  * **Restore to the selected datastore only when a Virtual Machine’s original datastore is not available.** Si la machine virtuelle sauvegardée contient plusieurs disques VMDK résidant sur un ou plusieurs magasins de données et qu'un ou plusieurs des magasins de données ne sont pas disponibles, la machine virtuelle entière est restaurée dans le magasin de données sélectionné. 

  Si vous restaurez une machine virtuelle ou un modèle dans un vCenter, et que la machine virtuelle d'origine est présente, la machine virtuelle est restaurée en tant que clone de la machine virtuelle d'origine avec le nom suivant : <VMname>-vra-restored-<Date>. La machine virtuelle est restaurée en tant que clone si la machine virtuelle d'origine est mise sous tension, hors tension ou suspendue. Si la machine virtuelle d'origine est mise sous tension et utilise une adresse IP statique, un conflit peut se produire au niveau de l'adresse IP lorsque la machine virtuelle clonée qui est restaurée est mise sous tension. {:note}

13.	Dans la liste **Destination Host**, cliquez sur l'hôte sur lequel vous souhaitez enregistrer les machines virtuelles. La liste montre uniquement les hôtes qui ont accès au magasin de données sélectionné.
14.	Sélectionnez l'une des options suivantes pour enregistrer les machines virtuelles restaurées avec les hôtes que vous avez sélectionnés : 
  * **Register all selected Virtual Machines with the selected hosts only.**
  * **Register with the selected hosts only when a Virtual Machine’s original hosts is not available.**
15.	Pour mettre sous tension les machines virtuelles après leur restauration, sélectionnez **Power VMs on after restoring**. 
16.	Sous **Performance options**, conservez le paramètre par défaut. 
17.	Cliquez sur **Run Restore**.

## Restauration de fichiers et de dossiers
{: #restoreFFVRA}

Vous pouvez restaurer les fichiers et les dossiers d'une machine virtuelle Windows protégée à l'aide de vSphere Recovery Agent (VRA). Vous pouvez restaurer les fichiers et les dossiers de plusieurs machines virtuelles à la fois. Vous ne pouvez pas restaurer les fichiers et les dossiers de machines virtuelles Linux avec VRA.
{:important}

Durant la restauration des fichiers et des dossiers, les volumes de la machine virtuelle sélectionnée sont montés en tant qu'unités sur la machine sur laquelle VRA s'exécute. Vous pouvez ensuite partager une partie ou l'ensemble des unités montées pour que les utilisateurs puissent copier les fichiers et les dossiers depuis les unités. Vous pouvez également vous connecter à la machine VRA et copier les fichiers et dossiers depuis les unités montées. 

Les fichiers et les dossiers des disques sont accessibles à toute personne sur le système VRA, y compris les utilisateurs non administrateurs. Si la sécurité vous préoccupe, sécurisez la machine agent et empêchez les utilisateurs de se connecter à la machine localement.
{:tip}

1. Sur la barre de navigation, cliquez sur **Computers**. La grille affiche les ordinateurs disponibles.
2. Localisez l'environnement vSphere contenant la machine virtuelle que vous souhaitez restaurer et développez sa vue en cliquant sur la ligne.
3. Cliquez sur **Jobs**. 
4. Localisez le travail de sauvegarde contenant la machine virtuelle que vous souhaitez restaurer et cliquez sur **Restore** dans le menu **Select Action** du travail.
5. Dans la boîte de dialogue **Choose What You Want to Restore**, sélectionnez **Files and Folders**.
6. Cliquez sur **Continue**. La boîte de dialogue Restore affiche le jeu sécurisé le plus récent du travail. 
  * Pour restaurer des données d'une autre ressource, cliquez sur Source dans la liste Source Device (coffre).
  * Pour restaurer des données d'un jeu sécurisé plus ancien, cliquez sur le bouton Browse Safesets. Dans le calendrier qui s'affiche, cliquez sur la date du jeu sécurisé à partir de laquelle vous souhaitez effectuer la restauration. A droite du calendrier, cliquez sur le jeu sécurisé spécifique depuis lequel vous souhaitez effectuer la restauration.  
7. Dans le panneau **Items to Restore**, sélectionnez la machine virtuelle contenant les fichiers ou les dossiers que vous souhaitez restaurer. 
8. Dans la zone **Encryption Password**, entrez le mot de passe de chiffrement des données. 
9. Dans la zone **Idle Time**, entrez le nombre de minutes d'inactivités après lequel l'unité partagée doit annuler automatiquement le partage. Le délai d'inactivité peut être compris entre 2 et 180 minutes. 
    
    L'unité n'annule pas le partage tant que de nouvelles données sont copiées. Si vous copiez les mêmes données d'une unité partagée plusieurs fois, le système peut être interrompu car aucune donnée nouvelle n'est lue.
    {:note}
    
10.	Dans **Performance options**, sélectionnez Use all available bandwidth. 
11.	Cliquez sur **Run Restore**. 
12. Les volumes restaurés de la machine virtuelle sélectionnée sont mappés en tant qu'unités sur la machine sur laquelle VRA s'exécute et sont disponibles dans un dossier Restore Mount. Effectuez l'une des opérations suivantes.
  * Copiez les fichiers et les dossiers que vous souhaitez restaurer des unités mappées. 
  * Partagez une ou plusieurs unités mappées avec d'autres utilisateurs. Les utilisateurs peuvent ensuite accéder au partage UNC et copier les fichiers et les dossiers qu'ils souhaitent restaurer.  
  * Partagez un ou plusieurs répertoires du dossier Restore Mount sur la machine VRA. Les utilisateurs peuvent ensuite accéder au partage UNC et copier les fichiers et les dossiers qu'ils souhaitent restaurer.  
