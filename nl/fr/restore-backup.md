---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-12"

---
{:new_window: target="_blank"}

# Restauration à partir d'une sauvegarde

Procédez comme indiqué ci-après pour effectuer une restauration de fichier à l'aide d'EVault. Pour restaurer une image système, suivez les instructions pour [BMR Windows](restoring-evault-bmr-system-volume-image.html).

## Démarrage de WebCC

**Remarque** : prenez soin de démarrer votre connexion {{site.data.keyword.BluVPN}} pour pouvoir accéder au réseau privé {{site.data.keyword.BluSoftlayer_full}}. Sinon, le lien WebCC ne fonctionnera pas. 

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} et cliquez sur **Stockage** > **Sauvegarde** dans le menu principal pour afficher les serveurs jouissant du service de sauvegarde EVault.
2. Sélectionnez le serveur sur lequel se trouvent les fichiers à sauvegarder. Cliquez sur la flèche pour afficher le lien WebCC.
3. Cliquez sur **WebCC** pour lancer le client WebCC dans votre navigateur.

## Restauration de vos données

1. Dans le panneau de navigation de gauche, cliquez sur **Tous les agents**
2. Cliquez sur l'agent pour afficher les travaux.
3. Cliquez sur le travail contenant la sauvegarde désirée.
4. Cliquez sur **Exécuter la restauration**.
5. Sélectionnez une source de restauration.
6. Sélectionnez une version de sauvegarde. 
7. Entrez le mot de passe de chiffrement.
8. Cliquez sur **Suivant** pour continuer.
9. Cochez les cases en regard des fichiers et des répertoires que vous désirez inclure, puis cliquez sur **Inclure** pour enregistrer vos sélections.
10. Vous pouvez filtrer davantage vos sélections à l'aide de la fenêtre qui s'affiche, ou cliquer sur **OK** pour utiliser en l'état les sélections que vous avez effectuées. <br/>
Une fois que vous avez ajouté vos choix en matière de fichiers et de répertoires, les fichiers ne peuvent plus être sélectionnés dans le panneau **Fichiers de données**. Ils sont affichés dans le panneau **Groupe de sauvegarde** sur la droite. <br/>**Remarque** : vous pouvez répéter l'étape 10 pour ajouter d'autres fichiers ou pour supprimer des fichiers que vous aviez ajoutés (à l'aide d'une instruction **Exclude**). <br/>Vous pouvez également utiliser l'option **Supprimer** pour éliminer une ligne quelconque du panneau **Groupe de sauvegarde**.
11. Une fois que vous avez configuré ce groupe de sauvegarde selon vos souhaits, cliquez sur **Suivant** pour continuer.
12. Conservez les paramètres par défaut dans le panneau suivant ou personnalisez la restauration d'après vos préférences, puis cliquez sur **Exécuter la restauration**.
13. Les fichiers sont restaurés lorsque le statut passe à **Restauration terminée** sur l'écran **Informations du processus**.
