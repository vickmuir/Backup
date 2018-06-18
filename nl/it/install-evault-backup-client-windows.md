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

# Installazione del client EVault Backup in Windows

L'installazione del client EVault Backup in Windows viene completata attraverso una serie di interazioni mentre si è connessi al server designato per il servizio EVault Backup. Attieniti alla seguente procedura per installare il client EVault Backup in Windows.

**Nota**: Windows 2016 non è attualmente supportato.

## Accedi al server del dispositivo di destinazione

1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e seleziona **Devices** > **Device List** dal menu principale per vedere l'elenco dei dispositivi server disponibili.
2. Trova il dispositivo per il quale hai acquistato il servizio EVault e prendi nota del suo indirizzo IP pubblico. 
3. Fai clic sulla freccia di espansione rivolta verso destra per visualizzare ulteriori informazioni sul dispositivo, incluso il nome utente e la password. Se la password non viene visualizzata, fai clic sulla casella di spunta **Show Password**. 
4. Accedi al dispositivo di destinazione utilizzando la connessione al desktop remoto.

## Scarica il client EVault

1. Sul server di destinazione, apri una sessione del browser e immetti il seguente l'URL per scaricare il file eseguibile per il client EVault Backup. <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}
  
2. Fai doppio clic sul file scaricato e seleziona **Run** nella casella a comparsa che viene visualizzata.


## Installa e registra l'agent EVault
 
1. Immetti l'indirizzo di rete: <br />
  ```
  ev-webcc01.service.softlayer.com
  ```
  {: pre}
  
2. Immetti il nome utente di EVault Backup nel campo **User name**. 
3. Immetti la password di EVault Backup nel campo **Password**. 
6. Fai clic su **Next** 
7. Fai clic su **Install** per completare l'installazione.

## Passi successivi

Accedi a WebCC per configurare e gestire i tuoi agent di backup. Fai riferimento all'[Esercitazione introduttiva](index.html#configuring-evault-agent-in-webcc) per istruzioni.
