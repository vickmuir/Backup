---

copyright:
  years: 2014, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Introduzione ai servizi {{site.data.keyword.backup_notm}}

I backup assicurano che i tuoi dati vengano memorizzati in modo sicuro all'esterno del tuo dispositivo e protetti in caso di perdita. {{site.data.keyword.backup_full}} è un sistema di backup automatizzato basato su agent che viene gestito tramite l'utilità di gestione basata su browser del portale {{site.data.keyword.backup_notm}}. {{site.data.keyword.backup_notm}} fornisce agli utenti un metodo per eseguire il backup dei dati tra server in uno o più data center sulla rete {{site.data.keyword.BluSoftlayer_full}}. Gli amministratori possono impostare i backup in modo che seguano una pianificazione giornaliera, settimanale o personalizzata rivolta a sistemi completi, directory specifiche o persino singoli file. I plug-in aggiuntivi assicurano la compatibilità con software come Microsoft Exchange e Microsoft SQL, con altri tipi di software di terze parti e consentono agli utenti di completare un ripristino bare metal laddove necessario.

## Ordinazione di {{site.data.keyword.backup_notm}}

Puoi acquistare il servizio {{site.data.keyword.backup_notm}} in due modi.

- [Acquisto di backup quando ordini un server](#purchasing-ibm-cloud-backup-when-you-order-a-server).
- [Acquisto di backup come un upgrade](#purchasing-ibm-cloud-backup-as-an-upgrade).

Per ulteriori informazioni sui prezzi, vedi [{{site.data.keyword.backup_notm}} storage ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/cloud/backup-and-restore){:new_window} e [{{site.data.keyword.backup_notm}} on IBM Cloud ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/cloud/evault/pricing){:new_window}.

### Acquisto {{site.data.keyword.backup_notm}} quando ordini un server

1. Accedi al [catalogo IBM Cloud ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}/catalog/){:new_window} oppure al [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}
2. Ordina un server bare metal mensile. Per ulteriori informazioni sull'ordinazione di server bare metal, vedi [Creazione di un server bare metal personalizzato](https://{DomainName}/docs/bare-metal/baremetal-provision.html){:new_window}.
   1. Seleziona la quantità e l'opzione di fatturazione. Immetti i nomi di host e dominio. Puoi scegliere il nome host e dominio che preferisci.

      Il servizio {{site.data.keyword.backup_notm}} non è disponibile quando stai ordinando un server con fatturazione oraria. Tuttavia, il servizio può essere aggiunto successivamente come aggiornamento.
      {:tip}
   2. Seleziona l'ubicazione.
   3. Seleziona il tipo di configurazione del server e di immagine del sistema operativo. Puoi anche scegliere più componenti aggiuntivi.
   4. Nella sezione **Storage Disks**, fai clic su **Add-ons** e seleziona **{{site.data.keyword.backup_notm}}**. Scegli l'opzione che corrisponde a ciò di cui si ha bisogno.
   5. In **Interfaccia di rete**, seleziona Velocità porta di uplink e gli eventuali componenti aggiuntivi che desideri.
3. Sulla destra, riesamina il riepilogo del tuo ordine.
4. Dopo che hai riesaminato i termini e le condizioni, seleziona la casella **Ho letto e accetto gli accordi di servizio di terze parti**.
5. Fai clic su **Provisioning**. Vieni reindirizzato a una schermata con il tuo numero dell'ordine di provisioning. Puoi stampare la schermata in quanto è anche la tua ricevuta dell'ordine di provisioning.

   Puoi anche salvare questo ordine senza acquistare facendo clic su **Salva come preventivo**.
   {:tip}

Al tuo amministratore viene inviata una serie di e-mail relative alla conferma di ricezione dell'ordine di provisioning, all'approvazione ed elaborazione dell'ordine di Provisioning e al completamento del Provisioning. L'e-mail sul completamento del Provisioning include un collegamento alla tua pagina *Device Details* a cui puoi accedere dopo l'accesso a {{site.data.keyword.cloud_notm}}. Puoi anche accedere direttamente al {{site.data.keyword.slportal}}.

#### Conferma dell'acquisto di {{site.data.keyword.backup_notm}}
1. Nella [console {{site.data.keyword.cloud_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}/){:new_window}, fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**.</br>
   In alternativa, puoi accedere al [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Device** > **Device List**.
2. Individua il nuovo server che hai ordinato.
  - Se accanto all'URL vedi un'icona di orologio, devi aspettare per continuare con la conferma dell'acquisto di {{site.data.keyword.backup_notm}}. Puoi aggiornare la pagina per vedere uno stato aggiornato sul nuovo server. Quando l'icona di orologio non è più presente, puoi procedere con i passi successivi per confermare l'acquisto del servizio {{site.data.keyword.backup_notm}}.
  - Quando l'icona di orologio non viene più visualizzata per il tuo server, fai clic sul collegamento (l'URL del server) per accedere alla pagina **Device Details**.
3. Fai clic sulla scheda **Storage** per visualizzare le informazioni su {{site.data.keyword.backup_notm}}.
4. Esamina la sezione {{site.data.keyword.backup_notm}} e verifica che la dimensione che era stata selezionata durante il processo di acquisto sia visualizzata.

### Acquisto di {{site.data.keyword.backup_notm}} come un upgrade

#### Seleziona un server su cui installare {{site.data.keyword.backup_notm}}

1. Accedi alla console [{{site.data.keyword.cloud_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}){:new_window} e fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**.</br>
   In alternativa, puoi accedere al [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}.
2. Seleziona **Devices** > **Device List** dal menu principale. Trova il dispositivo per il quale desideri aggiungere il servizio di backup.
3. Fai clic sul nome dispositivo per andare alla pagina **Device Details**.

#### Aggiunta (acquisto) del servizio {{site.data.keyword.backup_notm}}
1. Fai clic sulla scheda **Storage** e scorri verso il basso per individuare la sezione {{site.data.keyword.backup_notm}}.
2. Fai clic sul collegamento **Add**.
3. Nella finestra, seleziona un'ubicazione e una dimensione.
4. Seleziona il tipo di pagamento e fai clic su **Continue**
5. Se ne hai uno, immetti il **Promo Code** e fai clic su **Recalculate**.
6. Controlla il tuo ordine e fai clic sul collegamento per leggere i termini e le condizioni.
7. Fai clic sulla casella di spunta se accetti i termini e le condizioni.
7. Fai clic su **Place Order**.

#### Conferma dell'acquisto dell'upgrade di {{site.data.keyword.backup_notm}}
1. Aggiorna la pagina **Device Details** e assicurati che sia selezionata la scheda **Storage**.
2. Esamina la sezione {{site.data.keyword.backup_notm}} e verifica che la dimensione che era stata selezionata durante il processo di acquisto sia visualizzata.

   Se la dimensione dell'archiviazione di backup continua a mostrare una capacità pari a zero, potrebbe essere necessario un secondo aggiornamento della pagina.
   {:tip}

## Accesso e visualizzazione dei dettagli dell'archiviazione di {{site.data.keyword.backup_notm}}

I dettagli dell'archiviazione del tuo servizio possono essere visualizzati nella [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/){:new_window} e nel {{site.data.keyword.slportal}} in qualsiasi momento. I dettagli che possono essere visualizzati includono la password, l'indirizzo di archiviazione e l'utilizzo associati al servizio {{site.data.keyword.backup_notm}} selezionato.

1. Accedi alla [console {{site.data.keyword.cloud_notm}}](https://{DomainName}){:new_window} e fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**.</br>
   In alternativa, puoi accedere al [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Storage** e seleziona **Backup** dall'elenco.
2. Fai clic in qualsiasi punto della riga dell'archivio per visualizzare i suoi dettagli di archiviazione. Da questa vista, la password non è visibile.
3. Fai clic sulla casella di spunta **Show** accanto al campo **Password** per visualizzare la password per il servizio {{site.data.keyword.backup_notm}} selezionato.

Le modifiche apportate alla password di {{site.data.keyword.backup_notm}} all'interno del {{site.data.keyword.slportal}} vengono apportate al servizio stesso. Per reimpostare la tua password, attieniti alla procedura in [Modifica della password per il servizio di backup](change-password.html).
{:important}

## Installazione dell'agent {{site.data.keyword.backup_notm}}

L'agent {{site.data.keyword.backup_notm}} è supportato sul seguente sistema operativo:

**Windows**
 - Windows Server 2016
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

**Linux**
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - RHEL 7.x
 - RHEL 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

Segui le istruzioni appropriate per il tuo sistema operativo,
- [Installazione del client Backup in Linux](install-backup-client-linux.html)
- [Installazione del client Backup in Windows](install-backup-client-windows.html)
- [Installazione del client Backup in Windows 2016](install-backup-client-windows2016.html)

## Accesso al portale {{site.data.keyword.backup_notm}} (in precedenza WebCC)

Il portale {{site.data.keyword.backup_notm}} viene utilizzato per interagire con qualsiasi servizio {{site.data.keyword.backup_notm}} offerto da {{site.data.keyword.BluSoftlayer_full}}. Il portale {{site.data.keyword.backup_notm}} è un client basato su browser eseguito sulla rete privata {{site.data.keyword.BluSoftlayer_full}} e consente il pieno controllo di qualsiasi servizio {{site.data.keyword.backup_notm}}, inclusi la configurazione e i ripristini.

1. Accedi alla rete privata tramite VPN.

   Non è possibile accedere al portale {{site.data.keyword.backup_notm}} sulla rete pubblica. Per prima cosa deve essere stabilita una connessione VPN.
   {:important}
2. Accedi alla schermata Backup storage nel [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}.
3. Fai clic dovunque nella riga del servizio {{site.data.keyword.backup_notm}} che vuoi vedere per espandere la vista.
4. Fai clic su **{{site.data.keyword.backup_notm}} portal Login** per avviare il client del portale nel tuo browser.

## Configurazione dell'agent Backup e della pianificazione del backup

Una volta che hai ordinato {{site.data.keyword.backup_notm}} e che l'agent è installato sul server, puoi iniziare a creare i backup dei tuoi dati. Segui questa procedura per configurare l'agent, la pianificazione della conservazione e avviare il tuo primo lavoro di backup.

1. Accedi al portale {{site.data.keyword.backup_notm}}.
2. Fai clic su **All Agents**> **Unconfigured Agents**.
3. Fai clic sul collegamento **This is a new Agent I would like to configure**. Passa attraverso il processo e immetti le seguenti informazioni:
   1. Agent configuration - fornisci la descrizione dell'agent e fai clic su **Next**.
   2. Job type selection - immetti il nome e la descrizione del lavoro e il tipo di origine del backup e fai clic su **Next**.
   3. Selection - seleziona le directory e fai clic su **Include...**
   4. Options - fornisci le password
   5. Schedule - fai clic su **Add** per creare una pianificazione e fai clic su **Next**.
   6. Seleziona l'archivio predefinito e fai clic su **OK**.
   7. Fai clic su **Save**.
4. Crea una pianificazione di conservazione.
   1. Seleziona **Edit** > **Agent Settings**.
   2. Fai clic su **Add**.
   3. Completa i tuoi dettagli di conservazione.
   4. Fai clic su **OK**.
   5. Fai clic su **Save**.

      Per ulteriori informazioni sugli schemi di conservazione, vedi le [Domande frequenti (FAQ)](faqs.html).
      {:tip}
5. Esegui l'agent e avvia un backup.
   1. Fai clic su **All Agents**, quindi seleziona l'agent che hai configurato.
   2. Fai clic su **Run Backup**.
   3. Conferma la destinazione e seleziona uno schema di conservazione.
   4. Fai clic su **Start Backup**. Puoi visualizzare i dettagli del backup mentre il processo è in esecuzione.
   5. Al termine del backup, fai clic su **Close**.

Per ulteriori informazioni, vedi [Configurazione di un semplice backup a livello di file su Linux](configure-simple-file-backup-linux.html).
{:tip}

## Come ottenere aiuto online

I sistemi del portale {{site.data.keyword.backup_notm}} sono completamente documentati e il supporto per l'applicazione è accessibile nel portale {{site.data.keyword.backup_notm}}. Fai clic sul punto interrogativo bianco in un cerchio blu che si trova in alto a destra per **Help**. Fai clic su qualsiasi articolo o argomento nella barra di navigazione sul lato sinistro per visualizzare ulteriori informazioni.
