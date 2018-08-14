---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# Configurazione di un lavoro di backup BMR su Windows

**Prerequisito**

Per creare un backup BMR devi acquistare il plugin BMR. BMR è disponibile solo per i server bare metal Windows. Nessuna opzione BMR è disponibile per VSI.

## Avvio di WebCC
**Nota**: per poter avviare WebCC devi essere connesso alla rete privata di {{site.data.keyword.BluSoftlayer_full}}.
1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e fai clic su **Storage** > **Backup** dal menu principale per visualizzare i server con il servizio EVault Backup. 
2. Seleziona il server in cui si trovano i file di cui eseguire il backup. Fai clic sulla freccia di espansione rivolta verso destra per visualizzare il link WebCC.
4. Fai clic su **WebCC Login** per avviare il client WebCC nel tuo browser.
  **Nota**: se WebCC non si avvia, potresti avere un problema con la tua connessione VPN. Potresti anche vedere un messaggio che indica che il modulo che stai inviando non è sicuro. Questo messaggio è previsto e puoi procedere con l'invio del modulo.
  
## Configurazione di un lavoro di backup BMR

1. Nel riquadro di navigazione a sinistra, fai clic su **All Agents** per visualizzare gli agent EVault correnti.
2. Fai clic su **This is a new Agent I would like to configure**.
3. Immetti un nome e una descrizione per il lavoro che stai configurando o creando.
4. Per **Backup Source Type**, seleziona il tipo di file system di cui vuoi eseguire il backup dall'elenco e fai clic su **Next**
5. Viene visualizzato il menu **Job Type Selection**. Seleziona la casella accanto a **Bare Metal Restore** e fai clic su **Next** per continuare.
6. Fai clic su **Yes** nelle finestre di conferma.
7. La schermata mostra che il nuovo lavoro è ora nell'insieme di backup. Fai clic su **Next**.
8. La schermata visualizza le opzioni di crittografia e le opzioni di backup avanzate. Normalmente queste opzioni non sono necessarie. Fai clic su **Next**.   
9. Nella pagina **Create a schedule**, hai due scelte. 
   - Fai clic su **Next** per creare un lavoro manuale e procedi all'esecuzione del nuovo lavoro
   - Fai clic su **Add** per pianificare un lavoro di backup basato sul tempo. 
     1. Seleziona i giorni e l'ora del giorno per eseguire i tuoi backup. 
     2. Seleziona il tuo schema di conservazione. Per ulteriori informazioni sugli schemi di conservazione, fai clic [qui](evault-backup-faq.html)
     3. Dopo aver configurato la tua pianificazione di backup, fai clic su **Ok** per salvarla. Il tuo lavoro pianificato viene aggiunto all'elenco di lavori pianificati. 
10. Seleziona un archivio per il tuo lavoro di backup e fai clic su **Save Changes**.


## Esecuzione di un lavoro di backup BMR

  - Se hai pianificato un lavoro di backup basato sul tempo, non hai bisogno di fare altro. Il tuo lavoro viene eseguito automaticamente come pianificato.
  - Se hai configurato un lavoro manuale (senza una pianificazione basata sul tempo), puoi eseguirlo selezionando la relativa riga nell'elenco lavori e facendo clic su **Run backup**. <br/> Come per i lavori basati sul tempo, puoi scegliere le opzioni di **Retention Scheme** e **Advanced backup options**. Dopo aver effettuato le tue scelte di configurazione, fai clic su **Start backup** per avviare il lavoro.
