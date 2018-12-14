---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Upgrade del Backup Software Agent per Windows

Utilizza queste istruzioni dettagliate per eseguire un upgrade del {{site.data.keyword.backup_notm}} Agent su un server Windows.

1. Controlla in remoto il tuo server {{site.data.keyword.BluSoftlayer_full}} che ha bisogno di un upgrade del {{site.data.keyword.backup_notm}} tramite RDP.
2. Apri un browser e vai al seguente indirizzo:
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
3. Fai clic sul file che ti serve. (Ad esempio, Agent-Windows-x64-6-72-1072a.exe)

   Il numero di versione si trova nel nome file. Scegli quello più recente. <br/>Ci sono programmi di installazione separati a 32 bit e 64 bit. Se hai un sistema operativo a 64 bit, scarica il file che include x64 nel nome.
   {:tip}
4. Fai clic su **Run** nella schermata di download e di nuovo dopo che è stato scaricato.
5. Fai clic su **Yes** per aggiornare **EVault Software Agent**.

   Il programma di installazione potrebbe scomparire per un minuto durante il caricamento.
   {:note}
6. Seleziona **Keep my current registration** e fai clic su **next**.
7. Fai clic su **next**. L'agent inizia il processo di aggiornamento. Potrebbero essere necessari alcuni minuti.
8. Nella schermata di completamento, fai clic su **Finish**.
