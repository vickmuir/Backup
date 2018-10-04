---

copyright:
  years: 1994, 2018
lastupdated: "2018-08-15"

---
{:new_window: target="_blank"}

# Multiarchivio

Il multiarchivio consente a un client/server di connettersi a più di una ubicazione EVault. Fornisce ridondanza e la sicurezza che i backup sono disponibili anche in caso di guasto di un sito. 

**Punti chiave**

1. Più EVault possono essere gestiti attraverso lo stesso WebCC e amministrati allo stesso modo. L'unica differenza è che hai diverse scelte di archivio.
2. La concessione di licenza del plug-in è basata sull'archivio; ad esempio, se hai acquistato il plug-in MSSQL per un archivio in Washington DC, non funziona nell'archivio di Seattle.
3. Il nuovo archivio deve essere aggiunto manualmente al WebCC dopo ogni acquisto.

**Ubicazioni dei selettori EVault**

Il multiarchivio è disponibile in tutti i data center e non vi è alcun limite geografico nella selezione di un archivio remoto. Quando gli archivi vengono configurati seguendo i passi indicati in questo documento, tutti gli archivi configurati vengono visualizzati nelle impostazioni dell'archivio.

>**Nota** - Il backup nelle ubicazioni di data center remoti potrebbe richiedere più tempo rispetto al backup nello stesso data center in cui si trova il tuo server.

## Aggiunta di un archivio remoto a un account

Devi aggiungere il nuovo archivio di memorizzazione EVault remoto all'account prima che sia possibile aggiungere una nuova ubicazione di backup nel WebCC. 

1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Fai clic su **Devices**
3. Individua e fai clic sul link per il server in questione.
4. In **Device Details**, fai clic su **Storage**.
5. Quando viene visualizzata la sezione Storage, scorri fino a **EVault** e fai clic su **Add**.
6. Nella finestra **Order EVault**, seleziona l'ubicazione dell'archivio remoto facendo clic sull'elenco del menu a discesa.
7. Seleziona la dimensione della quantità di archiviazione, quindi fai clic su **Continue**
8. Seleziona la casella di spunta **I have read the Master...** e fai clic su **Place Order**.

L'archivio appena ordinato viene aggiunto automaticamente all'account. Se ciò non avviene, contatta il settore vendite per assistenza.
Al termine del processo di ordine, passa a **Storage** > **Backup** per vedere il nuovo archivio elencato.

## Aggiunta di un archivio supplementare in WebCC

1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e fai clic su **Storage** > **Backup** dal menu principale per visualizzare i server con il servizio EVault Backup. 
2. Seleziona il server per cui vuoi essere in grado di eseguire il backup in più archivi. Fai clic sulla freccia rivolta verso destra per visualizzare il link WebCC.
3. Fai clic sul link **WebCC Login** per avviare il client WebCC nel tuo browser.
   >**Nota** - WebCC è accessibile solo tramite {{site.data.keyword.BluVPN}}.
4. Nel riquadro di navigazione a sinistra, fai clic su **All Agents**.
5. In alto a destra, fai clic su **Edit** e seleziona **Vault Settings**.
6. Nella finestra **Vault Settings**, fai clic su **Add**.
7. Nella finestra **New Vault** ,
  1. Nel menu Vault Profile, scegli **Enter Vault Settings** per creare una nuova voce. Non aggiornare la voce esistente, non funziona.
  2. Il nome dell'archivio non può essere uguale a quello di un altro archivio. Prova ad aggiungere una tag -2 alla fine del nome. <br/> 
     >**Nota** - Questo campo ha un limite di 15 caratteri.
  3. Il campo dell'indirizzo IP viene popolato con le informazioni sull'ubicazione dei selettori di EVault. Ad esempio, `ev-director301.service.softlayer.com` ha l'indirizzo IP 10.1.114.46 e si trova a WDC.
  4. Nel campo delle credenziali, immetti l'ID account, il nome utente EVault per l'archivio selezionato e la password per l'archivio selezionato.
  5. Fai clic su **Save Changes**.

In pochi secondi, il nuovo archivio è utilizzabile. Se si verifica un errore di connessione, controlla le tue impostazioni e prova di nuovo. Ricorda che l'aggiunta di un altro archivio ti offre un'ulteriore destinazione da scegliere per un lavoro. Non esegue automaticamente i lavori entrambe le volte. Devi configurare i lavori per utilizzare l'archivio aggiuntivo. Fai riferimento all'[Esercitazione introduttiva](index.html#getting-started-with-evault-backup-services) per istruzioni.
