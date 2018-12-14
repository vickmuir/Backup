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
- Wiederherstellung eines Systems aus Sicherungen, die im IBM Cloud-Backup gespeichert sind.
- Startbare Wiederherstellungstransaktion, die eine Wiederherstellung der Daten ohne ein bootfähiges System ermöglicht.
.
## Plug-in bestellen

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}/catalog/){:new_window} an und klicken Sie oben links auf das Symbol **Menü**. Wählen Sie **Klassische Infrastruktur** aus.

   Alternativ können Sie sich beim [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} anmelden.
2. Klicken Sie auf **Speicher** > **Sicherung**, um die Server mit Backup-Service anzuzeigen.
3. Wählen Sie Ihr Konto aus und klicken Sie auf **Plug-ins bestellen**.
4. Wählen Sie **{{site.data.keyword.backup_notm}}-Plug-in - BMR (Bare-Metal-Wiederherstellung)** aus und klicken Sie auf **Weiter**.
5. Geben Sie einen gegebenenfalls verfügbaren Werbeaktionscode ein und klicken Sie auf **Neu berechnen**.
6. Die aktualisierten Gebühren werden angezeigt. Prüfen Sie Ihre Bestellung.
7. Aktivieren Sie das Kontrollkästchen, um anzugeben, dass Sie die Servicevereinbarung eines anderen Anbieters gelesen haben und akzeptieren.
8. Klicken Sie auf **Bestellung aufgeben**.

## Benutzerhandbuch herunterladen

Stellen Sie eine Verbindung zum {{site.data.keyword.BluSoftlayer_full}}-Netz mit {{site.data.keyword.BluVPN}} her, damit Sie auf das Benutzerhandbuch zugreifen und es über [Für den Download verfügbare {{site.data.keyword.backup_notm}} Dokumentation ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window} herunterladen können.

## Häufig gestellte Fragen

**Kann ich mein System von einer Einzelplattenkonfiguration auf einen RAID-Array umstellen?**

Ja, das funktioniert. Sie müssen jedoch aufgrund der durch das RAID-Array verursachten Größenabnahme eine Einheit mit hoher Kapazität auswählen.

**Was passiert, wenn das Image auf einem Datenträger wiederhergestellt wird, der größer als der ursprüngliche Datenträger ist?**

Falls Sie das Image auf einem größeren Datenträger als dem ursprünglichen Datenträger wiederherstellen, wird der übrigbleibende Bereich freigegeben. Beispiel: Wenn Sie die Daten eines Laufwerks mit 500-GB GB auf einem 1-TB-Datenträger wiederherstellen, werden 500 GB Plattenspeicherplatz freigegeben. Bei Windows 2008 können Sie das integrierte Datenträgerdienstprogramm verwenden, um die primäre Partition zu vergrößern. In Windows 2003 gibt es hingegen keine ähnliche integrierte Funktionalität, sodass Sie den Speicherbereich auf andere Weise zuordnen müssen.

**Kann BMR für reguläre Sicherungen verwendet werden?**

Bei einer BMR-Sicherung handelt es sich nicht um ein Plattenimage, sondern um ein Sicherungssystem für Systemdatenträgerimages. Das System ist nicht zur Erstellung regulärer Sicherungen gedacht, sondern dient als Ergänzung zu Systemen für solche Sicherungen.  

**Kann BMR für Datenbanksicherungen verwendet werden?**

Datenbanksicherungen müssen separat mit den herkömmlichen IBM Cloud-Backup-Methoden vorgenommen werden. BMR macht Plug-ins für SQL oder Oracle keinesfalls überflüssig. BMR verwendet zwar die VSS-Technologie zum Sichern geöffneter Dateien, es kann aber nicht in jedem Fall gewährleistet werden, dass die gesicherten Dateien transaktionskonsistent sind. Für solche Typen von Fachanwendungen empfiehlt sich die Erstellung von zwei Sicherungsjobs, nämlich einem Job zum Sichern der Betriebssystems- und Anwendungsbinärdateien und einem weiteren Job für die Anwendungsdaten. Am Ende des Benutzerhandbuchs für BMR finden Sie einen diesbezüglichen Hinweis.

**Welche Arten von Wiederherstellungsjobs können mit BMR ausgeführt werden?**

Sie können entweder eine vollständige Systemwiederherstellung durchführen oder einzelne Dateien aus der Sicherung für die Wiederherstellung auswählen. Der BMR-Sicherungsjob kann Ihren aktuellen Dateisicherungsjob ersetzen. Der Wiederherstellungsprozess kann wie ein konventioneller Sicherungsjob innerhalb des Betriebssystems ausgeführt werden.

**Besitzt BMR Funktionen für die Sicherung von geöffneten Dateien?**

BMR ist mit Funktionen zur Sicherung von geöffneten Dateien ausgestattet. BMR macht jedoch Plug-ins für SQL oder Oracle keinesfalls überflüssig. Weitere Informationen zum MSSQL-Plug-in finden Sie [hier](mssql-plugin.html).

**Wie viel Plattenspeicherplatz und Zeit benötigt eine BMR-Wiederherstellung?**

Eine Sicherung, die auf Basis einer Standardinstallation erstellt wird, benötigt etwa 6 GB. Die Wiederherstellung einer solchen Sicherung über einen 1-GB-Port dauert ungefähr 15 Minuten. Dieser Prozess wird auch durch die private Portgeschwindigkeit beeinflusst. Falls Sie schnellere Sicherungen und Wiederherstellungen benötigen, ist möglicherweise eine Erhöhung der Portgeschwindigkeit erforderlich.
