---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Backup e ripristino da una VSI a un'altra nello stesso data center

A volte potresti voler ripristinare i dati in un server diverso all'interno dello stesso data center. Queste istruzioni ti aiuteranno a realizzare questa attività. Questa procedura si applica solo ai ripristini a livello di file per i file non di sistema. Per ripristinare un'immagine del sistema, segui le istruzioni di [Windows BMR](restoring-evault-bmr-system-volume-image.html).

Questo processo include la ri-registrazione dell'agent EVault sul secondo server per accedere all'ubicazione EVault del primo server e l'esecuzione di un **ripristino da un altro computer**.


## Prerequisiti

- Server1 e Server2 devono avere lo stesso sistema operativo. I ripristini multipiattaforma non sono supportati.
- Nel Server1 e Server2 devono essere configurati gli agent EVault. Per informazioni su come configurare gli agent EVault, fai clic [qui](index.html#configuring-evault-agent-in-webcc)
- Un lavoro di backup per Server1 ha prodotto un backup nell'ubicazione EVault del Server1.

**Nota**: disabilita tutte le attività di pianificazione su entrambi i server per evitare conflitti. 

## Avvia WebCC di Server2

**Nota**: ricorda di avviare la tua connessione {{site.data.keyword.BluVPN}} per ottenere l'accesso alla rete privata {{site.data.keyword.BluSoftlayer_full}}, altrimenti i link WebCC non funzioneranno.

1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e fai clic su **Storage** > **Backup** dal menu principale per visualizzare i server con il servizio EVault Backup. 
2. Seleziona Server2. Fai clic sulla freccia di espansione rivolta verso destra per visualizzare il link WebCC.
3. Fai clic su **WebCC Login** per avviare il client WebCC nel tuo browser.

## Registra di nuovo l'EVault:
1. Fai clic su **All Agents** e apri l'agent specifico che desideri modificare.
2. Fai clic su **Edit** e seleziona *Vault Settings".
3. Fai clic su **Reregister** per connettere Server1 a Server2.
4. Nella schermata **Re-register Vault** per la voce **Use a Vault Profile**, seleziona **Enter Vault Settings**.
5. Immetti il nome archivio, che è uguale al nome EVault di Server1.
6. Immetti le credenziali per Server1 per accedere all'EVault per Server1.
7. Fai clic su **Load Computers**; questo mostra i server collegati all'ubicazione dell'archivio.
8. Fai clic su **Save Changes**.
9. Quando richiesto, fai clic su **Yes** per confermare la nuova registrazione dell'EVault.

## Esegui il lavoro di backup da Server1 come lavoro di ripristino su Server2

1. Fai clic su **All Agents**. <br/> **Nota**: potrebbe essere necessario aggiornare la pagina per vedere i lavori definiti su Server1 come accessibili/sincronizzati nella scheda **Jobs** di Server2
2. Passa con il mouse su **Advanced** e seleziona **Restore from another Computer**.
3. Nella schermata **Restore From Another Computer**, effettua le seguenti selezioni:
  - Vault: il valore predefinito di questa voce deve essere l'EVault di Server1
  - Computer: seleziona Server1 come computer di backup da cui ripristinare. 
  - Job: seleziona il lavoro di backup da Server1.
4. Fai clic su **Next**
5. Conferma le informazioni relative all'origine
  - **Safeset location** deve essere l'ubicazione dell'archivio per Server1.
  - Nella sezione **Select a Backup Version**, la versione di backup specificata deve essere il tuo backup da Server1
  - La password di crittografia deve essere la password che hai usato durante l'esecuzione del backup su Server1.
6. Fai clic su **Next**
7. Data Selection: seleziona i file che devono essere ripristinati dal backup di Server1. Seleziona le caselle di spunta accanto ai file e alle directory che vuoi includere, quindi fai clic su **Include** per salvare le tue scelte.
8. Fai clic su **Next** per passare alle opzioni di ripristino.
9. Nelle opzioni:
  - Destination: seleziona **Restore to original location**
  - File Overwrite: seleziona **Overwrite existing files**
10. Fai clic su **Run Restore**.
11. La schermata Process Detail visualizza lo stato del lavoro di ripristino.


## Verifica il ripristino

1. Collegati alla root di Server2 tramite SSH.
2. Elenca i file incluse tutte le voci di directory in un formato esteso.
  ```
  ls -la
  ```
  {: pre}
  
3. Confronta l'output.
  
## Riprendi la normale pianificazione di backup.

1. Al termine del ripristino, rimuovi le informazioni di registrazione del server1 da cui sono stati ripristinati i dati. 
2. Immetti la registrazione del server2 corrente e abilita le attività di pianificazione.
 

  

 
 
  
  
