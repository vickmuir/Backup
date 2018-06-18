---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-16"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Restauration à partir d'une sauvegarde

Cet article décrit les étapes de restauration de fichiers à l'aide d'EVault. Pour restaurer une image système, suivez les instructions pour [BMR Windows](restoring-evault-bmr-system-volume-image.html).

## Démarrez WebCC

**Remarque **: prenez soin de lancer votre connexion {{site.data.keyword.BluVPN}} pour pouvoir accéder au réseau privé {{site.data.keyword.BluSoftlayer_full}}, faute de quoi le lien WebCC ne fonctionnera pas.

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} et cliquez sur **Stockage** > **Sauvegarde** dans le menu principal pour afficher les serveurs jouissant du service de sauvegarde EVault. 
2. Sélectionnez le serveur sur lequel résident les fichiers à restaurer. Cliquez sur la flèche pour afficher le lien WebCC.
3. Cliquez sur **WebCC** pour lancer le client WebCC dans votre navigateur. 

## Effectuez la restauration

1. Dans le panneau de navigation de gauche, cliquez sur **Tous les agents**
2. Cliquez sur l'agent pour afficher les travaux.
3. Cliquez sur le travail contenant la sauvegarde désirée.
4. Cliquez sur **Exécuter la restauration**.
5. Sélectionnez une source de restauration.
6. Sélectionnez **Restaurer depuis un jeu sécurisé unique** ou **Restaurer depuis le jeu sécurisé saisi dans la zone de texte ci-dessous**. Les deux options ont le même effet.
7. Sélectionnez une version de sauvegarde ou entrez le numéro du jeu sécurisé (le premier dans la liste déroulante de sélection)
8. Entrez le mot de passe de chiffrement.
9. Cliquez sur **Suivant** pour continuer.
10. Cochez les cases en regard des fichiers et des répertoires que vous désirez englober, puis cliquez sur **Inclure** pour enregistrer vos sélections.
11. Vous pouvez filtrer davantage vos sélections à l'aide de l'écran en incrustation qui apparaît ou cliquer sur **OK** pour utiliser en l'état les sélections que vous avez effectuées. <br/>
Une fois que vous avez ajouté vos choix de fichiers et de répertoires, ceux-ci ne peuvent plus être sélectionnés dans le panneau **Fichiers de données**. Ils sont affichés dans le panneau **Groupe de sauvegarde** sur le côté droit de l'écran. Vous pouvez répéter l'étape 101 pour ajouter d'autres fichiers ou pour supprimer des fichiers que vous aviez ajoutés (à l'aide d'une instruction **Exclude**). Vous pouvez également utiliser l'option **Supprimer** pour éliminer une ligne quelconque du panneau **Groupe de sauvegarde**. Une fois ce groupe configuré comme vous le souhaitez, cliquez sur **Suivant** pour continuer.
12. Conservez les paramètres par défaut dans le panneau suivant ou personnalisez la restauration d'après vos préférences, puis cliquez sur **Exécuter la restauration**. 
13. Les fichiers sont complètement restaurés lorsque le statut affiche **Restauration terminée** sur l'écran **Informations du processus**.
