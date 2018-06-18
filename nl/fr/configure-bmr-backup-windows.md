---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:new_window: target="_blank"}

# Configuration de travail de sauvegarde BMR sous Windows

## Prérequis

Vous devez acquérir le plug-in BMR pour effectuer une sauvegarde BMR. BMR est disponible uniquement pour Bare Metal Servers sous Windows. Aucune option BMR n'est disponible pour les instances de service virtuel (VSI).

## Lancement de WebCC
**Remarque **: vous devez être connecté au réseau privé {{site.data.keyword.BluSoftlayer_full}} pour pouvoir lancer WebCC.
1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} et cliquez sur **Stockage** > **Sauvegarde** dans le menu principal pour afficher les serveurs jouissant du service de sauvegarde EVault. 
2. Sélectionnez le serveur sur lequel résident les fichiers à sauvegarder. Cliquez sur la flèche d'expansion pointant vers la droite pour dévoiler le lien WebCC.
4. Cliquez sur **Connexion WebCC** pour lancer le client WebCC dans votre navigateur.**Remarque **: si WebCC ne démarre pas, ceci peut dénoter un problème avec votre connexion VPN. Un message pourrait également vous aviser que le formulaire que vous envoyez n'est pas sécurisé. Ceci est dans l'ordre des choses, envoyez donc le formulaire.
  
## Configuration d'un travail de sauvegarde BMR

1. Dans le panneau de navigation de gauche, cliquez sur **Tous les agents** pour afficher les agents EVault en cours
2. Cliquez sur **Il s'agit d'un nouvel agent que je désire configurer**. 
3. Entrez un nom et une description du travail que vous configurez ou créez.
4. Pour **Type de source de sauvegarde**, sélectionnez dans le menu déroulant le type de système de fichiers que vous désirez sauvegarder, puis cliquez sur **Suivant**
5. Le menu **Sélection du type de travail** s'affiche. Cochez la case en regard de **Bare Metal Restore**, puis cliquez sur **Suivant** pour continuer.
6. Cliquez sur **Oui** dans la fenêtre de confirmation.
7. L'écran indique que le nouveau travail fait à présent partie du groupe Sauvegarde. Cliquez sur **Suivant**.
8. L'écran affiche les options de chiffrement et les options de sauvegarde avancées. Normalement, vous ne devriez pas en avoir besoin. Cliquez sur **Suivant** pour accéder à l'écran **Créer un planning**.   
9. Sur la page **Créer un planning**, cliquez sur **Ajouter** pour planifier un travail de sauvegarde ponctuel ou sur **Suivant** pour créer un travail manuel.
  - Si vous choisissez de créer un travail manuel, passez à l'exécution de votre nouveau travail.
  - Si vous optez pour un travail basé calendrier, sélectionnez les jours et l'heure auxquels effectuer vos sauvegardes.
  - Sélectionnez votre schéma de conservation. Cliquez [ici](evault-backup-faq.html#how-do-the-retention-schemes-work-) pour plus d'informations sur les schémas de conservation.
  - Après avoir configuré votre planning de sauvegarde, cliquez sur **OK** pour l'enregistrer. Votre travail planifié est ajouté à la liste de ces travaux. 
10. Sélectionnez un coffre pour votre travail de sauvegarde, puis cliquez sur **Enregistrer les modifications**.


## Exécution d'un travail de sauvegarde BMR
  - Si vous avez planifié un travail de sauvegarde basé calendrier, vous n'avez pas à effectuer d'étapes supplémentaires. Votre travail s'exécutera automatiquement comme planifié.
  - Si vous avez configuré un travail manuel (sans planning basé calendrier), vous pouvez le lancer en sélectionnant sa ligne dans la liste des travaux et en cliquant sur **Effectuer la sauvegarde**. <br/> Comme pour les travaux basés calendrier, vous pouvez choisir le **Schéma de conservation**, ainsi que des **Options de sauvegarde avancées**. Après avoir procédé à vos choix de configuration, cliquez sur **Lancer la sauvegarde** pour déclencher le travail.
