---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Multiarchivio

Il multiarchivio consente a un client/server di connettersi a più di una ubicazione di archivio. Fornisce ridondanza e la sicurezza che i backup sono disponibili anche in caso di guasto di un sito.

**Punti chiave**

1. Più archivi possono essere amministrati attraverso lo stesso WebCC e sono gestiti allo stesso modo. L'unica differenza è che hai diverse scelte di archivio.
2. La concessione di licenza del plug-in è basata sull'archivio; ad esempio, se hai acquistato il plug-in MSSQL per un archivio in Washington DC, non funziona nell'archivio di Seattle.
3. Il nuovo archivio deve essere aggiunto manualmente al WebCC dopo ogni acquisto.

**Ubicazioni dei selettori di archivio {{site.data.keyword.backup_notm}}**

Il multiarchivio è disponibile in tutti i data center e non vi è alcuna limitazione geografica nella selezione di un archivio remoto. Quando gli archivi vengono configurati seguendo i passi indicati in questo documento, tutti gli archivi configurati vengono visualizzati nelle impostazioni dell'archivio.

Il backup nelle ubicazioni di data center remoti potrebbe richiedere più tempo rispetto al backup nello stesso data center in cui si trova il tuo server.
{:note}

## Aggiunta di un archivio remoto a un account

Devi aggiungere il nuovo archivio {{site.data.keyword.backup_notm}} remoto all'account prima che sia possibile aggiungere una nuova ubicazione di backup nel WebCC.

1. Accedi alla [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} e fai clic sull'icona **Menu** nella parte superiore sinistra. Seleziona **Infrastruttura classica**.

   In alternativa, puoi eseguire l'accesso al [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Devices**
3. Individua e fai clic sul collegamento per il server in questione.
4. In **Device Details**, fai clic su **Storage**.
5. Quando viene visualizzata la sezione Storage, scorri verso il basso fino a **{{site.data.keyword.backup_notm}}** e fai clic su **Add**.
6. Nella finestra **Order {{site.data.keyword.backup_notm}}**, seleziona l'ubicazione dell'archivio remoto facendo clic sulla relativa voce nell'elenco del menu a discesa.
7. Seleziona la dimensione della quantità di archiviazione, quindi fai clic su **Continue**
8. Seleziona la casella di spunta **I have read the Master...** e fai clic su **Place Order**.

L'archivio appena ordinato viene aggiunto automaticamente all'account. Se ciò non avviene, contatta il settore vendite per assistenza.

Al termine del processo di ordine, passa a **Storage** > **Backup** per vedere il nuovo archivio elencato.

## Aggiunta di un archivio supplementare in WebCC

1. Accedi alla [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} e fai clic sull'icona **Menu** nella parte superiore sinistra. Seleziona **Infrastruttura classica**.

   In alternativa, puoi eseguire l'accesso al [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Storage** > **Backup** per visualizzare i server con un servizio di backup.
3. Seleziona il server per cui vuoi essere in grado di eseguire il backup in più archivi. Fai clic sulla freccia rivolta verso destra per visualizzare il collegamento WebCC.
4. Fai clic sul collegamento **WebCC Login** per avviare il client WebCC nel tuo browser.

   WebCC è accessibile solo tramite {{site.data.keyword.BluVPN}}.
   {:tip}
5. Nel riquadro di navigazione a sinistra, fai clic su **All Agents**.
6. In alto a destra, fai clic su **Edit** e seleziona **Vault Settings**.
7. Nella finestra **Vault Settings**, fai clic su **Add**.
8. Nella finestra **New Vault** ,
  1. Nel menu Vault Profile, scegli **Enter Vault Settings** per creare una nuova voce. Non aggiornare la voce esistente, non funziona.
  2. Il nome dell'archivio non può essere uguale a quello di un altro archivio. Prova ad aggiungere una tag -2 alla fine del nome. <br/>

     Questo campo ha un limite di 15 caratteri.
     {:important}
  3. Il campo dell'indirizzo IP viene compilato con le informazioni sull'ubicazione dei selettori di {{site.data.keyword.backup_notm}}. Ad esempio, `ev-director301.service.softlayer.com` ha l'indirizzo IP 10.1.114.46 e si trova a WDC.
  4. Nel campo delle credenziali, immetti l'ID account, il nome utente {{site.data.keyword.backup_notm}} per l'archivio selezionato e la password per l'archivio selezionato.
  5. Fai clic su **Save Changes**.

In pochi secondi, il nuovo archivio è utilizzabile. Se si verifica un errore di connessione, controlla le tue impostazioni e prova di nuovo. Ricorda che l'aggiunta di un altro archivio ti offre un'ulteriore destinazione da scegliere per un lavoro. Non esegue automaticamente i lavori entrambe le volte. Devi configurare i lavori per utilizzare l'archivio aggiuntivo. Per ulteriori informazioni, vedi l'[Esercitazione introduttiva](index.html).
