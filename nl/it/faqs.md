---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:faq: data-hd-content-type='faq'}


# Domande frequenti

## Di quali tipi di applicazioni posso eseguire il backup?
{: faq}

{{site.data.keyword.backup_full}} può essere utilizzato per eseguire il backup di diverse applicazioni. Tuttavia, {{site.data.keyword.BluSoftlayer_full}} offre agent software per alcuni dei più comuni sistemi software che vengono sottoposti a backup, che includono:

- Ripristino Bare Metal
- Microsoft Exchange
- Microsoft SQL
- Oracle

I plug-in qui elencati sono compatibili solo con i server Windows, fatta eccezione per il plug-in Oracle. Ogni agent è disponibile come componente aggiuntivo per il tuo servizio di backup. Per aggiungere un agent al tuo servizio, contatta un membro del team di vendita oggi stesso.

<hr>

## Con quale frequenza è possibile eseguire il backup dei dati?
{: faq}

All'interno di WebCC, i backup possono essere eseguiti manualmente oppure possono essere pianificati come una singola istanza o per essere ricorrenti. I backup ricorrenti possono essere effettuati giornalmente, settimanalmente, mensilmente o in base a una pianificazione personalizzata e possono essere aggiornati o annullati in qualsiasi momento.

I backup molto frequenti eseguiti più volte al giorno o ogni ora possono causare il danneggiamento dei lavori di backup. Questo danneggiamento si verifica perché l'archivio di backup non ha abbastanza tempo per eseguire le attività di manutenzione di background richieste. I lavori di backup hanno la precedenza sulle attività di manutenzione. Quindi, in caso di backup molto frequenti, l'archivio continua a eseguire i lavori di backup e causare la crescita del numero di set sicuri.
{:note}

<hr>

## Come funzionano gli schemi di conservazione?
{: faq}

{{site.data.keyword.backup_notm}} consente la conservazione dei dati a seconda del lasso di tempo a cui vuoi far risalire il rollback. Gli schemi di conservazione **giornalieri** mantengono i dati per sette giorni, mentre gli schemi **settimanali** mantengono i dati per un mese e gli schemi **mensili** li mantengono un anno. Al termine di ciascun periodo, il dataset più vecchio viene ruotato e il primo "backup delta" realizzato diventa il più vecchio punto di ripristino disponibile.

Puoi modificare gli schemi di conservazione predefiniti e puoi creare degli schemi di conservazione personalizzati. Tuttavia, consigliamo vivamente di utilizzare le conservazioni predefinite come punto di partenza. Quando crei un nuovo schema di conservazione o modifichi una conservazione esistente, assicurati che l'opzione di archiviazione (Archiving) non sia selezionata. L'archiviazione non è supportata.
{:tip}

<hr>

## Cos'è la tecnologia delta?
{: faq}

Il primo backup è un "seed" (un backup completo), quelli successivi sono "delta" (ossia, solo modifiche), ma equivalgono a un "backup completo" e sono ancora considerati come tale. Vale a dire, sei in grado di ripristinare da esso tutti o alcuni file. Questa tecnologia consente di eseguire "backup completi" in ogni sessione, ma risparmia enormi quantità di spazio sull'archivio e riduce il tempo necessario per il completamento di ogni backup successivo.

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

I backup dello stato del sistema includono il database di registrazione della classe COM +, il registro, i file di avvio, i file di sistema, il contatore delle prestazioni e altro ancora. Tutti dipendono dal tuo sistema. I file di sistema variano a seconda del sistema operativo e dei service pack del sistema. Di solito ce ne sono diverse migliaia. MS Windows crea un elenco dinamico di queste DLL quando le includi nel backup. Includendo i file di sistema, puoi eseguire il ripristino in caso di file di sistema danneggiati o se disinstalli casualmente alcuni service pack oppure se vuoi utilizzare un ripristino bare metal. Puoi tornare allo stato del backup senza dover reinstallare il sistema operativo dal kit di installazione e quindi installare ciascun service pack separatamente.

Nessun file di dati utente è incluso nel backup dello stato del sistema. Un lavoro di backup dello stato del sistema deve essere configurato come lavoro autonomo. Non deve essere presente alcuna altra origine dati inclusa nel lavoro di backup dello stato del sistema
{:important}

<hr>

## Cosa accade ai file aperti?
{: faq}

Per impostazione predefinita, il client di base ha una tecnologia all'avanguardia per gestire la maggior parte dei file aperti in esecuzione sul sistema operativo.

<hr>

## Dove posso trovare le informazioni sui prezzi?
{: faq}

Per ulteriori informazioni, consulta [Backup storage](https://www.ibm.com/cloud/backup-and-restore){:new_window} e [{{site.data.keyword.backup_notm}} on IBM Cloud: Pricing](https://www.ibm.com/cloud/evault/pricing){:new_window}.

<hr>

## È possibile incrementare/decrementare la capacità di {{site.data.keyword.backup_notm}} senza compromettere i backup?
{: faq}

Puoi aumentare o diminuire la dimensione del tuo archivio tramite il [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}. La modifica della capacità non influisce sull'integrità dei dati memorizzati nell'archivio. Per ulteriori informazioni, vedi [Espansione della capacità](expanding-capacity.html).

<hr>

## Cosa succede quando viene superata la capacità di {{site.data.keyword.backup_notm}}?
{: faq}

Puoi ancora salvare e richiamare i tuoi backup anche se hai raggiunto il limite della capacità che hai acquistato precedentemente. Nota: nell'estratto conto sarà presente un addebito supplementare per ogni GB aggiuntivo utilizzato.

<hr>

## Come posso configurare le notifiche in WebCC per essere informato se i miei backup non riescono?
{: faq}

Le notifiche possono essere configurate nella scheda Advanced. Attieniti alle istruzioni che puoi trovare in **Quick Links** in WebCC.
