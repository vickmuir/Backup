---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:codeblock: .codeblock}
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Installazione del client backup in Linux
{: #InstallinLinux}

L'installazione del client {{site.data.keyword.backup_full}} su un sistema operativo basato su Linux può essere eseguita tramite una serie di comandi nella shell o nel terminale all'interno del sistema operativo. Questa procedura descrive i passi necessari per installare il client sui seguenti sistemi operativi basati su Linux:

- RHEL
- CentOS
- CloudLinux

Dopo aver completato la procedura, il processo automatizzato registra il servizio Agent con il portale {{site.data.keyword.backup_notm}}, quindi scarica e installa i file necessari per eseguire il servizio.

Se hai acquistato {{site.data.keyword.backup_notm}} quando hai ordinato un server tramite il [catalogo {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog){:new_window} o il {{site.data.keyword.slportal}}, il software viene installato automaticamente per tuo conto. Non hai bisogno di utilizzare le procedure descritte in questo documento.
{:tip}

Se hai acquistato {{site.data.keyword.backup_notm}} come un upgrade nel {{site.data.keyword.slportal}}, attieniti alla seguente procedura per installare il software.

## Accesso al server del dispositivo di destinazione
{: #logintargetLin}

1. Accedi alla [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/){:new_window} e fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**.<br/>
   In alternativa, puoi accedere al [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}.
2. Seleziona **Devices** > **Device List** dal menu principale per visualizzare l'elenco di dispositivi server disponibili.
3. Trova il dispositivo per il quale hai acquistato il servizio {{site.data.keyword.backup_notm}} e prendi nota del suo indirizzo IP pubblico.
  - Questo indirizzo IP deve essere utilizzato nei seguenti passi quando si accede al dispositivo da una riga di comando UNIX o Linux. Sostituisci <publicIpAddress> con l'indirizzo IP pubblico reale nel comando illustrato nel passo 5.
4. Fai clic sulla freccia rivolta verso destra per visualizzare ulteriori informazioni sul dispositivo, incluso il nome utente e la password.
  - Se la password non viene visualizzata, fai clic su **Show Password**. Il nome utente e la password vengono utilizzati nel passo successivo per accedere al dispositivo di test. Sostituisci `<user name>` con il nome utente effettivo.
5. Accedi al dispositivo di destinazione immettendo il seguente comando da una riga di comando UNIX o Linux.
   ```
   ssh <user name>@<publicIpAddress>
   ```
   {: pre}

   Se non hai effettuato l'accesso a questo server con questo nome utente prima, viene visualizzato un messaggio relativo all'autenticità dell'host. Ti viene anche chiesto se vuoi continuare. Rispondi **yes** per continuare.
   {:note}

6. Ti viene richiesto di immettere la password a meno che tu non abbia configurato precedentemente le chiavi ssh per accedere a questo server.

## Aggiornamento del sistema operativo per la preparazione all'installazione (solo RHEL)

Questo passo è obbligatorio per RHEL ma facoltativo per le altre distribuzioni Linux.
{:tip}

- Esegui questo comando nel prompt del server.
  ```
  yum update
  ```
  {: pre}

  Se richiesto, conferma che la dimensione del download è adeguata. L'aggiornamento procede e al termine viene visualizzato il messaggio "Complete".

## Ottenimento dello script di installazione

- Esegui questo comando nel prompt del server.
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}

## Esecuzione dello script di installazione

1. Esegui questo comando nel prompt del server.
   ```
   sh ./evault_manual.sh
   ```
   {: pre}

2. Immetti i tuoi nome utente e password del portale {{site.data.keyword.backup_notm}}.

   Per ulteriori informazioni sulla visualizzazione di nome utente e password di {{site.data.keyword.backup_notm}}, vedi [Introduzione ai servizi di backup](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).
   {:tip}

3. Dopo il nome utente e la password, non è richiesto alcun ulteriore input. I prompt visualizzati a schermo man mano che l'installazione procede possono essere tranquillamente ignorati.

   Sono prodotti da un indice che viene avviato dallo script `evault_manual.sh`. Lo script `evault_manual.sh` fornisce l'input per questi prompt.
   {:note}

4. L'installazione è completa quando vengono visualizzati i seguenti messaggi.

   ```
   Starting VVAgent: [  OK  ]
   Starting buagent: [  OK  ]
   ```
   {: codeblock}

## Verifica che l'installazione sia riuscita

1. Verifica che il messaggio "Registered to The Portal" sia visualizzato nell'output di installazione. La verifica può essere fatta cercando il messaggio sulla schermata o controllando l'output del seguente comando.
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

  Gli ID processo rappresentati da `xxxxx` variano con ciascuna installazione.
  {:tip}

**Passi successivi**

Accedi al portale {{site.data.keyword.backup_notm}} per configurare e gestire i tuoi agent backup. Per ulteriori informazioni, vedi l'[Esercitazione introduttiva](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started) e [Configurazione di un semplice backup a livello di file su Linux](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup).
