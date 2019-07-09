---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-13"

keywords: IBM Cloud backup, bare metal restore, bmr, plug-in, plugin, EVault, Carbonite, baremetal, point-in-time restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Informationen zum Plug-in für Bare-Metal-Wiederherstellung
{: #BMRplugin}

Die Bare-Metal-Wiederherstellung (BMR, Bare Metal Restore) ist eine Disaster-Recovery-Lösung. Mit BMR können Sie Ihren Server aus einem Bare-Metal-Status nach einem schwerwiegenden Zwischenfall wiederherstellen. Dieser Fall kann beispielsweise eintreten, wenn das Betriebssystem oder eine Hardwarekomponente ausfällt. Mit BMR können Sie das Systemimage schnell von einer sicheren, geschützten Position wiederherstellen, die von {{site.data.keyword.cloud}} verwaltet wird.

BMR ist ein Produkt, das nur für Microsoft Windows auf physischen Servern geeignet ist. Für virtuelle Server ist es nicht verfügbar. Bare-Metal-Wiederherstellungen für Linux-Distributionen werden nicht unterstützt. BMR wird nur vom Sicherungsagenten (Backup Agent) 8.30 oder früheren Versionen unterstützt. (Stand: 30. Juni 2018)
{:important}

## Bereitgestelltes Leistungsspektrum
{: #BMRcapabilities}

- Wiederherstellung eines Systems für einen ausgewählten Zeitpunkt.
- Wiederherstellung eines Systems aus einem Image oder aus dateibasierten Sicherungen.
- Wiederherstellung eines Systems aus Sicherungen, die in der {{site.data.keyword.backup_notm}}-Instanz gespeichert sind.
- Startbare Wiederherstellungstransaktion, die eine Wiederherstellung der Daten ohne ein bootfähiges System ermöglicht.

## BMR-Plug-in installieren
{: #installingBMR}

Das Plug-in wird während der Installation des Windows-Agenten installiert. Das Plug-in kann zusammen mit dem Agenten oder auch später installiert werden, indem die Installation mit der Auswahl **Ändern** erneut ausgeführt wird.

## BMR-Sicherungsjob konfigurieren
{: #configBMRplugin}

Weitere Informationen finden Sie in [BMR-Sicherungsjobs konfigurieren](/docs/infrastructure/Backup?topic=Backup-configureBMR).

## BMR-Systemdatenträgerimage wiederherstellen
{: #restoringBMimage}
Weitere Informationen finden Sie in [BMR-Systemdatenträgerimage wiederherstellen](/docs/infrastructure/Backup?topic=Backup-restoreBMR).

## Benutzerhandbuch herunterladen
{: #BMRUserGuide}

Stellen Sie eine Verbindung zum {{site.data.keyword.cloud}}-Netz mit {{site.data.keyword.BluVPN}} her, damit Sie auf das Benutzerhandbuch zugreifen und es über die [für den Download verfügbare {{site.data.keyword.backup_notm}}-Dokumentation](http://downloads.service.softlayer.com/evault/Documentation/){: external} herunterladen können.
