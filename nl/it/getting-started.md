---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-28"

keywords: IBM Cloud backup, EVault, Carbonite, backup, getting started, setup, configure, run backup

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:shortdesc: .shortdesc}

# Esercitazione introduttiva
{: #getting-started}

I backup assicurano che i tuoi dati vengano memorizzati in modo sicuro all'esterno del tuo dispositivo e protetti in caso di perdita. {{site.data.keyword.backup_full}} è un sistema di backup automatizzato basato su agent che viene gestito tramite l'utilità di gestione basata su browser del portale {{site.data.keyword.backup_notm}}. {{site.data.keyword.backup_notm}} fornisce agli utenti un metodo per eseguire il backup dei dati tra server in uno o più data center sulla rete {{site.data.keyword.cloud}}. Gli amministratori possono impostare i backup in modo che seguano una pianificazione giornaliera, settimanale o personalizzata rivolta a sistemi completi, directory specifiche o persino singoli file. I plug-in aggiuntivi garantiscono la compatibilità con software come [Microsoft Exchange](/docs/infrastructure/Backup?topic=Backup-Exchangeplugin), [Microsoft SQL](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin), [Oracle](/docs/infrastructure/Backup?topic=Backup-Oracleplugin#Oracleplugin), [VMware vSphere](/docs/infrastructure/Backup?topic=Backup-VRA) e consentono agli utenti di completare un [Ripristino bare metal](/docs/infrastructure/Backup?topic=Backup-BMRplugin#BMRplugin), laddove necessario.
{:shortdesc}

## Prima di iniziare
{: #prereqs}

Devi avere una licenza valida per utilizzare IBM Cloud Backup. Puoi acquistare il servizio {{site.data.keyword.backup_notm}} in due modi.

- [Acquisto di backup quando ordini un server](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingwithserver).
- [Acquisto di backup come un upgrade](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingasupgrade).

Per ulteriori informazioni sull'ordinazione e i prezzi, consulta [Provisioning di {{site.data.keyword.backup_notm}}](/docs/infrastructure/Backup?topic=Backup-ordering).

## Installazione dell'agent {{site.data.keyword.backup_notm}}
{: #installagentgettingstarted}

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
- [Installazione del client Backup in Linux](/docs/infrastructure/Backup?topic=Backup-InstallinLinux)
- [Installazione del client Backup in Windows](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)

## Accesso al portale {{site.data.keyword.backup_notm}} (in precedenza WebCC)
{: #accessingWebCC}

Il portale {{site.data.keyword.backup_notm}} viene utilizzato per interagire con qualsiasi servizio {{site.data.keyword.backup_notm}} offerto da {{site.data.keyword.cloud}}. Il portale {{site.data.keyword.backup_notm}} è un client basato su browser eseguito sulla rete privata {{site.data.keyword.cloud}} e consente il pieno controllo di qualsiasi servizio {{site.data.keyword.backup_notm}}, inclusi la configurazione e i ripristini.

1. Accedi alla rete privata tramite VPN.

   Non è possibile accedere al portale {{site.data.keyword.backup_notm}} sulla rete pubblica. Per prima cosa deve essere stabilita una connessione VPN.
   {:important}
2. Accedi alla [console {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} e fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**.
2. Fai clic su **Storage** > **Backup** per visualizzare i server con i servizi di backup.
3. Seleziona il server in cui si trovano i file di cui eseguire il backup. Fai clic sulla freccia di espansione che punta a destra per visualizzare il link del portale {{site.data.keyword.backup_notm}}.
4. Fai clic su **{{site.data.keyword.backup_notm}} portal Login** per avviare il client del portale nel tuo browser.

## Configurazione dell'agent Backup e della pianificazione del backup
{: #configureagentschedule}

Una volta che hai ordinato {{site.data.keyword.backup_notm}} e che l'agent è installato sul server, puoi iniziare a creare i backup dei tuoi dati. Segui questa procedura per configurare l'agent e la pianificazione della conservazione.

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

      Per ulteriori informazioni sugli schemi di conservazione, vedi le [Domande frequenti (FAQ)](/docs/infrastructure/Backup?topic=Backup-faqs#faqs).
      {:tip}

      L'archiviazione non è supportata. Quando crei uno schema di conservazione o modifichi uno schema esistente, assicurati che l'opzione di archiviazione (Archiving) **non** sia selezionata.
      {:important}

## Esecuzione del tuo primo lavoro di backup
{: #runfirstbackup}

1. Accedi al portale {{site.data.keyword.backup_notm}}.
2. Fai clic su **All Agents**, quindi seleziona l'agent che hai configurato.
3. Fai clic su **Run Backup**.
4. Conferma la destinazione e seleziona uno schema di conservazione.
5. Fai clic su **Start Backup**. Puoi visualizzare i dettagli del backup mentre il processo è in esecuzione.
6. Al termine del backup, fai clic su **Close**.

Per ulteriori informazioni, vedi [Configurazione di un semplice backup a livello di file su Linux](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup).
{:tip}

## Accesso e visualizzazione dei dettagli dell'archiviazione di {{site.data.keyword.backup_notm}} nella console
{: #viewingdetailsinconsole}

I dettagli dell'archiviazione del tuo servizio possono essere visualizzati nella [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/classic/storage/backup){: external} in qualsiasi momento. I dettagli che possono essere visualizzati includono la password, l'indirizzo di archiviazione e l'utilizzo associati al servizio {{site.data.keyword.backup_notm}} selezionato.

1. Accedi alla [console {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} e fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**.
2. Fai clic su **Storage** e seleziona **Backup** dall'elenco.
2. Fai clic in qualsiasi punto della riga dell'archivio per visualizzare i suoi dettagli di archiviazione. Da questa vista, la password non è visibile.
3. Fai clic sulla casella di spunta **Show** accanto al campo **Password** per visualizzare la password per il servizio {{site.data.keyword.backup_notm}} selezionato.

Le modifiche apportate alla password di {{site.data.keyword.backup_notm}} all'interno della console {{site.data.keyword.cloud_notm}} vengono apportate al servizio stesso. Per reimpostare la tua password, attieniti alla procedura in [Modifica della password per il servizio di backup](/docs/infrastructure/Backup?topic=Backup-changePassword).
{:important}

## Come ottenere ulteriore aiuto online
{: #onlinehelp}

I sistemi del portale {{site.data.keyword.backup_notm}} sono completamente documentati e il supporto per l'applicazione è accessibile nel portale {{site.data.keyword.backup_notm}}. Fai clic sul punto interrogativo bianco in un cerchio blu che si trova in alto a destra per **Help**. Fai clic su qualsiasi articolo o argomento nella barra di navigazione sul lato sinistro per visualizzare ulteriori informazioni.
