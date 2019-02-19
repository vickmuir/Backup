---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Ripristino da un backup
{: #simplerestore}

Utilizza questa procedura per completare un ripristino di file con {{site.data.keyword.backup_full}}. Per ripristinare un'immagine del sistema, segui le istruzioni di [Windows BMR](restore-bmr-system-volume-image.html).

## Avvio del portale {{site.data.keyword.backup_notm}}

Ricordati di avviare la tua connessione {{site.data.keyword.BluVPN}} per ottenere l'accesso alla rete privata {{site.data.keyword.BluSoftlayer_full}}. In caso contrario, il link del portale {{site.data.keyword.backup_notm}} non funziona.
{:important}

1. Accedi alla [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/){:new_window} e fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**. <br/>
   In alternativa, puoi accedere al [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Storage** > **Backup** per visualizzare i server con un servizio di backup.
3. Seleziona il server in cui si trovano i file di cui eseguire il ripristino. Fai clic sulla freccia per visualizzare il link del portale {{site.data.keyword.backup_notm}}.
4. Fai clic su **{{site.data.keyword.backup_notm}} portal** per avviare il client del portale {{site.data.keyword.backup_notm}} nel tuo browser.

## Ripristino dei tuoi dati

1. Nel riquadro di navigazione a sinistra, fai clic su **All Agents**.
2. Fai clic sull'agent per visualizzare i lavori.
3. Fai clic sul lavoro che contiene i dati desiderati.
4. Fai clic su **Run Restore**.
5. Seleziona l'origine di ripristino.
6. Seleziona la versione di backup.
7. Immetti la password di crittografia.
8. Fai clic su **Next** per continuare.
9. Seleziona le caselle di spunta accanto ai file e alle directory che vuoi includere. Fai quindi clic su **Include** per salvare le tue scelte.
10. Puoi filtrare ulteriormente le tue selezioni utilizzando la finestra che appare o fare clic su **OK** per utilizzare le selezioni effettuate così come sono.
Dopo aver incluso le tue scelte di file e directory, i file non possono più essere selezionati nel riquadro dei file di dati. Vengono visualizzati nel riquadro dell'insieme di backup sul lato destro.

   Puoi ripetere il passo 10 per aggiungere altri file o per rimuovere i file che hai aggiunto precedentemente (utilizzando il pulsante **Exclude**). Puoi anche utilizzare **Remove** per eliminare qualsiasi voce dal riquadro **Backup Set**.
   {:tip}

11. Quando il tuo insieme di backup è configurato nel modo desiderato, fai clic su **Next** per continuare.
12. Lascia le impostazioni predefinite nel riquadro successivo o personalizza il ripristino in base alle tue preferenze. Fai quindi clic su **Run Restore**.
13. I file sono ripristinati quando lo stato visualizza **Restore completed** sulla schermata **Process Details**.
