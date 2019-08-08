---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud backup, EVault, Carbonite, backup, install agent, Windows

subcollection: Backup

---
{:pre: .pre}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Installation du client de sauvegarde sous Windows
{: #InstallinWindows}

L'installation du client {{site.data.keyword.backup_full}} sous Windows est réalisée via une série d'interactions sur le serveur désigné pour le service {{site.data.keyword.backup_notm}}.

Pour plus d'informations sur les sauvegardes pour les serveurs Windows 2016, voir [Configuration de {{site.data.keyword.backup_notm}} sous Windows 2016](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016).
{:tip}

## Connexion au serveur de l'unité cible
{: #logintargetWin}

1. Connectez-vous à la console [{{site.data.keyword.cloud_notm}}](https://{DomainName}){: external}. Dans le menu de navigation, sélectionnez **Infrastructure classique**.
2. Sélectionnez **Unités** > **Liste des unités** dans le menu principal pour afficher la liste des serveurs disponibles.
3. Recherchez l'unité pour laquelle vous avez fait l'acquisition du service {{site.data.keyword.backup_notm}} et notez son adresse IP publique.
4. Cliquez sur la flèche pour développer l'arborescence et afficher plus d'informations sur l'unité, notamment le nom d'utilisateur et le mot de passe. Si le mot de passe n'est pas affiché, cliquez sur **Afficher mot de passe** pour l'afficher.
5. Connectez-vous à l'unité cible à l'aide d'une connexion de bureau à distance.

## Téléchargement du client de sauvegarde

1. Sur le serveur cible, ouvrez une session de navigateur et entrez l'URL suivante pour télécharger le fichier exécutable du client {{site.data.keyword.backup_notm}}. <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}

2. Cliquez deux fois sur le fichier téléchargé.
3. Cliquez sur **Exécuter**.


## Installation et enregistrement de l'agent de sauvegarde

1. Entrez l'adresse réseau : <br />
  ```
  ev-webcc01.service.softlayer.com
  ```
  {: pre}

2. Entrez le nom de l'utilisateur dans la zone **nom d'utilisateur**.
3. Entrez le mot de passe dans la zone **mot de passe**.
6. Cliquez sur **Suivant**.
7. Cliquez sur **Installer** pour terminer l'installation.

## Configuration des agents de sauvegarde

Connectez-vous au portail {{site.data.keyword.backup_notm}} pour configurer et gérer vos agents de sauvegarde. Pour plus d'informations, voir le [Tutoriel d'initiation](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).
