---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-13"

---
{:pre: .pre}
{:new_window: target="_blank"}

# Configurazione di EVault su Windows 2016

## Installazione di EVault Software agent

1. Sul server di destinazione, apri una sessione del browser e immetti il seguente l'URL per scaricare il file eseguibile
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
2. Fai doppio clic sul file scaricato e seleziona **Run** nella finestra che viene visualizzata.
3. Seleziona la lingua per l'installazione e fai clic su **OK**.
4. Fai clic su **Next** per iniziare.
5. Leggi i termini e le condizioni e seleziona **I accept the terms in the license agreement**. Poi, fai clic su **Next**.
6. Seleziona **Typical** per il tipo di installazione. Fai clic su **Next**.
7. Nella schermata Register Agent with Portal, seleziona **Skip Registration**. Fai clic su **Next**
8. Nella schermata successiva, fai clic su **Install**.
9. Al termine dell'installazione, fai clic su **Finish**.

## Installazione di EVault Software CentralControl 8.30

1. Sul server di destinazione, apri una sessione del browser e immetti il seguente l'URL per scaricare il file eseguibile.

   ```
   http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. Fai doppio clic sul file scaricato e seleziona **Run** nella finestra che viene visualizzata.
3. Segui i passi di installazione per una configurazione **Typical**.
   1. Quando ti viene richiesto di aggiungere un collegamento sul desktop, seleziona **Yes**. Fai clic su **Next**.
   2. Dopo che hai letto l'accordo di licenza software, seleziona **ACCEPT**. Fai clic su **Next**.
   3. Mantieni la cartella di destinazione predefinita e fai clic su **Next**.
4. Al termine dell'installazione, seleziona **Launch EVault Software Central Control**. Fai clic su **Finish**. 


## Configurazione di CentralControl

Questa attività viene completata attraverso una serie di interazioni mentre si è connessi al server designato per il servizio EVault Backup.

1. Esegui il controllo remoto del tuo server tramite RDP.
2. Avvia CentralControl.
3. Nello spazio di lavoro, fai clic con il tasto destro del mouse su **MyAgent** e seleziona **Agent Configuration**.
4. Nella scheda Vaults, fai clic su **New**. Viene visualizzata la procedura guidata di configurazione dell'archivio. Fai clic su **Next**.
5. Seleziona **Register as a new computer** e fai clic su **Next**.
6. Immettere il nome dell'archivio nel campo del nome profilo. Il nome dell'archivio può essere ottenuto da [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
6. Immetti l'indirizzo di rete (l'indirizzo IP dell'archivio assegnato) e fai clic su **Add**. Poi, fai clic su **Next**.
7. Immetti i nuovi valori di porta, fai clic su **Add** e quindi su **Next**.
8. Nella schermata delle impostazioni di connessione, immetti il numero di secondi/minuti desiderato. Lascia la casella **Enable over the wire encryption for transmissions to/from the vault** selezionata. Fai clic su **Next**.
9. Nella schermata di autenticazione, immetti le tue credenziali e fai clic su **Next**.
10. Viene visualizzata la finestra dei computer registrati che visualizza il nome host del tuo server. Fai clic su **Next**.
11.	Fai clic su **Finish** per completare la configurazione.


## Creazione degli schemi di conservazione EVault

1. Esegui il controllo remoto del tuo server tramite RDP.
2. Avvia CentralControl.
3. Nello spazio di lavoro, fai clic con il tasto destro del mouse su **MyAgent** e seleziona **Agent Configuration**.
4. Fai clic sulla scheda **Retentions**. Viene visualizzata la procedura guidata di conservazione, fai clic su **Next**.
5. Immetti il nome della conservazione. Fai clic su **Next**.<br/>
   **Nota** - La voce può avere una lunghezza massima di 32 caratteri alfanumerici. Gli spazi non sono consentiti, ma possono essere utilizzati caratteri di sottolineatura (`_`) e trattini (`-`).
6. Immettere le copie e i giorni di conservazione online per questo tipo di conservazione. Poi, fai clic su **Next**.<br/>
   **Nota** - La combinazione delle copie e dei giorni di conservazione viene utilizzata per garantire che vengano conservati una durata e un numero di backup minimo.
7. Seleziona **I do not want to create any archive backup copies**. Fai clic su **Next**.
8. Fai clic su **Finish** per completare la configurazione dello schema di conservazione.


## Configurazione del lavoro EVault

1. Esegui il controllo remoto del tuo server tramite RDP.
2. Avvia CentralControl.
3. Nello spazio di lavoro, fai clic con il tasto destro del mouse su **MyAgent** e seleziona **New Job**. 
4. Sul pannello di benvenuto, fai clic su **Next**.
5. Seleziona il tipo di origine di backup.
6. Seleziona **Unicode** per la codifica. Fai clic su **Next**.
7. Seleziona la destinazione di questo lavoro. Fai clic su **Next**.
8. Immetti il nome per il lavoro e la relativa descrizione.<br/>
   **Nota** - Il nome deve avere una lunghezza compresa tra 1 e 30 caratteri. Il nome può contenere lettere, numeri, caratteri di sottolineatura (`_`), trattini (`-`) e simboli dollaro (`$`).
9. Seleziona le origini dati. Fai clic su **Add**.
10. Specifica le opzioni di elaborazione e di backup. Seleziona **Quick file scanning** e immetti le ore e minuti che desideri per la tua finestra di tempo di backup. Poi, fai clic su **Next**.
11. Seleziona il tipo di codifica (l'impostazione predefinita è AES 256-bit) e immetti la tua password di crittografia. Fai clic su **Next**
12. Seleziona le opzioni di registrazione per il tuo lavoro. Seleziona **Create log file** e **Automatically purge expired log files only**. Poi, fai clic su **Next**
13. Seleziona **Just exit from this wizard** e fai clic su **Finish** per completare la configurazione. Il nuovo lavoro viene ora visualizzato in MyAgent.


## Esecuzione del lavoro EVault

1. Esegui il controllo remoto del tuo server tramite RDP.
2. Avvia CentralControl.
3. Nello spazio di lavoro, fai clic con il tasto destro del mouse su **MyAgent** e seleziona l'agent che hai creato. 
4. Sul pannello di benvenuto, fai clic su **Next**.
5. Seleziona la destinazione di backup o un'ubicazione alternativa per eseguire il seeding del lavoro di backup. Fai clic su **Next**.<br/>
   *Suggerimento* - Per ulteriori informazioni sugli archivi multipli, consulta [Multiarchivio](multivaulting.html)
6. Seleziona l'opzione di scansione file rapida per evitare la lettura dei file che non sono stati modificati. Fai clic su **Next**.
7. Fai clic su **Finish** per completare la configurazione e avviare il backup. Viene visualizzata una finestra con le informazioni sul processo che mostra lo stato del lavoro di backup. Al termine del backup, fai clic su **Close**.
