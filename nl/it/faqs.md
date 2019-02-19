---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:faq: data-hd-content-type='faq'}


# Domande frequenti
{: #faqs}

## Di quali tipi di applicazioni posso eseguire il backup?
{: faq}

{{site.data.keyword.backup_full}} può essere utilizzato per eseguire il backup di diverse applicazioni. {{site.data.keyword.BluSoftlayer_full}} offre anche agent software per alcuni dei più comuni sistemi software che vengono sottoposti a backup, che includono

- Bare Metal Restore
- Microsoft Exchange
- Microsoft SQL
- Oracle

I plug-in qui elencati sono compatibili solo con i server Windows, fatta eccezione per il plug-in Oracle. Ogni agent è disponibile come componente aggiuntivo per il tuo servizio di backup. Per aggiungere un agent al tuo servizio, contatta un membro del team di vendita oggi stesso.

<hr>

## Con quale frequenza possiamo eseguire il backup dei dati?
{: faq}

All'interno del portale {{site.data.keyword.backup_notm}}, i backup possono essere eseguiti manualmente oppure possono essere pianificati come una singola istanza o per essere ricorrenti. I backup ricorrenti possono essere effettuati giornalmente, settimanalmente, mensilmente o in base a una pianificazione personalizzata e possono essere aggiornati o annullati in qualsiasi momento.

I backup molto frequenti eseguiti più volte al giorno o ogni ora possono causare il danneggiamento dei lavori di backup. Questo danneggiamento si verifica perché l'archivio di backup non ha abbastanza tempo per eseguire le attività di manutenzione di background richieste. I lavori di backup hanno la precedenza sulle attività di manutenzione. Quindi, quando i backup vengono eseguiti con un'elevata frequenza, l'archivio continua a eseguire i lavori di backup e causare la crescita del numero di set sicuri.
{:note}

<hr>

## Come funzionano gli schemi di conservazione?
{: faq}

{{site.data.keyword.backup_notm}} consente la conservazione dei dati a seconda del lasso di tempo a cui vuoi far risalire il rollback. Gli schemi di conservazione **giornalieri** mantengono i dati per sette giorni, mentre gli schemi **settimanali** mantengono i dati per un mese e gli schemi **mensili** li mantengono un anno. Al termine di ciascun periodo, il dataset più vecchio viene ruotato e il primo "backup delta" realizzato diventa il più vecchio punto di ripristino disponibile.

Puoi modificare gli schemi di conservazione predefiniti e puoi creare degli schemi di conservazione personalizzati. Tuttavia, IBM ti consiglia di utilizzare le conservazioni predefinite come punto di partenza. Quando crei un nuovo schema di conservazione o modifichi una conservazione esistente, assicurati che l'opzione di archiviazione (Archiving) non sia selezionata. L'archiviazione non è supportata.
{:tip}

<hr>

## Cos'è la tecnologia delta?
{: faq}

Il primo backup è un "seed" (un backup completo), quelli successivi sono "delta" (ossia, solo modifiche), ma equivalgono a un "backup completo" e sono ancora considerati come tale. Vale a dire, sei in grado di ripristinare da esso tutti o alcuni file. Con questa tecnologia, vengono creati dei "backup completi" a ogni sessione, ma si risparmiano enormi quantità di spazio nell'archivio e si riduce il tempo necessario per il completamento di ogni backup successivo.

<hr>

## I backup sono protetti?
{: faq}

Per impostazione predefinita, tutta la crittografia trasmessa è codificata con la crittografia AES a 256 bit. Puoi anche scegliere di memorizzare i dati nel formato crittografato
con AES a 256 bit.

Devi ricordarti la tua password di crittografia. Non è possibile ripristinare i tuoi dati senza la password. Se perdi la tua password non puoi recuperare i tuoi dati.
{:important}

I rapporti di compressione consentono una compressione da zero a un rapporto massimo che, a seconda del tipo file, potrebbe comprimere dal 20 al 30 per cento.

<hr>

## Quali informazioni vengono memorizzate con i backup dello stato del sistema?
{: faq}

I backup dello stato del sistema includono il database di registrazione della classe COM +, il registro, i file di avvio, i file di sistema, il contatore delle prestazioni e altro ancora. Tutti dipendono dal tuo sistema. I file di sistema variano a seconda del sistema operativo e dei service pack del sistema. Di solito ce ne sono diverse migliaia. MS Windows crea un elenco dinamico di queste DLL quando le includi nel backup. Includendo i file di sistema, puoi eseguire il ripristino in caso di file di sistema danneggiati o se rimuovi casualmente alcuni service pack oppure se vuoi eseguire il recupero utilizzando un ripristino bare metal. Puoi tornare allo stato del backup senza dover reinstallare il sistema operativo dal kit di installazione e quindi installare ciascun service pack separatamente.

Nessun file di dati utente è incluso nel backup dello stato del sistema. Un lavoro di backup dello stato del sistema deve essere configurato come lavoro autonomo. Non deve essere presente alcuna altra origine dati inclusa nel lavoro di backup dello stato del sistema
{:important}

<hr>

## Cosa accade ai file aperti?
{: faq}

Per impostazione predefinita, il client di base ha una tecnologia all'avanguardia per gestire la maggior parte dei file aperti in esecuzione sul sistema operativo.

<hr>

## Dove posso trovare le informazioni sui prezzi?
{: faq}

Per ulteriori informazioni, vedi [Backup storage ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/cloud/backup-and-restore){:new_window} e [EVault on IBM Cloud: Pricing ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/cloud/evault/pricing){:new_window}.

<hr>

## È possibile incrementare/decrementare la capacità di {{site.data.keyword.backup_full}} senza compromettere i backup?
{: faq}

Puoi aumentare o diminuire la dimensione del tuo archivio tramite il [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}. La modifica della capacità non influisce sull'integrità dei dati memorizzati nell'archivio. Per ulteriori informazioni, vedi [Espansione della capacità](expanding-capacity.html).

<hr>

## Cosa succede quando viene superata la capacità di {{site.data.keyword.backup_notm}}?
{: faq}

Puoi ancora salvare e richiamare i tuoi backup anche se hai raggiunto il limite della capacità che hai acquistato precedentemente. Tuttavia, riceverai un addebito supplementare per ogni GB aggiuntivo che è stato usato nel prossimo estratto conto.

<hr>

## Come posso configurare le notifiche nel portale {{site.data.keyword.backup_notm}} per essere informato se i miei backup non riescono?
{: faq}

Le notifiche possono essere configurate nella scheda Advanced. Attieniti alle istruzioni che puoi trovare in **Quick Links** nel portale {{site.data.keyword.backup_notm}}.

<hr>

## Quando usiamo il plug-in BMR, possiamo passare da un singolo disco ad un array raid?

Sì, funziona. Tuttavia, devi selezionare un dispositivo di grande capacità a causa della diminuzione delle dimensioni causata dall'array RAID.

<hr>

## Quando usiamo il plug-in BMR, cosa succede quando l'immagine viene ripristinata su un disco più grande rispetto al volume originale?
{: faq}

Se ripristini l'immagine su un disco più grande del volume originale, lo spazio restante viene deallocato. Quindi, se hai un'unità da 500-GB e ripristini i suoi dati su un disco da 1-TB, ci saranno 500 GB di spazio su disco deallocato. Con Windows 2008, puoi utilizzare il programma di utilità del disco integrato per aumentare la partizione primaria. Tuttavia, Windows 2003 non ha alcuna funzionalità integrata simile, quindi devi assegnare lo spazio in un altro modo.

<hr>

## È possibile utilizzare BMR per il backup regolare?
{: faq}

Il backup BMR non è un'immagine del disco, ma un sistema di backup dell'immagine del volume di sistema. Il sistema non è destinato a essere utilizzato per backup regolari, ma insieme a essi.  

<hr>

##È possibile utilizzare BMR per i backup del database?
{: faq}

I backup del database devono essere eseguiti separatamente con i normali metodi di {{site.data.keyword.backup_notm}} BMR non sostituisce la necessità di plug-in SQL o Oracle. Sebbene BMR utilizzi la tecnologia VSS per eseguire il backup di file aperti, non può sempre garantire che i file di backup siano coerenti con le transazioni. Il consiglio per questi tipi di applicazioni specializzate è la creazione di due lavori di backup: uno per il backup del sistema operativo e dei file binari dell'applicazione e un altro per i dati dell'applicazione.

<hr>

## Che tipo di lavori di ripristino è possibile eseguire con BMR?

Puoi eseguire un ripristino dell'intero sistema oppure selezionare singoli file dal backup da ripristinare. Il lavoro di backup BMR può sostituire il lavoro di backup dei file corrente. Il processo di ripristino viene eseguito all'interno del sistema operativo, proprio come un lavoro di backup tradizionale.

<hr>

## BMR ha capacità di backup dei file aperti?
{: faq}

BMR ha capacità di backup dei file aperti. Tuttavia, BMR non sostituisce la necessità di plug-in SQL o Oracle. Fai clic [qui](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin) per le istruzioni di installazione del plug-in MSSQL.

<hr>

## Quanto spazio su disco e tempo sono necessari per un ripristino BMR?
{: faq}

Un backup effettuato da un'installazione predefinita utilizza circa 6 GB. Tale ripristino richiede circa 15 minuti su una porta da 1-GB. Questo processo è influenzato anche dalla velocità della porta privata. Se hai bisogno di backup e ripristini più veloci, potrebbe essere necessario un aumento della velocità della porta.

<hr>

## A cosa serve VSS (Volume Shadow Copy Services)?
{: faq}

La versione corrente del plug-in SQL Server utilizza VSS (Volume Shadow Copy Services) per completare i backup. Utilizzando VSS, il plug-in SQL Server esegue efficacemente il backup dei database SQL, anche dei database SQL che si estendono sui volumi. I backup possono essere completati mentre le applicazioni continuano a scrivere in un volume. Il plug-in SQL Server fornisce la congruenza dei dati all'interno e tra i database. VSS consente di eseguire più backup contemporaneamente.
