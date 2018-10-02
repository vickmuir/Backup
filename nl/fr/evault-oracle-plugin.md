---

copyright:
  years: 1994, 2018
lastupdated: "2018-08-10"

---
{:pre: .pre}
{:new_window: target="_blank"}

# Installation du plug-in Oracle d'EVault

Le plug-in Oracle est un module complémentaire qui est installé avec l'agent Windows ou l'agent Linux sur l'hôte de base de données Oracle. A l'aide du portail WebCC, vous pouvez configurer des travaux, sauvegarder des bases de données Oracle dans un coffre distant sécurisé et restaurer des bases de données Oracle. Le plug-in Oracle s'intègre dans l'architecture existante.

**Fonctions fournies**

- Prise en charge de la sauvegarde et la récupération de base de données Oracle.
- Le plug-in Oracle permet des sauvegardes basées ARCHIVELOG, non RMAN, d'instances de bases de données en ligne complètes. Tous les espaces table et les fichiers de paramètres d'instance non temporaires sont automatiquement sauvegardés. Oracle Corporation recommande de procéder aux sauvegardes au cours des périodes de faible activité de la base de données.
- Les restaurations intégrales et partielles des bases de données sont réalisées par le biais de mécanismes de reprise Oracle gérés par l'utilisateur.

**Limitations**
- Seules les bases de données locales, basées disque et ne comportant qu'une seule instance, sont sauvegardées.
- Les clusters de base de données ne sont pas sauvegardés.
- Les unités en mode brut ne sont pas sauvegardées.
- Les bases de données distantes ne sont pas sauvegardées.
- La base de données doit opérer en mode ARCHIVELOG et l'utilisateur sous lequel la sauvegarde est configurée doit disposer des privilèges SYSDBA.
- Les mots de passe de base de données sont chiffrés pour sécurité accrue par rapport aux méthodes basées script.

## Commande du plug-in

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** > **Sauvegarde**.
3. Sélectionnez votre compte EVault, puis cliquez sur **Commander plug-ins**.
4. Sélectionnez **Plug-in EVault - Oracle** et cliquez sur **Continuer**.
5. Entrez votre code promotionnel si vous en avez un et cliquez sur **Recalculer**.
6. Les frais mis à jour sont affichés. Passez en revue votre commande.
7. Cochez la case indiquant que vous avez lu et accepté les contrats de service tiers. 
8. Cliquez sur **Valider la commande**.

## Installation du plug-in Oracle pour Windows

Le plug-in Oracle pour Windows est installé avec l'agent Windows 32 bits ou 64 bits. Pour installer le plug-in Oracle pour Windows, exécutez le kit d'installation de l'agent. Le plug-in Oracle s'affiche en tant qu'option sur la page **Installation personnalisée**.

>**Remarque** : avant d'installer le plug-in pour votre serveur Microsoft Windows, arrêtez les deux services EVault dans `services.msc`.  

1. Accédez au dossier `c:\installs\evault` et lancez le fichier .exe doté du plus haut niveau de révision.
2. Sur l'écran de langue, cliquez sur **OK**.
3. Sur l'écran d'accueil, cliquez sur **Suivant**.
4. Sélectionnez l'option **Modifier l'installation** et cliquez sur **Suivant**.
5. Sélectionnez l'option **Laisser inchangé** et cliquez sur **Suivant**.
6. Sur l'écran de configuration personnalisée, sélectionnez chaque plug-in dont vous avez fait l'acquisition et sélectionnez **Cette fonction sera installée sur...**, puis cliquez sur **Suivant**.
7. Sélectionnez **Conserver mon enregistrement actuel** et cliquez sur **Suivant**.
8. Cliquez sur **Installer**.
9. Une fois l'installation terminée, vérifiez que les deux services sont activés et opérationnels.
10. Si WebCC parvient à accéder à la base de données et à l'afficher, cela indique que l'installation a abouti. 

## Installation du plug-in Oracle pour Unix

Le plug-in Oracle est un module complémentaire de l'agent Linux, installé avec celui-ci sur l'hôte de base de données. L'application Linux Agent doit être installée avant l'installation du plug-in Oracle. L'agent Linux est disponible sous forme d'application 32 bits ou 64 bits. Pour plus d'informations sur l'installation de l'agent Linux, voir [Installation du client de sauvegarde EVault sous Linux](install-evault-backup-client-linux.html).

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
   
>**Remarque** - Le plug-in Oracle effectue une sauvegarde complète "incohérente" qui requiert que la base de données s'exécute en mode ARCHIVELOG. L'administrateur de base de données doit s'assurer que la base de données est en mode ARCHIVELOG avant de démarrer les sauvegardes. Pour plus d'informations, voir le guide d'utilisation de EVault Agent v8.0 for Linux and Oracle Plug-in.


## Téléchargement du guide d'utilisation

Connectez-vous au réseau {{site.data.keyword.BluSoftlayer_full}} avec {{site.data.keyword.BluVPN}} pour pouvoir télécharger les fichiers EVault Agent v8.0 for Microsoft Windows - Oracle plug-in Guide.pdf et EVault Agent v8.0 for Linux and Oracle Plug-in - User Guide.pdf depuis [Downloadable EVault Documentation](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.




