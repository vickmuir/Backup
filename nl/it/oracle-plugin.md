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

# Installazione del plug-in Oracle
{: #Oracleplugin}

Il plug-in Oracle è un componente aggiuntivo e viene installato con l'agent Windows o l'agent Linux sull'host del database Oracle. Tramite il portale {{site.data.keyword.backup_notm}}, puoi configurare i lavori, eseguire il backup dei database Oracle in un archivio remoto protetto e ripristinare i database Oracle. Il plug-in Oracle si integra nell'architettura esistente.

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

## Ordinazione del plug-in
{: #orderingOraclePlugin}

1. Accedi alla [console {{site.data.keyword.cloud_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}/){:new_window} e fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**. <br/>
   In alternativa, puoi accedere al [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Storage** > **Backup** per visualizzare i server con un servizio di backup.
3. Seleziona il tuo account e fai clic su **Order plug-ins**.
4. Seleziona **{{site.data.keyword.backup_notm}} plug-in - Oracle**, e fai clic su **Continue**.
5. Se ne hai uno, immetti il tuo codice promozionale e fai clic su **Recalculate**.
6. Vengono visualizzati i costi aggiornati. Riesamina l'ordine.
7. Seleziona la casella per indicare che hai letto e accettato gli accordi di servizio di terze parti.
8. Fai clic su **Place Order**.

## Installazione del plug-in per Windows
{: #installOracleWin}

Il plug-in Oracle per Windows viene installato con l'agent Windows a 32 o 64 bit. Per installare il plug-in, esegui il kit di installazione dell'agent. Il plug-in viene visualizzato come opzione nella pagina **Custom Setup**. Per ulteriori informazioni, vedi [Installazione del client {{site.data.keyword.backup_notm}} in Windows](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)

Prima di installare il plug-in per il tuo server Microsoft Windows, arresta entrambi i servizi {{site.data.keyword.backup_notm}} in `services.msc`.
{:tip}

1. Passa alla cartella `c:\installs\evault` ed esegui il file .exe con il numero di revisione più alto.
2. Nella schermata della lingua, fai clic su **OK**
3. Nella schermata di benvenuto, fai clic su **Next**
4. Seleziona **Modify installation** e fai clic su **Next**.
5. Seleziona **Leave Unchanged** e fai clic su **Next**.
6. Nella schermata di configurazione personalizzata, seleziona ciascun plug-in che hai acquistato e seleziona **This feature will be installed on ...**, quindi fai clic su **Next**.
7. Seleziona **Keep my current registration** e fai clic su **Next**.
8. Fai clic su **Install**.
9. Una volta che l'installazione è terminata, verifica che entrambi i servizi siano abilitati e in esecuzione.
10. Se il portale {{site.data.keyword.backup_notm}} è in grado di accedere al database o di visualizzarlo, l'installazione ha avuto esito positivo.

## Installazione del plug-in per Linux
{: #installOracleLin}

Il plug-in Oracle è un componente aggiuntivo per l'agent Linux e viene installato con l'agent sull'host del database. L'applicazione agent Linux deve essere installata prima che si verifichi l'installazione del plug-in. L'agent è disponibile come un'applicazione a 32 bit e come un'applicazione a 64 bit. Per ulteriori informazioni, vedi [Installazione del client {{site.data.keyword.backup_notm}} in Linux](/docs/infrastructure/Backup?topic=Backup-InstallinLinux).

Il kit di installazione del plug-in Oracle è disponibile in un file tar.gz.

1. Sull'host, scarica il pacchetto di installazione.
   ```
   http://downloads.softlayer.com/evault/Oracle-Plugin-Linux-x64-8.10.5249.tar.gz
   ```
   {: pre}

2. Estrai i file dal pacchetto.
   ```
   # cd /tmp
   # tar xvf Oracle-Plugin-Linux-x64-8.10.5249.tar
   ```
   {: pre}

3. Vai alla cartella.
   ```
   # cd Oracle-Plugin-Linux-x64-8.10.5249.xxxx
   ```
   {: pre}

4. Esegui lo script di installazione.
   ```
   # ./install.sh
   ```
   {: pre}

5. Attieniti alle istruzioni di installazione sullo schermo.

Il plug-in Oracle esegue un backup dell'intero database "incongruente" che richiede che il database sia eseguito in modalità ARCHIVELOG. L'amministratore del database deve assicurarsi che il database sia in modalità ARCHIVELOG prima che vengano avviati i backup. Per ulteriori informazioni, consulta la guida utente.
{:important}


## Download della guida utente
{: #OracleUserGuide}

Connettiti alla rete {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} in modo da poter scaricare le guide utente dalla [documentazione di {{site.data.keyword.backup_notm}} scaricabile ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}
