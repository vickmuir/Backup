---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-18"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# EVault Backup - Domande frequenti

## Di quali tipi di applicazioni posso eseguire il backup con EVault?

EVault consente il backup di varie applicazioni. Tuttavia, {{site.data.keyword.BluSoftlayer_full}} offre agent software per alcuni dei più comuni sistemi software che vengono sottoposti a backup, che includono:

- Ripristino Bare Metal
- Microsoft SQL
- Oracle

Ogni agent è disponibile come componente aggiuntivo per il tuo servizio EVault Backup. Per aggiungere un agent al tuo servizio, contatta oggi un membro del nostro team di vendita. Nota che i plug-in qui elencati sono compatibili solo con i server Windows.

## Con che frequenza posso eseguire il backup dei miei dati con EVault Backup?

Puoi eseguire il backup dei dati tutte le volte che vuoi. All'interno di WebCC, i backup possono essere eseguiti manualmente o possono essere pianificati come singola istanza o per essere ricorrenti. I backup ricorrenti possono essere effettuati giornalmente, settimanalmente, mensilmente o in base a una pianificazione personalizzata e possono essere aggiornati o annullati in qualsiasi momento.

**Nota**: i backup molto frequenti eseguiti più volte al giorno o ogni ora possono causare il danneggiamento dei lavori di backup. Ciò si verifica perché l'archivio potrebbe non essere in grado di rimuovere i vecchi set sicuri o di eseguire altre attività in background richieste.

## Come funzionano gli schemi di conservazione?

EVault consente la conservazione dei dati a seconda del tempo in cui vuoi eseguire il ripristino. Gli schemi di conservazione **giornalieri** mantengono i dati per sette giorni, mentre gli schemi **settimanali** mantengono i dati per un mese e gli schemi **mensili** li mantengono un anno. Al termine di ciascun periodo, il dataset più vecchio viene ruotato e il primo "backup delta" realizzato diventa il più vecchio punto di ripristino disponibile.

## Cos'è la tecnologia delta?

Il primo backup è un "seed" (un backup completo), quelli successivi sono "delta" (ossia, solo modifiche), ma equivalgono a un "backup completo" e sono ancora considerati come tale. Vale a dire, sei in grado di ripristinare da esso tutti o alcuni file. Questa tecnologia consente di eseguire "backup completi" in ogni sessione, ma risparmia enormi quantità di spazio sull'archivio e riduce il tempo necessario per il completamento di ogni backup successivo.

## I miei backup sono sicuri?

Per impostazione predefinita, tutta la crittografia trasmessa è codificata con la crittografia AES a 256 bit. Puoi anche scegliere di memorizzare i dati nel formato crittografato
con AES a 256 bit.

**Nota**: non devi dimenticare la tua password di crittografia. Non è possibile ripristinare i tuoi dati senza la password. Se perdi la tua password non sarai in grado di recuperare i tuoi dati.

I rapporti di compressione consentono una compressione da zero a un rapporto massimo che, a seconda del tipo file, potrebbe comprimere dal 20 al 30 per cento.

## Quali informazioni vengono memorizzate con i backup dello stato del sistema?

I backup dello stato del sistema includono il database di registrazione della classe COM +, il registro, i file di avvio, i file di sistema, il contatore delle prestazioni e altro ancora. Tutti dipendono dal tuo sistema. I file di sistema variano a seconda del sistema operativo e dei service pack del sistema. Di solito ce ne sono diverse migliaia. MS Windows crea un elenco dinamico di queste DLL quando le includi nel backup. L'inclusione dei file di sistema ti consente di eseguire il ripristino in caso di file di sistema danneggiati o se disinstalli casualmente alcuni service pack oppure se vuoi utilizzare un ripristino bare metal. Ti consente di tornare allo stato del backup senza dover reinstallare il sistema operativo dal kit di installazione e quindi installare ciascun service pack separatamente.

**Nota**: nessun file di dati utente è incluso nel backup dello stato del sistema. Un lavoro di backup dello stato del sistema deve essere configurato come lavoro autonomo. Non ci devono essere altre origini dati incluse nel lavoro di backup dello stato del sistema.

## Cosa accade ai file aperti?

Per impostazione predefinita, il client di base ha una tecnologia all'avanguardia per gestire la maggior parte dei file aperti in esecuzione sul sistema operativo. In rari casi, se i backup non riescono a causa della limitazione dei file aperti, puoi acquistare dei plug-in secondari per migliorare la gestione dei file aperti. In generale, non hai bisogno del plug-in di file aperti a meno che non visualizzi errori nei tuoi backup causati dai file aperti, nel qual caso puoi ordinare i plug-in.
