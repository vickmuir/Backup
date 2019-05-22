---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, configuration, linux

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configurazione di un semplice backup a livello di file su Linux
{: #configureLinuxBackup}

Una volta che hai ordinato {{site.data.keyword.backup_full}} e che l'agent è installato sul server, puoi iniziare a creare i backup dei tuoi dati. L'articolo fornisce i passi per configurare l'agent, la pianificazione della conservazione e avviare il tuo primo lavoro di backup.

## Avvio del portale {{site.data.keyword.backup_notm}}
{: #startWebCCconfigLin}

1. Accedi alla [console {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} e fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**. <br>
   In alternativa, puoi accedere al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}.
2. Fai clic su **Storage** > **Backup** per visualizzare i server con un servizio di backup.
2. Seleziona il server in cui si trovano i file di cui eseguire il backup. Fai clic sulla freccia di espansione che punta a destra per visualizzare il link del portale {{site.data.keyword.backup_notm}}.
3. Avvia la tua connessione VPN per ottenere l'accesso alla rete privata IBM.
4. Fai clic sul link {{site.data.keyword.backup_notm}} portal Login per avviare il client del portale nel tuo browser.<br/>

  Se il portale {{site.data.keyword.backup_notm}} non si avvia, potresti avere un problema con la tua connessione VPN. Potresti anche vedere un messaggio che indica che il modulo che stai inviando non è sicuro. Questo messaggio è previsto e puoi procedere con l'invio del modulo.
  {:tip}

## Configurazione di un lavoro di backup

1. Nel riquadro di navigazione, fai clic su **All Agents** per visualizzare gli agent {{site.data.keyword.backup_notm}} correnti
2. Fai clic su **This is a new Agent I would like to configure**.
3. Immetti un nome e una descrizione per il lavoro che stai creando.
4. Per **Backup Source Type**, seleziona il tipo di file system di cui vuoi eseguire il backup.
5. Fai clic su **Next** per continuare.
6. Nel riquadro dei file di dati, vai ai file e alle directory che vuoi includere nel tuo backup facendo clic sui simboli **+** e **-** accanto alle icone cartella.
7. Seleziona le caselle di spunta accanto ai file e alle directory che vuoi includere, quindi fai clic su **Include** per salvare le tue scelte.
8. Puoi filtrare ulteriormente le tue selezioni utilizzando la schermata a comparsa che appare o fare clic su **OK** per utilizzare le selezioni effettuate così come sono. Dopo aver incluso le tue scelte di file e directory, i file e le directory selezionati vengono visualizzati nel riquadro dell'insieme di backup sul lato destro della schermata. Fai clic su **Next** per continuare.

   Puoi ripetere i passi da 6 a 8 per aggiungere altri file o per rimuovere i file che hai precedentemente aggiunto (utilizzando **Exclude**). Puoi anche utilizzare **Remove** per eliminare qualsiasi voce dal riquadro dell'insieme di backup. Dopo aver configurato il tuo insieme di backup nel modo desiderato,
   {:tip}
9. Seleziona il tipo di crittografia che vuoi utilizzare.
  - Se non vuoi crittografare il tuo backup, seleziona **None**.
  - Se vuoi la utilizzare la crittografia, seleziona **AES 256 bit** e immetti una password nei campi Password e Verify Password. Puoi anche aggiungere un suggerimento password.

    Hai bisogno di questa password per ripristinare i file dal backup. Senza la password, non puoi ripristinare un backup crittografato e non c'è modo di recuperare una password perduta.
    {:important}
10. Puoi utilizzare una qualsiasi delle **Advanced Options**.
  - **Retention** - Puoi gestire l'utilizzo dei dati con questa opzione. Il periodo di conservazione determina per quanto tempo viene mantenuto il tuo backup. Una volta che il periodo di conservazione è stato raggiunto, il backup viene rimosso automaticamente. Le scelte integrate sono Daily, Weekly o Monthly.
  - **Compression** - Puoi utilizzare questa opzione per ridurre la capacità utilizzata per salvare i backup.
  - **Backup files that are opened for write** - Questa opzione consente di eseguire il backup dei file, anche se sono aperti da un'applicazione durante l'esecuzione del lavoro di backup.
  - **Create log file** - Crei e gestisci il contenuto e la conservazione dei file di log generati durante il processo di backup.
  - **Back up a single instance of all selected hard linked files**. Questa opzione si applica solo ai sistemi in stile UNIX. Se utilizzi i collegamenti fisici per creare più nomi di file per alcuni contenuti, questa opzione consente di salvare solo una copia del contenuto. Al momento del ripristino, tutti gli collegamenti fisici vengono ripristinati. Questa opzione richiede un passo di pre-scansione nella selezione dei file, che può richiedere una quantità significativa di tempo e memoria.
11. Dopo aver effettuato la tua scelta di crittografia, fai clic su **Next** per passare alla schermata **Create a schedule**.
12. Nella pagina Create a schedule, fai clic su **Add** per pianificare un lavoro di backup basato sul tempo o fai clic su **Next** per creare un lavoro manuale.
  - Se scegli di creare un lavoro manuale, procedi al Passo 15.
  - Se scegli di pianificare un lavoro basato sul tempo, seleziona i giorni e l'ora del giorno per eseguire i tuoi backup.
  - Seleziona il tuo schema di conservazione. Per ulteriori informazioni sugli schemi di conservazione, vedi le [Domande frequenti (FAQ)](/docs/infrastructure/Backup?topic=Backup-faqs).
  - Fai clic su **Advanced Schedule Options** per ulteriori opzioni di configurazione. Puoi selezionare **Use Deferring** per impedire l'esecuzione di backup di grandi dimensioni nei momenti di picco della rete.

    Quando l'opzione di differimento è abilitata, il lavoro di backup non esegue il backup di nuovi dati dopo il periodo di tempo specificato. Esegue il commit del set sicuro nell'archivio, anche se alcuni dati nel lavoro non vengono sottoposti a backup. Le modifiche ai dati di cui è stato eseguito il backup in precedenza vengono sottoposte a backup, indipendentemente dal periodo di tempo specificato. <br/> Quando il lavoro viene eseguito nuovamente, l'agent verifica la presenza di modifiche nei dati di cui è già stato eseguito il backup, esegue il backup di tali modifiche e quindi esegue il backup dei dati rimanenti. Se un lavoro di backup viene rinviato mentre viene eseguito il backup di un elemento, il backup per quell'elemento è incompleto e i dati dell'elemento non possono essere ripristinati. Tuttavia, puoi ripristinare gli elementi di cui è stato eseguito il backup prima che il lavoro fosse rinviato.
    {:note}
13. Dopo aver configurato la tua pianificazione di backup, fai clic su **Ok** per salvarla. Il tuo lavoro pianificato viene aggiunto all'elenco di lavori pianificati.
  - Puoi ripetere il passo 12 per pianificare ulteriori backup.
  - Per aggiornare un lavoro di backup esistente, seleziona il lavoro facendo clic sulla sua riga, quindi fai clic su **Edit** e apporta le tue modifiche.
14. Seleziona un archivio per il tuo lavoro di backup e fai clic su **Save Changes**.
15. Esegui un lavoro di backup
  - Se hai pianificato un lavoro di backup basato sul tempo, non hai bisogno di fare altro. Il tuo lavoro viene eseguito automaticamente come pianificato.
  - Se hai configurato un lavoro manuale (senza una pianificazione basata sul tempo), puoi ora eseguirlo selezionando la relativa riga nell'elenco lavori e facendo clic su **Run backup**. Come per i lavori basati sul tempo, puoi scegliere le opzioni di **Retention Scheme** e **Advanced Backup Options**. Dopo aver effettuato le tue scelte di configurazione, fai clic su **Start backup** per avviare il lavoro.
