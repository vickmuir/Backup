---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:codeblock: .codeblock}
{:pre: .pre}
{:new_window: target="_blank"}

# Installazione del client EVault Backup in Linux 

L'installazione del client EVault Backup su un sistema operativo basato su Linux può essere eseguita tramite una serie di comandi nella shell o nel terminale all'interno del sistema operativo. Questa procedura descrive i passi necessari per installare il client EVault Backup su uno dei seguenti sistemi operativi basati su Linux:

- RedHat Enterprise Linux
- CentOS
- CloudLinux

Dopo aver completato la procedura, il processo automatizzato registra il servizio Agent con WebCC, quindi scaricherà e installerà i file necessari per eseguire il servizio.

>**Nota** - Se hai acquistato EVault durante l'ordine di un server nel {{site.data.keyword.slportal}}, il software viene installato automaticamente. Non hai bisogno di utilizzare le procedure descritte in questo documento.

Se hai acquistato EVault come aggiornamento nel {{site.data.keyword.slportal}}, segui questi passi per installare il software.

## Accesso al server del dispositivo di destinazione

1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e seleziona **Devices** > **Device List** dal menu principale per vedere l'elenco dei dispositivi server disponibili.
2. Trova il dispositivo per il quale hai acquistato il servizio EVault e prendi nota del suo indirizzo IP pubblico. 
  - Questo indirizzo IP deve essere utilizzato nei seguenti passi quando si accede al dispositivo da una riga di comando UNIX o Linux. Sostituisci <publicIpAddress> con l'indirizzo IP pubblico reale nel comando illustrato nel passo 4. 
3. Fai clic sulla freccia rivolta verso destra per visualizzare ulteriori informazioni sul dispositivo, incluso il nome utente e la password. 
  - Se la password non viene visualizzata, fai clic su **Show Password**. Il nome utente e la password vengono utilizzati nel passo successivo per accedere al dispositivo di test.  Sostituisci `<user name>` con il nome utente effettivo.
4. Accedi al dispositivo di destinazione immettendo il seguente comando da una riga di comando UNIX o Linux.
   ```
   ssh <user name>@<publicIpAddress>
   ```
   {: pre}
   
   >**Nota** - Se non hai effettuato l'accesso a questo server con questo nome utente prima, viene visualizzato un messaggio relativo all'autenticità dell'host. Ti viene anche chiesto se vuoi continuare. Rispondi **yes** per continuare.
5. Ti viene richiesto di immettere la password a meno che tu non abbia configurato precedentemente le chiavi ssh per accedere a questo server.

## Aggiornamento di Linux per preparare l'installazione del client EVault (solo RedHat Linux)
>**Nota** - Questo passo è obbligatorio per RedHat Linux, ma facoltativo per le altre distribuzioni Linux.

- Esegui questo comando nel prompt del server.
  ```
  yum update
  ```
  {: pre}
   
  Se richiesto, conferma che la dimensione del download è adeguata. L'aggiornamento procede e al termine viene visualizzato il messaggio "Complete!".

## Ottenimento dello script di installazione EVault

- Esegui questo comando nel prompt del server.
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}
   
## Esecuzione dello script di installazione EVault

1. Esegui questo comando nel prompt del server.
   ```
   sh ./evault_manual.sh
   ```
   {: pre}

2. Immetti il nome utente e la password WebCC.     
   >**Nota** - Fai riferimento all'articolo [Introduzione ai servizi di backup](/docs/infrastructure/Backup/index.html) per istruzioni su come visualizzare il nome utente e la password di EVault Backup.
3. Dopo il nome utente e la password, non è richiesto alcun ulteriore input, anche se sono presenti alcuni prompt scritti sulla schermata mentre l'installazione procede. Questi prompt possono essere tranquillamente ignorati. Sono prodotti da un indice che viene avviato dallo script `evault_manual.sh`. Lo script `evault_manual.sh` fornisce l'input per questi prompt.
4. Quando vengono visualizzati messaggi simili ai seguenti, l'installazione è completa:
   ```
   Starting VVAgent: [  OK  ]
   Starting buagent: [  OK  ]
   ```
   {: codeblock}
   
## Verifica che l'installazione sia riuscita

1. Verifica che il messaggio "Registered to The Portal." sia visualizzato nell'output di installazione. La verifica può essere fatta cercando il messaggio sulla schermata o controllando l'output del seguente comando:
   ```
   grep 'Registered'  /opt/BUAgent/Install.log
   ```
   {: pre}

2. Esegui questo comando e osserva l'output.
   ```
   service vvagent status
   ```
   {: pre}
   
   Vengono visualizzati i seguenti messaggi.
   ```
   VVAgent is running (PID xxxxx).
   buagent is running (PID xxxxx).
   ```
   {: codeblock}
   
  >**Nota** - Gli ID del processo rappresentati da `xxxxx` variano con ogni installazione. 
  
**Passi successivi**

Accedi a WebCC per configurare e gestire i tuoi agent di backup. Fai riferimento all'[Esercitazione introduttiva](index.html#configuring-evault-agent-in-webcc) per istruzioni.
