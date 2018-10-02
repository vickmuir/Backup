---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:pre: .pre}
{:new_window: target="_blank"}

# Création de données de sauvegarde et de restauration depuis une instance de serveur virtuel vers une autre dans le même centre de données

Vous voudrez parfois restaurer des données sur un serveur différent dans le même centre de données. Cette procédure s'applique uniquement aux restaurations de niveau fichier pour des fichiers ne faisant pas partie du système d'exploitation. Pour restaurer une image système, suivez les instructions pour [BMR Windows](restoring-evault-bmr-system-volume-image.html).

Cette procédure inclut le réenregistrement de l'agent EVault sur le second serveur pour accéder à l'emplacement EVault du premier serveur et la réalisation d'une **restauration à partir d'un autre ordinateur**.

**Conditions prérequises**

- Serveur1 et Serveur2 doivent avoir le même système d'exploitation. Les restaurations inter-plateformes ne sont pas prises en charge.
- Serveur1 et Serveur2 doivent être dotés d'agents EVAult déjà configurés. Cliquez [ici](index.html#configuring-evault-agent-in-webcc) pour découvrir comment configurer les agents EVault
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
3. Sur l'écran **Restaurer à partir d'un autre ordinateur**, effectuez les sélections suivantes :
  - Coffre - cette entrée prend par défaut l'EVault de Serveur1.
  - Ordinateur - sélectionnez Serveur1 comme ordinateur de sauvegarde à partir duquel effectuer la restauration. 
  - Travail - sélectionnez le travail de sauvegarde de Serveur1.
4. Cliquez sur **Suivant**.
5. Confirmez les informations sur la source.
  - **Emplacement du jeu sécurisé** : correspond à l'emplacement du coffre pour Serveur1.
  - Dans la section **Sélectionner une version de sauvegarde**, spécifiez votre sauvegarde depuis Serveur1 comme version de sauvegarde.
  - Le mot de passe de chiffrement est le mot de passe que vous avez utilisé lors de la création de la sauvegarde de serveur1.
6. Cliquez sur **Suivant**.
7. Sélectionnez les fichiers devant être restaurés depuis la sauvegarde de Serveur1. Cochez les cases en regard des fichiers et des répertoires que vous désirez restaurer, puis cliquez sur **Inclure** pour enregistrer vos sélections.
8. Cliquez sur **Suivant** pour accéder aux options de restauration.
9. Définissez les options suivantes :
  - Destination - sélectionnez **Restaurer à l'emplacement d'origine**
  - Ecrasement de fichiers - sélectionnez **Ecraser les fichiers existants**
10. Cliquez sur **Exécuter la restauration**.
11. L'écran Informations du processus affiche le statut du travail de restauration.


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
