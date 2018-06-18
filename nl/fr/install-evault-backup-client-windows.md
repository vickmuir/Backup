---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-14"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Installation du client de sauvegarde EVault sous Windows

L'installation du client de sauvegarde EVault sous Windows est réalisée via une série d'interactions alors que vous êtes connecté au serveur désigné pour le service de sauvegarde EVault. Procédez comme suit pour installer le client de sauvegarde EVault sous Windows.

**Remarque **: Windows 2016 n'est pas pris en charge actuellement.

## Connectez-vous au serveur de l'unité cible

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} et sélectionnez dans le menu principal **Unités** > **Liste des unités** pour afficher la liste des unités serveur disponibles.
2. Recherchez l'unité pour laquelle vous avez fait l'acquisition du service EVault et notez son adresse IP publique. 
3. Cliquez sur la flèche d'expansion pointant vers la droite pour révéler plus d'informations sur l'unité, notamment son nom d'utilisateur et mot de passe. Si le mot de passe n'est pas affiché, cochez la case **Afficher mot de passe** pour le révéler.  
4. Connectez-vous à l'unité cible à l'aide d'une connexion de bureau à distance (RDC).

## Téléchargez le client EVault

1. Sur le serveur cible, ouvrez une session de navigateur et entrez l'URL suivante pour télécharger le fichier exécutable du client de sauvegarde EVault. <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}
  
2. Double-cliquez sur le fichier téléchargé, puis cliquez sur **Exécuter** dans la boîte de dialogue en incrustation qui apparaît.


## Installez et enregistrez l'agent EVault
 
1. Entrez l'adresse réseau : <br />
  ```
  ev-webcc01.service.softlayer.com
  ```
  {: pre}
  
2. Entrez dans la zone **Nom d'utilisateur** le nom d'utilisateur de la sauvegarde EVault. 
3. Entrez dans la zone **Mot de passe** le mot de passe de la sauvegarde EVault. 
6. Cliquez sur **Suivant**. 
7. Cliquez sur **Installer** pour terminer l'installation.

## Etapes suivantes

Connectez-vous à WebCC pour configurer et gérer vos agents de sauvegarde. Reportez-vous au [Tutoriel d'initiation](index.html#configuring-evault-agent-in-webcc) pour les instructions.
