---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, multiple vaults, mulitple locations, disaster recovery

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Utilisation de coffres multiples
{: #multivault}

L'utilisation de coffres multiples fait référence à la capacité d'un client de se connecter à plusieurs emplacements de coffre. Elle permet une redondance et une tranquillité d'esprit puisque des sauvegardes demeurent disponibles même en cas de panne d'un site.

**Points clés**

1. Plusieurs coffres peuvent être gérés via le même portail {{site.data.keyword.backup_notm}} et traités de la même manière. La seule différence est que vous disposez de plusieurs choix de coffre.
2. La licence de plug-in s'applique au niveau du coffre, par exemple, si vous avez acquis le plug-in MSSQL pour un coffre à Washington DC, il ne fonctionne pas sur le coffre de Seattle.
3. Le nouveau coffre doit être ajouté manuellement au portail {{site.data.keyword.backup_notm}} après chaque achat.



**Emplacements {{site.data.keyword.backup_notm}} Vault Director**

La fonction de coffre multiple est disponible sur tous les centres de données et aucune limitation géographique ne restreint le choix d'un coffre distant. Les coffres correctement configurés apparaissent tous dans les paramètres de coffre.

Une sauvegarde vers des emplacements de centres de données distants peut prendre plus de temps qu'une sauvegarde sur le centre de données où se trouve votre serveur.
{:note}

## Ajout d'un coffre distant à un compte

Vous devez ajouter le nouveau coffre distant au compte avant de pouvoir ajouter un nouvel emplacement de sauvegarde dans le portail {{site.data.keyword.backup_notm}}.
{:important}

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}){:new_window}, puis cliquez sur l'icône **menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.<br/>
   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Unités**
3. Localisez et cliquez sur le lien du serveur concerné.
4. Sous **Détails de l'unité**, cliquez sur **Stockage**.
5. Lorsque la section Stockage s'ouvre, faites défiler l'écran jusqu'à **{{site.data.keyword.backup_notm}}**, puis cliquez sur **Ajouter**.
6. Dans la boîte de dialogue **Commander {{site.data.keyword.backup_notm}}**, sélectionnez l'emplacement du coffre distant en cliquant sur l'entrée correspondante dans le menu déroulant.
7. Sélectionnez la taille du stockage, puis cliquez sur **Continuer**
8. Cochez la case **J'ai lu l'accord cadre...** et cliquez sur **Valider la commande**.

Le nouveau coffre commandé est ajouté automatiquement au compte. Sinon, contactez le service commercial pour obtenir de l'aide.

Une fois le processus de commande terminé, accédez à **Stockage** > **Sauvegarde** pour voir le nouveau coffre répertorié.

## Ajout d'un coffre supplémentaire dans le portail {{site.data.keyword.backup_notm}}

1. Connectez-vous à la console [{{site.data.keyword.cloud_notm}} ](https://{DomainName}){:new_window} et cliquez sur l'icône **menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.<br/>
   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** > **Sauvegarde** pour afficher les serveurs avec service de sauvegarde.
3. Sélectionnez le serveur qui doit être capable de sauvegarder plusieurs coffres. Cliquez sur la flèche pointant vers la droite pour afficher le lien du portail {{site.data.keyword.backup_notm}}.
4. Cliquez sur le lien de connexion au portail **{{site.data.keyword.backup_notm}} ** pour démarrer le client de portail dans votre navigateur.

   Le portail {{site.data.keyword.backup_notm}} est accessible uniquement via {{site.data.keyword.BluVPN}}.
   {:tip}
5. Dans le panneau de navigation de gauche, cliquez sur **Tous les agents**.
6. Dans l'angle supérieur droit, cliquez sur **Modifier** et sélectionnez **Paramètres du coffre**.
7. Dans la fenêtre **Paramètres du coffre**, cliquez sur **Ajouter**.
8. Dans la fenêtre **Nouveau coffre** :
  1. Dans le menu Profil du coffre, sélectionnez **Entrer les paramètres du coffre** pour créer une nouvelle entrée. Ne mettez pas à jour l'entrée existante, cela ne fonctionnera pas.
  2. Le nom du coffre ne doit pas être identique à celui de l'autre coffre. Ajoutez la balise `-2` à la fin de ce nom. <br/>

     La zone du nom du coffre est limitée à 15 caractères.
     {:important}
  3. La zone d'adresse IP est renseignée avec les informations sur l'emplacement d'{{site.data.keyword.backup_notm}} Director. Par exemple, `ev-director301.service.softlayer.com` a pour adresse IP 10.1.114.46 et se trouve dans WDC.
  4. Dans la zone des données d'identification, entrez l'ID de compte, le nom d'utilisateur {{site.data.keyword.backup_notm}} pour le coffre sélectionné et le mot de passe du coffre sélectionné.
  5. Cliquez sur **Enregistrer les modifications**.

En quelques secondes, le nouveau coffre est utilisable. Si une erreur de connexion se produit, vérifiez les paramètres et réessayez. N'oubliez pas que l'ajout d'un coffre vous offre une destination supplémentaire que vous pouvez choisir pour un travail. Cela n'exécute pas automatiquement des travaux vis à vis des deux coffres. Vous devez configurer des travaux pour qu'ils utilisent le coffre supplémentaire. Pour plus d'informations, voir le [Tutoriel d'initiation](/docs/infrastructure/Backup?topic=Backup-getting-started).
