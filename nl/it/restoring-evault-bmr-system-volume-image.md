---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-14"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Ripristino di un'immagine del volume di sistema EVault BMR 

Se hai bisogno di ripristinare un backup dell'immagine Bare Metal da EVault, puoi ripristinarlo rapidamente dal nostro sistema EVault BMR Rescue Kernel. Questo ti consente di ripristinare il sistema senza la necessità di un sistema operativo avviabile ed è molto utile se il sistema operativo non è più utilizzabile o se le unità del sistema sono state sostituite.

## Avvio del sistema EVault BMR Rescue Kernel

Puoi accedere al sistema EVault BMR Rescue Kernel attraverso il {{site.data.keyword.slportal}}.
1. Accedi al [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Fai clic su **Storage** > **Backup** 
3. Fai clic sulla **freccia** accanto all'archivio.
4. Fai clic su **Initiate Bare Metal Restore**. Questa azione avvia una transazione che verrà completata in pochi minuti. Successivamente puoi accedere al server seguendo i passi descritti qui. Riceverai un'email quando il sistema completa il processo di avvio.


## Ripristino da EVault BMR Rescue Kernel

1. Quando la transazione di EVault BMR Rescue Kernel è stata caricata, puoi scegliere di accedervi in 2 modi diversi. 
  - Un client VNC e l'indirizzo IP privato/pubblico del tuo server e la password che è elencata nel {{site.data.keyword.slportal}} 
  - La console KVM della tua scheda IPMI.
  Entrambi questi modi funzionano correttamente. 
2. Dopo aver effettuato l'accesso a EVault BMR Rescue Kernel per la prima volta, verrà visualizzata la schermata iniziale per la selezione della lingua. Seleziona la lingua che preferisci e fai clic su **Next**.
<br/>![Figura 1: selezione della lingua BMR](/images/bmr1.png)<br/> Questa azione ti porta al contratto di licenza per il software. 
3. Se accetti i termini, seleziona la casella di spunta e fai clic su **Next** per continuare. <br/> Questa azione visualizza il menu principale di ripristino del sistema EVault. 
4. Per questa operazione, seleziona **Restore My System**.
<br/>![Figura 2: menu principale BMR](/images/bmr2.png)
5. Viene visualizzata la procedura guidata di ripristino del sistema EVault. Fornisce una panoramica generale di ciò che verrà fatto e dei passi necessari. Seleziona **Next** per continuare.
<br/>![Figura 3: procedura guidata BMR](/images/bmr3.png)
6. Seleziona un tipo di backup da cui ripristinare. Seleziona **EVault software** e fai clic su **Next** per continuare.
7. Nella schermata di **ubicazione backup**, seleziona l'archivio e immetti l'indirizzo dell'archivio, il numero di account EVault, il nome utente e la password dell'account EVault. Quindi, fai clic su **Next** per continuare.
<br/>![Figura 4: scegli l'ubicazione di backup](/images/bmr4.png)
8. Ora dovresti vedere il tuo sistema elencato in questa schermata. Assicurati che sia evidenziato e fai clic su **Next**.
<br/>![Figura 5: scegli il tuo sistema](/images/bmr5.png)
9. Nella schermata di **selezione del lavoro di backup**, seleziona il lavoro da cui eseguire il ripristino e fai clic su **Next**.
<br/>![Figura 6: scegli il tuo punto di ripristino](/images/bmr6.png)
10. Dal menu **Select Restore Point**, seleziona il punto di ripristino desiderato e fai clic su **Next**.
<br/>![Figura 8: scegli il punto di ripristino](/images/bmr8.png)
11. Seleziona i volumi di origine e di destinazione. Per ripristinare l'origine nella destinazione, trascina il volume di origine sul volume di destinazione.
<br/>![Figura 9: seleziona i volumi di origine e di destinazione](/images/bmr9.png)
12. Nella finestra di conferma della formattazione o unione dei dati, ci sono due opzioni. Per questo articolo, selezioniamo **Format** per un ripristino pulito che formatta il disco. Se vuoi unire i dati sul volume di destinazione, seleziona **Merge**.
<br/>![Figura 10: scegli l'unione](/images/bmr10.png)
13. Nella schermata principale del volume di origine e di destinazione. Fai clic su **Next**.
14. Nella schermata di riepilogo del piano di ripristino, seleziona la casella per accettare il piano e fai clic su **Next**.
<br/>![Figura 11: avvia il ripristino](/images/bmr11.png)
15. Viene visualizzata la schermata di avanzamento del ripristino che ti mostra lo stato di avanzamento in corso.
<br/>![Figura 12: avanzamento del ripristino](/images/bmr12.png)
16. Al termine, viene visualizzata una finestra di notifica in cui viene indicato che il ripristino è stato completato correttamente. Fai clic su **OK**.
17. Nella schermata di avanzamento del ripristino. Fai clic su **Next**.
18. Nella schermata finale, seleziona la casella per riavviare il sistema, quindi seleziona **Finish** e il server si avvierà nell'immagine del volume ripristinata.
  Il ripristino è ora completo. <br/>
  **Nota**: la prima volta che questo accadrà, vedrai il messaggio di arresto imprevisto. È completamente normale con questo tipo di backup e andrà via dopo il primo avvio. 
