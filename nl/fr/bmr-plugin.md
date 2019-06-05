---

copyright:
  years: 1994, 2019
lastupdated: "2019-03-26"

keywords: IBM Cloud backup, bare metal restore, bmr, plug-in, plugin, EVault, Carbonite, baremetal, point-in-time restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Installation du plug-in Bare Metal Restore
{: #BMRplugin}

BMR est une solution de reprise après incident. Vous pouvez utiliser BMR pour restaurer votre serveur à partir d'un état bare metal après un sinistre, par exemple, une panne de matériel ou de système d'exploitation. BMR vous permet de restaurer rapidement l'image système à partir d'un emplacement sécurisé qui est géré par {{site.data.keyword.cloud}}.

BMR est un produit opérant uniquement sur des serveurs physiques Microsoft Windows. Il n'est pas disponible pour les serveurs virtuels. Les restaurations Bare Metal pour les distributions Linux ne sont pas prises en charge. BMR n'est pris en charge que par Backup Agent 8.30 ou des versions antérieures (30 juin 2018).
{:important}

**Fonctions fournies**

- Restauration de votre système à un point de cohérence sélectionné.
- Restauration de votre système depuis des sauvegardes basées image ou fichiers.
- Restauration de votre système depuis des sauvegardes hébergées {{site.data.keyword.backup_notm}}.
- Transaction de reprise déclenchable permettant de restaurer vos données sans système amorçable.

## Commande du plug-in
{: #orderingBMR}

1. Connectez-vous à la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} et cliquez sur l'icône **menu** dans l'angle supérieur gauche. Sélectionnez **Infrastructure classique**.<br/>
   Sinon, vous pouvez vous connecter au portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}.
2. Cliquez sur **Stockage** > **Sauvegarde** pour afficher les serveurs avec service de sauvegarde.
3. Sélectionnez votre compte, puis cliquez sur **Commander plug-ins**.
4. Sélectionnez **Plug-in {{site.data.keyword.backup_notm}} - BMR (Bare Metal Restore)** et cliquez sur **Continuer**.
5. Entrez votre code promotionnel si vous en avez un et cliquez sur **Recalculer**.
6. Les frais mis à jour sont affichés. Passez en revue votre commande.
7. Cochez la case indiquant que vous avez lu et accepté les contrats de service tiers.
8. Cliquez sur **Valider la commande**.

## Téléchargement du guide d'utilisation
{: #BMRUserGuide}

Connectez-vous au réseau {{site.data.keyword.cloud}} avec {{site.data.keyword.BluVPN}} pour pouvoir accéder au guide d'utilisation et le télécharger depuis la [documentation {{site.data.keyword.backup_notm}} téléchargeable](http://downloads.service.softlayer.com/evault/Documentation/){: external}
