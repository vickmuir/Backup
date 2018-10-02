---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-27"

---
{:new_window: target="_blank"}

# Installation du plug-in Exchange d'EVault

Le plug-in Exchange est installé avec l'agent Windows sur l'hôte. A l'aide du portail WebCC, vous pouvez configurer des travaux, sauvegarder des bases de données Oracle dans un coffre distant sécurisé et restaurer des bases de données Oracle. Le plug-in Oracle s'intègre dans l'architecture existante.

**Fonctions fournies**

- Possibilité de sauvegarde et de restauration de bases de données Microsoft Exchange.

## Commande du plug-in

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** > **Sauvegarde**.
3. Sélectionnez votre compte EVault, puis cliquez sur **Commander plug-ins**.
4. Sélectionnez **Plug-in EVault - Exchange** et cliquez sur **Continuer**.
5. Entrez votre code promotionnel si vous en avez un et cliquez sur **Recalculer**.
6. Les frais mis à jour sont affichés. Passez en revue votre commande.
7. Cochez la case indiquant que vous avez lu et accepté les contrats de service tiers. 
8. Cliquez sur **Valider la commande**.

## Installation du plug-in Exchange

Le plug-in Exchange est installé avec l'agent Windows 64 bits. Il peut être installé en même temps que l'agent ou bien ultérieurement, en ré-exécutant l'installation et en sélectionnant l'option **Modifier**.

**Remarque** : avant d'installer le plug-in pour votre serveur Microsoft Windows, arrêtez les deux services EVault dans `services.msc`.  

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
11. Si WebCC parvient à accéder à la base de données et à l'afficher, cela indique que l'installation a abouti. 

## Téléchargement du guide d'utilisation

Connectez-vous au réseau {{site.data.keyword.BluSoftlayer_full}} avec {{site.data.keyword.BluVPN}} pour pouvoir télécharger le fichier Guide.pdf du plug-in Exchange de l'agent EVault v8.0 pour Microsoft Windows (64 bits) depuis la [documentation EVault téléchargeable](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}. Ce guide décrit comment réaliser une sauvegarde et une restauration de bases de données Microsoft Exchange à l'aide du plug-in Exchange. Il explique également comment partager un jeu sécurisé de sauvegarde DR. Un jeu sécurisé de sauvegarde DR permet de restaurer des boîtes aux lettres spécifiques, des messages ou d'autres objets dans un fichier .pst à l'aide de l'application Granular Restore for Microsoft Exchange.

