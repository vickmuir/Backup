---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Sauvegarde et restauration depuis une instance de serveur virtuel vers une autre dans le même centre de données

Vous voudrez parfois restaurer des données sur un serveur différent dans le même centre de données. Ces instructions vous aideront à accomplir cette tâche. Cette procédure s'applique uniquement aux restaurations de niveau fichier de fichiers ne faisant pas partie du système d'exploitation. Pour restaurer une image système, suivez les instructions pour [BMR Windows](restoring-evault-bmr-system-volume-image.html).

Cette procédure inclut le réenregistrement de l'agent EVault sur le second serveur pour accéder à l'emplacement EVAult du premier serveur et la réalisation d'une **restauration à partir d'un autre ordinateur**.


## Conditions prérequises

- Serveur1 et Serveur 2 doivent avoir le même système d'exploitation. Les restaurations inter-plateformes ne sont pas prises en charge.
- Serveur 1 et serveur 2 doivent avoir configuré des agents EVAult. Cliquez [ici](index.html#configuring-evault-agent-in-webcc) pour découvrir comment configurer les agents EVault 
- Une tâche de sauvegarde pour Serveur1 a généré une sauvegarde sur l'emplacement EVault de Serveur1.

**Remarque **: pour éviter des conflits, désactivez tous les travaux planifiés sur les deux serveurs. 

## Lancez le WebCC de Serveur2

**Remarque **: prenez soin de démarrer votre connexion {{site.data.keyword.BluVPN}} pour pouvoir accéder au réseau privé {{site.data.keyword.BluSoftlayer_full}}, faute de quoi les liens WebCC ne fonctionneront pas.

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} et cliquez sur **Stockage** > **Sauvegarde** dans le menu principal pour afficher les serveurs jouissant du service de sauvegarde EVault. 
2. Sélectionnez Serveur2. Cliquez sur la flèche d'expansion pointant vers la droite pour dévoiler le lien WebCC.
3. Cliquez sur **Connexion WebCC** pour lancer le client WebCC dans votre navigateur.

## Enregistrez à nouveau l'EVault :
1. Cliquez sur **tous les agents** et ouvrez l'agent spécifique que vous désirez modifier.
2. Cliquez sur **Editer** et sélectionnez *Paramètres du coffre".
3. Cliquez sur **Réenregistrer** pour connecter Serveur1 à Serveur2.
4. Sur l'écran **Réenregistrer le coffre** pour l'entrée **Utiliser un profil de coffre**, sélectionnez **Entrer les paramètres du coffre**.
5. Entrez le nom du coffre, lequel est le même que le nom EVault de Serveur1.
6. Entrez les données d'identification de Serveur 1 pour vous connecter au EVault de ce serveur.
7. Cliquez sur **Charger les ordinateurs**. Ceci affiche les serveurs rattachés à l'emplacement du coffre.
8. Cliquez sur **Enregistrer les modifications**.
9. A l'invite, cliquez sur **Oui** pour confirmer le réenregistrement d'EVault.

## Exécutez le travail de sauvegarde de Serveur1 en tant que travail de restauration sur Serveur2

1. Cliquez sur **Tous les agents**. <br/> **Remarque **: vous devrez éventuellement actualiser la page afin que les travaux définis sur Serveur1 indiquent qu'ils sont accessibles/synchronisés sous l'onglet **Travaux** de Serveur2.
2. Survolez **Avancé** et sélectionnez **Restaurer à partir d'un autre ordinateur**.
3. Sur l'écran **Restaurer à partir d'un autre ordinateur**, effectuez les sélections suivantes :
  - Coffre : cette entrée doit recevoir par défaut l'EVault de Serveur1.
  - Ordinateur : sélectionnez Serveur1 comme ordinateur de sauvegarde depuis lequel effectuer la restauration. 
  - Travail : sélectionnez le travail de sauvegarde de Serveur1.
4. Cliquez sur **Suivant**.
5. Confirmez les informations sur la source. 
  - **Emplacement du jeu sécurisé** : doit correspondre à l'emplacement du coffre pour Serveur1.
  - Dans la section **Sélectionner une version de sauvegarde**, celle spécifiée doit correspondre à votre sauvegarde depuis Serveur1
  - Le mot de passe de chiffrement doit être celui que vous avez utilisé lors de l'exécution de la sauvegarde sur Serveur1.
6. Cliquez sur **Suivant**.
7. Sélection de données : sélectionnez les fichiers devant être restaurés depuis la sauvegarde de Serveur1. Cochez les cases en regard des fichiers et des répertoires que vous désirez englober, puis cliquez sur **Inclure** pour enregistrer vos sélections.
8. Cliquez sur **Suivant** pour accéder aux options de restauration.
9. Dans Options :
  - Destination : sélectionnez **Restaurer à l'emplacement d'origine**
  - Ecrasement de fichiers : sélectionnez **Ecraser les fichiers existants**
10. Cliquez sur **Exécuter la restauration**.
11. L'écran Informations du processus affiche le statut du travail de restauration.


## Vérifiez la restauration

1. Connectez-vous à la racine de Serveur2 via SSH.
2. Recensez les fichiers, notamment les entrées de répertoire au format long.
  ```
  ls -la
  ```
  {: pre}
  
3. Comparez la sortie.
  
## Reprenez le planning de sauvegarde normal.

1. Lorsque la restauration est terminée, supprimez les informations d'enregistrement du Serveur1, depuis lequel les données ont été restaurées. 
2. Entrez l'enregistrement Serveur2 actuel et activez les tâches de planning.
 

  

 
 
  
  
