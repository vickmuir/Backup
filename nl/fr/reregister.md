---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Enregistrement d'un coffre
{: #reregister}

Ces étapes sont le plus souvent utilisées après le rechargement du système d'exploitation d'un serveur. Vous pouvez également les exécuter pour [utiliser les sauvegardes d'un serveur afin de restaurer des données sur un autre serveur](/docs/infrastructure/Backup?topic=Backup-restorefromotherVSI).
{:tip}

1. Démarrez le portail {{site.data.keyword.backup_notm}} et connectez-vous. Pour plus d'informations, voir le [Tutoriel d'initiation](/docs/infrastructure/Backup?topic=Backup-gettingstarted#gettingstarted).

   N'oubliez pas que le portail {{site.data.keyword.backup_notm}} est accessible uniquement via {{site.data.keyword.BluVPN}}.
   {:tip}
2. Sur la gauche, cliquez sur **Tous les agents**.
3. Dans l'angle supérieur droit, survolez l'option **Editer**.
4. Sélectionnez **Paramètres du coffre**.
5. Cliquez sur **Réenregistrer**.
6. Renseignez le formulaire.
  - Nom du coffre
  - Adresse du coffre
  - Compte

    "Compte" est équivalent au "Nom du compte" dans le portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}. Généralement, il est similaire à "SLE [ID compte]"
    {:tip}
  - Nom de l'utilisateur
  - Mot de passe
7. Cliquez sur **Charger les ordinateurs** et sélectionnez les ordinateurs que vous désirez charger.
8. Cliquez sur **Enregistrer les modifications**.
9. Actualisez le site Web pour restaurer les travaux de sauvegarde précédents.
10. Synchronisez chaque travail de sauvegarde pour restaurer l'historique du jeu sécurisé.
11. Si les travaux de sauvegarde ont été créés à l'aide d'un mot de passe de chiffrement, vous devez entrer le mot de passe de chiffrement pour restaurer des données, ou poursuivre les sauvegardes.
12. Cliquez sur **Fermer**.
