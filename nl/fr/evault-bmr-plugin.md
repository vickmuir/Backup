---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# Installation du plug-in Bare Metal Restore d'EVault

EVault BMR désigne une solution de reprise après incident pour Microsoft Windows permettant de restaurer complètement votre serveur depuis un état à nu (bare metal) en cas de sinistre, tel qu'une panne du matériel ou du système d'exploitation. Ce système vous permet de restaurer rapidement l'image système à partir d'un emplacement sécurisé géré par {{site.data.keyword.BluSoftlayer_full}}.

**Remarque **: BMR est un produit opérant uniquement sur des serveurs physiques Microsoft Windows. Il n'est pas disponible pour les serveurs virtuels. Les restaurations Bare Metal pour les distributions Linux ne sont pas prises en charge. BMR n'est pris en charge que par EVault Agent 8.30 (ou version antérieure) (30 juin 2018).

## Fonctions fournies

- Restauration de votre système à un point de cohérence sélectionné.
- Restauration de votre système depuis des sauvegardes basées image ou fichiers.
- Restauration de votre système depuis des sauvegardes hébergées sur EVault.
- Transaction de reprise déclenchable permettant de restaurer vos données sans système amorçable.

## Commande du plug-in

1. Connectez-vous au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** > **Sauvegarde**.
3. Sélectionnez votre compte EVault et cliquez sur **Commander Plug-ins**.
4. Sélectionnez **Plug-in EVault - BMR (Bare Metal Restore)** et cliquez sur **Continuer**.
5. Entrez votre code promotionnel si vous en avez un et cliquez sur **Recalculer**.
6. Les frais mis à jour sont affichés. Passez en revue votre commande. 
7. Cochez les cases indiquant que vous avez lu le Contrat cadre de service et acceptez les conditions de logiciel tiers. 
8. Cliquez sur **Valider la commande**.

## Guide d'utilisation

Connectez-vous au réseau {{site.data.keyword.BluSoftlayer_full}} avec {{site.data.keyword.BluVPN}} pour pouvoir télécharger le fichier Guide.pdf d'EVault System Restore v8.3 depuis la [Documentation EVault téléchargeable](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.

## Foire aux questions

### Puis-je migrer depuis un disque unique vers une grappe raid ?

Oui, celle-ci fonctionnera. Cependant, vous devrez sélectionner une unité de grande capacité en raison de la réduction de taille entraînée par la grappe raid.

### Que se passe-t-il si je restaure l'image sur un disque de plus grande capacité que le volume d'origine ?

Si vous restaurez l'image sur un disque de plus grande capacité que le volume d'origine, l'espace excédentaire est désaffecté. Si, par exemple, vous disposiez d'une unité de 500 Go et restaurez ses données sur un disque de 1 To, un espace disque de 500 Go sera désaffecté. Avec Windows 2008, vous pouvez utiliser l'utilitaire disque natif pour étendre la partition principale. Toutefois, cette capacité n'existe pas sous Windows 2003 et il est donc recommandé d'allouer simplement l'espace.

### Puis-je utiliser BMR pour ma sauvegarde régulière ?

Il ne s'agit pas d'une image disque mais d'un système de sauvegarde d'image sur un volume système. Ce système n'est pas destiné à être utilisé pour des sauvegardes régulières mais de pair avec celles-ci.  

### Puis-je utiliser BMR pour mes sauvegardes de base de données ?

Les sauvegardes de bases de données doivent être réalisées séparément, avec les méthodes de sauvegarde EVault ordinaires. BMR ne vient pas remplacer les plug-ins SQL ou Oracle. Bien que BMR utilise la technologie VSS pour sauvegarder les fichiers ouverts, il n'est pas garanti que les fichiers sauvegardés soient toujours cohérents avec les transactions. Notre recommandation pour ces types d'applications spécialisées est de créer deux travaux de sauvegarde : l'un pour sauvegarde du système d'exploitation et des fichiers binaires d'application, l'autre pour les données d'application. Une note à cet effet figure à la fin du guide d'utilisation de BMR.

### Quel type de travaux de restauration puis-je effectuer avec BMR ?

Vous pouvez effectuer une restauration intégrale du système ou bien sélectionner dans la sauvegarde des fichiers individuels à restaurer. Ceci signifie que ce travail peut remplacer le travail de sauvegarde de vos fichiers actuels. La procédure de restauration peut être effectuée depuis le système d'exploitation, tout comme un travail de sauvegarde traditionnel.

### BMR dispose-t-il de fonctionnalités de sauvegarde de fichiers ouverts ?

BMR dispose de fonctionnalités de sauvegarde de fichiers ouverts. Toutefois, BMR ne vient pas remplacer les plug-ins SQL ou Oracle. Cliquez [ici](evault-mssql-plugin-installation.html) pour les instructions d'installation du plug-in MSSQL.

### Combien d'espace disque et de temps sont-ils nécessaires pour une restauration BMR ?

Une sauvegarde réalisée depuis une installation par défaut utilise environ 6 Go d'espace disque. Une telle restauration prendrait environ 15 minutes sur un port avec un débit de 1 Go. Cette procédure est également affectée par la vitesse du port privé. Si vous avez besoin de sauvegardes et/ou de restaurations plus rapides, vous devrez éventuellement utiliser un port plus véloce.
