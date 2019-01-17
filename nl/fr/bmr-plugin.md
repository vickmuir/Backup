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
- Restauration de votre système depuis des sauvegardes hébergées {{site.data.keyword.backup_notm}}.
- Transaction de reprise déclenchable permettant de restaurer vos données sans système amorçable.

## Commande du plug-in

1. Connectez-vous à la console [{{site.data.keyword.cloud_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://{DomainName}){:new_window} et cliquez sur l'icône **menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**. <br/>
   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){:new_window}.
2. Cliquez sur **Stockage** > **Sauvegarde** pour afficher les serveurs avec service de sauvegarde.
3. Sélectionnez votre compte, puis cliquez sur **Commander plug-ins**.
4. Sélectionnez **Plug-in {{site.data.keyword.backup_notm}} - BMR (Bare Metal Restore)** et cliquez sur **Continuer**.
5. Entrez votre code promotionnel si vous en avez un et cliquez sur **Recalculer**.
6. Les frais mis à jour sont affichés. Passez en revue votre commande.
7. Cochez la case indiquant que vous avez lu et accepté les contrats de service tiers.
8. Cliquez sur **Valider la commande**.

## Téléchargement du guide d'utilisation

Connectez-vous au réseau {{site.data.keyword.BluSoftlayer_full}} avec {{site.data.keyword.BluVPN}} pour pouvoir accéder au guide d'utilisation et le télécharger depuis la [documentation {{site.data.keyword.backup_notm}} téléchargeable ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}
