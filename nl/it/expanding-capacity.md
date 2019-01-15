---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}


# Espansione della capacità dell'archivio

Gli utenti {{site.data.keyword.BluSoftlayer_full}} correnti sono in grado di espandere la dimensione del loro archivio fino a 4000 GB. Non hanno bisogno di creare un duplicato o di migrare manualmente i dati in un volume più grande. Il processo di aumento del limite non causa alcuna interruzione o mancanza di accesso.

## Ordine di un incremento

1. Accedi alla [console {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} e fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**.<br/>
   In alternativa, puoi accedere al [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Storage** > **Backup** per visualizzare i server con un servizio di backup.
3. Seleziona l'archivio che vuoi estendere.
4. Fai clic su **Actions** e seleziona **Modify {{site.data.keyword.backup_notm}}**.
5. Nella schermata successiva, seleziona la nuova dimensione e fai clic su **Upgrade**.

## Fatturazione

La fatturazione per il volume viene automaticamente aggiornata per aggiungere la differenza proporzionale del nuovo prezzo al ciclo di fatturazione corrente. Successivamente, la nuova quantità completa viene fatturata nel prossimo ciclo di fatturazione.

Lo stesso processo può essere utilizzato per ridimensionare il tuo {{site.data.keyword.backup_notm}}.
{:tip}
