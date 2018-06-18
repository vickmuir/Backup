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

# Installation du client de sauvegarde EVault sous Linux 

L'installation du client de sauvegarde EVault sur un système d'exploitation Linux peut être réalisée via une série de commandes de shell ou de terminal dans le système d'exploitation. Cette procédure décrit les étapes requises pour l'installation du client de sauvegarde EVault sur l'un des systèmes d'exploitation Linux suivants :

- RedHat Enterprise Linux
- CentOS
- CloudLinux

A l'issue de la procédure, le processus automatisé enregistre l'agent du service auprès de WebCC. Téléchargez et installez ensuite les fichiers nécessaires à l'exécution du service. Procédez comme suit pour installer le client de sauvegarde EVault sur votre système d'exploitation Linux.

**Remarque **: si vous avez fait l'acquisition d'EVault lors de la commande d'un serveur depuis le portail {{site.data.keyword.slportal}}, le logiciel est automatiquement installé pour vous et vous n'avez pas besoin de suivre les procédures décrites dans ce document.

Si vous avez fait l'acquisition d'EVault en tant que mise à niveau dans le portail {{site.data.keyword.slportal}}, procédez comme suit pour installer le logiciel.

## Connectez-vous au serveur de l'unité cible

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} et sélectionnez dans le menu principal **Unités** > **Liste des unités** pour afficher la liste des unités serveur disponibles.
2. Recherchez l'unité pour laquelle vous avez fait l'acquisition du service EVault et notez son adresse IP publique. Celle-ci sera utilisée dans les étapes suivantes lorsque vous vous connectez à l'unité depuis une invite de commande UNIX ou Linux. Remplacez <publicIpAddress> par l'adresse IP publique réelle dans les commandes ci-dessous. 
3. Cliquez sur la flèche d'expansion pointant vers la droite pour révéler d'autres informations sur l'unité, notamment son nom d'utilisateur et mot de passe. Si le mot de passe n'est pas affiché, cochez la case **Afficher mot de passe** pour le révéler. Le nom d'utilisateur et le mot de passe seront utilisés à l'étape suivante pour vous connecter au dispositif de test. Remplacez `<user name>` par le nom de l'utilisateur réel dans la commande ci-dessous.
4. Connectez-vous à l'unité cible à l'aide de ssh en exécutant la commande suivante à partir d'une ligne de commande Unix ou Linux :
  ```
  ssh <user name>@<publicIpAddress>
  ```
  {: pre}
  
 **Remarque **: si vous ne vous étiez pas encore connecté à ce serveur avec ce nom d'utilisateur, un message d'authentification de l'utilisateur vous sera présenté et vous demandera si vous désirez continuer.  Répondez **oui** pour continuer.
5. Vous serez invité à entrer le mot de passe à moins que vous n'ayez déjà configuré des clés ssh pour accéder à ce serveur.

## Mettez à jour Linux pour préparer l'installation du client EVault (RedHat Linux uniquement)
**Remarque **: cette étape est obligatoire pour RedHat Linux, mais facultative pour les autres distributions Linux.

- Exécutez la commande suivante à l'invite du serveur :
  ```
  yum update
  ```
  {: pre}
   
  Si vous y êtes invité, confirmez que la taille de téléchargement est correcte. La mise à jour sera lancée et affichera un message "Terminé" à son achèvement.

## Extrayez le script d'installation EVault
- Exécutez la commande suivante à l'invite du serveur :
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}
   
## Exécutez le script d'installation EVault
1. Exécutez la commande suivante à l'invite du serveur :
  ```
  sh ./evault_manual.sh
  ```
  {: pre}

2. Entrez votre nom d'utilisateur et votre mot de passe WebCC.     
  **Remarque **: reportez-vous à l'article [Initiation aux services de sauvegarde](/docs/infrastructure/Backup/index.html) pour les instructions d'affichage du nom d'utilisateur et du mot de passe EVaultbackup.
3. Aucune entrée supplémentaire n'est requise après le nom d'utilisateur et le mot de passe, même si des invites peuvent s'afficher à l'écran au cours de l'installation. Ces invites peuvent être ignorées en toute sécurité. Elles sont générées par un sous-script appelé par le script *evault_manual.sh*.  Le script *evault_manual.sh* fournit les entrées pour ces invites.
4. Lorsque des messages similaires aux suivants apparaissent, l'installation est terminée :
  ```
  Starting VVAgent: [  OK  ]
  Starting buagent: [  OK  ]
  ```
  {: codeblock}
   
## Vérifiez que l'installation a abouti
1. Vérifiez que le message "Registered to The Portal" figure dans la sortie de l'installation. Pour ce faire, vous pouvez rechercher le message sur l'écran ou inspecter la sortie de la commande suivante :
  ```
  grep 'Registered'  /opt/BUAgent/Install.log
  ```
  {: pre}

2. Exécutez la commande suivante et examinez sa sortie : 
  ```
  service vvagent status
  ```
  {: pre}
   
  Les messages suivants doivent s'afficher :
  ```
  VVAgent is running (PID xxxxx).
  buagent is running (PID xxxxx).
  ```
  {: codeblock}
   
  **Remarque **: le processus représenté ci-dessus par 'xxxxx' varie selon l'installation. 
  
## Etapes suivantes

Connectez-vous à WebCC pour configurer et gérer vos agents de sauvegarde. Reportez-vous au [Tutoriel d'initiation](index.html#configuring-evault-agent-in-webcc) pour les instructions.
