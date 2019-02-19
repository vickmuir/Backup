---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restauration de données depuis une instance de serveur virtuel vers une autre dans le même centre de données
{: #restorefromotherVSI}

Vous voudrez parfois restaurer des données sur un serveur différent dans le même centre de données. Cette procédure s'applique uniquement aux restaurations de niveau fichier pour des fichiers ne faisant pas partie du système d'exploitation. Pour restaurer une image système, suivez les instructions pour [BMR Windows](/docs/infrastructure/Backup?topic=Backup-restoreBMR).

Cette procédure inclut le réenregistrement de l'agent de sauvegarde sur le second serveur pour accéder à l'emplacement de coffre du premier serveur et la réalisation d'une **restauration à partir d'un autre ordinateur**.

**Conditions prérequises**

- Serveur1 et Serveur2 doivent avoir le même système d'exploitation. Les restaurations inter-plateformes ne sont pas prises en charge.
- Serveur1 et Serveur2 doivent être dotés d'agents de sauvegarde déjà configurés. Pour plus d'informations sur la configuration des agents de sauvegarde, voir la rubrique relative à la [configuration de l'agent de sauvegarde dans le portail {{site.data.keyword.backup_notm}}](docs/infrastructure/Backup?topic=Backup-GettingStarted).
- Un travail de sauvegarde pour Serveur1 doit avoir généré une sauvegarde sur l'emplacement de coffre de Serveur1.

Pour éviter tout conflit, désactivez tous les tâches planifiées sur les deux serveurs.
{:important}

## Démarrage du portail {{site.data.keyword.backup_notm}} de Serveur2

Prenez soin de lancer votre connexion {{site.data.keyword.BluVPN}} pour pouvoir accéder au réseau privé {{site.data.keyword.BluSoftlayer_full}}, sinon le lien du portail {{site.data.keyword.backup_notm}} ne fonctionnera pas.
{:tip}

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/){:new_window} et cliquez sur l'icône **menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**. <br/>
   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** > **Sauvegarde** pour afficher les serveurs avec service de sauvegarde.
3. Sélectionnez Serveur2. Cliquez sur la flèche d'expansion pointant vers la droite pour afficher le lien du portail {{site.data.keyword.backup_notm}}.
4. Cliquez sur **Connexion au portail {{site.data.keyword.backup_notm}}** pour lancer le client de portail dans votre navigateur.

## Réenregistrement du coffre

1. Cliquez sur **Tous les agents** et ouvrez l'agent spécifique que vous désirez modifier.
2. Cliquez sur **Editer** et sélectionnez **Paramètres du coffre**.
3. Cliquez sur **Réenregistrer** pour connecter Serveur1 à Serveur2.
4. Sur l'écran **Réenregistrer le coffre** pour l'entrée **Utiliser un profil de coffre**, sélectionnez **Entrer les paramètres du coffre**.
5. Entrez le nom du coffre, lequel est le même que le nom de coffre de Serveur1.
6. Entrez les données d'identification de Serveur1 pour vous connecter au coffre de Serveur1.
7. Cliquez sur **Charger les ordinateurs**. Les serveurs rattachés à l'emplacement du coffre s'affichent.
8. Cliquez sur **Enregistrer les modifications**.
9. A l'invite, cliquez sur **Oui** pour confirmer le réenregistrement du coffre.

## Exécution du travail de sauvegarde depuis Serveur1 en tant que travail de restauration sur Serveur2

1. Cliquez sur **Tous les agents**.

   Vous devrez éventuellement actualiser la page afin que les travaux définis sur Serveur1 indiquent qu'ils sont accessibles et synchronisés sous l'onglet **Travaux** de Server2.
   {:tip}
2. Survolez **Avancé** et sélectionnez **Restaurer à partir d'un autre ordinateur**.
3. Sur l'écran **Restaurer à partir d'un autre ordinateur**, effectuez les sélections suivantes :
  - Coffre - cette entrée prend par défaut le coffre de Serveur1.
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
