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

# Configurazione delle porte per consentire la comunicazione tra l'agent Backup e WebCC

L'agent {{site.data.keyword.backup_full}} installato sul tuo server deve essere in grado di comunicare con l'archivio che hai acquistato. Le informazioni sull'host di selettori {{site.data.keyword.backup_notm}} per un account {{site.data.keyword.backup_notm}} sono disponibili nel [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} e nella [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window}.

Registra sempre gli agent sui selettori di WebCC e {{site.data.keyword.backup_notm}} utilizzando il nome di dominio completo (FQDN, Full Qualified Domain Name) perché gli indirizzi IP di questi servizi potrebbero cambiare.

Affinché WebCC funzioni correttamente, i tuoi server devono comunicare con WebCC e con tutti i server proxy AMP, indipendentemente dall'ubicazione del data center.

```
evregister.service.softlayer.com TCP 8086,8087
```

È possibile aggiungere ulteriori server proxy AMP in base alle esigenze per gestire più agent {{site.data.keyword.backup_notm}} registrati nel WebCC.

Le porte TCP 8086, 8087 devono avere accesso a 10.0.0.0/8.

Se hai bisogno di utilizzare regole firewall più restrittive, potresti perdere l'accesso a WebCC man mano che l'infrastruttura viene espansa. Attualmente, come minimo, i tuoi server dovrebbero consentire l'accesso alle sottoreti 10.0.82.0/24 e 10.2.118.0/24 per le porte TCP 8086, 8087. In futuro, è possibile utilizzare ulteriori sottoreti in base alle esigenze.

## Commerciale

*Server proxy WebCC e AMP*

- ev-webcc01.service.softlayer.com [10.0.82.12] 8086, 8087
- evregister.service.softlayer.com [10.0.82.12] 8086, 8087

*Server proxy AMP commerciali*

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

## Federale

*Proxy WebCC e AMP*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087

L'agent deve consentire la porta TCP/2548 in entrata sulla rete privata. Questa impostazione consente a CentralControl e WebCC di connettersi all'agent per gestirlo. Le versioni precedenti di EVault utilizzavano la porta 808.

La porta di gestione {{site.data.keyword.backup_notm}} (2548) può essere modificata aggiornando la chiave di registro su: `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber` (che è un valore `dword`) nei sistemi operativi Windows.

Quando si tratta di impostazioni di connessione, la differenza tra CentralControl sul desktop e l'agent è spesso un punto di confusione. L'agent residente nel server si connette ai server {{site.data.keyword.backup_notm}}, mentre il CentralControl utilizzato dal desktop si connette al tuo server, utilizzando il proprio indirizzo e le credenziali del server per accedervi.
{:tip}
