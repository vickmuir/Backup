---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-26"

---
{:pre: .pre}
{:new_window: target="_blank"}

# Installation du client de sauvegarde EVault sous Windows

L'installation du client de sauvegarde EVault sous Windows est réalisée via une série d'interactions sur le serveur désigné pour le service de sauvegarde EVault.

**Remarque** : Windows 2016 n'est pas pris en charge actuellement. Voir les instructions qui s'appliquent à [Windows 2016](install-evault-windows2016.html)

## Connexion au serveur de l'unité cible

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} et sélectionnez **Unités** > **Liste des unités** dans le menu principal pour afficher la liste des serveurs disponibles.
2. Recherchez l'unité pour laquelle vous avez fait l'acquisition du service EVault et notez son adresse IP publique.
3. Cliquez sur la flèche pointant vers la droite pour développer l'arborescence et afficher plus d'informations sur l'unité, notamment le nom d'utilisateur et le mot de passe. Si le mot de passe n'est pas affiché, cliquez sur **Afficher mot de passe** pour l'afficher. 
4. Connectez-vous à l'unité cible à l'aide d'une connexion de bureau à distance.

## Téléchargement du client EVault

1. Sur le serveur cible, ouvrez une session de navigateur et entrez l'URL suivante pour télécharger le fichier exécutable du client de sauvegarde EVault. <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}
  
2. Cliquez deux fois sur le fichier téléchargé.
3. Cliquez sur **Exécuter**.


## Installation et enregistrement de l'agent EVault
 
1. Entrez l'adresse réseau : <br />
  ```
  ev-webcc01.service.softlayer.com
  ```
  {: pre}
  
2. Entrez dans la zone **Nom d'utilisateur** le nom d'utilisateur EVault. 
3. Entrez dans la zone **Mot de passe** le mot de passe EVault. 
6. Cliquez sur **Suivant**. 
7. Cliquez sur **Installer** pour terminer l'installation.

## Configuration d'agents de sauvegarde

Connectez-vous à WebCC pour configurer et gérer vos agents de sauvegarde. Reportez-vous au [Tutoriel d'initiation](index.html#configuring-evault-agent-in-webcc) pour obtenir des instructions.
