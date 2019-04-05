---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, configuration, linux

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configuration d'une sauvegarde simple au niveau fichier sous Linux
{: #configureLinuxBackup}

Une fois que vous avez commandé votre {{site.data.keyword.backup_full}} et que l'agent a été installé sur le serveur, vous pouvez commencer à créer des sauvegardes de vos données. Cet article décrit les étapes de configuration de votre agent, le planning de conservation des données et le déclenchement de votre premier travail de sauvegarde.

## Démarrage du portail {{site.data.keyword.backup_notm}}
{: #startWebCCconfigLin}

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}]https://{DomainName}){:new_window} et cliquez sur l'icône **menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**. <br>
   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** > **Sauvegarde** pour afficher les serveurs avec service de sauvegarde.
2. Sélectionnez le serveur sur lequel se trouvent les fichiers à sauvegarder. Cliquez sur la flèche d'expansion pointant vers la droite pour afficher le lien du portail {{site.data.keyword.backup_notm}}.
3. Démarrez votre connexion VPN pour pouvoir accéder au réseau privé IBM.
4. Cliquez sur le lien de connexion au portail {{site.data.keyword.backup_notm}} pour démarrer le client de portail dans votre navigateur.<br/>

  Si le portail {{site.data.keyword.backup_notm}} ne démarre pas, cela peut indiquer un problème au niveau de votre connexion VPN. Un message peut également s'afficher pour vous informer que le formulaire que vous envoyez n'est pas sécurisé. L'affichage de ce message est prévu ; vous pouvez envoyer le formulaire.
  {:tip}

## Configuration d'un travail de sauvegarde

1. Dans le panneau de navigation, cliquez sur **Tous les agents** pour afficher les agents {{site.data.keyword.backup_notm}} en cours.
2. Cliquez sur **Il s'agit d'un nouvel agent que je désire configurer**.
3. Entrez un nom et une description pour le travail que vous créez.
4. Pour **Type de source de sauvegarde**, sélectionnez le type de système de fichiers que vous voulez sauvegarder.
5. Cliquez sur **Suivant** pour continuer.
6. Dans le panneau des fichiers de données, accédez aux fichiers et aux répertoires que vous voulez inclure dans votre sauvegarde en cliquant sur les signes **+** et **-** en regard des icônes de dossier.
7. Cochez les cases en regard des fichiers et des répertoires que vous désirez inclure, puis cliquez sur **Inclure** pour enregistrer vos sélections.
8. Vous pouvez filtrer davantage vos sélections à l'aide de l'écran en incrustation qui apparaît, ou cliquer sur **OK** pour utiliser en l'état les sélections que vous avez effectuées. Une fois que vous avez ajouté vos choix en matière de fichiers et de répertoires, ceux-ci s'affichent dans le panneau de groupe de sauvegarde sur le côté droit de l'écran. Cliquez sur **Suivant** pour continuer.

   Vous pouvez répéter les étapes 6 à 8 pour ajouter d'autres fichiers ou supprimer (à l'aide du bouton **Exclure**) des fichiers que vous aviez déjà ajoutés. Vous pouvez également utiliser l'option **Retirer** pour supprimer une ligne d'article du panneau de groupe de sauvegarde. Une fois ce groupe de sauvegarde configuré comme vous le souhaitez,
   {:tip}
9. Sélectionnez le type de chiffrement voulu.
  - Si vous ne désirez pas chiffrer votre sauvegarde, sélectionnez **Aucune**.
  - Si vous désirez la chiffrer, sélectionnez **AES 256 bits** et renseignez les champs Mot de passe et Vérifier le mot de passe. Vous pouvez également ajouter une indication quant au mot de passe.

    Vous aurez besoin de ce mot de passe en vue de restaurer des fichiers depuis la sauvegarde. Vous ne pouvez pas restaurer une sauvegarde chiffrée sans connaître le mot de passe et il n'est pas possible de récupérer un mot de passe égaré.
    {:important}
