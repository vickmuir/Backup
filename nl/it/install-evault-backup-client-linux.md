---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-14"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Installazione del client EVault Backup in Linux 

L'installazione del client EVault Backup su un sistema operativo basato su Linux può essere eseguita tramite una serie di comandi nella shell o nel terminale all'interno del sistema operativo. Questa procedura descrive i passi necessari per installare il client EVault Backup su uno dei seguenti sistemi operativi basati su Linux:

- RedHat Enterprise Linux
- CentOS
- CloudLinux

Dopo aver completato la procedura, il processo automatizzato registrerà il servizio Agent con WebCC, quindi scaricherà e installerà i file necessari per eseguire il servizio. Attieniti alla seguente procedura per installare il client EVault Backup nel tuo sistema operativo basato su Linux.

**Nota**: se hai acquistato EVault durante l'ordine di un server nel {{site.data.keyword.slportal}}, il software viene installato automaticamente e non dovrai utilizzare le procedure descritte in questo documento.

Se hai acquistato EVault come aggiornamento nel {{site.data.keyword.slportal}}, segui questi passi per installare il software.

## Accedi al server del dispositivo di destinazione

1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e seleziona **Devices** > **Device List** dal menu principale per vedere l'elenco dei dispositivi server disponibili.
2. Trova il dispositivo per il quale hai acquistato il servizio EVault e prendi nota del suo indirizzo IP pubblico. Dovrà essere utilizzato nei seguenti passi quando si accede al dispositivo da una riga di comando UNIX o Linux. Sostituisci <publicIpAddress> con il reale indirizzo IP pubblico nei comandi che seguono. 
3. Fai clic sulla freccia di espansione rivolta verso destra per visualizzare ulteriori informazioni sul dispositivo, incluso il nome utente e la password.  Se la password non viene visualizzata, fai clic sulla casella di spunta **Show Password**. Il nome utente e la password verranno utilizzati nel passo successivo per accedere al dispositivo di test.  Sostituisci `<user name>` con il reale nome utente nei comandi che seguono.
4. Accedi al dispositivo di destinazione con ssh immettendo il seguente comando da una riga di comando Unix o Linux:
  ```
  ssh <user name>@<publicIpAddress>
  ```
  {: pre}
  
 **Nota**: se non hai ancora effettuato l'accesso a questo server con questo nome utente, ti verrà presentato un messaggio sull'autenticità dell'host e ti verrà chiesto se vuoi continuare.  Rispondi **yes** per continuare.
5. Ti verrà richiesto di immettere la password a meno che tu non abbia configurato precedentemente le chiavi ssh per accedere a questo server.

## Aggiorna Linux per preparare l'installazione del client EVault (solo RedHat Linux)
**Nota**: questo passo è obbligatorio per RedHat Linux, ma facoltativo per le altre distribuzioni Linux.

- Esegui questo comando nel prompt del server:
  ```
  yum update
  ```
  {: pre}
   
  Se richiesto, conferma che la dimensione del download è adeguata. L'aggiornamento procederà e al termine verrà visualizzato il messaggio "Complete!".

## Ottieni lo script di installazione EVault
- Esegui questo comando nel prompt del server:
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}
   
## Esegui lo script di installazione EVault
1. Esegui questo comando nel prompt del server:
  ```
  sh ./evault_manual.sh
  ```
  {: pre}

2. Immetti il nome utente e la password WebCC.     
  **Nota**: fai riferimento all'articolo [Introduzione ai servizi di backup](/docs/infrastructure/Backup/index.html) per istruzioni su come visualizzare il nome utente e la password di EVault Backup.
3. Dopo il nome utente e la password, non è richiesto alcun ulteriore input, anche se visualizzerai alcuni prompt scritti sulla schermata mentre l'installazione procede. Questi prompt possono essere tranquillamente ignorati. Sono prodotti da un indice che viene richiamato dallo script *evault_manual.sh*.  Lo script *evault_manual.sh* fornisce l'input per questi prompt.
4. Quando vengono visualizzati messaggi simili ai seguenti, l'installazione è completa:
  ```
  Starting VVAgent: [  OK  ]
  Starting buagent: [  OK  ]
  ```
  {: codeblock}
   
## Verifica che l'installazione sia riuscita
1. Verifica che il messaggio "Registered to The Portal." sia visualizzato nell'output di installazione. Per farlo, puoi cercare il messaggio sulla schermata o controllare l'output del seguente comando:
  ```
  grep 'Registered'  /opt/BUAgent/Install.log
  ```
  {: pre}

2. Esegui questo comando e osserva l'output: 
  ```
  service vvagent status
  ```
  {: pre}
   
  Dovrebbero essere visualizzati i seguenti messaggi:
  ```
  VVAgent is running (PID xxxxx).
  buagent is running (PID xxxxx).
  ```
  {: codeblock}
   
  **Nota**: gli ID di processo rappresentati sopra da 'xxxxx' variano a seconda dell'installazione. 
  
## Passi successivi

Accedi a WebCC per configurare e gestire i tuoi agent di backup. Fai riferimento all'[Esercitazione introduttiva](index.html#configuring-evault-agent-in-webcc) per istruzioni.
