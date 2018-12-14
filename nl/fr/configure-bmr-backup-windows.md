---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configuration de travail de sauvegarde BMR sous Windows

**Prérequis**

Vous devez acquérir le plug-in BMR pour créer une sauvegarde BMR. BMR est disponible uniquement pour Bare Metal Servers sous Windows. Aucune option BMR n'est disponible pour les instances de service virtuel (VSI).

## Démarrage de WebCC

Vous devez être connecté au réseau privé {{site.data.keyword.BluSoftlayer_full}} pour pouvoir lancer WebCC.{:important}

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} et cliquez sur l'icône **Menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.

   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** > **Sauvegarde** pour afficher les serveurs avec service de sauvegarde.
3. Sélectionnez le serveur sur lequel se trouvent les fichiers à sauvegarder. Cliquez sur la flèche d'expansion pointant vers la droite pour dévoiler le lien WebCC.
4. Cliquez sur **Connexion WebCC** pour lancer le client WebCC dans votre navigateur.

   Si WebCC ne démarre pas, cela peut indiquer un problème au niveau de votre connexion VPN. Un message peut également s'afficher pour vous informer que le formulaire que vous envoyez n'est pas sécurisé. L'affichage de ce message est prévu ; vous pouvez envoyer le formulaire.
   {:tip}

## Configuration d'un travail de sauvegarde BMR

1. Dans le panneau de navigation de gauche, cliquez sur **Tous les agents** pour afficher les agents IBM Cloud Backup en cours.
2. Cliquez sur **Il s'agit d'un nouvel agent que je désire configurer**.
3. Entrez un nom et une description pour le travail que vous configurez ou créez.
4. Pour **Type de source de sauvegarde**, sélectionnez dans la liste le type de système de fichiers que vous désirez sauvegarder, puis cliquez sur **Suivant**
5. Le menu **Sélection du type de travail** s'affiche. Cochez la case en regard de **Bare Metal Restore**, puis cliquez sur **Suivant** pour continuer.
6. Cliquez sur **Oui** dans la fenêtre de confirmation.
7. L'écran indique que le nouveau travail fait à présent partie du groupe de sauvegarde. Cliquez sur **Suivant**.
8. L'écran affiche les options de chiffrement et les options de sauvegarde avancées. Normalement, vous ne devriez pas en avoir besoin. Cliquez sur **Suivant**.   
9. Sur la page **Créer un planning**, vous avez deux possibilités.
   - Vous pouvez cliquer sur **Suivant** pour créer un travail manuel et passer à l'exécution de votre nouveau travail.
   - Vous pouvez cliquer sur **Ajouter** pour planifier un travail de sauvegarde basé calendrier.
     1. Sélectionnez les jours et l'heure d'exécution de vos sauvegardes.
     2. Sélectionnez votre schéma de conservation.

Pour plus d'informations sur les schémas de conservation, voir la [Foire aux questions](faqs.html).
   {:tip}
     3. Après avoir configuré votre planning de sauvegarde, cliquez sur **OK** pour l'enregistrer. Votre travail planifié est ajouté à la liste de ces travaux.
10. Sélectionnez un coffre pour votre travail de sauvegarde, puis cliquez sur **Enregistrer les modifications**.


## Exécution d'un travail de sauvegarde BMR

  - Si vous avez planifié un travail de sauvegarde basé calendrier, vous n'avez rien d'autre à faire. Votre travail s'exécute automatiquement comme planifié.
  - Si vous avez configuré un travail manuel (sans planning basé calendrier), vous pouvez le lancer en sélectionnant sa ligne dans la liste des travaux et en cliquant sur **Effectuer la sauvegarde**. <br/> Comme pour les travaux basés calendrier, vous pouvez choisir le **Schéma de conservation**, ainsi que des **options de sauvegarde avancées**. Après avoir procédé à vos choix de configuration, cliquez sur **Lancer la sauvegarde** pour déclencher le travail.
