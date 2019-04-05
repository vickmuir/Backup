---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, install agent, Linux

subcollection: Backup

---
{:codeblock: .codeblock}
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Installation du client de sauvegarde sous Linux
{: #InstallinLinux}

L'installation du client {{site.data.keyword.backup_full}} sur un système d'exploitation Linux peut être réalisée via une série de commandes de shell ou de terminal dans le système d'exploitation. Cette procédure décrit les étapes requises pour l'installation du client sur l'un des systèmes d'exploitation Linux suivants :

- RHEL
- CentOS
- CloudLinux

A l'issue de la procédure, le processus automatisé enregistre l'agent du service auprès du portail {{site.data.keyword.backup_notm}} puis télécharge et installe les fichiers nécessaires à l'exécution du service.

Si vous avez acheté {{site.data.keyword.backup_notm}} lors de la commande d'un serveur depuis le catalogue [{{site.data.keyword.cloud_notm}}]https://{DomainName}/catalog){:new_window} ou le portail {{site.data.keyword.slportal}}, le logiciel est automatiquement installé pour vous. Vous n'avez pas besoin de suivre les procédures décrites dans ce document.
{:tip}

Si vous avez fait l'acquisition d'{{site.data.keyword.backup_notm}} en tant que mise à niveau dans le portail {{site.data.keyword.slportal}}, procédez comme suit pour installer le logiciel.

## Connexion au serveur de l'unité cible
{: #logintargetLin}

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}]https://{DomainName}){:new_window} et cliquez sur l'icône **menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.<br/>
   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
2. Sélectionnez **Unités** > **Liste des unités** dans le menu principal pour afficher la liste des unités serveur disponibles.
3. Recherchez l'unité pour laquelle vous avez fait l'acquisition du service {{site.data.keyword.backup_notm}} et notez son adresse IP publique.
  - Celle-ci sera utilisée dans les étapes suivantes lorsque vous vous connecterez à l'unité depuis une invite de commande UNIX ou Linux. Remplacez <publicIpAddress> par l'adresse IP publique réelle dans la commande présentée à l'étape 5.
4. Cliquez sur la flèche pointant vers la droite pour afficher plus d'informations sur l'unité, notamment le nom d'utilisateur et le mot de passe.
  - Si le mot de passe n'est pas affiché, cochez la case **Afficher mot de passe** pour l'afficher. Le nom d'utilisateur et le mot de passe seront utilisés à l'étape suivante pour la connexion au dispositif de test. Remplacez `<user name>` par le nom de l'utilisateur réel.
5. Connectez-vous à l'unité cible en exécutant la commande suivante à partir d'une ligne de commande UNIX ou Linux :
   ```
   ssh <user name>@<publicIpAddress>
   ```
   {: pre}

   Si vous ne vous étiez pas encore connecté à ce serveur avec ce nom d'utilisateur, un message relatif à d'authenticité de l'hôte s'affiche. Vous êtes également invité à indiquer si vous souhaitez continuer. Répondez **oui** pour continuer.
   {:note}

6. Vous êtes invité à entrer le mot de passe sauf si vous avez déjà configuré des clés ssh pour accéder à ce serveur.

## Mise à jour du système d'exploitation pour préparer l'installation (RHEL uniquement)

Cette étape est obligatoire pour RHEL, mais facultative pour les autres distributions Linux.
{:tip}

- Exécutez la commande suivante à l'invite du serveur :
  ```
  yum update
  ```
  {: pre}

  Si vous y êtes invité, confirmez que la taille de téléchargement est correcte. La mise à jour est lancée et indique par un message quand elle est terminée.

## Obtention du script d'installation

- Exécutez la commande suivante à l'invite du serveur :
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}

## Exécution du script d'installation

1. Exécutez la commande suivante à l'invite du serveur :
   ```
   sh ./evault_manual.sh
   ```
   {: pre}

2. Entrez votre nom d'utilisateur et votre mot de passe de portail {{site.data.keyword.backup_notm}}.

   Pour plus d'informations sur l'affichage du nom d'utilisateur et du mot de passe {{site.data.keyword.backup_notm}}, voir [Initiation aux services de sauvegarde](/docs/infrastructure/Backup?topic=Backup-getting-started).
   {:tip}

3. Une fois le nom d'utilisateur et le mot de passe entrés, aucune autre entrée n'est requise. Vous pouvez en toute sécurité ignorer les invites qui s'affichent à l'écran concernant l'installation.

   Elles sont générées par un sous-script qui est démarré par le script `evault_manual.sh`. Le script `evault_manual.sh` fournit les entrées pour ces invites.
   {:note}

4. L'installation est terminée lorsque le message suivant s'affiche.

   ```
   Starting VVAgent: [  OK  ]
   Starting buagent: [  OK  ]
   ```
   {: codeblock}

## Vérification de l'aboutissement de l'installation

1. Vérifiez que le message "Registered to The Portal" figure dans la sortie de l'installation. Pour ce faire, vous pouvez rechercher le message sur l'écran ou inspecter la sortie de la commande suivante.
   ```
   grep 'Registered'  /opt/BUAgent/Install.log
   ```
   {: pre}

2. Exécutez la commande suivante et examinez sa sortie :
   ```
   service vvagent status
   ```
   {: pre}

   Les messages suivants s'affichent :
   ```
   VVAgent is running (PID xxxxx).
   buagent is running (PID xxxxx).
   ```
   {: codeblock}

  Les ID de processus représentés par `xxxxx` varient selon l'installation.
  {:tip}

**Etapes suivantes**

Connectez-vous au portail {{site.data.keyword.backup_notm}} pour configurer et gérer vos agents de sauvegarde. Pour plus d'informations, voir [Tutoriel d'initiation](/docs/infrastructure/Backup?topic=Backup-getting-started) et la rubrique [Configuration d'une sauvegarde simple au niveau fichier sous Linux](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup).
