---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Installazione del plug-in SQL Server
{: #MSSQLplugin}

Il plug-in SQL Server viene installato con l'agent Windows sull'host del database SQL. Tramite il portale {{site.data.keyword.backup_notm}}, puoi configurare i lavori, eseguire il backup dei database SQL in un archivio remoto protetto e ripristinare i database SQL.

**Capacità fornite**

- Puoi eseguire backup di database completi, backup di database completi con i log di transazioni o backup dei soli log di transazioni.
- Puoi eseguire più backup contemporaneamente.
- Puoi ripristinare i database SQL nella stessa istanza SQL o in un'istanza SQL diversa.
- Puoi ripristinare i database con i nomi database originali, sovrascrivere i database esistenti e ripristinare utilizzando l'opzione No Recovery.

Per ulteriori informazioni, vedi la sezione [Funzioni principali](#main-features).

## Ordinazione del plug-in
{: #orderingSQLPlugin}

1. Accedi alla [console {{site.data.keyword.cloud_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}){:new_window} e fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**.<br/>
   In alternativa, puoi accedere al [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Storage** > **Backup** per visualizzare i server con un servizio di backup.
3. Seleziona il tuo account e fai clic su **Order plug-ins**.
4. Seleziona **{{site.data.keyword.backup_notm}} plug-in - MSSQL** e fai clic su **Continue**.
5. Se ne hai uno, immetti il tuo codice promozionale e fai clic su **Recalculate**.
6. Vengono visualizzati i costi aggiornati. Riesamina l'ordine.
7. Seleziona la casella per indicare che hai letto e accettato gli accordi di servizio di terze parti.
8. Fai clic su **Place Order**.

## Installazione del plug-in MSSQL
{: #installSQLPlugin}

Per installare il plug-in, esegui il kit di installazione dell'agent. Il plug-in viene visualizzato come opzione nella pagina **Custom Setup**.

Prima di installare il plug-in MSSQL per il tuo server Microsoft Windows, arresta entrambi i servizi {{site.data.keyword.backup_notm}} in `services.msc`.
{:tip}

1. Passa alla cartella `c:\installs\evault` ed esegui il file .exe con il numero di revisione più alto.
2. Nella schermata della lingua, fai clic su **OK**.
3. Nella schermata di benvenuto, fai clic su **Next**.
4. Seleziona **Modify installation** e fai clic su **Next**.
5. Seleziona **Leave Unchanged** e fai clic su **Next**.
6. Nella schermata di configurazione personalizzata, seleziona ciascun plug-in che hai acquistato.
7. Seleziona **This feature will be installed on ...** e fai clic su **Next**.
8. Seleziona **Keep my current registration** e fai clic su **Next**.
9. Fai clic su **Install**.
10. Una volta installato, verifica che entrambi i servizi siano abilitati e in esecuzione.
11. Se il portale {{site.data.keyword.backup_notm}} è in grado di accedere al database, l'installazione ha avuto esito positivo.

## Download della guida utente
{: #SQLUserGuide}

Connettiti alla rete {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} in modo da poter scaricare la guida utente dalla [documentazione di {{site.data.keyword.backup_notm}} scaricabile ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}

## Funzioni principali
{: #main-features}

- Possibilità di specificare i nomi dei database da includere ed escludere nei lavori di backup di SQL Server utilizzando caratteri jolly (asterischi e punti interrogativi). I nuovi database con nomi corrispondenti ai filtri di un lavoro di backup vengono automaticamente inclusi o esclusi durante l'esecuzione del lavoro.
- Possibilità di proteggere i database secondari nei gruppi di disponibilità AlwaysOn utilizzando l'agent a 64 bit e il plug-in SQL Server.
- Possibilità di condividere i set sicuri SQL che includono database che contiene SharePoint 2010/2013 da utilizzare con l'applicazione Granular Restore per Microsoft SharePoint. Una volta condiviso un set sicuro, l'applicazione Granular Restore può essere utilizzata per ripristinare raccolte di siti, siti web, elenchi, librerie, cartelle, voci di elenco o documenti.
- Supporto per il backup Delta di database su volumi con spanning.
- Possibilità di proteggere i database nel modello di recupero completo con una singola voce di pianificazione. Questa opzione consente di proteggere i database e di gestire il troncamento dei log di transazioni in un'unica voce di pianificazione.
- Il plug-in SQL Server supporta backup completi, backup completi con i log di transazioni inclusi e backup dei log di transazioni (terminologia aggiornata per allinearla con la terminologia di SQL Server). L'applicazione continua a supportare la funzione di ripristino single pass che consente al cliente di selezionare un backup dei “log di transazioni” a un determinato momento. {{site.data.keyword.backup_notm}} ripristina il database completo e tutti i log di transazioni necessari per ripristinare il database al momento selezionato.
- Un lavoro di backup può contenere uno o più database dalla stessa singola istanza di SQL Server. È possibile creare un lavoro separato per eseguire il backup di altri database da un'istanza di SQL Server diversa che, se lo si desidera, può essere eseguito contemporaneamente.
- Possibilità di ripristinare i database con l'opzione "No Recovery" per fornire ulteriori opzioni di ripristino tramite SQL Server Management Studio.
- L'opzione di ripristino alternativo supporta il ripristino nei file, che consente all'amministratore del database di montare i database tramite SQL System Manager.
- Il ripristino alternativo include la possibilità di indirizzare il ripristino di un database in un altro anche quando i nomi dei database logici non corrispondono. Per gli oggetti non corrispondenti, il plug-in crea i database nell'ubicazione database predefinita per l'istanza.
- Supporto per Transparent Data Encryption (TDE) con SQL Server 2008 R2 (SP1) e SQL Server 2012 a 64 bit.
- Se un host di SQL Server viene perso, è possibile installare il software SQL Server e ripristinare il database. (Il database principale deve essere ripristinato per primo.)
- Una volta avviato, il backup si verifica con o senza i servizi di database in esecuzione.
- Sono supportati i ripristini ai nomi di database originali (con o senza sovrascrittura di database esistenti), i ripristini su un database esistente o nei file su disco.
