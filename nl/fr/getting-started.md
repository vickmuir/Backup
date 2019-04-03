---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-28"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}_
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:shortdesc: .shortdesc}

# Tutoriel d'initiation
{: #gettingstarted}

Les sauvegardes permettent de stocker en toute sécurité vos données hors de votre appareil et de les protéger si celui-ci venait à être perdu. {{site.data.keyword.backup_full}} est un système de sauvegarde automatisé basé sur un agent qui est géré via l'utilitaire de gestion de portail {{site.data.keyword.backup_notm}} reposant sur un navigateur. {{site.data.keyword.backup_notm}} fournit aux utilisateurs une méthode de sauvegarde des données entre les serveurs d'un ou de plusieurs centres de données sur le réseau {{site.data.keyword.BluSoftlayer_full}}. Les administrateurs peuvent faire en sorte que des sauvegardes soient effectuées tous les jours, toutes les semaines ou définir des sauvegardes personnalisées qui ciblent des systèmes complets, des répertoires spécifiques ou même des fichiers individuels. Des plug-ins supplémentaires permettent la compatibilité avec des logiciels tels que Microsoft Exchange et Microsoft SQL, ainsi qu'avec d'autres types de logiciels tiers. Ils permettent également aux utilisateurs d'effectuer une restauration physique, en cas de besoin.
{:shortdesc}

## Avant de commencer
{: #prereqs}

Vous devez disposer d'une licence valide pour utiliser IBM Cloud Backup. Vous pouvez acquérir le service {{site.data.keyword.backup_notm}} de deux manières.

- [Acquisition de sauvegardes lors de la commande d'un serveur](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingwithserver).
- [Acquisition de sauvegardes sous forme de mise à niveau](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingasupgrade).

Pour plus d'informations sur la commande et la tarification, voir [Mise à disposition de {{site.data.keyword.backup_notm}}](/docs/infrastructure/Backup?topic=Backup-ordering).

## Installation de l'agent {{site.data.keyword.backup_notm}}

L'agent {{site.data.keyword.backup_notm}} est pris en charge sur les systèmes d'exploitation suivants :

**Windows**
 - Windows Server 2016
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

**Linux**
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - RHEL 7.x
 - RHEL 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

Suivez les instructions correspondant à votre système d'exploitation.
- [Installation du client de sauvegarde sous Linux](/docs/infrastructure/Backup?topic=Backup-InstallinLinux)
- [Installation du client de sauvegarde sous Windows](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)
- [Installation du client de sauvegarde sous Windows 2016](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016)

## Accès au portail {{site.data.keyword.backup_notm}} (anciennement WebCC)

Le portail {{site.data.keyword.backup_notm}} est utilisé pour interagir avec un service {{site.data.keyword.backup_notm}} offert par {{site.data.keyword.BluSoftlayer_full}}. Le portail {{site.data.keyword.backup_notm}} est un client reposant sur un navigateur qui s'exécute sur le réseau privé {{site.data.keyword.BluSoftlayer_full}} et permet de contrôler totalement un service {{site.data.keyword.backup_notm}}, notamment pour la configuration et les restaurations.

1. Accédez au réseau privé via VPN.

   Le portail {{site.data.keyword.backup_notm}} n'est pas accessible via le réseau public. Une connexion VPN doit d'abord être établie.
   {:important}
2. Accédez à l'écran de stockage de sauvegarde sur le portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
3. Cliquez n'importe où sur la ligne du service {{site.data.keyword.backup_notm}} que vous voulez afficher pour développer la vue.
4. Cliquez sur **Connexion au portail {{site.data.keyword.backup_notm}}** pour lancer le client de portail dans votre navigateur.

## Configuration de l'agent de sauvegarde et du planning de sauvegarde

Une fois que vous avez commandé votre {{site.data.keyword.backup_notm}} et que l'agent a été installé sur le serveur, vous pouvez commencer à créer des sauvegardes de vos données. Procédez comme suit pour configurer votre agent et le planning de conservation.

1. Connectez-vous au portail {{site.data.keyword.backup_notm}}.
2. Cliquez sur **Tous les agents**> **Agents non configurés**.
3. Cliquez sur le lien **Il s'agit d'un nouvel agent que je désire configurer**. Suivez cette procédure en spécifiant les informations suivantes :
   1. Configuration de l'agent - fournissez la description, puis cliquez sur **suivant**.
   2. Sélection d'un type de travail - entrez le nom du travail, sa description, le type de source de la sauvegarde, puis cliquez sur **suivant**.
   3. Sélection - sélectionnez des répertoires et cliquez sur **Inclure...**
   4. Options - fournissez des mots de passe
   5. Planning - cliquez sur **Ajouter** pour créer un planning, puis cliquez sur **Suivant**.
   6. Sélectionnez le coffre par défaut, puis cliquez sur **OK**.
   7. Cliquez sur **Enregistrer**.
4. Créez un planning de conservation.
   1. Sélectionnez **Editer** > **Paramètres de l'agent**.
   2. Cliquez sur **Ajouter**.
   3. Renseignez les informations de conservation de vos données.
   4. Cliquez sur **OK**.
   5. Cliquez sur **Enregistrer**.

      Pour plus d'informations sur les schémas de conservation, voir la [Foire aux questions](/docs/infrastructure/Backup?topic=Backup-faqs#faqs).
      {:tip}

## Exécution de votre premier travail de sauvegarde

1. Connectez-vous au portail {{site.data.keyword.backup_notm}}.
2. Cliquez sur **Tous les agents**, puis sélectionnez celui que vous avez configuré.
3. Cliquez sur **Exécuter une sauvegarde**.
4. Confirmez la destination de sauvegarde et sélectionnez un schéma de conservation des données.
5. Cliquez sur **Lancer la sauvegarde**. Vous pouvez afficher les détails de la sauvegarde pendant l'exécution du processus.
6. Une fois la sauvegarde terminée, cliquez sur **Fermer**.

Pour plus d'informations, voir [Configuration d'une sauvegarde simple au niveau fichier sous Linux](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup).
{:tip}

## Accès et examen des détails du stockage du service de stockage {{site.data.keyword.backup_notm}} dans la console

Vous pouvez à tout moment accéder aux détails du stockage de votre service dans la console [{{site.data.keyword.cloud_notm}}](https://{DomainName}/){:new_window} et le portail {{site.data.keyword.slportal}}. Les détails que vous pouvez consulter comprennent le mot de passe, l'adresse de stockage et l'utilisation qui sont associés au service {{site.data.keyword.backup_notm}} sélectionné.

1. Connectez-vous à la console [{{site.data.keyword.cloud_notm}} ](https://{DomainName}){:new_window} et cliquez sur l'icône **menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.</br>
   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** et sélectionnez **Sauvegarde** dans la liste.
2. Cliquez n'importe où sur la ligne du coffre dont vous souhaitez examiner les informations de stockage. Dans cette vue, le mot de passe n'est pas visible.
3. Cochez la case **Afficher** en regard de la zone **Mot de passe** pour examiner le mot de passe du service {{site.data.keyword.backup_notm}} sélectionné.

Les modifications apportées au mot de passe {{site.data.keyword.backup_notm}} dans le portail {{site.data.keyword.slportal}} sont appliquées au service proprement dit. Pour réinitialiser votre mot de passe, suivez la procédure décrite dans [Modification du mot de passe d'un service de sauvegarde](/docs/infrastructure/Backup?topic=Backup-changePassword).
{:important}

## Obtention d'aide supplémentaire en ligne

Les systèmes de portail {{site.data.keyword.backup_notm}} disposent d'une documentation complète et le support de l'application est accessible depuis le portail {{site.data.keyword.backup_notm}}. Cliquez sur le point interrogation blanc dans un cercle bleu situé dans l'angle supérieur droit pour obtenir de l'**aide**. Cliquez sur un article ou une rubrique dans la barre de navigation sur le côté gauche pour afficher davantage d'informations.
