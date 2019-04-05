---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Installazione di vSphere Recovery Agent
{: #VRA}

vSphere Recovery Agent (VRA) è un'applicazione Windows che può eseguire il backup e il ripristino di VMDK fino a 10 TB. Puoi installare vSphere Recovery Agent su una macchina fisica o virtuale che dispone dell'accesso tramite rete locale al vCenter che vuoi proteggere. Per prestazioni ottimali, installa VRA su una macchina che si trova nella stessa sottorete di vCenter. Per distribuire il carico di lavoro, fino a cinque VRA possono proteggere le VM collegate a un singolo vCenter.

In un cluster esteso vSAN, ogni VM ha un sito preferito. Idealmente, un VRA locale viene installato in ogni sito che esegue il backup delle VM preferite di quel sito. Se una VM viene spostata su un sito diverso (a causa di manutenzione o guasti), le prestazioni di backup possono risultare ridotte ma rimangono accettabili.


## Ordinazione del plug-in
{: #orderingVRAPlugin}

{{site.data.keyword.cloud_notm}} fornisce gratuitamente VRA (vSphere Recovery Agent). Se disponi di una sottoscrizione corrente di {{site.data.keyword.backup_notm}}, puoi scaricare il plug-in dal portale {{site.data.keyword.backup_notm}}.

## Installazione del plug-in
{: #installVRAPlugin}

Assicurati che il risparmio energia sia disabilitato sul server su cui installi VRA.
{: important}

1. Scarica il kit di installazione da `http://downloads.service.softlayer.com/evault/`. Quindi, fai doppio clic sul kit di installazione.
2. Nel messaggio di conferma, fai clic su **YES**.
3. Nella pagina di benvenuto, fai clic su **Next**.
4. Nella pagina End-User-License Agreement, leggi l'accordo di licenza. Se accetti i termini, fai clic su **I accept the terms in the License Agreement** e quindi su **Next**.
5. Nella pagina Destination Folder, effettua una delle seguenti azioni.
   * Per installare VRA nell'ubicazione predefinita, fai clic su **Next**.
   * Per installare VRA in un'altra ubicazione, fai clic su **Change**. Nella finestra di dialogo Change destination folder, passa alla nuova cartella di installazione o immetti il suo nome nella casella Folder name. Fai clic su **OK**. Nella pagina Destination Folder, fai clic su **Next**.
6. Nella pagina Register Agent with Portal, specifica le seguenti informazioni.
   * Nel campo **Network address**, immetti `ev-webcc01.service.softlayer.com`.
   * Nel campo **Port**, immetti `8086`.
   * Nel campo **Username**, immetti il nome utente {{site.data.keyword.backup_notm}} per la gestione di VRA.
   * Nel campo **Password**, immetti la password dell'utente {{site.data.keyword.backup_notm}} specificato.
7.	Fai clic su **Next**. Al termine dell'installazione, fai clic su **Finish**.

## Configurazione di vSphere Recovery Agent
{: #configureVRA}

Una volta installato VRA, devi configurarlo nel portale {{site.data.keyword.backup_notm}}.

1. Accedi al portale {{site.data.keyword.backup_notm}}. Per ulteriori informazioni su come accedere al portale {{site.data.keyword.backup_notm}}, vedi l'[Esercitazione introduttiva](/docs/infrastructure/Backup?topic=Backup-getting-started#accessingWebCC).
2. Nella scheda Computers, seleziona il server di cui vuoi eseguire il backup.
3. Configura le informazioni sull'archivio.

   Le informazioni sull'archivio possono essere configurate in due modi: **Automaticamente** o **Manualmente**.<br/>Se l'agent viene configurato per la prima volta, può essere configurato utilizzando l'opzione di [Configurazione automatica](#VRAautoconfig).<br/>Se il computer è stato precedentemente registrato con un archivio, la configurazione automatica non funziona e l'archivio deve essere [configurato manualmente](#VRAmanualconfig).
   {: tip}

4. Configura le [importazioni di vCenter](#vCenterSettingsconfig)   

### Configurazione automatica dell'archivio
{: #VRAautoconfig}

Per configurare automaticamente le impostazioni dell'archivio, fai clic su **Configure Automatically**. La procedura guidata di configurazione esegue e configura automaticamente le impostazioni dell'archivio. Al termine, fai clic su **Go To Agent** per verificare le informazioni nella scheda **Vault Settings**.
 

### Configurazione manuale dell'archivio
{: #VRAmanualconfig}

Per configurare manualmente le impostazioni dell'archivio, fai clic su **Configure Manually**.   
1. Fai clic su **Vault Settings**.
2. Fai clic su **Add Vault**. Viene visualizzata la finestra Vault Settings. Dalle opzioni di **Vault Profile**, seleziona l'archivio appropriato.
   Se il computer è stato precedentemente registrato con un archivio {{site.data.keyword.backup_notm}}, tutte le informazioni vengono compilate automaticamente quando si seleziona l'archivio da Vault Profile.
   {:note}

3. Verifica tutte le informazioni nella pagina Vault settings e fai clic su **Save**.
4. Quando salvi le impostazioni dell'archivio, le informazioni sull'archivio diventano visibili nella scheda **Vault Settings**.


### Configurazione delle impostazioni dell'agent vCenter
{: #vCenterSettingsconfig}
Una volta registrato correttamente l'archivio, è necessario configurare le impostazioni di vCenter prima di poter creare ed eseguire i lavori di backup.

1. Fai clic sulla scheda **vCenter Settings**
2. Fornisci l'indirizzo IP, il nome dominio e le credenziali per il vCenter che vuoi proteggere.
   L'utente deve disporre dell'accesso di amministrazione al vCenter per eseguire correttamente questa attività.
   {:note}

3. Disabilita la funzione CBT (Change Block Tracking) rimuovendo il segno di spunta. CBT è una funzione VMware abilitata automaticamente dall'agent vSphere che tiene traccia dei settori di dischi modificati e migliora le prestazioni dei backup delle VM.
4. Fai clic su **Test vCenter Connection**. Una nuova finestra visualizza i risultati. Se le informazioni di accesso fornite sono corrette, viene visualizzato il messaggio “The vCenter credentials have been validated successfully”.
5. Fai clic su **Save** per salvare le impostazioni. 

## Passi successivi
{: #VRAnextteps}
1. [Configura, pianifica ed esegui un lavoro di backup](/docs/infrastructure/Backup?topic=Backup-ConfigureVRA#VConfigureVRA)
2. [Ripristina i dati vSphere](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore)

Connettiti alla rete {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} in modo da poter accedere e scaricare la guida utente dalla [documentazione di {{site.data.keyword.backup_notm}} scaricabile ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}
{:tip}
