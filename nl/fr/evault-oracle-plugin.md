---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# Installation du plug-in Oracle d'EVault

Le plug-in Oracle est installé avec l'agent Windows sur l'hôte de base de données Oracle. A l'aide du portail WebCC, vous pouvez configurer des travaux, sauvegarder des bases de données Oracle dans un coffre distant sécurisé et restaurer des bases de données Oracle. Le plug-in Oracle s'intègre dans l'architecture existante.

## Fonctions fournies

- Prise en charge de la sauvegarde et la récupération de base de données Oracle.
- Le plug-in Oracle permet des sauvegardes basées ARCHIVELOG, non RMAN, d'instances de bases de données en ligne complètes. Tous les espaces table et les fichiers de paramètres d'instance non temporaires sont automatiquement sauvegardés. Oracle Corporation recommande de procéder aux sauvegardes au cours des périodes de faible activité de la base de données.
- Les restaurations intégrales et partielles des bases de données sont réalisées par le biais de mécanismes de reprise Oracle gérés par l'utilisateur.

## Commande du plug-in

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** > **Sauvegarde**.
3. Sélectionnez votre compte EVault et cliquez sur **Commander Plug-ins**.
4. Sélectionnez **Plug-in EVault - Oracle** et cliquez sur **Continuer**.
5. Entrez votre code promotionnel si vous en avez un et cliquez sur **Recalculer**.
6. Les frais mis à jour sont affichés. Passez en revue votre commande. 
7. Cochez les cases indiquant que vous avez lu le Contrat cadre de service et acceptez les conditions de logiciel tiers. 
8. Cliquez sur **Valider la commande**.

## Installez le plug-in oracle

Le plug-in Oracle pour Windows est installé avec l'agent Windows 32 bits ou 64 bits. Pour installer le plug-in Oracle pour Windows, exécutez le kit d'installation de l'agent. Le plug-in Oracle s'affiche en tant qu'option sur la page **Installation personnalisée** .

**Remarque **: avant d'installer le plug-in pour votre serveur Microsoft Windows, arrêtez les deux services EVault dans `services.msc`.  

1. Accédez au dossier `c:\installs\evault` et lancez le fichier .exe doté du plus haut niveau de révision.
2. Dans l'écran de langue, cliquez sur **OK**.
3. Dans l'écran d'accueil, cliquez sur **Suivant**.
4. Sélectionnez l'option **Modifier l'installation** et cliquez sur **Suivant**.
5. Sélectionnez l'option **Laisser inchangé** et cliquez sur **Suivant**.
6. Sur l'écran de configuration personnalisée, sélectionnez chaque plug-in dont vous avez fait l'acquisition et sélectionnez **Cette fonction sera installée sur ...**, puis cliquez sur **Suivant**.
7. Sélectionnez le bouton d'option **Conserver mon enregistrement actuel** et cliquez sur **Suivant**.
8. Cliquez sur **Installer**.
9. Une fois installés, vérifiez que les deux services sont opérationnels.
10. Si WebCC parvient à accéder (afficher) aux bases de données, ceci indique que l'installation a abouti. 

## Guide d'utilisation

Connectez-vous au réseau {{site.data.keyword.BluSoftlayer_full}} avec {{site.data.keyword.BluVPN}} pour pouvoir télécharger le fichier Guide.pdf du plug-in Oracle de l'agent EVault v8.0 pour Microsoft Windows depuis la [Documentation EVault téléchargeable](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.

## Foire aux questions

### Quelles sont les limitations du plug-in Oracle?
- Seules les bases de données locales, basées disque et ne comportant qu'une seule instance, sont sauvegardées.
- Les clusters de base de données ne sont pas sauvegardés.
- Les unités en mode brut ne sont pas sauvegardées.
- Les bases de données distantes ne sont pas sauvegardées.
- La base de données doit opérer en mode ARCHIVELOG et l'utilisateur sous lequel la sauvegarde est configurée doit disposer des privilèges SYSDBA.
- Les mots de passe de base de données sont chiffrés pour sécurité accrue par rapport aux méthodes basées script.
