---

copyright:
  years: 2014, 2018
lastupdated: "2018-06-05"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Introduzione ai servizi EVault Backup

I backup assicurano che i tuoi dati vengano memorizzati in modo sicuro all'esterno del tuo dispositivo e protetti in caso di perdita. EVault Backup è un sistema di backup automatizzato basato su agent che viene gestito tramite l'utilità di gestione basata su browser WebCC di EVault, che fornisce agli utenti un metodo per eseguire il backup dei dati tra server in uno o più data center sulla rete {{site.data.keyword.BluSoftlayer_full}}. Gli amministratori possono impostare i backup in modo che seguano una pianificazione oraria, giornaliera, settimanale o personalizzata rivolta a sistemi completi, directory specifiche o persino singoli file. I plug-in aggiuntivi consentono la compatibilità con software come Microsoft Exchange e Microsoft SQL, nonché con altri tipi di software di terze parti, e consentono agli utenti di eseguire un ripristino bare metal laddove necessario.

## Ordine di EVault 

Per acquistare il servizio EVault Backup sono disponibili due modalità:

- Acquisto di EVault quando si ordina un server
- Acquisto di EVault come aggiornamento

### Acquisto di EVault quando si ordina un server

1. Accedi al [Catalogo di IBM Cloud](https://console.bluemix.net/catalog/){:new_window} o al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Ordina un server bare metal mensile. Per ulteriori informazioni su come ordinare i server bare metal, fai clic [qui](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html){:new_window}.
3. Vieni reindirizzato al portale di gestione per completare l'ordine.<br/>
  **Nota**: il servizio EVault Backup non è disponibile quando si ordina un server con fatturazione oraria. Tuttavia, il servizio può essere aggiunto successivamente come aggiornamento. 
4. Nella sezione **Add-ons**, scegli una della opzioni di EVault (diversa da "None").
6. In fondo alla pagina, fai clic su **Add to Order**. Viene visualizzata la pagina di checkout.
7. Nella pagina **CHECKOUT**, trova la sezione relativa ai nomi host e di dominio e inserisci i nomi corrispondenti. Puoi scegliere il nome host e dominio che preferisci.
8. Sul lato destro della pagina **CHECKOUT**, fai clic sulle caselle di spunta **Cloud Service terms** e **Third-Party Service Agreement**.
9. Conferma o immetti le informazioni di pagamento e fai clic su **Submit Order**. Vieni reindirizzato a una schermata con il tuo numero dell'ordine di provisioning. Puoi stampare la schermata in quanto è anche la tua ricevuta dell'ordine di provisioning. <br/>**Nota**: puoi anche salvare questo ordine senza completare l'acquisto facendo clic su **Save as Quote**.

Al tuo amministratore viene inviata una serie di e-mail relative alla conferma di ricezione dell'ordine di provisioning, all'approvazione ed elaborazione dell'ordine di provisioning e al completamento del provisioning. L'e-mail sul completamento del provisioning include un link alla tua pagina *Device Details* dopo l'accesso a {{site.data.keyword.cloud_notm}}. Puoi anche accedere direttamente al {{site.data.keyword.slportal}}.

**Conferma l'acquisto del servizio EVault**
1. Nel [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}, seleziona **Devices** > **Device List** dal menu principale. 
2. Individua il nuovo server che hai ordinato.
  - Se accanto all'URL c'è l'icona dell'orologio, dovrai aspettare per continuare con la conferma dell'acquisto di EVault. Puoi aggiornare la pagina per vedere uno stato aggiornato sul nuovo server. Quando l'icona dell'orologio non è più presente, puoi procedere con i passi successivi per confermare l'acquisto del servizio EVault.
  - Quando l'icona dell'orologio non viene più visualizzata per il tuo server, fai clic sul link (l'URL del server) per accedere alla pagina **Device Details**. 
3. Fai clic sulla scheda **Storage** per visualizzare le informazioni su EVault.
4. Esamina la sezione EVault e verifica che la dimensione selezionata durante il processo di acquisto di EVault sia visualizzata accanto al link EVault.

### Acquisto di EVault come aggiornamento

**Seleziona un server su cui installare EVault**
1. Accedi al [Catalogo di IBM Cloud](https://console.bluemix.net/catalog/){:new_window} o al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Seleziona **Devices** > **Device List** dal menu principale. Trova il dispositivo per il quale desideri aggiungere il servizio EVault.
3. Fai clic sul nome del dispositivo per accedere alla sua pagina dei dettagli.

**Aggiungi (acquista) il servizio EVault**
1. Fai clic sulla scheda **Storage** e individua la sezione EVault nella parte inferiore della pagina.
2. Fai clic sul link **Add**.
3. Nella finestra a comparsa, seleziona una posizione o accetta il valore predefinito e seleziona una dimensione.
4. Fai clic su **Continue**
5. Fai clic sulla casella di spunta se accetti i termini e le condizioni.
6. Fai clic su **Place Order**.

**Conferma l'acquisto del servizio EVault**
1. Aggiorna la pagina **Device Details** e assicurati che sia selezionata la scheda **Storage**.
2. Esamina la sezione EVault e verifica che la dimensione selezionata durante il processo di acquisto di EVault sia visualizzata accanto al link EVault. <br /> **Nota**: se la dimensione di archiviazione EVault continua a mostrare una capacità pari a zero, potrebbe essere necessario un secondo aggiornamento della pagina. 

## Accesso e visualizzazione dei dettagli di archiviazione di EVault Backup nel {{site.data.keyword.slportal}}

I dettagli di archiviazione relativi al tuo servizio EVault Backup possono essere visualizzati in qualsiasi momento utilizzando il {{site.data.keyword.slportal}}. I dettagli che possono essere visualizzati includono la password, l'indirizzo di archiviazione e l'utilizzo associati al servizio EVault Backup selezionato. 

1. Per accedere alla schermata **EVault Backup Storage** nel [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}, esegui l'accesso utilizzando le tue credenziali univoche.
2. Fai clic su **Storage** e seleziona **Backup** dall'elenco a discesa.
2. Fai clic in qualsiasi punto della riga per il servizio EVault Backup desiderato per visualizzare i suoi dettagli di archiviazione. Da questa vista, la password non è visibile. Procedi al passo successivo per visualizzare la password associata al tuo servizio EVault Backup.
3. Fai clic sulla casella di spunta **Show** accanto al campo **Password** per visualizzare la password per il servizio EVault Backup selezionato.

Per molti prodotti e servizi {{site.data.keyword.BluSoftlayer_full}}, la funzione di archiviazione della password disponibile nel {{site.data.keyword.slportal}} viene utilizzata esclusivamente per l'archiviazione o il tracciamento della password e le modifiche apportate alla password nel {{site.data.keyword.slportal}} non vengono applicate al prodotto o al servizio. Questo _non_ è il caso di EVault Backup. Le modifiche apportate alla password di EVault Backup all'interno del {{site.data.keyword.slportal}} verranno apportate al servizio stesso. Apporta le modifiche tenendo presente che queste influiranno direttamente sul tuo servizio. Per reimpostare la tua password, segui la procedura in [Come modificare una password di EVault Backup nel {{site.data.keyword.slportal}}](/docs/infrastructure/Backup/change-password-evault-backup-service.html).

## Installazione dell'agent EVault

L'agent EVault è supportato nei seguenti sistemi operativi:

### Windows
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

### Linux
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - Red Hat Enterprise Linux 7.x
 - Red Hat Enterprise Linux 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

Segui le istruzioni appropriate per il tuo sistema operativo:
- [Installazione del client EVault Backup in Linux](install-evault-backup-client-linux.html)
- [Installazione del client EVault Backup in Windows](install-evault-backup-client-windows.html)
- [Installazione del client EVault Backup per Windows 2016](install-evault-windows2016.html)

## Accesso a WebCentralControl (WebCC) per EVault Backup

WebCentralControl (WebCC) è il client utilizzato durante l'interazione con qualsiasi servizio EVault Backup offerto da  {{site.data.keyword.BluSoftlayer_full}}. WebCC è un client basato su browser eseguito sulla nostra rete privata che consente il pieno controllo di qualsiasi servizio EVault Backup, inclusa la configurazione e i ripristini. Segui questa procedura per accedere a WebCC per EVault Backup.

1. Accedi alla rete privata tramite VPN. <br/>
    **Nota**: non è possibile accedere a WebCC sulla rete pubblica. Per accedere a WebCC è necessario stabilire una connessione VPN.
2. Accedi alla schermata EVault Backup Storage nel [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
3. Fai clic in qualsiasi punto della riga per il servizio EVault Backup desiderato per espandere la vista.
3. Fai clic su **WebCC Login** per avviare il client WebCC nel tuo browser.

## Configurazione dell'agent EVault in WebCC

Una volta che hai ordinato il servizio EVault e che l'agent è installato sul server, puoi iniziare a creare i backup dei tuoi dati. Segui questa procedura per configurare l'agent, la pianificazione della conservazione e avviare il tuo primo lavoro di backup.

1. Accedi a WebCC.
2. Fai clic su **All Agents**> **Unconfigured Agents**.
3. Fai clic sul link **This is a new Agent I would like to configure**. Passa attraverso il processo e specifica quanto segue:
   1. Agent configuration - fornisci la descrizione dell'agent e fai clic su **Next**.
   2. Job type selection - immetti il nome e la descrizione del lavoro e il tipo di origine del backup e fai clic su **Next**.
   3. Selection - seleziona le directory e fai clic su **Include...**
   4. Options - fornisci le password
   5. Schedule - fai clic su **Add** per creare una pianificazione e fai clic su **Next**.
   6. Seleziona l'archivio predefinito e fai clic su **OK**.
   7. Fai clic su **Save**.
4. Crea una pianificazione di conservazione:
   1. Seleziona **Edit** > **Agent Settings**.
   2. Fai clic su **Add**.
   3. Inserisci i dettagli di conservazione.
   4. Fai clic su **OK**.
   5. Fai clic su **Save**.
   **Nota** - Per ulteriori informazioni su come funzionano gli schemi di conservazione, fai clic [qui](evault-backup-faq.html#how-do-the-retention-schemes-work-)
5. Esegui l'agent e avvia un backup.
   1. Fai clic su **All Agents**, quindi seleziona l'agent appena configurato.
   2. Fai clic su **Run Backup**.
   3. Conferma la destinazione e seleziona uno schema di conservazione.
   4. Fai clic su **Start Backup**. Puoi visualizzare i dettagli del backup mentre il processo è in esecuzione.
   5. Al termine del backup, fai clic su **Close**.
   
**Nota**: per ulteriori informazioni su come configurare semplici backup a livello di file su Linux, fai clic [qui](configure-simple-file-backup-linux.html).

## Operazioni successive

I sistemi WebCC sono completamente documentati e il supporto per l'applicazione è accessibile in WebCC. Fai clic su **Help** nell'angolo superiore destro, indicato da un punto interrogativo bianco in un cerchio blu. Fai clic su qualsiasi articolo o argomento nella barra di navigazione sul lato sinistro della finestra a comparsa per visualizzare ulteriori informazioni.


