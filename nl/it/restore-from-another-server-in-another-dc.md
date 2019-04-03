---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Ripristino dei dati da una VSI a un'altra in un Data Center differente
{: #restoreVSIotherlocation}

A volte potresti voler ripristinare i dati in un server diverso. Questa procedura si applica solo ai ripristini a livello di file per i file non di sistema. Per ripristinare un'immagine del sistema, segui le istruzioni di [Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR).

Il processo include la ri-registrazione dell'agent Backup sul secondo server per accedere all'ubicazione dell'archivio del primo server e il completamento di un **ripristino da un altro computer**.

**Prerequisiti**

- Server1 e Server2 devono avere lo stesso sistema operativo. I ripristini multipiattaforma non sono supportati.
- Server1 e Server2 devono avere gli agent backup che erano stati configurati in precedenza. Per ulteriori informazioni sulla configurazione degli agent backup, vedi [Configurazione dell'agent Backup nel portale {{site.data.keyword.backup_notm}}](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).
- Un lavoro di backup per Server1 che ha prodotto un backup nell'ubicazione dell'archivio del Server1.

Disabilita tutte le attività pianificate su entrambi i server per evitare conflitti.
{:important}

## Avvio del portale {{site.data.keyword.backup_notm}} del Server2
{: #startWebCCotherDC}

Ricordati di avviare la tua connessione {{site.data.keyword.BluVPN}} per ottenere l'accesso alla rete privata {{site.data.keyword.BluSoftlayer_full}}, altrimenti il link del portale {{site.data.keyword.backup_notm}} non funziona.
{:tip}

1. Accedi alla [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/){:new_window} e fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**. <br/>
   In alternativa, puoi accedere al [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Storage** > **Backup** per visualizzare i server con un servizio di backup.
3. Seleziona Server2. Fai clic sulla freccia di espansione che punta a destra per visualizzare il link del portale {{site.data.keyword.backup_notm}}.
4. Fai clic su **{{site.data.keyword.backup_notm}} portal Login** per avviare il client del portale nel tuo browser.

## Ri-registrazione dell'archivio
{: #reregistervaultotherDC}

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
{: #runbackuprestoreotherDC}

1. Fai clic su **All Agents**.

   Potresti dover aggiornare la pagina per visualizzare i lavori definiti su Server1 come accessibili e sincronizzati nella scheda **Jobs** di Server2.
   {:tip}
2. Passa con il mouse su **Advanced** e seleziona **Restore from another Computer**.
3. Nella schermata **Restore From Another Computer**, fai clic su **Add**. I campi vengono automaticamente compilati con i valori predefiniti, quindi modificali.
4. Fai clic sul campo Vault, seleziona **Enter Vault Settings** e immetti l'indirizzo IP dell'archivio di Server1. Fai clic su **Add**.
5. Aggiorna le credenziali con quelle di Server1.
6. Fai clic su **Save Changes**. Questa azione ti connette all'archivio di Server1.
7. Torna alla schermata **Restore From Another Computer**, aggiorna i campi Computer e Job.
  - Computer - Seleziona Server1 come computer di backup da cui ripristinare.
  - Job - Seleziona il lavoro di backup da Server1.
8. Fai clic su **Next** per avviare il processo di ripristino sul server2 in un altro data center.
9. Quando richiesto, immetti la password di backup e fai clic su **Next**.
10. Conferma di aver selezionato il lavoro di backup corretto e fai clic su **Next**. Il lavoro di ripristino è ora configurato su server2.
11. Seleziona il lavoro appena configurato e fai clic su **Run Restore**.
12. Seleziona i file che desideri ripristinare.
13. Fai clic sul segno più per espandere la selezione file.
14. Fai clic sulla casella di spunta dei singoli file o cartelle da ripristinare da server1 a server2. Poi, fai clic su **Include**.
15. I file popolano la finestra Backup Set sulla destra. Fai clic su **Next**.
16. Dopo aver completato la selezione dei dati, procedi alla selezione delle tue opzioni.
    - Seleziona **Restore to the original location**.
    - Seleziona **Overwrite existing files**.
17. Fai clic su **Run Restore**. La finestra Process Details fornisce lo stato del lavoro di backup in esecuzione. Al termine del backup, fai clic su **Close**.


## Verifica del ripristino
{: #verifyrestoreotherDC}

1. Collegati alla root di Server2 tramite SSH.
2. Elenca i file e tutte le voci di directory in un formato esteso.
  ```
  ls -la
  ```
  {: pre}

3. Confronta l'output.

## Ripresa della normale pianificazione del backup.
{: #resumescheduleotherCD}

1. Al termine del ripristino, rimuovi le informazioni di registrazione del server1 da cui sono stati ripristinati i dati.
2. Immetti la registrazione del server2 corrente e abilita le attività di pianificazione.
