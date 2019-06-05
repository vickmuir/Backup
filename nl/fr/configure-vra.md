---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configuration d'un travail de sauvegarde dans VRA
{: #ConfigureVRA}

Après avoir ajouté l'environnement VMware vSphere dans le portail {{site.data.keyword.backup_notm}}, vous pouvez créer un travail de sauvegarde qui désigne les machines virtuelles à sauvegarder et spécifie où les données de sauvegarde doivent être sauvegardées. Pour sauvegarder les données, vous pouvez exécuter le travail de sauvegarde manuellement ou planifier son exécution.

Avant d'ajouter un travail de sauvegarde, vous devez configurer les paramètres du coffre et les informations relatives à vCenter.
{:important}

## Démarrage du portail {{site.data.keyword.backup_notm}}
{: #startWebCCVRA}

Vous devez être connecté au réseau privé {{site.data.keyword.cloud}} pour pouvoir lancer le portail {{site.data.keyword.backup_notm}}.
{:important}

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} et cliquez sur l'icône **menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.<br/>
   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}.
2. Cliquez sur **Stockage** > **Sauvegarde** pour afficher les serveurs avec services de sauvegarde.
3. Sélectionnez le serveur sur lequel se trouvent les fichiers à sauvegarder. Cliquez sur la flèche d'expansion pointant vers la droite pour afficher le lien du portail {{site.data.keyword.backup_notm}}.
4. Cliquez sur **Connexion au portail {{site.data.keyword.backup_notm}}** pour lancer le client de portail dans votre navigateur.

   Si le portail {{site.data.keyword.backup_notm}} ne démarre pas, cela peut indiquer un problème au niveau de votre connexion VPN. Un message peut également s'afficher pour vous informer que le formulaire que vous envoyez n'est pas sécurisé. L'affichage de ce message est prévu ; vous pouvez envoyer le formulaire.
   {:tip}

## Ajout d'un travail de sauvegarde vSphere

1. Sur la barre de navigation, cliquez sur **Computers**. La page Computers affiche les ordinateurs et les environnements enregistrés.
2. Cliquez sur **Jobs**.
3. Dans le menu Select job Task, cliquez sur **Create New VMware vCenter Job**.
4. Spécifiez les informations suivantes.
   * Dans la zone **Name**, entrez un nom pour le travail de sauvegarde.
   * Dans la zone **Description**, entrez une description du travail de sauvegarde (facultatif).
   * Dans la liste **Destination**, sélectionnez le coffre dans lequel vous souhaitez sauvegarder les données de sauvegarde.
   * Dans les zones **Password** et **Confirm Password**, entrez un mot de passe de chiffrement. Vous pouvez également entrer une indication de mot de passe dans la zone Password Hint.
   Un coffre apparaît uniquement dans la liste s'il a été affecté à l'utilisateur ou si l'utilisateur l'a ajouté sous Vault Settings, sur l'ordinateur. <br/>
   Pour les nouveaux travaux de sauvegarde, la méthode de chiffrement est AES 256 bits. Les travaux existants peuvent avoir d'autres méthodes de chiffrement.
   {:note}

5.	Dans la zone **Include in Backup**, effectuez une ou plusieurs des étapes suivantes jusqu'à ce que la zone Backup Set affiche les machines virtuelles que vous souhaitez inclure dans le travail de sauvegarde .

   * Pour ajouter des machines virtuelles spécifiques au travail de sauvegarde, sélectionnez chaque machine virtuelle puis cliquez sur **Include**.
   * Pour exclure des machines virtuelles spécifiques du travail de sauvegarde, sélectionnez chaque machine virtuelle puis cliquez sur **Exclude**.
   * Pour ajouter des machines virtuelles au travail de sauvegarde par nom, cochez la case Machines virtuelles puis cliquez sur **Include**.
   * Pour supprimer un enregistrement d'inclusion ou d'exclusion de la boîte Backup Set, cliquez sur **Delete** en regard de l'enregistrement.

6. Cliquez sur **Apply Now** pour consolider et simplifier les enregistrements dans la boîte Backup Set, si des changements ont besoin d'être appliqués.
7. Cliquez sur **Create Job**.

## Configuration d'un planning

Une fois que le travail de sauvegarde est créé, vous pouvez ajouter un ou plusieurs plannings pour exécuter le travail automatiquement.

1. Lorsque vous cliquez sur **Create Job**, la fenêtre Schedule apparaît et vous donne l'option de configurer un planning personnalisé pour le travail de sauvegarde.

   L'option Daily retention est sélectionnée par défaut pour le travail. Dans cette fenêtre, vous pouvez changer la période de conservation et la planification des travaux. Vous pouvez également affecter plusieurs schémas de conservation au travail de sauvegarde.
   {:note}
2. Cliquez sur **Save** pour sauvegarder le nouveau planning. Le nouveau travail s'affiche sous l'onglet Computers, dans la section Jobs. Le statut de la dernière sauvegarde indique que le travail n'a jamais été exécuté. Le travail de sauvegarde planifié s'exécute automatiquement à l'heure planifiée.

## Exécution d'un travail planifié

Les travaux de sauvegarde planifiés peuvent également être exécutés immédiatement.

1. Cliquez sur **Select Action** et sélectionnez **Run Job**. La fenêtre Run Job apparaît et vous donne des informations sur le coffre de destination et le schéma de conservation assignés au travail.

   Si plusieurs coffres et schémas de conservation sont assignés au travail, ces options peuvent être changées dans la fenêtre Run job en cliquant sur les options de menu Destination and Retention Scheme.
   {:note}
2. Cliquez sur **Start Backup job** pour exécuter le travail de sauvegarde immédiatement. La fenêtre de progression affiche le statut du travail de sauvegarde et une fois que le travail est terminé, son statut passe de "Never Run" à "Completed".

Pour afficher le statut du dernier travail de sauvegarde exécuté, cliquez sur l'onglet Jobs. Tous les journaux des travaux sont accessibles depuis le menu Actions. Cliquez sur **Action** et sélectionnez **History/Logs**.
{:tip}

Pour en savoir plus sur la restauration des machines virtuelles ou des fichiers et des dossiers, voir [Restauration des données vSphere](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore).
