---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-30"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Nuova registrazione di un EVault

Questa attività è più comunemente un passo necessario dopo il ricaricamento del sistema operativo di un server, ma puoi anche utilizzare questa procedura per [usare i backup per un server, da ripristinare su un altro server](restore-from-another-computer.html).

1. Accedi come utente su WebCC. Per istruzioni, fai riferimento a [Introduzione ai servizi di backup](/docs/infrastructure/Backup/index.html). Ricorda che WebCC è accessibile solo tramite {{site.data.keyword.BluVPN}}.

2. Sulla sinistra, fai clic su **All Agents**.

3. Nell'angolo superiore destro, passa con il mouse su **Edit**.

4. Seleziona **Vault Settings**.

5. Fai clic su **Reregister**.

6. Completa i seguenti campi: 
  - Nome archivio
  - Indirizzo archivio
  - Account
  - Nome utente
  - Password. <br/>
  **Nota**: "Account" è l'equivalente del "Nome account" nella pagina [Introduzione ai servizi di backup](index.html). In genere, è simile a "SLE[ID account]"

7. Fai clic su **Load Computers** e seleziona i computer che vuoi caricare.

8. Fai clic su **Save Changes**.

9. Aggiorna il sito web per ripristinare i lavori di backup precedenti.

10. Sincronizza ogni lavoro di backup per ripristinare la cronologia del set sicuro. 

11. Se i lavori di backup sono stati creati utilizzando una password di crittografia, devi immettere tale password per ripristinare i dati o continuare con i backup.

12. Fai clic su **Close** per terminare.
