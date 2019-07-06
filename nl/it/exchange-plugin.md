---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-13"

keywords: IBM Cloud backup, Exchange, plug-in, plugin, EVault, Carbonite

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Informazioni sul plug-in Exchange
{: #Exchangeplugin}

Il plug-in Exchange viene installato con l'agent Windows sull'host. Tramite il portale {{site.data.keyword.backup_notm}}, è possibile configurare i lavori, eseguire il backup dei database Exchange in un archivio remoto, protetto e ripristinare i database Exchange. Il plug-in si integra nell'architettura esistente.

**Capacità fornite**

- Possibilità di eseguire il backup e il ripristino dei database di Microsoft Exchange.

## Installazione del plug-in
{: #installExchangePlugin}

Il plug-in Exchange viene installato durante l'installazione dell'agent Windows a 64 bit. Il plug-in può essere installato contemporaneamente all'agent oppure può essere installato successivamente, rieseguendo l'installazione con la selezione **Modify** .

Prima di installare il plug-in per il tuo server Microsoft Windows, arresta entrambi i servizi {{site.data.keyword.backup_notm}} in `services.msc`.
{:tip}

1. Passa alla cartella `c:\installs\{{site.data.keyword.backup_notm}}` ed esegui il file .exe con il numero di revisione più alto.
2. Nella schermata della lingua, fai clic su **OK**
3. Nella schermata di benvenuto, fai clic su **Next**
4. Seleziona **Modify installation** e fai clic su **Next**.
5. Seleziona **Leave Unchanged** e fai clic su **Next**.
6. Nella schermata di configurazione personalizzata, seleziona ciascun plug-in che hai acquistato.
7. Seleziona **This feature will be installed on ...** e fai clic su **Next**.
8. Seleziona **Keep my current registration** e fai clic su **Next**.
9. Fai clic su **Install**.
10. Una volta installato, verifica che entrambi i servizi siano abilitati e in esecuzione.
11. Se il portale {{site.data.keyword.backup_notm}} è in grado di accedere al database o di visualizzarlo, l'installazione ha avuto esito positivo.

## Download della guida utente
{: #ExchangeUserGuide}

Connettiti alla rete {{site.data.keyword.cloud}} con {{site.data.keyword.BluVPN}} in modo da poter accedere alla guida utente e scaricarla da [Downloadable {{site.data.keyword.backup_notm}} Documentation](http://downloads.service.softlayer.com/evault/Documentation/){: external}. La guida descrive come eseguire il backup e il ripristino dei database di Microsoft Exchange utilizzando il plug-in Exchange. La guida descrive anche come condividere un set sicuro di backup DR. Con un set sicuro di backup DR puoi ripristinare caselle di posta, messaggi o altri oggetti specifici in un file .pst utilizzando l'applicazione Granular Restore per Microsoft Exchange.
