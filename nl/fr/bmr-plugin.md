---


copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Installation du plug-in Bare Metal Restore

BMR est une solution de reprise après incident pour Microsoft Windows. Vous pouvez utiliser BMR pour restaurer votre serveur à partir d'un état bare metal après un sinistre, par exemple, une panne de matériel ou de système d'exploitation. BMR vous permet de restaurer rapidement l'image système à partir d'un emplacement sécurisé qui est géré par {{site.data.keyword.BluSoftlayer_full}}.

BMR est un produit opérant uniquement sur des serveurs physiques Microsoft Windows. Il n'est pas disponible pour les serveurs virtuels. Les restaurations Bare Metal pour les distributions Linux ne sont pas prises en charge. BMR n'est pris en charge que par Backup Agent 8.30 ou des versions antérieures (30 juin 2018).
{:important}

**Fonctions fournies**

- Restauration de votre système à un point de cohérence sélectionné.
- Restauration de votre système depuis des sauvegardes basées image ou fichiers.
- Restauration de votre système depuis des sauvegardes hébergées sur IBM Cloud Backup.
- Transaction de reprise déclenchable permettant de restaurer vos données sans système amorçable.
.
## Commande du plug-in

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} et cliquez sur l'icône **Menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.

   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** > **Sauvegarde** pour afficher les serveurs avec service de sauvegarde.
3. Sélectionnez votre compte, puis cliquez sur **Commander plug-ins**.
4. Sélectionnez **Plug-in {{site.data.keyword.backup_notm}} - BMR (Bare Metal Restore)** et cliquez sur **Continuer**.
5. Entrez votre code promotionnel si vous en avez un et cliquez sur **Recalculer**.
6. Les frais mis à jour sont affichés. Passez en revue votre commande.
7. Cochez la case indiquant que vous avez lu et accepté les contrats de service tiers.
8. Cliquez sur **Valider la commande**.

## Téléchargement du guide d'utilisation

Connectez-vous au réseau {{site.data.keyword.BluSoftlayer_full}} avec {{site.data.keyword.BluVPN}} pour pouvoir accéder au guide d'utilisation et le télécharger à partir de la  [documentation {{site.data.keyword.backup_notm}} téléchargeable ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.

## Foire aux questions

**Puis-je passer d'un disque unique à une grappe RAID ?**

Oui, c'est tout à fait possible. Cependant, vous devez sélectionner une unité de grande capacité en raison de la réduction de taille provoquée par la grappe RAID.

**Que se passe-t-il lorsque l'image est restaurée sur un disque plus grand que le volume d'origine ?**

Si vous restaurez l'image sur un disque de plus grande capacité que le volume d'origine, l'espace excédentaire est désaffecté. Si, par exemple, vous disposez d'une unité de 500 Go et que vous restaurez ses données sur un disque de 1 To, un espace disque de 500 Go est désaffecté. Avec Windows 2008, vous pouvez utiliser l'utilitaire disque intégré pour étendre la partition principale. Toutefois, il n'existe pas de fonction intégrée similaire dans Windows 2003, par conséquent, vous devez allouer l'espace d'une autre façon.

**BMR peut-il être utilisé pour une sauvegarde régulière ?**

La sauvegarde BMR n'est pas une image disque mais un système de sauvegarde d'image sur un volume système. Le système n'est pas destiné à être utilisé pour des sauvegardes régulières mais conjointement à celles-ci.  

**BMR peut-il être utilisé pour des sauvegardes de base de données ?**

Les sauvegardes de base de données doivent être réalisées séparément, avec les méthodes de sauvegarde IBM Cloud ordinaires. BMR ne vient pas remplacer les plug-ins SQL ou Oracle. Bien que BMR utilise la technologie VSS pour sauvegarder les fichiers ouverts, il n'est pas garanti que les fichiers sauvegardés soient toujours cohérents avec les transactions. Il est recommandé, pour ces types d'applications spécialisées, de créer deux travaux de sauvegarde : l'un pour sauvegarde du système d'exploitation et des fichiers binaires d'application, l'autre pour les données d'application. Une note à cet effet figure à la fin du guide d'utilisation de BMR.

**Quel type de travaux de restauration puis-je effectuer avec BMR ?**

Vous pouvez effectuer une restauration intégrale du système ou bien sélectionner dans la sauvegarde des fichiers individuels à restaurer. Le travail de sauvegarde BMR peut remplacer le travail de sauvegarde de vos fichiers actuels. La procédure de restauration est effectuée dans le système d'exploitation, tout comme un travail de sauvegarde traditionnel.

**BMR dispose-t-il de fonctionnalités de sauvegarde de fichiers ouverts ?**

BMR dispose de fonctionnalités de sauvegarde de fichiers ouverts. Toutefois, BMR ne vient pas remplacer les plug-ins SQL ou Oracle. Pour plus d'informations sur le plug-in MSSQL, cliquez [ici](mssql-plugin.html).

**Combien d'espace disque et de temps sont-ils nécessaires pour une restauration BMR ?**

Une sauvegarde qui est réalisée à partir d'une installation par défaut utilise environ 6 Go. Une restauration de ce type dure environ 15 minutes sur un port 1 Go. Cette procédure est également affectée par la vitesse du port privé. Si vous avez besoin de sauvegardes et de restaurations plus rapides, vous devrez éventuellement utiliser un port plus véloce.
