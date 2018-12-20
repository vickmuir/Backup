---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Ri-registrazione di un archivio

Questa attività è la più comunemente utilizzata dopo che viene ricaricato il sistema operativo di un server. Puoi anche utilizzare questa procedura per [usare i backup di un server per ripristinare i dati su un altro server](restore-from-another-computer.html).
{:tip}

1. Avvia il portale {{site.data.keyword.backup_notm}} ed esegui l'accesso. Per ulteriori informazioni, vedi l'[Esercitazione introduttiva](index.html).

   Ricordati che il portale {{site.data.keyword.backup_notm}} è accessibile solo tramite {{site.data.keyword.BluVPN}}.
   {:tip}
2. Sulla sinistra, fai clic su **All Agents**.
3. In alto a destra, passa con il mouse su **Edit**.
4. Seleziona **Vault Settings**.
5. Fai clic su **Reregister**.
6. Completare il modulo.
  - Nome archivio
  - Indirizzo archivio
  - Account

    "Account" è l'equivalente dell'"Account Name" nel [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}. In genere, è simile a "SLE[ID account]"
    {:tip}
  - Nome utente
  - Password
7. Fai clic su **Load Computers** e seleziona i computer che vuoi caricare.
8. Fai clic su **Save Changes**.
9. Aggiorna il sito web per ripristinare i lavori di backup precedenti.
10. Sincronizza ogni lavoro di backup per ripristinare la cronologia del set sicuro.
11. Se i lavori di backup sono stati creati con una password di crittografia, devi immettere tale password per ripristinare i dati o continuare con i backup.
12. Fai clic su **Close**.
