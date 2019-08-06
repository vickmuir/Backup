---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud backup,  EVault, Carbonite, backup, restore

subcollection: Backup

---
{:pre: .pre}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Ripristino dei dati da una VSI ad un'altra all'interno dello stesso data center
{: #restorefromotherVSI}

A volte potresti voler ripristinare i dati in un server diverso all'interno dello stesso data center. Questa procedura si applica solo ai ripristini a livello di file per i file non di sistema. Per ripristinare un'immagine del sistema, segui le istruzioni di [Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR).

Il processo include la ri-registrazione dell'agent Backup sul secondo server per accedere all'ubicazione dell'archivio del primo server e il completamento di un **ripristino da un altro computer**.

**Prerequisiti**

- Server1 e Server2 devono avere lo stesso sistema operativo. I ripristini multipiattaforma non sono supportati.
- Server1 e Server2 devono avere gli agent backup che erano stati configurati in precedenza. Per ulteriori informazioni sulla configurazione degli agent backup, vedi [Configurazione dell'agent backup nel portale {{site.data.keyword.backup_notm}}](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).
- Un lavoro di backup per Server1 che ha prodotto un backup nell'ubicazione dell'archivio del Server1.

Disabilita tutte le attività pianificate su entrambi i server per evitare conflitti.
{:important}

## Avvio del portale {{site.data.keyword.backup_notm}} del Server2
{: #startWebCC}

Ricordati di avviare la tua connessione {{site.data.keyword.BluVPN}} per ottenere l'accesso alla rete privata {{site.data.keyword.cloud}}, altrimenti il link del portale {{site.data.keyword.backup_notm}} non funziona.
{:tip}

1. Accedi alla [console {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external}. Dal menu di navigazione, seleziona **Classic Infrastructure**.
2. Fai clic su **Storage** > **Cloud Backup** per visualizzare i server con un servizio di backup.
3. Seleziona Server2. Fai clic sulla freccia di espansione per visualizzare il link del portale {{site.data.keyword.backup_notm}}.
4. Fai clic su **{{site.data.keyword.backup_notm}} portal Login** per avviare il client del portale nel tuo browser.

## Ri-registrazione dell'archivio
{: #reregistervault}

1. Fai clic su **All Agents** e apri l'agent specifico che desideri modificare.
2. Fai clic su **Edit** e seleziona **Vault Settings**.
3. Fai clic su **Reregister** per connettere Server1 a Server2.
4. Nella schermata **Re-register Vault** per la voce **Use a Vault Profile**, seleziona **Enter Vault Settings**.
5. Immetti il nome archivio (Vault Name), che è uguale al nome archivio di Server1.
6. Immetti le credenziali per Server1 per accedere all'archivio per Server1.
7. Fai clic su **Load Computers**; questa azione mostra i server collegati all'ubicazione dell'archivio.
8. Fai clic su **Save Changes**.
9. Quando ti viene richiesto, fai clic su **Yes** per confermare la ri-registrazione dell'archivio.

## Esecuzione del lavoro di backup da Server1 come lavoro di ripristino su Server2
{: #runbackuprestore}

1. Fai clic su **All Agents**.

   Potresti dover aggiornare la pagina per visualizzare i lavori definiti su Server1 come accessibili e sincronizzati nella scheda **Jobs** di Server2.
   {:tip}
2. Passa con il mouse su **Advanced** e seleziona **Restore from another Computer**.
3. Nella schermata **Restore From Another Computer**, effettua le seguenti selezioni.
  - Vault - questa voce viene impostata come valore predefinito sull'archivio di Server1
  - Computer - Seleziona Server1 come computer di backup da cui ripristinare.
  - Job - Seleziona il lavoro di backup da Server1.
4. Fai clic su **Next**
5. Conferma le informazioni relative all'origine
  - **Safeset location** è l'ubicazione dell'archivio per Server1.
  - Nella sezione **Select a Backup Version**, specifica il tuo backup da Server1 come la versione di backup.
  - La password di crittografia è la password utilizzata quando hai creato il backup di Server1.
6. Fai clic su **Next**
7. Seleziona i file che devono essere ripristinati dal backup di Server1. Seleziona le caselle accanto ai file e alle directory che vuoi ripristinare, quindi fai clic su **Include** per salvare le tue scelte.
8. Fai clic su **Next** per passare alle opzioni di ripristino.
9. In Options
  - Destination - Seleziona **Restore to original location**
  - File Overwrite - Seleziona **Overwrite existing files**
10. Fai clic su **Run Restore**.
11. La schermata Process Detail visualizza lo stato del lavoro di ripristino.


## Verifica del ripristino
{: #verifyrestore}

1. Collegati alla root di Server2 tramite SSH.
2. Elenca i file e tutte le voci di directory in un formato esteso.
  ```
  ls -la
  ```
  {: pre}

3. Confronta l'output.

## Ripresa della normale pianificazione del backup.
{: #resumeschedule}

1. Al termine del ripristino, rimuovi le informazioni di registrazione del server1 da cui sono stati ripristinati i dati.
2. Immetti la registrazione del server2 corrente e abilita le attività di pianificazione.
