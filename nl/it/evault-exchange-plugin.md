---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-27"

---
{:new_window: target="_blank"}

# Installazione del plug-in Exchange per EVault

Il plug-in Exchange viene installato con l'agent Windows sull'host. Tramite il portale WebCC puoi configurare i lavori, eseguire il backup dei database Oracle in un archivio remoto protetto e ripristinare i database Oracle. Il plug-in Oracle si integra nell'architettura esistente.

**Capacità fornite**

- Possibilità di eseguire il backup e il ripristino dei database di Microsoft Exchange.

## Ordine del plugin

1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Storage** > **Backup**.
3. Seleziona il tuo account EVault e fai clic su **Order plug-ins**.
4. Seleziona **EVault plug-in - Exchange** e fai clic su **Continue**.
5. Se ne hai uno, immetti il tuo codice promozionale e fai clic su **Recalculate**.
6. Vengono visualizzati i costi aggiornati. Riesamina l'ordine.
7. Seleziona la casella per indicare che hai letto e accettato gli accordi di servizio di terze parti. 
8. Fai clic su **Place Order**.

## Installazione del plug-in Exchange

Il plug-in Exchange viene installato durante l'installazione dell'agent Windows a 64 bit. Il plug-in può essere installato contemporaneamente all'agent oppure può essere installato successivamente, rieseguendo l'installazione con la selezione **Modify** .

**Nota**: prima di installare il plug-in per il tuo server Microsoft Windows, arresta entrambi i servizi EVault in `services.msc`.  

1. Passa alla cartella `c:\installs\evault` ed esegui il file .exe con il numero di revisione maggiore.
2. Nella schermata della lingua, fai clic su **OK**
3. Nella schermata di benvenuto, fai clic su **Next**
4. Seleziona **Modify installation** e fai clic su **Next**.
5. Seleziona **Leave Unchanged** e fai clic su **Next**.
6. Nella schermata di configurazione personalizzata, seleziona ciascun plug-in che hai acquistato.  
7. Seleziona **This feature will be installed on ...** e fai clic su **Next**.
8. Seleziona **Keep my current registration** e fai clic su **Next**.
9. Fai clic su **Install**.
10. Una volta installato, verifica che entrambi i servizi siano abilitati e in esecuzione.
11. Se WebCC è in grado di accedere/visualizzare il database, l'installazione ha avuto esito positivo. 

## Download della guida utente

Connettiti alla rete {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} per poter scaricare la guida EVault Agent v8.0 for Microsoft Windows (64-bit) - Exchange plug-in Guide.pdf da [Downloadable EVault Documentation](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}. La guida descrive come eseguire il backup e il ripristino dei database di Microsoft Exchange utilizzando il plug-in Exchange. La guida descrive anche come condividere un set sicuro di backup DR. Con un set sicuro di backup DR puoi ripristinare caselle di posta, messaggi o altri oggetti specifici in un file .pst utilizzando l'applicazione Granular Restore per Microsoft Exchange.

