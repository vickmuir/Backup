---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, upgrade agent, Windows

subcollection: Backup

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Upgrade dell'agent software di backup per Windows
{: #UpgradeinWindows}

L'agent backup più recente può essere scaricato dalla sezione Dashboard quick links del tuo portale {{site.data.keyword.backup_notm}}.
{:tip}

1. Controlla in remoto il tuo server {{site.data.keyword.BluSoftlayer_full}} che ha bisogno di un upgrade del {{site.data.keyword.backup_notm}}.
2. Apri un browser e vai al seguente indirizzo:
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
3. Fai clic sul file che ti serve. (Ad esempio, Agent-Windows-x64-6-72-1072a.exe)

   Il numero di versione si trova nel nome file. Scegli quello più recente. <br/>{{site.data.keyword.BluSoftlayer_full}} offre programmi di installazione a 32 bit e 64 bit separati. Se hai un sistema operativo a 64 bit, scarica il file che include x64 nel nome.
   {:tip}
4. Fai clic su **Run** nella schermata di download e di nuovo dopo che è stato scaricato.
5. Fai clic su **Yes** per eseguire un upgrade dell'agent software **{{site.data.keyword.backup_notm}}**.

   Il programma di installazione potrebbe scomparire per un minuto durante il caricamento.
   {:note}
6. Seleziona **Keep my current registration** e fai clic su **next**.
7. Fai clic su **next**. L'agent inizia il processo di aggiornamento. Potrebbero essere necessari alcuni minuti.
8. Nella schermata di completamento, fai clic su **Finish**.
