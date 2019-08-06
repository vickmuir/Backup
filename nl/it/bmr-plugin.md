---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud backup, bare metal restore, bmr, plug-in, plugin, EVault, Carbonite, baremetal, point-in-time restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Informazioni sul plug-in Bare Metal Restore
{: #BMRplugin}

Bare Metal Restore è una soluzione di ripristino di emergenza. Puoi utilizzare BMR per ripristinare il server da uno stato bare metal quando si verifica un'emergenza, ad esempio quando si verifica un malfunzionamento del sistema operativo o hardware. Con BMR, puoi ripristinare rapidamente l'immagine del sistema da un'ubicazione sicura e protetta gestita da {{site.data.keyword.cloud}}.

BMR è un prodotto solo per Windows sui server fisici. Non è disponibile per i server virtuali. I ripristini bare metal per le distribuzioni Linux non sono supportati.
{:important}

## Capacità fornite
{: #BMRcapabilities}

- Ripristina il tuo sistema in un momento specifico.
- Ripristina il tuo sistema da backup di immagini o file.
- Ripristina il tuo sistema dai backup che sono memorizzati su {{site.data.keyword.backup_notm}}.
- Avvia una transazione di ripristino che puoi utilizzare per ripristinare i tuoi dati senza un sistema di avvio.

## Installazione del plug-in BMR
{: #installingBMR}

Il plug-in viene installato durante l'installazione dell'agent Windows. Il plug-in può essere installato contemporaneamente all'agent oppure può essere installato successivamente, rieseguendo l'installazione con la selezione **Modify** .

## Configurazione del lavoro di backup BMR
{: #configBMRplugin}

Per ulteriori informazioni, vedi [Configurazione dei lavori di backup BMR](/docs/infrastructure/Backup?topic=Backup-configureBMR).

## Ripristino di un'immagine del volume di sistema BMR
{: #restoringBMimage}
Per ulteriori informazioni, vedi [Ripristino di un'immagine del volume di sistema BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR).

## Download della guida utente
{: #BMRUserGuide}

Connettiti alla rete {{site.data.keyword.cloud}} con {{site.data.keyword.BluVPN}} in modo da poter accedere alla guida utente e scaricarla da [Downloadable {{site.data.keyword.backup_notm}} Documentation](http://downloads.service.softlayer.com/evault/Documentation/){: external}
