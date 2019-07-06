---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere, backups

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Ripristino dei dati vSphere
{: #VRARestore}

Quando le VM sono protette nell'ambiente vSphere, puoi ripristinare le [VM vSphere](#restoreVMs) e [ripristinare i file e le cartelle](#restoreFFVRA) con vSphere Recovery Agent.

## Ripristino delle VM vSphere
{: #restoreVMs}

1.	Nella barra di navigazione, fai clic su **Computers**. Una griglia elenca i computer disponibili.
2.	Trova l'ambiente vSphere con la VM che desideri ripristinare ed espandi la sua vista facendo clic sulla riga.
3.	Fai clic su **Jobs**.
4.	Trova il lavoro di backup con la VM che desideri ripristinare e fai clic su **Restore** nel menu **Select Action** del lavoro.
5.	Nella finestra di dialogo **Choose What you Want to Restore**, seleziona **Virtual Machines**.
6.	Fai clic su **Continue**. La finestra di dialogo Restore mostra il set sicuro più recente per il lavoro.
    * Per ripristinare i dati da un'altra origine, fai clic su un'origine (archivio) nell'elenco **Source Device**.
    *	Per ripristinare da un set sicuro meno recente, fai clic sul pulsante **Browse Safesets**. Nel calendario che viene visualizzato, fai clic sulla data dei set sicuri da cui desideri eseguire il ripristino.
7.	Nel pannello **Items to Restore**, seleziona ogni VM che vuoi ripristinare.
8.	Nel campo **Encryption Password**, immetti la password di crittografia dei dati.
9.	Nell'elenco **Destination Datastore**, fai clic sull'archivio dati per le VM ripristinate.
10.	Seleziona una delle seguenti opzioni per ripristinare le VM sull'archivio dati che hai selezionato:
  * **Restore all selected Virtual Machines to the selected datastore only.**
  * **Restore to the selected datastore only when a Virtual Machine’s original datastore is not available.** Se la VM sottoposta a backup contiene più VMDK che risiedevano su due o più archivi dati e uno o più archivi dati non sono disponibili, l'intera VM viene ripristinata sull'archivio dati selezionato.

  Se ripristini una VM o un template su un vCenter e la VM originale è presente, la VM viene ripristinata sotto forma di clone dell'originale con il seguente nome: <VMname>-vra-restored-<Date>. La VM viene ripristinata come un clone se la VM originale è accesa, spenta o sospesa. Se la VM originale è accesa e utilizza un indirizzo IP statico, puoi riscontrare un conflitto di indirizzi IP quando la VM ripristinata e clonata viene accesa.
  {:note}

13.	Nell'elenco **Destination Host**, fai clic sull'host in cui vuoi registrare le VM. L'elenco mostra solo gli host che hanno accesso all'archivio dati selezionato.
14.	Seleziona una delle seguenti opzioni per registrare le VM ripristinate con gli host che hai selezionato:
  * **Register all selected Virtual Machines with the selected  hosts only.**
  * **Register with the selected hosts only when a Virtual Machine’s original hosts is not available.**
15.	Per accendere le VM dopo che sono state ripristinate, seleziona **Power VMs on after restoring**.
16.	In **Performance options**, mantieni l'impostazione predefinita.
17.	Fai clic su **Run Restore**.

## Ripristino di file e cartelle
{: #restoreFFVRA}

Puoi ripristinare file e cartelle da una VM di Windows protetta utilizzando vSphere Recovery Agent (VRA). I file e le cartelle possono essere ripristinati contemporaneamente da più di una VM. Non puoi ripristinare file e cartelle dalle VM di Linux utilizzando VRA.
{:important}

Durante un ripristino di file e cartelle, i volumi dalla VM selezionata vengono montati come unità sulla macchina in cui è in esecuzione VRA. Puoi quindi condividere alcune o tutte le unità montate in modo che gli utenti possano copiare i file e le cartelle dalle unità. Puoi anche accedere alla macchina VRA e copiare i file e le cartelle dalle unità montate.

I file e le cartelle sui dischi sono accessibili a chiunque nel sistema VRA, compresi gli utenti non amministratori. Se sei preoccupato per la sicurezza, proteggi la macchina dell'Agent e impedisci agli utenti di accedere localmente alla macchina.
{:tip}

1. Nella barra di navigazione, fai clic su **Computers**. La griglia elenca i computer disponibili.
2. Trova l'ambiente vSphere con la VM che desideri ripristinare ed espandi la sua vista facendo clic sulla riga.
3. Fai clic su **Jobs**.
4. Trova il lavoro di backup con la VM che desideri ripristinare e fai clic su **Restore** nel menu **Select Action** del lavoro.
5. Nella finestra di dialogo **Choose What You Want to Restore**, seleziona **Files and Folders**.
6. Fai clic su **Continue**. La finestra di dialogo per il ripristino mostra il set sicuro più recente per il lavoro.
  * Per ripristinare i dati da un'altra risorsa, fai clic sull'origine nell'elenco Source Device (archivio).
  * Per ripristinare da un set sicuro meno recente, fai clic sul pulsante Browse Safesets. Nel calendario che viene visualizzato, fai clic sulla data del set sicuro da cui desideri eseguire il ripristino. A destra del calendario, fai clic sullo specifico set sicuro da cui eseguire il ripristino.
7. Nel pannello **Items to Restore**, seleziona la VM con i file e le cartelle che vuoi ripristinare.
8. Nel campo **Encryption Password**, immetti la password di crittografia dei dati.
9. Nel **campo Idle Time**, immetti il numero di minuti di inattività dopo i quali l'unità di condivisione deve rimuovere automaticamente la condivisione. Il tempo di inattività può andare da 2 a 180 minuti.

    L'unità non rimuove la condivisione se è in corso la copia dei nuovi dati. Se copi gli stessi dati da un'unità condivisa più di una volta, il sistema potrebbe andare in timeout perché non vengono letti nuovi dati.
    {:note}

10.	In **Performance options**, seleziona Use all available bandwidth.
11.	Fai clic su **Run Restore**.
12. I volumi ripristinati dalla VM selezionata vengono associati come unità sulla macchina in cui è in esecuzione VRA e sono disponibili in una cartella Restore Mount.  Effettua uno dei seguenti passi.
  * Copia i file e le cartelle che vuoi ripristinare dalle unità associate.
  * Condividi una o più unità associate con altri utenti. Gli utenti possono quindi accedere alla condivisione UNC e copiare i file e le cartelle che desiderano ripristinare.
  * Condividi una o più directory dalla cartella Restore Mount sulla macchina VRA. Gli utenti possono quindi accedere alla condivisione UNC e copiare i file e le cartelle che desiderano ripristinare.
