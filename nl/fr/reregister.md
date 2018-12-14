---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Enregistrement d'un coffre

Ces étapes sont le plus souvent utilisées après le rechargement du système d'exploitation d'un serveur. Vous pouvez également les exécuter pour [utiliser les sauvegardes d'un serveur afin de restaurer des données sur un autre serveur](restore-from-another-computer.html).

1. Démarrez WebCC et connectez-vous. Pour plus d'informations, voir le [Tutoriel d'initiation](index.html).

   N'oubliez pas que WebCC n'est accessible que via le {{site.data.keyword.BluVPN}}.
   {:tip}
2. Sur la gauche, cliquez sur **Tous les agents**.
3. Dans l'angle supérieur droit, survolez l'option **Editer**.
4. Sélectionnez **Paramètres du coffre**.
5. Cliquez sur **Réenregistrer**.
6. Renseignez le formulaire.
  - Nom du coffre
  - Adresse du coffre
  - Compte

"Compte" est équivalent à la mention "Nom du compte" dans le portail [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}. Généralement, il est similaire à "SLE [ID compte]"
    {:tip}
  - Nom de l'utilisateur
  - Mot de passe
7. Cliquez sur **Charger les ordinateurs** et sélectionnez les ordinateurs que vous désirez charger.
8. Cliquez sur **Enregistrer les modifications**.
9. Actualisez le site Web pour restaurer les travaux de sauvegarde précédents.
10. Synchronisez chaque travail de sauvegarde pour restaurer l'historique du jeu sécurisé.
11. Si les travaux de sauvegarde ont été créés à l'aide d'un mot de passe de chiffrement, vous devez entrer le mot de passe de chiffrement pour restaurer des données, ou poursuivre les sauvegardes.
12. Cliquez sur **Fermer**.
