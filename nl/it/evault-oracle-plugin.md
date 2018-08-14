---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# Installazione del plug-in Oracle per EVault

Il plug-in Oracle viene installato con l'agent Windows sull'host del database Oracle. Tramite il portale WebCC puoi configurare i lavori, eseguire il backup dei database Oracle in un archivio remoto protetto e ripristinare i database Oracle. Il plug-in Oracle si integra nell'architettura esistente.

**Capacità fornite**

- Supporto per il backup e il ripristino del database Oracle.
- Il plug-in Oracle fornisce backup basati su ARCHIVELOG e non RMAN di tutte le istanze di database online. Tutti i file dei parametri di istanza e spazi tabella non temporanei vengono automaticamente sottoposti a backup. Oracle Corporation consiglia che i backup vengano eseguiti in periodi di scarsa attività del database.
- I database completi e parziali vengono ripristinati tramite i normali meccanismi di ripristino Oracle gestiti dall'utente.

**Limitazioni**
- Viene eseguito solo il backup dei database locali basati su disco a istanza singola.
- I cluster di database non vengono sottoposti a backup.
- I dispositivi non formattati non vengono sottoposti a backup.
- I database remoti non vengono sottoposti a backup.
- Il database deve essere eseguito in modalità ARCHIVELOG e l'utente con il quale è configurato il backup deve disporre dei privilegi SYSDBA.
- Le password del database sono crittografate per una maggiore sicurezza rispetto ai metodi basati su script.

## Ordine del plugin

1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Storage** > **Backup**.
3. Seleziona il tuo account EVault e fai clic su **Order plug-ins**.
4. Seleziona **EVault plug-in - Oracle** e fai clic su **Continue**.
5. Se ne hai uno, immetti il tuo codice promozionale e fai clic su **Recalculate**.
6. Vengono visualizzati i costi aggiornati. Riesamina l'ordine.
7. Seleziona la casella per indicare che hai letto e accettato gli accordi di servizio di terze parti. 
8. Fai clic su **Place Order**.

## Installazione del plug-in Oracle

Il plug-in Oracle per Windows viene installato con l'agent Windows a 32 o 64 bit. Per installare il plug-in Oracle per Windows, esegui il kit di installazione dell'agent. Il plug-in Oracle viene visualizzato come opzione nella pagina **Custom Setup**.

>**Nota** - Prima di installare il plug-in per il tuo server Microsoft Windows, arresta entrambi i servizi EVault in `services.msc`.  

1. Passa alla cartella `c:\installs\evault` ed esegui il file .exe con il numero di revisione maggiore.
2. Nella schermata della lingua, fai clic su **OK**
3. Nella schermata di benvenuto, fai clic su **Next**
4. Seleziona **Modify installation** e fai clic su **Next**.
5. Seleziona **Leave Unchanged** e fai clic su **Next**.
6. Nella schermata di configurazione personalizzata, seleziona ciascun plug-in che hai acquistato e seleziona **This feature will be installed on ...**, quindi fai clic su **Next**.
7. Seleziona **Keep my current registration** e fai clic su **Next**.
8. Fai clic su **Install**.
9. Una volta che l'installazione è terminata, verifica che entrambi i servizi siano abilitati e in esecuzione.
10. Se WebCC è in grado di accedere/visualizzare il database, l'installazione ha avuto esito positivo. 

## Download della guida utente

Connetti alla rete {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} per poter scaricare la guida EVault Agent v8.0 for Microsoft Windows - Oracle plug-in Guide.pdf da [Downloadable EVault Documentation](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.




