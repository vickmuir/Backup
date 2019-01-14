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

# Plug-in für Bare-Metal-Wiederherstellung installieren

Die Bare-Metal-Wiederherstellung (BMR, Bare Metal Restore) ist eine Disaster-Recovery-Lösung für Microsoft Windows. Mit BMR können Sie Ihren Server aus einem Bare-Metal-Status nach einem schwerwiegenden Zwischenfall wiederherstellen. Dieser Fall kann beispielsweise eintreten, wenn das Betriebssystem oder eine Hardwarekomponente ausfällt. Mit BMR können Sie das Systemimage schnell von einer sicheren, geschützten Position wiederherstellen, die von {{site.data.keyword.BluSoftlayer_full}} verwaltet wird.

BMR ist ein Produkt, das nur für Microsoft Windows auf physischen Servern geeignet ist. Für virtuelle Server ist es nicht verfügbar. Bare-Metal-Wiederherstellungen für Linux-Distributionen werden nicht unterstützt. BMR wird nur vom Sicherungsagenten (Backup Agent) 8.30 oder früheren Versionen unterstützt. (Stand: 30. Juni 2018)
{:important}

**Bereitgestelltes Leistungsspektrum**

- Wiederherstellung eines Systems für einen ausgewählten Zeitpunkt.
- Wiederherstellung eines Systems aus einem Image oder aus dateibasierten Sicherungen.
- Wiederherstellung eines Systems aus Sicherungen, die in der {{site.data.keyword.backup_notm}}-Instanz gespeichert sind.
- Startbare Wiederherstellungstransaktion, die eine Wiederherstellung der Daten ohne ein bootfähiges System ermöglicht.

## Plug-in bestellen

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}-Konsole ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}){:new_window} an und klicken Sie oben links auf das **Menüsymbol**. Wählen Sie **Klassische Infrastruktur** aus. <br/>
   Alternativ können Sie sich am [{{site.data.keyword.slportal}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){:new_window} anmelden.
2. Klicken Sie auf **Speicher** > **Sicherung**, um die Server mit Backup-Service anzuzeigen.
3. Wählen Sie Ihr Konto aus und klicken Sie auf **Plug-ins bestellen**.
4. Wählen Sie **{{site.data.keyword.backup_notm}}-Plug-in - BMR (Bare-Metal-Wiederherstellung)** aus und klicken Sie auf **Weiter**.
5. Geben Sie einen gegebenenfalls verfügbaren Werbeaktionscode ein und klicken Sie auf **Neu berechnen**.
6. Die aktualisierten Gebühren werden angezeigt. Prüfen Sie Ihre Bestellung.
7. Wählen Sie das Kontrollkästchen aus, um anzugeben, dass Sie die Servicevereinbarungen der anderen Anbieter gelesen haben und akzeptieren.
8. Klicken Sie auf **Bestellung aufgeben**.

## Benutzerhandbuch herunterladen

Stellen Sie eine Verbindung zum {{site.data.keyword.BluSoftlayer_full}}-Netz mit {{site.data.keyword.BluVPN}} her, damit Sie auf das Benutzerhandbuch zugreifen und es über die [für den Download verfügbare {{site.data.keyword.backup_notm}}-Dokumentation ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window} herunterladen können. 
