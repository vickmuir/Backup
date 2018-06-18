---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# Installazione del plug-in EVault Bare Metal Restore

EVault BMR è una soluzione di ripristino di emergenza per Microsoft Windows che ti consente di ripristinare completamente il tuo server da uno stato bare metal quando si verifica un'emergenza, ad esempio un errore del sistema operativo o un guasto hardware. Questo sistema ti consente di ripristinare rapidamente l'immagine del sistema da una posizione sicura e protetta gestita da {{site.data.keyword.BluSoftlayer_full}}.

**Note**: BMR è un prodotto solo per Microsoft Windows sui server fisici. Non è disponibile per i server virtuali. I ripristini bare metal per le distribuzioni Linux non sono supportati. BMR è supportato solo da EVault Agent 8.30 o versioni precedenti. (30 giungo 2018).

## Capacità fornite

- Ripristina il tuo sistema in un momento specifico.
- Ripristina il tuo sistema da backup di immagini o file.
- Ripristina il tuo sistema dai backup che sono memorizzati su EVault.
- Una transazione di ripristino avviabile che ti consentirà di ripristinare i tuoi dati senza un sistema di avvio.

## Ordina il plug-in

1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Storage** > **Backup**.
3. Seleziona il tuo account EVault e fai clic su **Order Plugins**.
4. Seleziona **EVault Plugin - BMR (Bare Metal Restore)** e fai clic su **Continue**.
5. Se ne hai uno, immetti il tuo codice promozionale e fai clic su **Recalculate**.
6. Vengono visualizzati i costi aggiornati. Riesamina l'ordine.
7. Seleziona le caselle per indicare che hai letto l'accordo di servizio principale e accetti i termini del software di terze parti. 
8. Fai clic su **Place Order**.

## Guida per l'utente

Connettiti alla rete {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} per poter scaricare la guida EVault System Restore v8.3 - User Guide.pdf da [Downloadable EVault Documentation](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.

## Domande frequenti

### Posso migrare da un singolo disco a un array RAID?

Sì, funzionerà. Tuttavia, devi selezionare un dispositivo di grande capacità a causa della diminuzione delle dimensioni causata dall'array RAID.

### Cosa succede se ripristino l'immagine su un disco più grande del volume originale?

Se ripristini l'immagine su un disco più grande del volume originale, lo spazio restante viene deallocato. Quindi, se ad esempio hai un'unità da 500 GB e ripristini i suoi dati su un disco da 1 TB, ci saranno 500 GB di spazio su disco deallocato. Con Windows 2008, puoi utilizzare il programma di utilità del disco nativo per aumentare la partizione primaria. Tuttavia, in Windows 2003 non esiste una funzionalità nativa per questo, quindi è consigliabile allocare lo spazio.

### Posso usare BMR per il mio regolare backup?

Non si tratta di un'immagine del disco, ma di un sistema di backup dell'immagine del volume di sistema. Questo sistema non è destinato a essere utilizzato per backup regolari, ma insieme a essi.  

### Posso usare BMR per i miei backup del database?

I backup del database devono essere eseguiti separatamente con i normali metodi di backup di EVault. BMR non sostituisce la necessità di plug-in SQL o Oracle. Sebbene BMR utilizzi la tecnologia VSS per eseguire il backup di file aperti, non possiamo sempre garantire che i file di backup siano coerenti con le transazioni. Il nostro consiglio per questi tipi di applicazioni specializzate è la creazione di due lavori di backup: uno per il backup del sistema operativo e dei file binari dell'applicazione e un altro per i dati dell'applicazione. È disponibile una nota al riguardo alla fine della guida utente BMR.

### Che tipo di lavori di ripristino posso eseguire con BMR?

Puoi eseguire un ripristino dell'intero sistema oppure selezionare singoli file dal backup da ripristinare. Ciò significa che questo lavoro può sostituire il lavoro di backup dei file corrente. Il processo di ripristino può essere eseguito all'interno del sistema operativo, proprio come un lavoro di backup tradizionale.

### BMR ha capacità di backup dei file aperti?

BMR ha capacità di backup dei file aperti. Tuttavia, BMR non sostituisce la necessità di plug-in SQL o Oracle. Fai clic [qui](evault-mssql-plugin-installation.html) per le istruzioni di installazione del plug-in MSSQL.

### Quanto spazio su disco e tempo sono necessari per un ripristino BMR?

Un backup eseguito da un'installazione predefinita utilizzerà circa 6 GB. Tale ripristino richiede circa 15 minuti su una porta da 1 GB. Questo processo è influenzato anche dalla velocità della porta privata. Se hai bisogno di backup/ripristini più veloci, potrebbe essere necessario un aumento della velocità della porta.
