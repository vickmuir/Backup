---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Utilisation de coffres multiples

L'utilisation de coffres multiples se réfère à la capacité d'un client/serveur de se connecter à plusieurs emplacements EVault. Elle permet une redondance et une tranquillité d'esprit puisque des sauvegardes demeurent disponibles même en cas de panne d'un site. 

## Points clés

1. Plusieurs coffres EVault peuvent être gérés via le même WebCC et traités de la même manière. La seule différence est que vous disposez de plusieurs choix de coffre.
2. La licence de plug-in s'applique au niveau du coffre (par exemple, si vous avez souscrit à une licence EVault pour le plug-in MSSQL à Washington DC, elle ne sera pas valide sur un coffre à Seattle).
3. Le nouveau service EVault doit être ajouté manuellement au WebCC après chaque commande.

## Ajout d'un coffre distant à un compte

Vous devez ajouter le nouveau coffre de stockage distant EVault au compte avant de pouvoir ajouter un nouvel emplacement de sauvegarde dans WebCC. 

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Cliquez sur **Unités**
3. Localisez et cliquez sur le lien du serveur concerné.
4. Sous **Détails de l'unité**, cliquez sur **Stockage**
5. Lorsque la section Stockage s'ouvre, faites défiler l'écran jusqu'à **EVault** et cliquez sur **Ajouter**
6. Dans la boîte de dialogue **Commander EVault** qui s'ouvre, sélectionnez l'emplacement du coffre distant en cliquant dans le menu déroulant.
7. Sélectionnez la taille du stockage, puis cliquez sur **Continuer**
8. Cochez la case **J'ai lu l'accord cadre...** et cliquez sur **Valider la commande**.

Le nouveau coffre commandé est ajouté automatiquement au compte. Sinon, contactez le service commercial pour obtenir de l'aide. Une fois le processus de commande terminé, accédez à **Stockage** > **Sauvegarde** pour voir le nouveau coffre répertorié.

## Ajout d'un coffre supplémentaire à WebCC

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} et cliquez sur **Stockage** > **Sauvegarde** dans le menu principal pour afficher les serveurs jouissant du service de sauvegarde EVault. 
2. Sélectionnez le serveur sur lequel résident les fichiers à restaurer. Cliquez sur la flèche d'expansion pointant vers la droite pour dévoiler le lien WebCC.
3. Cliquez sur le lien Connexion WebCC pour lancer le client WebCC dans votre navigateur. <br/>**Remarque **: WebCC est accessible uniquement via le {{site.data.keyword.BluVPN}}.
4. Dans le panneau de navigation de gauche, cliquez sur **Tous les agents**.
5. Dans le coin supérieur droit, cliquez sur **Modifier** et sélectionnez **Paramètres du coffre**.
6. Dans la fenêtre **Paramètres du coffre", cliquez sur **Ajouter**.
7. Dans la boîte de dialogue **Nouveau coffre** :
  1. Dans la liste déroulante Profil du coffre, sélectionnez **Entrer les paramètres du coffre** pour créer une nouvelle entrée. Ne mettez pas à jour l'entrée existante, ceci ne fonctionnera pas.
  2. Le nom du coffre ne doit pas être identique à celui de l'autre coffre. Nous vous recommandons d'ajouter la balise -2 à la fin de ce nom. <br/> **Remarque **: cette zone est limitée à 15 caractères.
  3. La zone d'adresse IP doit être renseignée avec les informations d'emplacement evdirector. Par exemple, ev-director301.service.softlayer.com has a pour adresse IP 10.1.114.46 et est situé dans WDC. Reportez-vous au bas de la page pour les autres emplacements et adresses EVault Director.
  4. Dans la zone des données d'identification, le compte sera l'ID de compte du client, le nom d'utilisateur celui de l'utilisateur EVault pour le coffre sélectionné et le mot de passe celui pour le coffre sélectionné.
  5. Cliquez sur **Enregistrer les modifications**.

Dans quelques secondes, le nouveau coffre sera utilisable. Si vous obtenez une erreur de connexion, vérifiez les paramètres et réessayez. N'oubliez pas que l'ajout d'un coffre supplémentaire vous offre seulement une autre destination que vous pouvez choisir pour un travail et n'exécute pas automatiquement des travaux vis à vis des deux coffres. Vous devez configurer des travaux pour exploiter le coffre supplémentaire. Reportez-vous au [Tutoriel d'initiation](index.html#getting-started-with-evault-backup-services) pour les instructions.

## Emplacements EVault Director

La fonction de coffre multiple est disponible sur tous les centres de données et aucune limitation géographique ne restreint le choix d'un coffre distant. Lorsque des coffres sont configurés conformément aux étapes de ce document, tous les coffres configurés figurent dans les paramètres de coffre.

**Remarque **: une sauvegarde vers des emplacements de centres de données distants peut prendre plus longtemps qu'une sauvegarde sur le même centre de données où est situé votre serveur.

