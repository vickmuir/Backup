---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# Installazione del plug-in SQL Server per EVault

Il plug-in SQL Server viene installato con l'agent Windows sull'host del database SQL. Tramite il portale WebCC puoi configurare i lavori, eseguire il backup dei database SQL in un archivio remoto protetto e ripristinare i database SQL.

**Capacità fornite**

- Puoi eseguire backup di database completi, backup di database completi con i log di transazioni o backup dei soli log di transazioni.
- Puoi eseguire più backup contemporaneamente. 
- Puoi ripristinare i database SQL nella stessa istanza SQL o in un'istanza SQL diversa.
- Puoi ripristinare i database con i nomi database originali, sovrascrivere i database esistenti e ripristinare utilizzando l'opzione No Recovery.

## Ordine del plugin

1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Fai clic su **Storage** > **Backup**.
3. Seleziona il tuo account EVault e fai clic su **Order plug-ins**.
4. Seleziona **EVault plug-in - MSSQL** e fai clic su **Continue**.
5. Se ne hai uno, immetti il tuo codice promozionale e fai clic su **Recalculate**.
6. Vengono visualizzati i costi aggiornati. Riesamina l'ordine.
7. Seleziona la casella per indicare che hai letto e accettato gli accordi di servizio di terze parti. 
8. Fai clic su **Place Order**.

## Installazione del plug-in MSSQL

Per installare il plug-in SQL per Windows, esegui il kit di installazione dell'agent. Il plug-in viene visualizzato come opzione nella pagina **Custom Setup**.

**Nota**: prima di installare il plug-in MSSQL EVault per il tuo server Microsoft Windows, arresta entrambi i servizi EVault in `services.msc`.  

1. Passa alla cartella `c:\installs\evault` ed esegui il file .exe con il numero di revisione maggiore.
2. Nella schermata della lingua, fai clic su **OK**.
3. Nella schermata di benvenuto, fai clic su **Next**.
4. Seleziona **Modify installation** e fai clic su **Next**.
5. Seleziona **Leave Unchanged** e fai clic su **Next**.
6. Nella schermata di configurazione personalizzata, seleziona ciascun plug-in che hai acquistato.
7. Seleziona **This feature will be installed on ...** e fai clic su **Next**.
8. Seleziona **Keep my current registration** e fai clic su **Next**.
9. Fai clic su **Install**.
10. Una volta installato, verifica che entrambi i servizi siano abilitati e in esecuzione.
11. Se WebCC è in grado di accedere/visualizzare il database, l'installazione ha avuto esito positivo. 

## Download della guida utente

Connettiti alla rete {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} per poter scaricare la guida EVault Agent for Microsoft Windows v8.0 - SQL Server plug-in Guide.pdf da [Downloadable EVault Documentation](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.

## Domande Frequenti (FAQ)

**A cosa serve VSS (Volume Shadow Copy Services)?**

La versione corrente del plug-in SQL Server utilizza VSS (Volume Shadow Copy Services) per completare i backup. Utilizzando VSS, il plug-in SQL Server esegue efficacemente il backup dei database SQL, anche dei database SQL che si estendono sui volumi. I backup possono essere completati mentre le applicazioni continuano a scrivere in un volume. Il plug-in SQL Server fornisce la congruenza dei dati all'interno e tra i database. VSS consente di eseguire più backup contemporaneamente.

**Quali sono le funzioni principali del plug-in SQL?**

- Possibilità di specificare i nomi dei database da includere ed escludere nei lavori di backup di SQL Server utilizzando caratteri jolly (asterischi e punti interrogativi). I nuovi database con nomi corrispondenti ai filtri di un lavoro di backup vengono automaticamente inclusi o esclusi durante l'esecuzione del lavoro. 
- Possibilità di proteggere i database secondari nei gruppi di disponibilità AlwaysOn utilizzando l'agent a 64 bit e il plug-in SQL Server.
- Possibilità di condividere i set sicuri SQL che includono database che contiene SharePoint 2010/2013 da utilizzare con l'applicazione Granular Restore per Microsoft SharePoint. Una volta condiviso un set sicuro, l'applicazione Granular Restore può essere utilizzata per ripristinare raccolte di siti, siti web, elenchi, librerie, cartelle, voci di elenco o documenti.
- Supporto per il backup Delta di database su volumi con spanning.
- Possibilità di proteggere i database nel modello di recupero completo con una singola voce di pianificazione. Questa opzione consente di proteggere i database e di gestire il troncamento dei log di transazioni in un'unica voce di pianificazione.
- Il plug-in SQL Server supporta backup completi, backup completi con i log di transazioni inclusi e backup dei log di transazioni (terminologia aggiornata per allinearla con la terminologia di SQL Server). EVault continua a supportare la funzione di ripristino single pass che consente al cliente di selezionare un backup dei “log di transazioni” in un determinato momento. EVault ripristina il database completo e tutti i log di transazioni necessari per ripristinare il database al momento selezionato.
- Un lavoro di backup può contenere uno o più database dalla stessa singola istanza di SQL Server. È possibile creare un lavoro separato per eseguire il backup di altri database da un'istanza di SQL Server diversa che, se lo si desidera, può essere eseguito contemporaneamente.
- Possibilità di ripristinare i database con l'opzione "No Recovery" per fornire ulteriori opzioni di ripristino tramite SQL Server Management Studio.
- L'opzione di ripristino alternativo supporta il ripristino nei file, che consente all'amministratore del database di montare i database tramite SQL System Manager.
- Il ripristino alternativo include la possibilità di indirizzare il ripristino di un database in un altro anche quando i nomi dei database logici non corrispondono. Per gli oggetti non corrispondenti, il plug-in crea i database nell'ubicazione database predefinita per l'istanza.
- Supporto per Transparent Data Encryption (TDE) con SQL Server 2008 R2 (SP1) e SQL Server 2012 a 64 bit.
- Se un host di SQL Server viene perso, è possibile installare il software SQL Server e ripristinare il database. (Il database principale deve essere ripristinato per primo.)
- Una volta avviato, il backup si verifica con o senza i servizi di database in esecuzione.
- Sono supportati i ripristini ai nomi di database originali (con o senza sovrascrittura di database esistenti), i ripristini su un database esistente o nei file su disco.

