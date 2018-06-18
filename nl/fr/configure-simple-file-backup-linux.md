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

# Configuration d'une sauvegarde simple au niveau fichier sur Linux

Une fois que vous avez commandé votre service EVault et que l'agent a été installé sur le serveur, vous pouvez commencer à créer des sauvegardes de vos données. Cet article décrit les étapes de configuration de votre agent, le planning de conservation des données et le déclenchement de votre premier travail de sauvegarde.

## Lancement de WebCC

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} et cliquez sur **Stockage** > **Sauvegarde** dans le menu principal pour afficher les serveurs jouissant du service de sauvegarde EVault. 
2. Sélectionnez le serveur sur lequel résident les fichiers à sauvegarder. Cliquez sur la flèche d'expansion pointant vers la droite pour dévoiler le lien WebCC.
3. Démarrez votre connexion VPN pour pouvoir accéder au réseau privé IBM.
4. Cliquez sur le lien Connexion WebCC pour lancer le client WebCC dans votre navigateur.<br/>
  **Remarque **: si WebCC ne démarre pas, ceci peut dénoter un problème avec votre connexion VPN. Un message pourrait également vous aviser que le formulaire que vous envoyez n'est pas sécurisé. Ceci est dans l'ordre des choses, envoyez donc le formulaire.
  
## Configuration d'un travail de sauvegarde

1. Dans le panneau de navigation de gauche, cliquez sur **Tous les agents** pour afficher les agents EVault actuels. 
2. Cliquez sur **Il s'agit d'un nouvel agent que je désire configurer**. 
3. Entrez un nom et une description du travail que vous configurez ou créez.
4. Pour **Type de source de sauvegarde**, sélectionnez dans le menu déroulant le type de système de fichiers que vous désirez sauvegarder.
5. Cliquez sur **Suivant** pour continuer. 
6. Dans le panneau **Fichiers de données**, accédez aux fichiers et aux répertoires que vous désirez englober dans votre sauvegarde en cliquant sur les signes **+** et **-** en regard des icônes des dossiers correspondants.
7. Cochez les cases en regard des fichiers et des répertoires que vous désirez englober, puis cliquez sur **Inclure** pour enregistrer vos sélections.
8. Vous pouvez filtrer davantage vos sélections à l'aide de l'écran en incrustation qui apparaît ou cliquer sur **OK** pour utiliser en l'état les sélections que vous avez effectuées. <br /> Une fois que vous avez ajouté vos choix de fichiers et de répertoires, ceux-ci s'affichent dans le panneau **sauvegarde** sur le côté droit du côté de l'écran. Vous pouvez répéter les étapes 6 à 8 pour ajouter d'autres fichiers ou supprimer (par le biais du bouton **exclure**) des fichiers que vous aviez déjà ajoutés. Vous pouvez également utiliser le bouton **Retirer** pour supprimer n'importe quelle ligne du panneau **Jeu de sauvegarde**. Une fois ce jeu configuré comme vous le souhaitez, cliquez sur **Suivant** pour continuer.
9. Sélectionnez le type de chiffrement voulu. 
  - Si vous ne désirez pas chiffrer votre sauvegarde, sélectionnez **Aucune**.   
  - Si vous désirez la chiffrer, sélectionnez **AES 256 bits** et renseignez les champs Mot de passe et Vérifier le mot de passe. Si vous le souhaitez, vous pouvez ajouter une indication quant au mot de passe. <br/> **Remarque **: vous aurez besoin de ce mot de passe en vue de restaurer des fichiers depuis la sauvegarde. Il n'est pas possible de récupérer un mot de passe égaré ou de restaurer une sauvegarde chiffrée sans connaître le mot de passe.   
10. Si vous désirez utiliser l'une des **Options avancées**, celles-ci sont expliquées ci-dessous :
  - **Conservation** : vous aide à gérer l'utilisation de vos données. Cette période détermine pendant combien de temps votre sauvegarde sera conservée. Au terme de cette période, la sauvegarde est automatiquement supprimée. Options intégrées : quotidienne, hebdomadaire ou mensuelle.
  - **Compression** : utilisée pour réduire la capacité utilisée pour enregistrement des sauvegardes.
