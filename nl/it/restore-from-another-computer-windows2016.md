---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

---

# Ripristino di un lavoro da un altro computer su Windows 2016
{: #restorefromother2016}

Utilizza questa procedura per completare il ripristino di un file da un altro computer utilizzando il Windows Central Control in Windows 2016.

1. Esegui il controllo remoto del tuo server Windows 2016 tramite RDP.
2. Apri CentralControl.
3. Fai clic con il tasto destro su **Agent** e seleziona **Agent Configuration**.
4. Rimuovi le impostazioni correnti dell'archivio da CentralControl selezionando la voce e facendo clic su **Delete**.
5. Fai clic su **New** e, sulla schermata successiva, seleziona **Re-register previously registered computer**. Fai clic su **Next**.
6. Immetti l'indirizzo di rete, fai clic su **Add** e quindi su **Next**.
7. Immetti i nuovi valori di porta, fai clic su **Add** e quindi su **Next**.
8. Nella schermata delle impostazioni di connessione, immetti il numero di secondi/minuti desiderato.
9. Nella schermata di autenticazione, immetti le tue credenziali e fai clic su **Next**.
10. Viene visualizzata la finestra dei computer registrati che visualizza il nome host del tuo server. Fai clic su **Next**.
11.	Quando la procedura guidata di configurazione dell'archivio termina la raccolta delle tue informazioni, fai clic su **Finish** per completare la registrazione.
12. Quando richiesto, conferma di voler procedere con la ri-registrazione.
13. Al termine della registrazione, fai clic su **Restore** dalla barra dei menu.
9.	Seleziona il set sicuro appropriato e immetti la password di crittografia. Fai clic su **Next**.
10.	Seleziona i file che vuoi ripristinare, seleziona le opzioni predefinite e fai clic su **Finish**.
11.	Al termine del ripristino, rimuovi la registrazione dell'archivio e effettua di nuovo la registrazione con le informazioni sull'account dell'archivio corrente.
