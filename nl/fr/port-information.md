---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-17"

keywords: IBM Cloud backup, EVault, Carbonite, backup, port information, configure, configuring,

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configuration de ports afin d'autoriser la communication entre l'agent de sauvegarde et le portail {{site.data.keyword.backup_notm}}
{: #portinfo}

L'agent {{site.data.keyword.backup_full}} qui est installé sur votre serveur doit pouvoir communiquer avec le coffre dont vous avez fait l'acquisition. Les informations sur l'hôte Director pour un compte utilisateur {{site.data.keyword.backup_notm}} se trouvent sur la [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/classic/storage/backup){: external}.

Enregistrez systématiquement les agents auprès du portail {{site.data.keyword.backup_notm}} et des directeurs en utilisant le nom de domaine complet puisque les adresses IP de ces services sont susceptibles de changer.

Vos serveurs doivent pouvoir communiquer avec le portail {{site.data.keyword.backup_notm}} et tous les serveurs proxy AMP pour que le portail {{site.data.keyword.backup_notm}} fonctionne correctement, quel que soit l'emplacement du centre de données.

```
evregister.service.softlayer.com TCP 8086,8087
```

Vous pouvez ajouter à votre guise d'autres serveurs proxy AMP pour gérer davantage d'agents {{site.data.keyword.backup_notm}} enregistrés auprès du portail {{site.data.keyword.backup_notm}}.

Les ports TCP 8086 et 8087 doivent pouvoir accéder à 10.0.0.0/8.
{:important}

Si vous avez besoin d'utiliser des règles de pare-feu plus contraignantes, vous risquez de perdre l'accès au portail {{site.data.keyword.backup_notm}} après une expansion de l'infrastructure. Actuellement, au minimum, vos serveurs doivent autoriser l'accès aux sous-réseaux 10.0.82.0/24 et 10.2.118.0/24 pour les ports TCP 8086 et 8087. D'autres sous-réseaux pourraient être utilisés à l'avenir en cas de besoin.

## Commerce

Portail *{{site.data.keyword.backup_notm}} et serveurs proxy AMP*

- `ev-webcc01.service.softlayer.com` [10.0.82.12] 8086, 8087
- `evregister.service.softlayer.com` [10.0.82.12] 8086, 8087

*Serveurs proxy AMP à usage commercial*

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

## Fédéral

Portail *{{site.data.keyword.backup_notm}} et proxy AMP*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087

L'agent doit autoriser le port TCP 2548 en entrée sur le réseau privé. Ce paramètre permet à Central Control et au portail {{site.data.keyword.backup_notm}} de se connecter à l'agent pour le gérer. Les versions plus anciennes d'EVault utilisaient le port 808.

Le port de gestion {{site.data.keyword.backup_notm}} (2548) peut être changé en mettant à jour la clé de registre sur `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber` (élément `dword`) sur les systèmes d'exploitation Windows.

La différence entre Central Control et l'agent en ce qui concerne les paramètres de connexion est souvent un point de confusion. L'agent résidant sur le serveur se connecte aux serveurs {{site.data.keyword.backup_notm}}, tandis que Central Control (utilisé par le poste de travail) se connecte à votre serveur, en se servant de son adresse et des données d'identification du serveur pour y accéder.
{:tip}
