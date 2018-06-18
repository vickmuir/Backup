---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# Installazione del plug-in Exchange per EVault

Il plug-in Exchange viene installato con l'agent Windows sull'host. Utilizzando il portale WebCC puoi configurare i lavori, eseguire il backup dei database Oracle in un archivio remoto protetto e ripristinare i database Oracle. Il plug-in Oracle si integra nell'architettura esistente.

## Capacità fornite

- Possibilità di eseguire il backup e il ripristino dei database di Microsoft Exchange.

## Ordina il plug-in

1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Storage** > **Backup**.
3. Seleziona il tuo account EVault e fai clic su **Order Plugins**.
4. Seleziona **EVault Plugin - Exchange** e fai clic su **Continue**.
5. Se ne hai uno, immetti il tuo codice promozionale e fai clic su **Recalculate**.
6. Vengono visualizzati i costi aggiornati. Riesamina l'ordine.
7. Seleziona le caselle per indicare che hai letto l'accordo di servizio principale e accetti i termini del software di terze parti. 
8. Fai clic su **Place Order**.

## Installa il plug-in Exchange

Il plug-in Exchange viene installato durante l'installazione dell'agent Windows a 64 bit. Il plug-in può essere installato durante l'installazione dell'agent o può essere installato in un secondo momento, eseguendo nuovamente l'installazione e selezionando Modify.

**Nota**: prima di installare il plug-in per il tuo server Microsoft Windows, arresta entrambi i servizi EVault in `services.msc`.  

1. Passa alla cartella `c:\installs\evault` ed esegui il file .exe con il numero di revisione maggiore.
2. Nella schermata della lingua, fai clic su **OK**
3. Nella schermata di benvenuto, fai clic su **Next**
4. Seleziona **Modify installation** e fai clic su **Next**.
5. Seleziona **Leave Unchanged** e fai clic su **Next**.
6. Nella schermata di configurazione personalizzata, seleziona ciascun plug-in che hai acquistato e seleziona **This feature will be installed on ...**, quindi fai clic su **Next**.
7. Seleziona il pulsante di opzione **Keep my current registration** e fai clic su **Next**.
8. Fai clic su **Install**.
9. Una volta installato, verifica che entrambi i servizi siano abilitati e in esecuzione.
10. Se WebCC è in grado di accedere (visualizzare) ai database, l'installazione ha avuto esito positivo. 

## Guida per l'utente

Connettiti alla rete {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} per poter scaricare la guida EVault Agent v8.0 for Microsoft Windows (64-bit) - Exchange Plug-in Guide.pdf da [Downloadable EVault Documentation](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}. Questa guida descrive come eseguire il backup e il ripristino dei database di Microsoft Exchange utilizzando il plug-in Exchange. Questa guida descrive inoltre come condividere un set sicuro di backup DR in modo da poter ripristinare caselle di posta, messaggi o altri oggetti specifici in un file .pst utilizzando l'applicazione Granular Restore per Microsoft Exchange.


