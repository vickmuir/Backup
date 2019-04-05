---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-28"

keywords: IBM Cloud backup, EVault, Carbonite, IBM Cloud backup, Enterprise backup

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Provisioning di {{site.data.keyword.backup_notm}}
{: #ordering}

Puoi acquistare il servizio {{site.data.keyword.backup_notm}} in due modi.

- [Acquisto di backup quando ordini un server](#purchasingwithserver).
- [Acquisto di backup come un upgrade](#purchasingasupgrade).

Per ulteriori informazioni sui prezzi, vedi [{{site.data.keyword.backup_notm}} storage ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/cloud/backup-and-restore){:new_window} e [{{site.data.keyword.backup_notm}} on IBM Cloud ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.ibm.com/cloud/backup/pricing){:new_window}.

## Acquisto {{site.data.keyword.backup_notm}} quando ordini un server
{: #purchasingwithserver}

1. Accedi al [catalogo IBM Cloud ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")]https://{DomainName}/catalog){:new_window} oppure al [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}
2. Ordina un server bare metal mensile. Per ulteriori informazioni sull'ordinazione di server bare metal, vedi [Creazione di un server bare metal personalizzato](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server#ordering-baremetal-server){:new_window}.
   1. Seleziona la quantità e l'opzione di fatturazione. Immetti i nomi di host e dominio. Puoi scegliere il nome host e dominio che preferisci.

      Il servizio {{site.data.keyword.backup_notm}} non è disponibile quando stai ordinando un server con fatturazione oraria. Tuttavia, il servizio può essere aggiunto successivamente come aggiornamento.
      {:tip}
   2. Seleziona l'ubicazione.
   3. Seleziona il tipo di configurazione del server e di immagine del sistema operativo. Puoi anche scegliere più componenti aggiuntivi.
   4. Nella sezione **Storage Disks**, fai clic su **Add-ons** e seleziona **{{site.data.keyword.backup_notm}}**. Scegli l'opzione che corrisponde a ciò di cui si ha bisogno.
   5. In **Interfaccia di rete**, seleziona Velocità porta di uplink e gli eventuali componenti aggiuntivi che desideri.
3. Sulla destra, riesamina il riepilogo del tuo ordine.
4. Dopo che hai riesaminato i termini e le condizioni, seleziona la casella **Ho letto e accetto gli accordi di servizio di terze parti**.
5. Fai clic su **Provisioning**. Vieni reindirizzato a una schermata con il tuo numero dell'ordine di provisioning. Puoi stampare la schermata in quanto è anche la tua ricevuta dell'ordine di provisioning.

   Puoi anche salvare questo ordine senza acquistare facendo clic su **Salva come preventivo**.
   {:tip}

Al tuo amministratore viene inviata una serie di e-mail relative alla conferma di ricezione dell'ordine di provisioning, all'approvazione ed elaborazione dell'ordine di Provisioning e al completamento del Provisioning. L'e-mail sul completamento del Provisioning include un collegamento alla tua pagina *Device Details* a cui puoi accedere dopo l'accesso a {{site.data.keyword.cloud_notm}}. Puoi anche accedere direttamente al {{site.data.keyword.slportal}}.

### Conferma dell'acquisto di {{site.data.keyword.backup_notm}}
1. Nella [console {{site.data.keyword.cloud_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")]https://{DomainName}){:new_window}, fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**.</br>
   In alternativa, puoi accedere al [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Device** > **Device List**.
2. Individua il nuovo server che hai ordinato.
  - Se accanto all'URL vedi un'icona di orologio, devi aspettare per continuare con la conferma dell'acquisto di {{site.data.keyword.backup_notm}}. Puoi aggiornare la pagina per vedere uno stato aggiornato sul nuovo server. Quando l'icona di orologio non è più presente, puoi procedere con i passi successivi per confermare l'acquisto del servizio {{site.data.keyword.backup_notm}}.
  - Quando l'icona di orologio non viene più visualizzata per il tuo server, fai clic sul collegamento (l'URL del server) per accedere alla pagina **Device Details**.
3. Fai clic sulla scheda **Storage** per visualizzare le informazioni su {{site.data.keyword.backup_notm}}.
4. Esamina la sezione {{site.data.keyword.backup_notm}} e verifica che la dimensione che era stata selezionata durante il processo di acquisto sia visualizzata.

## Acquisto di {{site.data.keyword.backup_notm}} come un upgrade
{: #purchasingasupgrade}

### Seleziona un server su cui installare {{site.data.keyword.backup_notm}}

1. Accedi alla console [{{site.data.keyword.cloud_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}){:new_window} e fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**.</br>
   In alternativa, puoi accedere al [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}.
2. Seleziona **Devices** > **Device List** dal menu principale. Trova il dispositivo per il quale desideri aggiungere il servizio di backup.
3. Fai clic sul nome dispositivo per andare alla pagina **Device Details**.

### Aggiunta (acquisto) del servizio {{site.data.keyword.backup_notm}}
1. Fai clic sulla scheda **Storage** e scorri verso il basso per individuare la sezione {{site.data.keyword.backup_notm}}.
2. Fai clic sul collegamento **Add**.
3. Nella finestra, seleziona un'ubicazione e una dimensione.
4. Seleziona il tipo di pagamento e fai clic su **Continue**
5. Se ne hai uno, immetti il **Promo Code** e fai clic su **Recalculate**.
6. Controlla il tuo ordine e fai clic sul collegamento per leggere i termini e le condizioni.
7. Fai clic sulla casella di spunta se accetti i termini e le condizioni.
7. Fai clic su **Place Order**.

### Conferma dell'acquisto dell'upgrade di {{site.data.keyword.backup_notm}}
1. Aggiorna la pagina **Device Details** e assicurati che sia selezionata la scheda **Storage**.
2. Esamina la sezione {{site.data.keyword.backup_notm}} e verifica che la dimensione che era stata selezionata durante il processo di acquisto sia visualizzata.

   Se la dimensione dell'archiviazione di backup continua a mostrare una capacità pari a zero, potrebbe essere necessario un secondo aggiornamento della pagina.
   {:tip}

Quando sei pronto, vai avanti e installa l'agent software sul server e configura la tua pianificazione del backup nel portale {{site.data.keyword.backup_notm}}. Per ulteriori informazioni, vedi l'[Esercitazione introduttiva](/docs/infrastructure/Backup?topic=Backup-gettingstarted).