Les fichiers Backup ouverts pour l'option d'écriture permettent la sauvegarde de ces fichiers, même s'ils sont ouverts par une application alors que le travail de sauvegarde s'exécute.
  - **Créer un fichier journal : ** permet de créer et de gérer le contenu et la conservation des fichiers journaux générés au cours du processus de sauvegarde. 
  - **Sauvegarde d'une instance unique de tous les fichiers à lien fixe sélectionnés**. Cette option ne s'applique qu'aux systèmes de fichiers Unix. Si vous utilisez des liens fixes pour créer plusieurs noms de fichiers pour le même contenu, cette option entraîne la sauvegarde d'une seule copie du contenu. Au cours de la restauration, tous les liens fixes sont restaurés. Cette option requiert un passage précédant l'analyse à travers la sélection de fichiers, ce qui peut prendre un temps significatif et monopoliser de la mémoire.
11. Après votre choix de chiffrement, cliquez sur **Suivant** pour accéder à l'écran **Créer un planning**.   
12. Sur la page Créer un planning, cliquez sur **Ajouter** pour programmer un travail de sauvegarde basé calendrier ou sur **Suivant** pour créer un travail manuel.
  - Si vous décidez de créer un travail manuel, passez à l'étape 15.
  - Si vous optez pour un travail basé calendrier, sélectionnez les jours et l'heure auxquels effectuer vos sauvegardes.
  - Sélectionnez votre schéma de conservation. Cliquez [ici](evault-backup-faq.html#how-do-the-retention-schemes-work-) pour plus d'informations sur les schémas de conservation.
  - Cliquez le cas échéant sur **Options de planning avancées** pour plus de choix de configuration. Vous pouvez sélectionner **Déferrer* pour empêcher l'exécution de sauvegardes volumineuses aux heures de pointe sur le réseau. Lorsque cette option est activée, le travail de sauvegarde ne sauvegarde pas de nouvelles données après le délai imparti et consigne le jeu de données dans le coffre, et ce même si certaines données dans le travail n'ont pas été sauvegardées. Les modifications de données sauvegardées au préalable seront sauvegardées, sans tenir compte de la période de temps spécifiée. <br/> Lorsque le travail s'exécute à nouveau, l'agent vérifie les changements de données sauvegardées auparavant, sauvegarde ces modifications, puis les données restantes. Si un travail de sauvegarde a été reporté alors qu'un élément, (par exemple, fichier, base de données, volume, VMDK vSphere ou Hyper-V VM) est en cours de sauvegarde, la sauvegarde de cet élément est incomplète et les données de cet élément ne peuvent pas être restaurées. Vous pouvez toutefois restaurer des éléments qui ont été complètement sauvegardés dans le travail avant le report de ce travail.
13. Après avoir configuré votre planning de sauvegarde, cliquez sur **OK** pour l'enregistrer. Votre travail planifié est ajouté à la liste des travaux planifiés. 
  - Vous pouvez répéter l'étape 12 pour planifier des sauvegardes supplémentaires. 
  - Pour apporter des modifications à un travail de sauvegarde existant, sélectionnez celui-ci en cliquant sur sa ligne, puis sur **Editer** et apportez vos modifications.
14. Sélectionnez un coffre pour votre travail de sauvegarde, puis cliquez sur **Enregistrer les modifications**.
15. Exécutez un travail de sauvegarde
  - Si vous avez planifié un travail de sauvegarde basé calendrier, vous n'avez pas à effectuer d'étapes supplémentaires. Votre travail s'exécutera automatiquement comme planifié.
  - Si vous avez configuré un travail manuel (sans planning basé calendrier), vous pouvez le lancer en sélectionnant sa ligne dans la liste des travaux et en cliquant sur **Effectuer la sauvegarde**. <br/> Comme pour les travaux basés calendrier, vous pouvez choisir un schéma de conservation et des options de sauvegarde avancées. Après avoir procédé à vos choix de configuration, cliquez sur **Lancer la sauvegarde** pour déclencher le travail.
