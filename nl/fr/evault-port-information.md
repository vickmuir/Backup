---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-30"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Informations de port EVault

L'agent EVault installé sur votre serveur doit pouvoir communiquer avec le coffre dont vous avez fait l'acquisition. Les informations sur l'hôte EVault Director d'un compte utilisateur sont accessibles sur le portail client. Enregistrez systématiquement les agents auprès du WebCC et des EVault Directors à l'aide du nom de domaine complet (FQDN) vu que les adresses IP de ces services sont susceptibles de changer. 

Vos serveurs doivent pouvoir communiquer avec l'utilitaire WebCC et tous les serveurs proxy AMP pour que WebCC fonctionne correctement, quel que soit l'emplacement du centre de données : evregister.service.softlayer.com TCP 8086,8087. 

Vous pouvez ajouter à votre guise d'autres serveurs proxy AMP pour gérer des agents EVault supplémentaires enregistrés auprès de WebCC. 

Les ports TCP 8086 et 8087 doivent pouvoir accéder au sous-réseau 10.0.0.0/8. 

Si vous avez besoin de règles de pare-feu plus contraignantes, vous pourriez perdre l'accès à l'utilitaire WebCC après une expansion de l'infrastructure. Actuellement, au minimum, vos serveurs doivent autoriser l'accès aux sous-réseaux 10.0.82.0/24 et 10.2.118.0/24 pour les ports TCP 8086 et 8087. Des sous-réseaux supplémentaires pourraient être utilisés à l'avenir en cas de besoin.

## Usage commercial :

### WebCC et serveurs proxy AMP :

- ev-webcc01.service.softlayer.com [10.0.82.12] 8086, 8087
- evregister.service.softlayer.com [10.0.82.12] 8086, 8087

### Serveurs proxy AMP à usage commercial :

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

## Usage fédéral :

### WebCC et proxy AMP :

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087
 
L'agent doit autoriser le port TCP/2548 en entrée sur le réseau privé. Ceci permet à CentralControl et à WebCC de se connecter à l'agent pour le gérer. Les versions plus anciennes d'EVault utilisaient le port 808.

Le port de gestion EVault (2548) peut être changé en mettant à jour la clé de registre sur \SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber (élément dword) sur les systèmes d'exploitation Windows.

**Précision supplémentaire** : la différence entre l'utilisation de CentralControl et l'agent en ce qui concerne les paramètres de connexion est souvent un point de confusion. L'agent résidant sur le serveur se connecte à nos serveurs EVault, tandis que CentralControl (utilisé par le poste de travail) se connecte en fait à votre serveur à l'aide de cette adresse et des données d'identification du serveur pour y accéder.
