---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-12"

---
{:new_window: target="_blank"}

# Ripristino da un backup

Utilizza questa procedura per completare il ripristino di un file con EVault. Per ripristinare un'immagine del sistema, segui le istruzioni di [Windows BMR](restoring-evault-bmr-system-volume-image.html).

## Avvio di WebCC

**Nota**: ricorda di avviare la tua connessione {{site.data.keyword.BluVPN}} per ottenere l'accesso alla rete privata {{site.data.keyword.BluSoftlayer_full}}. Il link WebCC altrimenti non funziona.

1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e fai clic su **Storage** > **Backup** dal menu principale per visualizzare i server con il servizio EVault Backup.
2. Seleziona il server in cui si trovano i file di cui eseguire il ripristino. Fai clic sulla freccia per visualizzare il link WebCC.
3. Fai clic su **WebCC** per avviare il client WebCC nel tuo browser.

## Ripristino dei tuoi dati

1. Nel riquadro di navigazione a sinistra, fai clic su **All Agents**.
2. Fai clic sull'agent per visualizzare i lavori.
3. Fai clic sul lavoro che contiene il backup desiderato.
4. Fai clic su **Run Restore**.
5. Selezione un'origine di ripristino.
6. Selezione una versione del backup.
7. Immetti la password di crittografia.
8. Fai clic su **Next** per continuare.
9. Seleziona le caselle di spunta accanto ai file e alle directory che vuoi includere, quindi fai clic su **Include** per salvare le tue scelte.
10. Puoi filtrare ulteriormente le tue selezioni utilizzando la finestra che appare o fare clic su **OK** per utilizzare le selezioni effettuate così come sono. <br/>
Dopo aver incluso le tue scelte di file e directory, i file non possono più essere selezionati nel riquadro **Data Files**. Vengono visualizzati nel riquadro **Backup Set** a destra. <br/>**Nota**: puoi ripetere il passo 10 per aggiungere altri file o per rimuovere i file che hai aggiunto precedentemente (utilizzando il pulsante **Exclude**). <br/>Puoi anche utilizzare **Remove** per eliminare qualsiasi voce dal riquadro **Backup Set**.
11. Quando il tuo insieme di backup è configurato nel modo desiderato, fai clic su **Next** per continuare.
12. Lascia le impostazioni predefinite nel riquadro successivo o personalizza il ripristino in base alle tue preferenze, quindi fai clic su **Run Restore**.
13. I file sono ripristinati quando lo stato visualizza **Restore completed** sulla schermata **Process Details**.
