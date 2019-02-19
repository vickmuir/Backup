---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configurazione delle porte per consentire le comunicazioni tra l'agent backup e il portale {{site.data.keyword.backup_notm}}
{: #portinfo}

L'agent {{site.data.keyword.backup_full}} installato sul tuo server deve essere in grado di comunicare con l'archivio che hai acquistato. Le informazioni sull'host Director per un account utente {{site.data.keyword.backup_notm}} sono disponibili nel [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window} e nella console [{{site.data.keyword.cloud_notm}}![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}/){:new_window}.

Registra sempre gli agent sul portale {{site.data.keyword.backup_notm}} e sui director utilizzando il nome di dominio completo (FQDN, Full Qualified Domain Name) perché gli indirizzi IP di questi servizi potrebbero cambiare.

Affinché il portale {{site.data.keyword.backup_notm}} funzioni correttamente, i tuoi server devono comunicare con il portale {{site.data.keyword.backup_notm}} e con tutti i server proxy AMP, indipendentemente dall'ubicazione del data center.

```
https://evregister.service.softlayer.com TCP 8086,8087
```

È possibile aggiungere ulteriori server proxy AMP in base alle esigenze per gestire più agent {{site.data.keyword.backup_notm}} registrati nel portale {{site.data.keyword.backup_notm}}.

Le porte TCP 8086, 8087 devono avere accesso a 10.0.0.0/8.
{:important}

Se hai bisogno di utilizzare regole firewall più restrittive, potresti perdere l'accesso al portale {{site.data.keyword.backup_notm}} man mano che l'infrastruttura viene espansa. Attualmente, come minimo, i tuoi server dovrebbero consentire l'accesso alle sottoreti 10.0.82.0/24 e 10.2.118.0/24 per le porte TCP 8086, 8087. In futuro, è possibile utilizzare ulteriori sottoreti in base alle esigenze.

## Commerciale

*Portale {{site.data.keyword.backup_notm}} e server proxy AMP*

- `https://ev-webcc01.service.softlayer.com` [10.0.82.12] 8086, 8087
- `https://evregister.service.softlayer.com` [10.0.82.12] 8086, 8087

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

*Portale {{site.data.keyword.backup_notm}} e proxy AMP*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087

L'agent deve consentire la porta TCP 2548 in entrata sulla rete privata. Questa impostazione consente a Central Control e {{site.data.keyword.backup_notm}} di connettersi all'agent per gestirlo. Le versioni precedenti di EVault utilizzavano la porta 808.

La porta di gestione {{site.data.keyword.backup_notm}} (2548) può essere modificata aggiornando la chiave di registro su: `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber` (che è un valore `dword`) nei sistemi operativi Windows.

Quando si tratta di impostazioni di connessione, la differenza tra Central Control sul desktop e l'agent è spesso motivo di confusione. L'agent residente nel server si connette ai server {{site.data.keyword.backup_notm}}, mentre il Central Control utilizzato dal desktop si connette al tuo server, utilizzando il proprio indirizzo e le credenziali del server per accedervi.
{:tip}