10. Vous pouvez utiliser n'importe laquelle des **options avancées**.
  - **Conservation** - cette option vous permet de gérer l'utilisation de vos données. La durée de conservation détermine pendant combien de temps votre sauvegarde est conservée. Une fois la durée de conservation écoulée, la sauvegarde est automatiquement supprimée. Options intégrées : quotidienne, hebdomadaire ou mensuelle.
  - **Compression** - cette option vous permet de réduire la capacité qui est utilisée pour l'enregistrement des sauvegardes.
  - **Fichiers de sauvegarde qui sont ouverts pour l'écriture** - cette option permet la sauvegarde de fichiers, même s'ils sont ouverts par une application alors que le travail de sauvegarde s'exécute.
  - **Créer un fichier journal** - cette option vous permet de créer et gérer le contenu et la conservation des fichiers journaux générés au cours du processus de sauvegarde.
  - **Sauvegarde d'une instance unique de tous les fichiers à lien fixe sélectionnés**. Cette option ne s'applique qu'aux systèmes de style UNIX. Si vous utilisez des liens fixes pour créer plusieurs noms de fichiers pour le même contenu, cette option entraîne la sauvegarde d'une seule copie du contenu. Au cours de la restauration, tous les liens fixes sont restaurés. Cette option requiert un passage précédant l'analyse à travers la sélection de fichiers, ce qui peut prendre un temps significatif et monopoliser de la mémoire.
11. Après votre choix de chiffrement, cliquez sur **Suivant** pour accéder à l'écran **Créer un planning**.
12. Sur la page Créer un planning, cliquez sur **Ajouter** pour programmer un travail de sauvegarde basé calendrier ou sur **Suivant** pour créer un travail manuel.
  - Si vous décidez de créer un travail manuel, passez à l'étape 15.
  - Si vous optez pour un travail basé calendrier, sélectionnez les jours et l'heure auxquels effectuer vos sauvegardes.
  - Sélectionnez votre schéma de conservation. Pour plus d'informations sur les schémas de conservation, voir la [Foire aux questions](/docs/infrastructure/Backup?topic=Backup-faqs).
  - Cliquez sur **Options de planning avancées** pour obtenir plus de choix en matière de configuration. Vous pouvez sélectionner **Déferrer** pour empêcher l'exécution de sauvegardes volumineuses aux heures de pointe sur le réseau.

    Lorsque cette option est activée, le travail de sauvegarde ne sauvegarde pas de nouvelles données après le délai imparti. Il consigne le jeu sécurisé dans le coffre, et ce même si certaines données dans le travail n'ont pas été sauvegardées. Les modifications des données préalablement sauvegardées sont sauvegardées, sans tenir compte de la période de temps spécifiée. <br/> Lorsque le travail s'exécute à nouveau, l'agent vérifie les changements de données sauvegardées auparavant, sauvegarde ces modifications, puis les données restantes. Si un travail de sauvegarde a été reporté alors qu'un élément est en cours de sauvegarde, la sauvegarde de cet élément est incomplète et les données de cet élément ne peuvent pas être restaurées. Vous pouvez toutefois restaurer des éléments qui ont été sauvegardés dans le travail avant le report de ce travail.
    {:note}
13. Après avoir configuré votre planning de sauvegarde, cliquez sur **OK** pour l'enregistrer. Votre travail planifié est ajouté à la liste des travaux planifiés.
  - Vous pouvez répéter l'étape 12 pour planifier d'autres sauvegardes.
  - Pour mettre à jour un travail de sauvegarde existant, sélectionnez celui-ci en cliquant sur sa ligne, puis sur **Editer** et apportez vos modifications.
14. Sélectionnez un coffre pour votre travail de sauvegarde, puis cliquez sur **Enregistrer les modifications**.
15. Exécutez un travail de sauvegarde
  - Si vous avez planifié un travail de sauvegarde basé calendrier, vous n'avez rien d'autre à faire. Votre travail s'exécute automatiquement comme planifié.
  - Si vous avez configuré un travail manuel (sans planning basé calendrier), vous pouvez le lancer en sélectionnant sa ligne dans la liste des travaux et en cliquant sur **Effectuer la sauvegarde**. Comme pour les travaux basés calendrier, vous pouvez choisir le **Schéma de conservation**, ainsi que des **Options de sauvegarde avancées**. Après avoir procédé à vos choix de configuration, cliquez sur **Lancer la sauvegarde** pour déclencher le travail.
