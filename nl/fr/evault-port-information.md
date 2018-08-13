---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-26"

---
{:new_window: target="_blank"}

# Configuration de ports afin d'autoriser la communication entre l'agent EVault et WebCC

L'agent EVault qui est installé sur votre serveur doit pouvoir communiquer avec le coffre dont vous avez fait l'acquisition. Les informations sur l'hôte EVault Director pour un compte utilisateur figurent dans le portail [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}. 

Enregistrez systématiquement les agents auprès du WebCC et des EVault Directors à l'aide du nom de domaine complet (FQDN) étant donné que les adresses IP de ces services sont susceptibles de changer. 


```
evregister.service.softlayer.com TCP 8086,8087
```

Vos serveurs doivent pouvoir communiquer avec l'utilitaire WebCC et tous les serveurs proxy AMP pour que WebCC fonctionne correctement, quel que soit l'emplacement du centre de données. Vous pouvez ajouter à votre guise d'autres serveurs proxy AMP pour gérer davantage d'agents EVault enregistrés auprès de WebCC. 

Les ports TCP 8086 et 8087 doivent pouvoir accéder à 10.0.0.0/8. 

Si vous avez besoin d'utiliser des règles de pare-feu plus contraignantes, vous risquez de perdre l'accès à l'utilitaire WebCC après une expansion de l'infrastructure. Actuellement, au minimum, vos serveurs doivent autoriser l'accès aux sous-réseaux 10.0.82.0/24 et 10.2.118.0/24 pour les ports TCP 8086 et 8087. D'autres sous-réseaux pourraient être utilisés à l'avenir en cas de besoin.

**Usage commercial**

*WebCC et serveurs proxy AMP*

- ev-webcc01.service.softlayer.com [10.0.82.12] 8086, 8087
- evregister.service.softlayer.com [10.0.82.12] 8086, 8087

*Serveurs proxy AMP à usage commercial*

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

**Usage fédéral**

*WebCC et proxy AMP*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087
 
L'agent doit autoriser le port TCP/2548 en entrée sur le réseau privé. Cela permet à CentralControl et à WebCC de se connecter à l'agent pour le gérer. Les versions plus anciennes d'EVault utilisaient le port 808.

Le port de gestion EVault (2548) peut être changé en mettant à jour la clé de registre sur `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber` (élément `dword`) sur les systèmes d'exploitation Windows.

**Précision supplémentaire**. La différence entre l'utilisation de CentralControl et l'agent en ce qui concerne les paramètres de connexion est souvent un point de confusion. L'agent résidant sur le serveur se connecte aux serveurs EVault, tandis que CentralControl (utilisé par le poste de travail) se connecte à votre serveur à l'aide de son adresse et des données d'identification du serveur pour y accéder.
