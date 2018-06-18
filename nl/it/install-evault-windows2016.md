---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-05"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configura EVault su Windows 2016

Attualmente, WebCC di EVault non è ufficialmente supportato su Windows 2016. I server in esecuzione su Windows 2016 devono utilizzare il software Windows Central Control.

## Installazione dell'agent EVault Backup

1. Sul server di destinazione, apri una sessione del browser e immetti il seguente l'URL per scaricare il file eseguibile
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
2. Fai doppio clic sul file scaricato e seleziona **Run** nella casella a comparsa che viene visualizzata.
3. Seleziona la lingua per l'installazione e fai clic su **OK**.
4. Seleziona **Typical** per il tipo di installazione. Fai clic su **Next**.
5. Nella schermata Register Agent with Portal, seleziona **Skip Registration**. 
6. Fai clic su **Next** e quindi su **Finish**.

## Installazione di EVault Software CentralControl

1. Sul server di destinazione, apri una sessione del browser e immetti il seguente l'URL per scaricare il file eseguibile.

   ```
   http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. Fai doppio clic sul file scaricato e seleziona **Run** nella casella a comparsa che viene visualizzata.
3. Segui i passi di installazione per una configurazione tipica.

## Configurazione di CentralControl

Questa attività viene completata attraverso una serie di interazioni mentre si è connessi al server designato per il servizio EVault Backup.

1. Esegui il controllo remoto del tuo server tramite RDP.
2. Avvia CentralControl.
3. Nello spazio di lavoro, fai clic con il tasto destro del mouse su **Agent** e seleziona **Agent Configuration**.
4. Fai clic su **New**.
5. Seleziona **Register as a new computer** e fai clic su **Next**.
6. Immetti l'indirizzo di rete, fai clic su **Add** e quindi su **Next**.
7. Immetti i nuovi valori di porta, fai clic su **Add** e quindi su **Next**.
8. Nella schermata delle impostazioni di connessione, immetti il numero di secondi/minuti desiderato. 
9. Nella schermata di autenticazione, immetti le tue credenziali e fai clic su **Next**.
10. Viene visualizzata la finestra dei computer registrati che visualizza il nome host del tuo server. Fai clic su **Next**.
11.	La procedura guidata di configurazione dell'archivio ha terminato la raccolta delle tue informazioni, fai clic su **Finish** per completare la registrazione.


