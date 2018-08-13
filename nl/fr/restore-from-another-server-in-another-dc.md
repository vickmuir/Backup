---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-05"

---
{:pre: .pre}
{:new_window: target="_blank"}

# Création de données de sauvegarde et de restauration depuis une instance de serveur virtuel vers une autre dans un centre de données différent

Vous voudrez parfois restaurer des données sur un serveur différent. Cette procédure s'applique uniquement aux restaurations de niveau fichier pour des fichiers ne faisant pas partie du système d'exploitation. Pour restaurer une image système, suivez les instructions pour [BMR Windows](restoring-evault-bmr-system-volume-image.html).

Cette procédure inclut le réenregistrement de l'agent EVault sur le second serveur pour accéder à l'emplacement EVault du premier serveur et la réalisation d'une **restauration à partir d'un autre ordinateur**.

**Conditions prérequises**

- Serveur1 et Serveur2 doivent avoir le même système d'exploitation. Les restaurations inter-plateformes ne sont pas prises en charge.
- Serveur1 et Serveur2 doivent être dotés d'agents EVAult déjà configurés. Cliquez [ici](index.html#configuring-evault-agent-in-webcc) pour découvrir comment configurer les agents EVault.
- Un travail de sauvegarde pour Serveur1 doit avoir généré une sauvegarde sur l'emplacement EVault de Serveur1.

**Remarque** : pour éviter des conflits, désactivez tous les travaux planifiés sur les deux serveurs. 

## Démarrage du WebCC de Serveur2

>**Remarque** : prenez soin de lancer votre connexion {{site.data.keyword.BluVPN}} pour pouvoir accéder au réseau privé {{site.data.keyword.BluSoftlayer_full}}, faute de quoi le lien WebCC ne fonctionnera pas.

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} et cliquez sur **Stockage** > **Sauvegarde** dans le menu principal pour afficher les serveurs jouissant du service de sauvegarde EVault. 
2. Sélectionnez Serveur2. Cliquez sur la flèche d'expansion pointant vers la droite pour dévoiler le lien WebCC.
3. Cliquez sur **Connexion WebCC** pour lancer le client WebCC dans votre navigateur.

## Réenregistrement d'EVault

1. Cliquez sur **Tous les agents** et ouvrez l'agent spécifique que vous désirez modifier.
2. Cliquez sur **Editer** et sélectionnez **Paramètres du coffre**. 
3. Cliquez sur **Réenregistrer** pour connecter Serveur1 à Serveur2.
4. Sur l'écran **Réenregistrer le coffre** pour l'entrée **Utiliser un profil de coffre**, sélectionnez **Entrer les paramètres du coffre**.
5. Entrez le nom du coffre, lequel est le même que le nom EVault de Serveur1.
6. Entrez les données d'identification de Serveur1 pour vous connecter au EVault de ce serveur.
7. Cliquez sur **Charger les ordinateurs**. Les serveurs rattachés à l'emplacement du coffre s'affichent.
8. Cliquez sur **Enregistrer les modifications**.
9. A l'invite, cliquez sur **Oui** pour confirmer le réenregistrement d'EVault.

## Exécution du travail de sauvegarde depuis Serveur1 en tant que travail de restauration sur Serveur2

1. Cliquez sur **Tous les agents**.
   >**Remarque** : vous devrez éventuellement actualiser la page afin que les travaux définis sur Serveur1 indiquent qu'ils sont accessibles/synchronisés sous l'onglet **Travaux** de Serveur2.
2. Survolez **Avancé** et sélectionnez **Restaurer à partir d'un autre ordinateur**.
3. Sur l'écran **Restaurer à partir d'un autre ordinateur**, cliquez sur **Ajouter**. Les zones sont déjà renseignées avec des valeurs par défaut ; vous pouvez les modifier. 
4. Cliquez dans la zone Coffre, sélectionnez **Entrer les paramètres du coffre** et entrez l'adresse IP du coffre de Serveur1. Cliquez sur **Ajouter**.
5. Mettez à jour les données d'identification avec celles de Serveur1. 
6. Cliquez sur **Enregistrer les modifications**. Cette action a pour conséquence de vous connecter au coffre de Serveur1. 
7. De retour sur l'écran **Restaurer à partir d'un autre ordinateur**, mettez à jour les zones Ordinateur et Travail. 
  - Ordinateur - sélectionnez Serveur1 comme ordinateur de sauvegarde à partir duquel effectuer la restauration. 
  - Travail - sélectionnez le travail de sauvegarde de Serveur1.
8. Cliquez sur **Suivant** pour démarrer le processus de restauration sur Serveur2 dans un autre centre de données. 
9. A l'invite, entrez le mot de passe de sauvegarde et cliquez sur **Suivant**.
10. Vérifiez que le travail de sauvegarde approprié est sélectionné, puis cliquez sur **Suivant**. Le travail de restauration est maintenant configuré sur Serveur2. 
11. Sélectionnez le travail qui vient d'être configuré, puis cliquez sur **Exécuter la restauration**.
12. Sélectionnez les fichiers que vous souhaitez restaurer.  
13. Cliquez sur le signe Plus pour développer la sélection de fichiers. 
14. Cochez la case en regard de chacun des fichiers ou dossiers que vous souhaitez restaurer depuis Serveur1 sur Serveur2. Cliquez ensuite sur **Inclure**.
15. Les fichiers apparaissent dans la fenêtre Groupe de sauvegarde sur la droite. Cliquez sur **Suivant**. 
16. Après avoir sélectionné vos données, passez à la sélection de vos options.
    - Sélectionnez **Restaurer vers l'emplacement d'origine**.
    - Sélectionnez **Remplacer les fichiers existants**.
17. Cliquez sur **Exécuter la restauration**. La fenêtre Détails du processus indique le statut du travail de sauvegarde en cours d'exécution. Lorsque la sauvegarde est terminée, cliquez sur **Fermer**.


## Vérification de la restauration

1. Connectez-vous à la racine de Serveur2 via SSH.
2. Recensez les fichiers et toutes les entrées de répertoire au format long.
  ```
  ls -la
  ```
  {: pre}
  
3. Comparez la sortie.
  
## Reprise du planning de sauvegarde normal

1. Lorsque la restauration est terminée, supprimez les informations d'enregistrement du Serveur1, depuis lequel les données ont été restaurées. 
2. Entrez l'enregistrement Serveur2 actuel et activez les tâches de planning.
