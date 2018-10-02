---

copyright:
  years: 1994, 2018
lastupdated: "2018-08-15"

---
{:new_window: target="_blank"}

# Utilisation de coffres multiples

L'utilisation de coffres multiples fait référence à la capacité d'un client/serveur de se connecter à plusieurs emplacements EVault. Elle permet une redondance et une tranquillité d'esprit puisque des sauvegardes demeurent disponibles même en cas de panne d'un site. 

**Points clés**

1. Plusieurs coffres EVault peuvent être gérés via le même WebCC et traités de la même manière. La seule différence est que vous disposez de plusieurs choix de coffre.
2. La licence de plug-in s'applique au niveau du coffre, par exemple, si vous avez acquis le plug-in MSSQL pour un coffre à Washington DC, il ne fonctionne pas sur le coffre de Seattle.
3. Le nouveau coffre doit être ajouté manuellement au WebCC après chaque achat.

**Emplacements EVault Director**

La fonction de coffre multiple est disponible sur tous les centres de données et aucune limitation géographique ne restreint le choix d'un coffre distant. Lorsque des coffres sont configurés conformément aux étapes de ce document, ils apparaissent tous dans les paramètres de coffre.

>**Remarque ** : une sauvegarde vers des emplacements de centres de données distants peut prendre plus longtemps qu'une sauvegarde sur le centre de données où se trouve votre serveur.

## Ajout d'un coffre distant à un compte

Vous devez ajouter le nouveau coffre de stockage distant EVault au compte avant de pouvoir ajouter un nouvel emplacement de sauvegarde dans WebCC. 

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Cliquez sur **Unités**
3. Localisez et cliquez sur le lien du serveur concerné.
4. Sous **Détails de l'unité**, cliquez sur **Stockage**.
5. Lorsque la section Stockage s'ouvre, faites défiler l'écran jusqu'à **EVault** et cliquez sur **Ajouter**.
6. Dans la boîte de dialogue **Commander EVault**, sélectionnez l'emplacement du coffre distant en cliquant sur l'entrée correspondante dans le menu déroulant.
7. Sélectionnez la taille du stockage, puis cliquez sur **Continuer**
8. Cochez la case **J'ai lu l'accord cadre...** et cliquez sur **Valider la commande**.

Le nouveau coffre commandé est ajouté automatiquement au compte. Sinon, contactez le service commercial pour obtenir de l'aide.
Une fois le processus de commande terminé, accédez à **Stockage** > **Sauvegarde** pour voir le nouveau coffre répertorié.

## Ajout d'un coffre supplémentaire dans WebCC

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} et cliquez sur **Stockage** > **Sauvegarde** dans le menu principal pour afficher les serveurs jouissant du service de sauvegarde EVault. 
2. Sélectionnez le serveur qui doit être capable de sauvegarder plusieurs coffres. Cliquez sur la flèche pointant vers la droite pour afficher le lien WebCC.
3. Cliquez sur le lien **Connexion WebCC** pour lancer le client WebCC dans votre navigateur.
   >**Remarque** : WebCC est accessible uniquement via l'{{site.data.keyword.BluVPN}}.
4. Dans le panneau de navigation de gauche, cliquez sur **Tous les agents**.
5. Dans l'angle supérieur droit, cliquez sur **Modifier** et sélectionnez **Paramètres du coffre**.
6. Dans la fenêtre **Paramètres du coffre**, cliquez sur **Ajouter**.
7. Dans la fenêtre **Nouveau coffre** :
  1. Dans le menu Profil du coffre, sélectionnez **Entrer les paramètres du coffre** pour créer une nouvelle entrée. Ne mettez pas à jour l'entrée existante, cela ne fonctionnera pas.
  2. Le nom du coffre ne doit pas être identique à celui de l'autre coffre. Ajoutez la balise -2 à la fin de ce nom. <br/> 
     >**Remarque** : cette zone est limitée à 15 caractères.
  3. La zone d'adresse IP est renseignée avec les informations sur l'emplacement d'EVault Director. Par exemple, `ev-director301.service.softlayer.com` a pour adresse IP 10.1.114.46 et se trouve dans WDC.
  4. Dans la zone des données d'identification, entrez l'ID de compte, le nom d'utilisateur EVault pour le coffre sélectionné et le mot de passe du coffre sélectionné.
  5. Cliquez sur **Enregistrer les modifications**.

En quelques secondes, le nouveau coffre est utilisable. Si une erreur de connexion se produit, vérifiez les paramètres et réessayez. N'oubliez pas que l'ajout d'un coffre supplémentaire vous offre seulement une autre destination que vous pouvez choisir pour un travail. Cela n'exécute pas automatiquement des travaux vis à vis des deux coffres. Vous devez configurer des travaux pour qu'ils utilisent le coffre supplémentaire. Reportez-vous au [Tutoriel d'initiation](index.html#getting-started-with-evault-backup-services) pour les instructions.
