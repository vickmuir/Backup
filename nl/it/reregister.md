---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud backup, EVault, Carbonite, backup, reregister

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Ri-registrazione di un archivio
{: #reregister}

Questa attività è la più comunemente utilizzata dopo che viene ricaricato il sistema operativo di un server. Puoi anche utilizzare questa procedura per [usare i backup di un server per ripristinare i dati su un altro server](/docs/infrastructure/Backup?topic=Backup-restorefromotherVSI).
{:tip}

1. Avvia il portale {{site.data.keyword.backup_notm}} ed esegui l'accesso. Per ulteriori informazioni, vedi l'[Esercitazione introduttiva](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).

   Ricordati che il portale {{site.data.keyword.backup_notm}} è accessibile solo tramite {{site.data.keyword.BluVPN}}.
   {:tip}
2. Fai clic su **All Agents**.
3. Passa con il mouse su **Edit**.
4. Seleziona **Vault Settings**.
5. Fai clic su **Reregister**.
6. Completa il modulo.
  - Nome archivio
  - Indirizzo archivio
  - Account

    "Account" è l'equivalente di "Account Name" nella [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/classic/storage/backup){: external}. In genere, è simile a "SLE[ID account]"
    {:tip}
  - Nome utente
  - Password
7. Fai clic su **Load Computers** e seleziona i computer che vuoi caricare.
8. Fai clic su **Save Changes**.
9. Aggiorna il sito web per ripristinare i lavori di backup precedenti.
10. Sincronizza ogni lavoro di backup per ripristinare la cronologia del set sicuro.
11. Se i lavori di backup sono stati creati con una password di crittografia, devi immettere tale password per ripristinare i dati o continuare con i backup.
12. Fai clic su **Close**.
