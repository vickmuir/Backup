---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-30"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Réenregistrement d'un EVault

Cette tâche est généralement une étape requise après le rechargement du système d'exploitation d'un serveur, mais vous pouvez également les suivre pour utiliser les [sauvegardes d'un autre serveur en les utilisant sur un serveur différent](restore-from-another-computer.html).

1. Connectez-vous en tant qu'utilisateur sur WebCC. Reportez-vous à la rubrique [Initiation au service de sauvegarde](/docs/infrastructure/Backup/index.html) pour les instructions. N'oubliez pas que WebCC n'est accessible que via le {{site.data.keyword.BluVPN}}.

2. Sur la gauche, cliquez sur **Tous les agents**.

3. A l'angle supérieur droit, survolez l'option **Editer**.

4. Sélectionnez **Paramètres du coffre**.

5. Cliquez sur **Réenregistrer**.

6. Terminé : 
  - Nom du coffre
  - Adresse du coffre
  - Compte
  - Nom de l'utilisateur
  - Mot de passe<br/>
  **Remarque **: "Compte" est équivalent à la mention "Nom du compte" sur la page [Initiation aux services de sauvegarde](index.html). Généralement, il est similaire à "SLE [ID compte]"

7. Cliquez sur **Charger les ordinateurs** et sélectionnez les ordinateurs que vous désirez charger.

8. Cliquez sur **Enregistrer les modifications**.

9. Actualiser le site Web pour restaurer les travaux de sauvegarde précédents.

10. Synchronisez chaque travail de sauvegarde pour restaurer l'historique du jeu sécurisé. 

11. Si les travaux de sauvegarde ont été créés à l'aide d'un mot de passe de chiffrement, vous devez entrer l'entrer pour restaurer des données ou poursuivre les sauvegardes.

12. Cliquez sur **Terminer**. Vous en avez fini.
