---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-26"

---
{:new_window: target="_blank"}

# Configurazione delle porte per consentire la comunicazione tra l'agent EVault e WebCC

L'agent EVault installato sul tuo server deve essere in grado di comunicare con l'archivio che hai acquistato. Le informazioni sull'host del selettore EVault per un account utente EVault sono disponibili nel [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}. 

Registra gli agent sui selettori di WebCC e EVault utilizzando sempre il nome di dominio completo perché gli indirizzi IP di questi servizi potrebbero cambiare. 


```
evregister.service.softlayer.com TCP 8086,8087
```

Affinché WebCC funzioni correttamente, i tuoi server devono comunicare con WebCC e con tutti i server proxy AMP, indipendentemente dall'ubicazione del data center. È possibile aggiungere ulteriori server proxy AMP in base alle esigenze per gestire più agent EVault registrati nel WebCC. 

Le porte TCP 8086, 8087 devono avere accesso a 10.0.0.0/8. 

Se hai bisogno di utilizzare regole firewall più restrittive, potresti perdere l'accesso a WebCC man mano che l'infrastruttura viene espansa. Attualmente, come minimo, i tuoi server dovrebbero consentire l'accesso alle sottoreti 10.0.82.0/24 e 10.2.118.0/24 per le porte TCP 8086, 8087. In futuro, è possibile utilizzare ulteriori sottoreti in base alle esigenze.

**Commerciale**

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

**Federale**

*Proxy WebCC e AMP*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087
 
L'agent deve consentire la porta TCP/2548 in entrata sulla rete privata. Questa impostazione consente a CentralControl e WebCC di connettersi all'agent per gestirlo. Le versioni precedenti di EVault utilizzavano la porta 808.

La porta di gestione EVault (2548) può essere modificata aggiornando la chiave di registro su: `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber` (che è un valore `dword`) nei sistemi operativi Windows.

**Chiarimento**. Quando si tratta di impostazioni di connessione, la differenza tra CentralControl sul desktop e l'agent è spesso un punto di confusione. L'agent residente nel server si connette ai server EVault, mentre il CentralControl utilizzato dal desktop si connette al tuo server, utilizzando il proprio indirizzo e le credenziali del server per accedervi.
