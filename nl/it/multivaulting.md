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

# Multiarchivio

Il multiarchivio consente a un client/server di connettersi a più di una ubicazione EVault. Fornisce ridondanza e la sicurezza che i backup saranno disponibili anche in caso di guasto di un sito. 

## Punti chiave

1. Più EVault possono essere gestiti attraverso lo stesso WebCC e amministrati allo stesso modo. L'unica differenza è che hai diverse scelte di archivio.
2. La concessione di licenza del plug-in è basata sull'archivio; ad esempio, se hai una licenza di un EVault per il plug-in MSSQL a Washington DC, non funzionerà nell'archivio di Seattle.
3. Il nuovo EVault deve essere aggiunto manualmente al WebCC dopo ogni ordine.

## Aggiunta di un archivio remoto a un account

Devi aggiungere il nuovo archivio di memorizzazione EVault remoto all'account prima che sia possibile aggiungere una nuova ubicazione di backup nel WebCC. 

1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Fai clic su **Devices**
3. Individua e fai clic sul link per il server in questione.
4. In **Device Details**, fai clic su **Storage**
5. Quando viene visualizzata la sezione Storage, scorri fino a **EVault** e fai clic su  **Add**
6. Nella finestra di dialogo **Order EVault** che viene visualizzata, seleziona l'ubicazione dell'archivio remoto facendo clic sul menu a discesa.
7. Seleziona la dimensione della quantità di archiviazione, quindi fai clic su **Continue**
8. Seleziona la casella di spunta **I have read the Master...** e fai clic su **Place Order**.

L'archivio appena ordinato viene aggiunto automaticamente all'account. Se ciò non avviene, contatta il settore vendite per assistenza.
Al termine del processo di ordine, passa a **Storage** > **Backup** per vedere il nuovo archivio elencato.

## Aggiunta di un ulteriore archivio a WebCC

1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e fai clic su **Storage** > **Backup** dal menu principale per visualizzare i server con il servizio EVault Backup. 
2. Seleziona il server in cui si trovano i file da ripristinare. Fai clic sulla freccia di espansione rivolta verso destra per visualizzare il link WebCC.
3. Fai clic sul link WebCC Login per avviare il client WebCC nel tuo browser. <br/>**Nota**: WebCC è accessibile solo tramite {{site.data.keyword.BluVPN}}.
4. Nel riquadro di navigazione a sinistra, fai clic su **All Agents**.
5. Nell'angolo superiore destro, fai clic su **Edit** e seleziona **Vault Settings**.
6. Nella finestra **Vault Settings", fai clic su **Add**.
7. Nella finestra di dialogo **New Vault**:
  1. Nel menu a discesa Vault Profile, scegli **Enter Vault Settings** per creare una nuova voce. Non aggiornare la voce esistente, altrimenti non funzionerà.
  2. Il nome dell'archivio non deve essere uguale a quello di un altro archivio. Consigliamo di aggiungere una tag -2 alla fine del nome. <br/> **Nota**: questo campo ha un limite di 15 caratteri.
  3. Il campo dell'indirizzo IP sarà completato con le informazioni sull'ubicazione evdirector. Ad esempio, ev-director301.service.softlayer.com ha l'indirizzo IP 10.1.114.46 e si trova a WDC. Puoi trovare altre ubicazioni e indirizzi dei selettori EVault in fondo alla pagina.
  4. Nel campo delle credenziali, l'account sarà l'ID account del cliente, il nome utente sarà il nome utente EVault per l'archivio selezionato e la password sarà la password per l'archivio selezionato.
  5. Fai clic su **Save Changes**.

In pochi secondi, il nuovo archivio sarà utilizzabile. Se si verifica un errore di connessione, controlla le tue impostazioni e prova di nuovo. Ricorda che l'aggiunta di un altro archivio ti offre solo un'ulteriore destinazione da scegliere per un lavoro e non esegue automaticamente i lavori in entrambi gli archivi. Devi configurare i lavori per utilizzare l'archivio aggiuntivo. Fai riferimento all'[Esercitazione introduttiva](index.html#getting-started-with-evault-backup-services) per istruzioni.

## Ubicazioni dei selettori EVault

Il multiarchivio è disponibile in tutti i data center e non vi è alcun limite geografico nella selezione di un archivio remoto. Quando gli archivi vengono configurati seguendo i passi indicati in questo documento, tutti gli archivi configurati vengono visualizzati nelle impostazioni dell'archivio.

**Nota**: il backup nelle ubicazioni di data center remoti potrebbe richiedere più tempo rispetto al backup nello stesso data center in cui si trova il tuo server. 

