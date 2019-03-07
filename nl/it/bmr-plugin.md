---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Installazione del plug-in Bare Metal Restore
{: #BMRplugin}

BMR è una soluzione di ripristino di emergenza per Microsoft Windows. Puoi utilizzare BMR per ripristinare il server da uno stato bare metal quando si verifica un'emergenza, ad esempio quando si verifica un malfunzionamento del sistema operativo o hardware. Con BMR, puoi ripristinare rapidamente l'immagine del sistema da un'ubicazione sicura e protetta gestita da {{site.data.keyword.BluSoftlayer_full}}.

BMR è un prodotto solo per Microsoft Windows sui server fisici. Non è disponibile per i server virtuali. I ripristini bare metal per le distribuzioni Linux non sono supportati. BMR è supportato solo da agent Backup 8.30 o versioni precedenti. (30 giungo 2018).
{:important}

**Capacità fornite**

- Ripristina il tuo sistema in un momento specifico.
- Ripristina il tuo sistema da backup di immagini o file.
- Ripristina il tuo sistema dai backup che sono memorizzati su {{site.data.keyword.backup_notm}}.
- Una transazione di ripristino avviabile che puoi utilizzare per ripristinare i tuoi dati senza un sistema di avvio.

## Ordinazione del plug-in
{: #orderingBMR}

1. Accedi alla console [{{site.data.keyword.cloud_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}){:new_window} e fai clic sull'icona **menu** nell'angolo superiore sinistro. Seleziona **Infrastruttura classica**. <br/>
   In alternativa, puoi accedere al [{{site.data.keyword.slportal}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){:new_window}.
2. Fai clic su **Storage** > **Backup** per visualizzare i server con un servizio di backup.
3. Seleziona il tuo account e fai clic su **Order plug-ins**.
4. Seleziona **{{site.data.keyword.backup_notm}} plug-in - BMR (Bare Metal Restore)** e fai clic su **Continue**.
5. Se ne hai uno, immetti il tuo codice promozionale e fai clic su **Recalculate**.
6. Vengono visualizzati i costi aggiornati. Riesamina l'ordine.
7. Seleziona la casella per indicare che hai letto e accettato gli accordi di servizio di terze parti.
8. Fai clic su **Place Order**.

## Download della guida utente
{: #BMRUserGuide}

Connettiti alla rete {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} in modo da poter accedere e scaricare la guida utente dalla [documentazione di {{site.data.keyword.backup_notm}} scaricabile ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}
