---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-10"

keywords: IBM Cloud backup, EVault, Carbonite, backup, configure BMR, bmr plug-in, bmr plugin, configuration

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configuration de travail de sauvegarde BMR sous Windows
{: #configureBMR}

Vous devez acquérir le plug-in BMR pour créer une sauvegarde BMR. BMR est disponible uniquement pour Bare Metal Servers sous Windows. Aucune option BMR n'est disponible pour les instances de service virtuel (VSI). Pour plus d'informations, voir [Installation du plug-in Bare Metal Restore](/docs/infrastructure/Backup?topic=Backup-BMRplugin#BMRplugin)
{:important}

## Démarrage du portail {{site.data.keyword.backup_notm}}
{: #startWebCCBMR}

Vous devez être connecté au réseau privé {{site.data.keyword.cloud}} pour pouvoir lancer le portail {{site.data.keyword.backup_notm}}.
{:important}

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} et cliquez sur l'icône **menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.
2. Cliquez sur **Stockage** > **Sauvegarde** pour afficher les serveurs avec services de sauvegarde.
3. Sélectionnez le serveur sur lequel se trouvent les fichiers à sauvegarder. Cliquez sur la flèche d'expansion pointant vers la droite pour afficher le lien du portail {{site.data.keyword.backup_notm}}.
4. Cliquez sur **Connexion au portail {{site.data.keyword.backup_notm}}** pour lancer le client de portail dans votre navigateur.

   Si le portail {{site.data.keyword.backup_notm}} ne démarre pas, cela peut indiquer un problème au niveau de votre connexion VPN. Un message peut également s'afficher pour vous informer que le formulaire que vous envoyez n'est pas sécurisé. L'affichage de ce message est prévu ; vous pouvez envoyer le formulaire.
   {:tip}

## Configuration d'un travail de sauvegarde BMR

1. Dans le panneau de navigation de gauche, cliquez sur **Tous les agents** pour afficher les agents {{site.data.keyword.backup_notm}} en cours.
2. Cliquez sur **Il s'agit d'un nouvel agent que je désire configurer**.
3. Entrez un nom et une description pour le travail que vous créez.
4. Pour **Type de source de sauvegarde**, sélectionnez le type de système de fichiers, puis cliquez sur **Suivant**.
5. Le menu **Sélection du type de travail** s'affiche. Cochez la case en regard de **Bare Metal Restore**, puis cliquez sur **Suivant** pour continuer.
6. Cliquez sur **Oui** dans la fenêtre de confirmation.
7. L'écran indique que le nouveau travail fait à présent partie du groupe de sauvegarde. Cliquez sur **Suivant**.
8. L'écran affiche les options de chiffrement et les options de sauvegarde avancées. Normalement, vous ne devriez pas en avoir besoin. Cliquez sur **Suivant**.   
9. Sur la page **Créer un planning**, vous avez deux possibilités.
   - Cliquez sur **Suivant** pour créer un travail manuel et passer à l'exécution de votre nouveau travail.
   - Vous pouvez cliquer sur **Ajouter** pour planifier un travail de sauvegarde basé calendrier.
     1. Sélectionnez les jours et l'heure d'exécution de vos sauvegardes.
     2. Sélectionnez votre schéma de conservation.

        Pour plus d'informations sur les schémas de conservation, voir la [Foire aux questions](/docs/infrastructure/Backup?topic=Backup-faqs).
        {:tip}
     3. Après avoir configuré votre planning de sauvegarde, cliquez sur **OK** pour l'enregistrer. Votre travail planifié est ajouté à la liste de ces travaux.
10. Sélectionnez un coffre pour votre travail de sauvegarde, puis cliquez sur **Enregistrer les modifications**.


## Exécution d'un travail de sauvegarde BMR

  - Si vous avez planifié un travail de sauvegarde basé calendrier, vous n'avez rien d'autre à faire. Votre travail s'exécute automatiquement comme planifié.
  - Si vous avez configuré un travail manuel (sans planning basé calendrier), vous pouvez le lancer en sélectionnant sa ligne dans la liste des travaux et en cliquant sur **Effectuer la sauvegarde**. <br/> Comme pour les travaux basés calendrier, vous pouvez choisir le **Schéma de conservation**, ainsi que des **options de sauvegarde avancées**. Après avoir procédé à vos choix de configuration, cliquez sur **Lancer la sauvegarde** pour déclencher le travail.
