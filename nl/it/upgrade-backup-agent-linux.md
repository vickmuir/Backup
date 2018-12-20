---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Upgrade dell'agent software di backup per Linux

L'agent {{site.data.keyword.backup_notm}} più recente può essere scaricato dalla sezione Dashboard quick links del tuo portale {{site.data.keyword.backup_notm}}.
{:tip}

Seguire il processo di upgrade garantisce che tu possa eseguire un upgrade del tuo agent {{site.data.keyword.backup_notm}} senza perdere la registrazione

1. Accedi al tuo host a livello root.
2. Scarica la versione più recente dell'agent.
   ```
   wget -N downloads.service.softlayer.com/evault/Agent-Linux-x64-8.11.5251.tar.gz2.
   ```
   {:pre}

3. Estrai il contenuto del file scaricato.

   ```
   tar -xzvf Agent-Linux-x64-8.11.5251.tar.gz3.
   ```
4. Vai alla recente directory di installazione
   ```
   cd Agent-Linux-x64-8.11.5251/4.
   ```

5. Esegui lo script di installazione.
   ```
   ./install.sh
   ```
   {:pre}

6. Rispondi alle richieste selezionando `N` per non registrare il computer come un nuovo host, selezionando la tua lingua e `A` per crittografare i dati utilizzando il metodo di crittografia integrato.

7. Se l'installazione ha esito positivo, viene registrata in `/opt/BUAgent/Install.log`.
