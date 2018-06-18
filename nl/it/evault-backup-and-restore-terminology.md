---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-04"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Terminologia di backup e ripristino EVault 

## Tecnologia delta:
Il primo backup è un “seed” (un backup completo), quelli successivi sono delta (ossia, solo modifiche), ma equivalgono a un backup “completo” e sono ancora considerati come tale. Vale a dire, sei in grado di ripristinare da esso tutti o alcuni file. Questa tecnologia consente di eseguire “Backup completi” in ogni sessione, ma risparmia enormi quantità di spazio sull'archivio e riduce il tempo necessario per il completamento di ogni backup successivo.

## Schemi di conservazione: 
EVault consente la conservazione dei dati a seconda del tempo in cui vuoi eseguire il ripristino. Gli schemi di conservazione giornalieri manterranno i dati per 7 giorni, mentre quelli settimanali manterranno i dati per 1 mese e quelli mensili li manterranno per 1 anno. Al termine di ciascun periodo, il dataset più vecchio viene ruotato e il primo delta realizzato diventa il più vecchio punto di ripristino disponibile. 

## Compressione: 
EVault offre 6 tipi di soluzioni di crittografia per i tuoi dati: DES a 56 bit, Blowfish a 56 bit, Triple DES a 112 bit, Blowfish 128 a bit, AES 128 a bit e AES a 256 bit. I rapporti di compressione consentono una compressione da zero a un rapporto massimo che, a seconda del tipo file, può comprimere dal 20% al 30%.

## Crittografia:
Per impostazione predefinita, tutta la crittografia trasmessa è codificata con la crittografia AES a 128 bit. Se vuoi che i dati siano memorizzati in un formato crittografato, hai a disposizione diverse opzioni come parte del processo di backup. Nota che se perdi la tua password NON sarai in grado di recuperare i tuoi dati. 

## Backup speciali: 
I backup dello stato del sistema includono il database di registrazione della classe COM +, il registro, i file di avvio, i file di sistema, il contatore delle prestazioni e altro ancora, tutti dipendenti dal tuo sistema. I file di sistema variano a seconda del sistema operativo e dei service pack del sistema. Di solito ce ne sono diverse migliaia. MS Windows crea un elenco dinamico di queste DLL quando le includi nel backup. L'inclusione dei file di sistema ti consente di eseguire il ripristino in caso di file di sistema danneggiati o se disinstalli casualmente alcuni service pack oppure se vuoi utilizzare un ripristino bare metal. Ti consente di tornare allo stato del backup senza dover reinstallare il sistema operativo dal kit di installazione e quindi installare ciascun service pack separatamente. 

## File aperti: 
Per impostazione predefinita, il client di base ha una tecnologia all'avanguardia per gestire la maggior parte dei file aperti in esecuzione sul sistema operativo. In rari casi, se i backup non riescono a causa della limitazione dei file aperti, puoi acquistare dei plug-in secondari per migliorare la gestione dei file aperti. La regola generale è che non hai bisogno del plug-in di file aperti a meno che non visualizzi errori nei tuoi backup causati dai file aperti, nel qual caso puoi ordinare i plug-in.
