---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-13"

keywords: IBM Cloud backup, bare metal restore, bmr, plug-in, plugin, EVault, Carbonite, baremetal, point-in-time restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# En savoir plus sur le plug-in Bare Metal Restore
{: #BMRplugin}

BMR est une solution de reprise après incident. Vous pouvez utiliser BMR pour restaurer votre serveur à partir d'un état bare metal après un sinistre, par exemple, une panne de matériel ou de système d'exploitation. BMR vous permet de restaurer rapidement l'image système à partir d'un emplacement sécurisé qui est géré par {{site.data.keyword.cloud}}.

BMR est un produit opérant uniquement sur des serveurs physiques Microsoft Windows. Il n'est pas disponible pour les serveurs virtuels. Les restaurations Bare Metal pour les distributions Linux ne sont pas prises en charge. BMR n'est pris en charge que par Backup Agent 8.30 ou des versions antérieures (30 juin 2018).
{:important}

## Fonctions fournies
{: #BMRcapabilities}

- Restauration de votre système à un point de cohérence sélectionné.
- Restauration de votre système depuis des sauvegardes basées image ou fichiers.
- Restauration de votre système depuis des sauvegardes hébergées {{site.data.keyword.backup_notm}}.
- Transaction de reprise déclenchable permettant de restaurer vos données sans système amorçable.

## Installation du plug-in BMR
{: #installingBMR}

Le plug-in est installé avec l'agent Windows. Il peut être installé en même temps que l'agent ou bien ultérieurement, en ré-exécutant l'installation et en sélectionnant l'option **Modifier**.

## Configuration d'un travail de sauvegarde BMR
{: #configBMRplugin}

Pour plus d'informations, voir [Configuration de travaux de sauvegarde BMR](/docs/infrastructure/Backup?topic=Backup-configureBMR).

## Restauration d'une image de volume système BMR
{: #restoringBMimage}
Pour plus d'informations, voir [Restauration d'une image de volume système BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR).

## Téléchargement du guide d'utilisation
{: #BMRUserGuide}

Connectez-vous au réseau {{site.data.keyword.cloud}} avec {{site.data.keyword.BluVPN}} pour pouvoir accéder au guide d'utilisation et le télécharger depuis la [documentation {{site.data.keyword.backup_notm}} téléchargeable](http://downloads.service.softlayer.com/evault/Documentation/){: external}
