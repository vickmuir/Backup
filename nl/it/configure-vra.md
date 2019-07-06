---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-10"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configurazione dei lavori di backup di VRA
{: #ConfigureVRA}

Una volta che l'ambiente VMware vSphere è stato aggiunto nel portale {{site.data.keyword.backup_notm}}, puoi creare un lavoro di backup che specifica quali macchine virtuali (VM) sottoporre a backup e dove salvare i dati di backup. Per eseguire il backup dei dati, puoi eseguire manualmente il lavoro di backup o pianificarne l'esecuzione.

Prima di poter aggiungere un lavoro di backup, devi configurare le impostazioni dell'archivio e le informazioni di vCenter.
{:important}

## Avvio del portale {{site.data.keyword.backup_notm}}
{: #startWebCCVRA}

Devi essere connesso alla rete privata {{site.data.keyword.cloud}} per poter avviare il portale {{site.data.keyword.backup_notm}}.
{:important}

1. Accedi alla [console {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} e fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**.
2. Fai clic su **Storage** > **Backup** per visualizzare i server con i servizi di backup.
3. Seleziona il server in cui si trovano i file di cui eseguire il backup. Fai clic sulla freccia di espansione che punta a destra per visualizzare il link del portale {{site.data.keyword.backup_notm}}.
4. Fai clic su **{{site.data.keyword.backup_notm}} portal Login** per avviare il client del portale nel tuo browser.

   Se il portale {{site.data.keyword.backup_notm}} non si avvia, potresti avere un problema con la tua connessione VPN. Potresti anche vedere un messaggio che indica che il modulo che stai inviando non è sicuro. Questo messaggio è previsto e puoi procedere con l'invio del modulo.
   {:tip}

## Aggiunta di un lavoro di backup vSphere

1. Nella navigazione, fai clic su **Computers**. La pagina Computers mostra i computer e gli ambienti registrati.
2. Fai clic su **Jobs**.
3. Nel menu Select job Task, fai clic su **Create New VMware vCenter Job**.
4. Specifica le seguenti informazioni.
   * Nel campo **Name**, immetti un nome per il lavoro di backup.
   * Nel campo **Description**, immetti una descrizione facoltativa per il lavoro di backup.
   * Nell'elenco **Destination**, seleziona l'archivio in cui vuoi salvare i dati di backup.
   * Nei campi **Password** e **Confirm Password**, immetti una password di crittografia. Puoi anche immettere un suggerimento password nel campo Password Hint.
   Un archivio viene visualizzato nell'elenco solo se è assegnato all'utente o se l'utente lo ha aggiunto alle impostazioni di archivio del computer.<br/>
   Per i nuovi lavori di backup, il metodo di crittografia è AES a 256 bit. I lavori esistenti possono avere altri metodi di crittografia.
   {:note}

5.	Nel campo **Include in Backup**, effettua uno o più dei seguenti passi finché il campo Backup Set non mostra le VM che vuoi includere nel lavoro di backup.

   * Per aggiungere specifiche VM al lavoro di backup, seleziona ciascuna VM e fai quindi clic su **Include**.
   * Per escludere specifiche VM dal lavoro di backup, seleziona ciascuna VM e fai quindi clic su **Exclude**.
   * Per aggiungere VM al lavoro di backup in base al nome, seleziona la casella Virtual Machines e fai quindi clic su **Include**.
   * Per rimuovere un record di inclusione o di esclusione dalla casella Backup Set, fai clic su **Delete** accanto al record.

6. Se è necessario applicare le modifiche, fai clic su **Apply Now** per consolidare e semplificare i record nella casella Backup Set.
7. Fai clic su **Create Job**.

## Configurazione di una pianificazione

Dopo aver creato il lavoro di backup, puoi aggiungere una o più pianificazioni per l'esecuzione automatica del lavoro.

1. Quando fai clic su **Create Job**, viene visualizzata la finestra Schedule che ti fornisce un'opzione per configurare una pianificazione personalizzata per il lavoro di backup.

   Per impostazione predefinita, per il lavoro è selezionata la conservazione giornaliera. La pianificazione della conservazione e del lavoro può essere modificata in questa finestra e possono inoltre essere assegnati diversi schemi di conservazione al lavoro di backup.
   {:note}
2. Fai clic su **Save** per salvare la nuova pianificazione. Il nuovo lavoro viene mostrato nella scheda Computers della sezione Jobs. Lo stato dell'ultimo backup mostra che il lavoro non è stato mai eseguito. Il lavoro di backup pianificato viene eseguito automaticamente all'ora pianificata.

## Esecuzione di un lavoro pianificato

I lavori di backup pianificati possono anche essere eseguiti immediatamente.

1. Fai clic su **Select Action** e seleziona **Run Job**. Viene visualizzata la finestra Run Job che ti fornisce informazioni sull'archivio di destinazione e sullo schema di conservazione assegnati al lavoro.

   Se al lavoro sono assegnati più archivi e schemi di conservazione, è possibile modificare queste opzioni nella finestra Run job facendo clic sulle opzioni di menu Destination e Retention Scheme.
   {:note}
2. Fai clic su **start Backup job** per eseguire immediatamente il lavoro di backup. La finestra di avanzamento ti mostra lo stato del lavoro di backup e, una volta terminato, lo stato del lavoro cambia da "Never Run" a "Completed".

Per vedere lo stato dell'ultimo lavoro di backup eseguito, fai clic sulla scheda Jobs. Tutti i log dei lavori sono accessibili dal menu azioni. Fai clic su **Action** e seleziona **History/Logs**.
{:tip}

Per ulteriori informazioni sul ripristino delle VM o di file e cartelle, vedi [Ripristino dei dati vSphere](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore).
