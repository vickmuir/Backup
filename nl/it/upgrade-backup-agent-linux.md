---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Upgrade dell'agent software di backup per Linux
{: #UpgradeinLinux}

L'agent backup più recente può essere scaricato dalla sezione Dashboard quick links del tuo portale {{site.data.keyword.backup_notm}}.
{:tip}

Seguire il processo di upgrade garantisce che tu possa eseguire un upgrade del tuo agent {{site.data.keyword.backup_notm}} senza perdere la registrazione

1. Accedi al tuo host a livello root.
2. Scarica la versione più recente dell'agent.
   ```
   wget -N downloads.service.softlayer.com/evault/Agent-Linux-x64-8.11.5251.tar.gz2
   ```
   {:pre}

3. Estrai il contenuto del file scaricato.

   ```
   tar -xzvf Agent-Linux-x64-8.11.5251.tar.gz3
   ```
4. Vai alla directory di installazione recente.
   ```
   cd Agent-Linux-x64-8.11.5251/4
   ```

5. Esegui lo script di installazione.
   ```
   ./install.sh
   ```
   {:pre}

6. Rispondi alle richieste selezionando la tua lingua, selezionando `N` per non registrare il computer come un nuovo host e `A` per crittografare i dati utilizzando il metodo di crittografia integrato.

7. Se l'installazione ha esito positivo, viene registrata in `/opt/BUAgent/Install.log`.
