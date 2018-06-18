---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-03"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Installazione del client EVault Backup per VMware

L'installazione del client EVault Backup su un server VMware può essere eseguita tramite una serie di comandi nella shell o nel terminale all'interno del server ESX di destinazione. Questa procedura descrive i passi necessari per installare il client EVault Backup sul tuo server VMware:

Per installare l'agent, scarica e copia il pacchetto `Agent-VMware-ESX-Server-6.71.<version-info>.tar.gz` sul server ESX di destinazione utilizzando il seguente comando:

`wget -N http://downloads.service.softlayer.com/evault/archive/Agent-VMware-ESX-Server-6.71.2105.tar.gz`

**Nota**:  la seguente procedura deve essere eseguita localmente sul server ESX di destinazione.

1. Estrai i file dal pacchetto. Per farlo, utilizza questo comando (in cui “PACKAGENAME” potrebbe essere “Agent-VMware-ESX-Server-6.71”):
    `tar xvfz PACKAGENAME.tar.gz`
2. Vai alla directory in cui hai estratto il pacchetto.
3. Esegui lo script di installazione:
    `# ./install.sh`

    **Nota**:  lo script di installazione ti richiederà in modo interattivo informazioni di configurazione quali la registrazione web (indirizzo, numero di porta e autenticazione) e il nome del file di log. 
     
    - Immetti il nome utente WebCC per questo server.
    - Immetti la password WebCC per questo server.
     
4. Immetti l'**EVault Backup Username** come input per il prompt che richiede il nome utente WebCC. 
5. Immetti la **EVault Backup Password** come input per il prompt che richiede la password WebCC.
6. Al termine dell'installazione, verrà visualizzato un messaggio di completamento e il daemon dell'agent sarà in esecuzione.


### Altre note di installazione:
Install.log si troverà nella directory di installazione se l'installazione ha avuto esito positivo.
Ad esempio: `/opt/BUAgent/Install.log`

Se l'installazione ha esito negativo ed esegue il ripristino allo stato precedente, il log di installazione sarà in `<Installation Failure directory>`.
Se ha esito negativo e non esegue il ripristino allo stato precedente, il log di installazione sarà in `<Installation Kit directory>`.

Per ulteriori informazioni, scarica la guida [VMware_Agent_User_Guide](http://downloads.service.softlayer.com/evault/Documentation/VMware_Agent_User_Guide.pdf){:new_window}. Assicurati di essere connesso a {{site.data.keyword.BluVPN}} per poter visualizzare questo link.
