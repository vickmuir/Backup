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
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Installation du plug-in SQL Server
{: #MSSQLplugin}

Le plug-in SQL Server est installé avec l'agent Windows sur l'hôte de base de données SQL. A l'aide du portail {{site.data.keyword.backup_notm}}, vous pouvez configurer des travaux, sauvegarder des bases de données SQL dans un coffre distant sécurisé et restaurer des bases de données SQL.

**Fonctions fournies**

- Vous pouvez réaliser des sauvegardes intégrales de base de données, d'une base de données complète avec les sauvegardes des journaux de transactions ou encore uniquement des journaux de transactions.
- Vous pouvez effectuer plusieurs sauvegardes en même temps.
- Vous pouvez restaurer des bases de données SQL sur la même instance SQL ou une autre.
- Vous pouvez restaurer des bases de données sous leur nom d'origine, écraser des bases de données existantes et les restaurer à l'aide de l'option Pas de reprise.

Pour plus d'informations, voir la section [Principales caractéristiques](#main-features).

## Commande du plug-in
{: #orderingSQLPlugin}

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://{DomainName}/){:new_window} et cliquez sur l'icône **menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.<br/>
   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** > **Sauvegarde** pour afficher les serveurs avec service de sauvegarde.
3. Sélectionnez votre compte, puis cliquez sur **Commander plug-ins**.
4. Sélectionnez **Plug-in {{site.data.keyword.backup_notm}} - MSSQL**, puis cliquez sur **Continuer**.
5. Entrez votre code promotionnel si vous en avez un et cliquez sur **Recalculer**.
6. Les frais mis à jour sont affichés. Passez en revue votre commande.
7. Cochez la case indiquant que vous avez lu et accepté les contrats de service tiers.
8. Cliquez sur **Valider la commande**.

## Installation du plug-in MSSQL
{: #installSQLPlugin}

Pour installer le plug-in, exécutez le kit d'installation de l'agent. Le plug-in s'affiche en tant qu'option sur la page **Configuration personnalisée**.

Avant d'installer le plug-in MSSQL pour votre serveur Microsoft Windows, arrêtez les deux services {{site.data.keyword.backup_notm}} dans `services.msc`.
{:tip}

1. Accédez au dossier `c:\installs\evault` et lancez le fichier .exe doté du plus haut niveau de révision.
2. Sur l'écran de langue, cliquez sur **OK**.
3. Sur l'écran d'accueil, cliquez sur **Suivant**.
4. Sélectionnez l'option **Modifier l'installation** et cliquez sur **Suivant**.
5. Sélectionnez l'option **Laisser inchangé** et cliquez sur **Suivant**.
6. Sur l'écran de configuration personnalisée, sélectionnez chaque plug-in dont vous avez fait l'acquisition.
7. Sélectionnez **Cette fonction sera installée sur ...**, puis cliquez sur **Suivant**.
8. Sélectionnez **Conserver mon enregistrement actuel** et cliquez sur **Suivant**.
9. Cliquez sur **Installer**.
10. Une fois l'installation terminée, vérifiez que les deux services sont activés et opérationnels.
11. Si le portail {{site.data.keyword.backup_notm}} parvient à afficher la base de données et à y accéder, cela signifie que l'installation a abouti.

## Téléchargement du guide d'utilisation
{: #SQLUserGuide}

Connectez-vous au réseau {{site.data.keyword.BluSoftlayer_full}} avec {{site.data.keyword.BluVPN}} pour pouvoir télécharger le guide d'utilisation à partir de la [documentation {{site.data.keyword.backup_notm}} téléchargeable ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}

## Principales caractéristiques
{: #main-features}

- Possibilité de spécifier à l'aide de caractères génériques (astérisques et points d'interrogation) les noms des bases de données à inclure ou à exclure des travaux de sauvegarde de SQL Server. Les nouvelles bases de données dont les noms correspondent aux filtres d'un travail de sauvegarde sont automatiquement incluses ou exclues lorsque le travail s'exécute.
- Possibilité de protéger les bases de données secondaires dans des groupes de disponibilité AlwaysOn à l'aide de l'agent 64 bits et du plug-in SQL Server.
- Possibilité de partager des jeux de données SQL sécurisés contenant des bases de données au contenu SharePoint 2010/2013 pour une utilisation avec l'application Granular Restore for Microsoft SharePoint. Après ce partage, l'application Granular Restore peut être utilisée pour restaurer des collections de sites, des sites Web, des listes, des bibliothèques, des dossiers, des éléments de liste ou des documents.
- Prise en charge de sauvegardes delta situées sur les volumes répartis.
- Possibilité de protéger les données en mode de reprise intégrale avec une seule entrée de planning. Cette option permet de protéger les bases de données et de gérer la troncature des journaux de transactions dans une entrée de planning unique.
- Le plug-in SQL Server gère les sauvegardes intégrales, les sauvegardes intégrales avec inclusion des journaux de transactions et les sauvegardes de journaux de transactions (terminologie mise à jour pour être alignée avec celle de SQL Server). L'application continue à prendre en charge la fonctionnalité de restauration en un seul passage, laquelle permet à un client de sélectionner une sauvegarde de “journal de transactions” basée sur un point de cohérence. {{site.data.keyword.backup_notm}} restaure la base de données complète, ainsi que tous les journaux de transactions nécessaires pour restaurer la base de données au point de cohérence sélectionné.
- Un travail de sauvegarde peut contenir une ou plusieurs bases de données de la même instance SQL Server unique. Un travail distinct peut être créé pour sauvegarder d'autres bases de données d'une instance SQL Server différente, sauvegardes pouvant être réalisées simultanément si vous le désirez.
- Possibilité de restaurer des bases de données avec le mode "Pas de reprise" pour fournir des options de reprise supplémentaires via SQL Server Management Studio.
- Une option de restauration alternative permet d'effectuer l'opération sur des fichiers, ce qui permet à l'administrateur de base de données de monter celles-ci via SQL System Manager.
- Une option de restauration alternative permet de diriger l'opération vers une autre base de données même lorsque les noms de base de données logique ne concordent pas. En cas d'objets non concordants, le plug-in crée des bases de données sous leur emplacement par défaut pour l'instance.
- Prise en charge de TDE (Transparent Data Encryption) avec SQL Server 2008 R2 (SP1) 64 bits et SQL Server 2012.
- Si un hôte SQL Server est perdu, le logiciel SQL Server peut être installé et la base de données peut être restaurée. (La base de données maître doit être restaurée en premier.)
- Une fois que la sauvegarde est lancée, elle peut s'exécuter que les services de base de données soient en cours d'exécution ou non.
- Les restaurations peuvent appliquer les noms de base de données d'origine (en écrasant ou non les bases de données existantes), restaurer une base de données existante, ou encore concerner des fichiers sur disque.
