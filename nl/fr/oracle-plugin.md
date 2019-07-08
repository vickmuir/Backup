---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-13"

keywords: IBM Cloud backup, oracle, plug-in, plugin, EVault, Carbonite

subcollection: Backup

---
{:pre: .pre}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# En savoir plus sur le plug-in Oracle
{: #Oracleplugin}

Le plug-in Oracle est un module complémentaire qui est installé avec l'agent Windows ou l'agent Linux sur l'hôte de base de données Oracle. A l'aide du portail {{site.data.keyword.backup_notm}}, vous pouvez configurer des travaux, sauvegarder des bases de données Oracle dans un coffre distant sécurisé et restaurer des bases de données Oracle. Le plug-in Oracle s'intègre dans l'architecture existante.

## Fonctions fournies
{: #Oraclecapabilities}

- Prise en charge de la sauvegarde et la récupération de base de données Oracle.
- Le plug-in Oracle permet des sauvegardes basées ARCHIVELOG, non RMAN, d'instances de bases de données en ligne complètes. Tous les espaces table et les fichiers de paramètres d'instance non temporaires sont automatiquement sauvegardés. Oracle Corporation recommande de procéder aux sauvegardes au cours des périodes de faible activité de la base de données.
- Les restaurations intégrales et partielles des bases de données sont réalisées par le biais de mécanismes de reprise Oracle gérés par l'utilisateur.

## Limites
{: #Oraclelimitations}
- Seules les bases de données locales, basées disque et ne comportant qu'une seule instance, sont sauvegardées.
- Les clusters de base de données ne sont pas sauvegardés.
- Les unités en mode brut ne sont pas sauvegardées.
- Les bases de données distantes ne sont pas sauvegardées.
- La base de données doit opérer en mode ARCHIVELOG et l'utilisateur sous lequel la sauvegarde est configurée doit disposer des privilèges SYSDBA.
- Les mots de passe de base de données sont chiffrés pour sécurité accrue par rapport aux méthodes basées script.

## Installation du plug-in pour Windows
{: #installOracleWin}

Le plug-in Oracle pour Windows est installé avec l'agent Windows 32 bits ou 64 bits. Pour installer le plug-in, exécutez le kit d'installation de l'agent. Le plug-in s'affiche en tant qu'option sur la page **Configuration personnalisée**. Pour plus d'informations, voir [Installation du client {{site.data.keyword.backup_notm}} sous Windows](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)

Avant d'installer le plug-in, arrêtez les deux services {{site.data.keyword.backup_notm}} dans `services.msc`.
{:tip}

1. Accédez au dossier `c:\installs\evault` et lancez le fichier .exe doté du plus haut niveau de révision.
2. Sur l'écran de langue, cliquez sur **OK**.
3. Sur l'écran d'accueil, cliquez sur **Suivant**.
4. Sélectionnez l'option **Modifier l'installation** et cliquez sur **Suivant**.
5. Sélectionnez l'option **Laisser inchangé** et cliquez sur **Suivant**.
6. Sur l'écran de configuration personnalisée, sélectionnez chaque plug-in dont vous avez fait l'acquisition et sélectionnez **Cette fonction sera installée sur...**, puis cliquez sur **Suivant**.
7. Sélectionnez **Conserver mon enregistrement actuel** et cliquez sur **Suivant**.
8. Cliquez sur **Installer**.
9. Une fois l'installation terminée, vérifiez que les deux services sont activés et opérationnels.
10. Si le portail {{site.data.keyword.backup_notm}} parvient à accéder à la base de données ou à l'afficher, l'installation a donc abouti.

## Installation du plug-in pour Linux
{: #installOracleLin}

Le plug-in Oracle est un module complémentaire de l'agent Linux, installé avec celui-ci sur l'hôte de base de données. L'application Linux Agent doit être installée avant l'installation du plug-in. L'agent est disponible sous forme d'application 32 bits ou 64 bits. Pour plus d'informations, voir [Installation du client {{site.data.keyword.backup_notm}} sous Linux](/docs/infrastructure/Backup?topic=Backup-InstallinLinux).

Le kit d'installation du plug-in Oracle est disponible dans un fichier tar.gz.

1. Sur l'hôte, téléchargez le module d'installation.
   ```
   http://downloads.softlayer.com/evault/Oracle-Plugin-Linux-x64-8.10.5249.tar.gz
   ```
   {: pre}

2. Extrayez les fichiers du package.
   ```
   # cd /tmp
   # tar xvf Oracle-Plugin-Linux-x64-8.10.5249.tar
   ```
   {: pre}

3. Accédez au dossier.
   ```
   # cd Oracle-Plugin-Linux-x64-8.10.5249.xxxx
   ```
   {: pre}

4. Exécutez le script d'installation.
   ```
   # ./install.sh
   ```
   {: pre}

5. Suivez les instructions d'installation à l'écran.

Le plug-in Oracle effectue une sauvegarde complète "incohérente" qui requiert que la base de données s'exécute en mode ARCHIVELOG. L'administrateur de base de données doit s'assurer que la base de données est en mode ARCHIVELOG avant de démarrer les sauvegardes. Pour plus d'informations, voir le guide d'utilisation.
{:important}


## Téléchargement du guide d'utilisation
{: #OracleUserGuide}

Connectez-vous au réseau {{site.data.keyword.cloud}} avec {{site.data.keyword.BluVPN}} pour pouvoir télécharger le guides d'utilisation à partir de la [documentation {{site.data.keyword.backup_notm}} téléchargeable](http://downloads.service.softlayer.com/evault/Documentation/){: external}
