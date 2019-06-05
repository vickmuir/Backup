---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, install agent, Windows

subcollection: Backup

---
{:pre: .pre}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Installazione del client backup in Windows
{: #InstallinWindows}

L'installazione del client {{site.data.keyword.backup_full}} in Windows viene completata attraverso una serie di interazioni sul server designato per il servizio {{site.data.keyword.backup_notm}}.

Per ulteriori informazioni sui backup per i server Windows 2016, vedi [Configurazione di {{site.data.keyword.backup_notm}} su Windows 2016](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016).
{:tip}

## Accesso al server del dispositivo di destinazione
{: #logintargetWin}

1. Accedi alla [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog){: external} e fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**. <br/>
   In alternativa, puoi eseguire l'accesso al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}.
2. Seleziona **Devices** > **Device List** dal menu principale per visualizzare l'elenco di server disponibili.
3. Trova il dispositivo per cui hai acquistato il servizio {{site.data.keyword.backup_notm}} e prendi nota del suo indirizzo IP pubblico.
4. Fai clic sulla freccia rivolta verso destra per espandere ulteriori informazioni sul dispositivo, incluso il nome utente e la password. Se la password non viene visualizzata, fai clic su **Show Password**.
5. Accedi al dispositivo di destinazione utilizzando la connessione al desktop remoto.

## Download del client backup

1. Sul server di destinazione, apri una sessione del browser e immetti il seguente l'URL per scaricare il file eseguibile per il client {{site.data.keyword.backup_notm}}. <br/> 
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}

2. Fai doppio clic sul file scaricato.
3. Fai clic su **Run**.


## Installazione e registrazione dell'agent Backup

1. Immetti l'indirizzo di rete: <br />
  ```
  https://ev-webcc01.service.softlayer.com
  ```
  {: pre}

2. Immetti il nome utente nel campo **user name**.
3. Immetti la password nel campo **password**.
6. Fai clic su **Next**
7. Fai clic su **Install** per completare l'installazione.

## Configurazione degli agent backup

Accedi al portale {{site.data.keyword.backup_notm}} per configurare e gestire i tuoi agent backup. Per ulteriori informazioni, vedi l'[Esercitazione introduttiva](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).
