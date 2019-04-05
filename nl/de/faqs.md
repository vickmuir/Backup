---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud backup, EVault, Carbonite, backup, backup frequency, backup types, backup retention scheme, plugins, delta technology, open files, pricing

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:faq: data-hd-content-type='faq'}


# Häufig gestellte Fragen
{: #faqs}

## Welche Art von Anwendungen können gesichert werden?
{: faq}

{{site.data.keyword.backup_full}} kann zum Sichern verschiedener Anwendungen verwendet werden. {{site.data.keyword.BluSoftlayer_full}} bietet auch Softwareagenten zur Sicherung für einige der gängigeren Softwaresysteme, wie beispielsweise folgende:

- [Bare-Metal-Wiederherstellung](/docs/infrastructure/Backup?topic=Backup-BMRplugin)
- [Microsoft Exchange](/docs/infrastructure/Backup?topic=Backup-Exchangeplugin)
- [Microsoft SQL](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin#MSSQLplugin)
- [Oracle](/docs/infrastructure/Backup?topic=Backup-Oracleplugin#Oracleplugin)
- [VMware VRA](/docs/infrastructure/Backup?topic=Backup-VRA#VRA)

Die hier aufgeführten Plug-ins sind nur mit Windows-Servern kompatibel, mit Ausnahme des Oracle- oder VMware-Plug-ins. Jeder Agent ist als Add-on für Ihren Sicherungsservice kostenlos verfügbar. 

<hr>

## Wie häufig können die Daten gesichert werden?
{: faq}

Innerhalb des {{site.data.keyword.backup_notm}}-Portals können Sicherungen manuell erstellt oder als einzelne Instanz geplant oder als wiederholend auszuführend geplant werden. Wiederholte Sicherungen können täglich, wöchentlich, monatlich oder nach einem angepassten Zeitplan erfolgen und jederzeit aktualisiert oder abgebrochen werden.

Sehr häufige Sicherungen, die mehrmals täglich oder stündlich ausgeführt werden, können zur Beschädigung von Sicherungsjobs führen. Diese Beschädigung tritt auf, weil die Sicherungsvault nicht genügend Zeit erhält, um erforderliche Hintergrundwartungstasks auszuführen. Sicherungsjobs haben Vorrang vor Wartungsaufgaben. Im Falle von sehr häufigen Sicherungen führt die Vault weiterhin die Sicherungsjobs aus. Dies bewirkt, dass die Anzahl der Sicherungsgruppen zunimmt.
{:note}

<hr>

## Wie funktionieren die Aufbewahrungsschemas?
{: faq}

{{site.data.keyword.backup_notm}} ermöglicht es Ihnen, die Datenspeicherung davon abhängig zu machen, wie weit zurück Sie eine Rollback-Operation durchführen möchten. Die Aufbewahrungsschemas des Typs **Täglich** behalten Daten für sieben Tage bei, während die Schemas des Typs **Wöchentlich** Daten für einen Monat und die Schemas des Typs **Monatlich** Daten für ein Jahr beibehalten. Am Ende jedes Zeitraums wird der älteste Datenbestand turnusmäßig ausgelagert und die erste erstellte Deltasicherung wird zum ältesten verfügbaren Wiederherstellungspunkt.

Sie können Standardaufbewahrungsschemas ändern und angepasste Aufbewahrungsschemas erstellen. IBM empfiehlt jedoch, die Standardaufbewahrungszeiträume als Ausgangspunkt zu verwenden. Wenn Sie ein neues Aufbewahrungsschema erstellen oder ein vorhandenes Aufbewahrungsschema ändern, sollten Sie sicherstellen, dass die Archivierungsoption nicht ausgewählt ist. Das Archivieren wird nicht unterstützt.
{:tip}

<hr>

## Was ist Delta-Technologie?
{: faq}

Die erste Sicherung, bei der es sich um eine vollständige Gesamtsicherung handelt, ist ein so genannter 'Seed'. Die nächste und alle nachfolgenden Sicherungen werden als 'Deltasicherungen' bezeichnet, weil sie nur Änderungen enthalten, sind jedoch zu Gesamtsicherungen äquivalent und gelten als Gesamtsicherungen. Dies bedeutet, dass Sie aus diesen Sicherungen alle oder einige Dateien wiederherstellen können. Diese Technologie ermöglicht die Durchführung von Gesamtsicherungen in jeder Sitzung, spart jedoch enorm Mengen an Speicherplatz in der Vault und verringert die Zeit, die zur Ausführung aller nachfolgenden Sicherungen benötigt wird.

<hr>

## Sind die Sicherungen sicher?
{: faq}

Standardmäßig findet die gesamte Verschlüsselung über die Verbindung unter Verwendung des Verschlüsselungstyps 'AES 256-Bit' statt. Sie können außerdem auswählen, dass Daten in einem verschlüsselten Format unter Verwendung von AES 256-Bit gespeichert werden.

Sie müssen sich Ihr Verschlüsselungskennwort merken. Ohne Ihr Kennwort können Ihre Daten nicht wiederhergestellt werden. Falls Sie Ihr Kennwort vergessen, sind Sie nicht in der Lage, Ihre Daten wiederherzustellen.
{:important}

Komprimierungsverhältnisse ermöglichen die Verwendung von keiner Komprimierung bis hin zu einem maximalen Komprimierungsverhältnis, das je nach Dateityp zwischen 20 und 30 Prozent liegen kann.

<hr>

## Welche Informationen werden mit den Systemstatussicherungen gespeichert?
{: faq}

Systemstatussicherungen umfassen unter anderem die COM- und Klassenregistrierungsdatenbank, die Registry, Bootdateien Systemdateien und Leistungszähler, sind jedoch nicht hierauf beschränkt. Maßgeblich ist jeweils das System. Systemdateien variieren nach Betriebssystem und Service-Packs des Systems. Normalerweise gibt es mehrere Tausend dieser Dateien. MS Windows erstellt eine dynamische Liste dieser DLLs, wenn Sie sie in die Sicherung einbeziehen. Durch die Einbeziehung der Systemdateien können Sie eine Wiederherstellung bei beschädigten Systemdateien, beim versehentlichen Entfernen von Service-Packs oder bei einer erforderlichen Bare-Metal-Wiederherstellung vornehmen. Sie können zum Status der Sicherung zurückkehren, ohne das Betriebssystem mit dem Installationskit erneut installieren und anschließend jedes Service-Pack separat installieren zu müssen.

Es ist keine Benutzerdatendatei in der Systemstatussicherung enthalten. Ein Systemstatussicherungsjob muss als eigenständiger Job konfiguriert werden. Es darf keine andere Datenquelle vorhanden sein, die in den Systemstatussicherungsjob eingeschlossen wird.
{:important}

<hr>

## Was passiert mit geöffneten Dateien?
{: faq}

Der Basisclient ist standardmäßig mit ausgereifter Technologie ausgestattet, um die meisten geöffneten Dateien im Betriebssystem zu behandeln.

<hr>

## Wo finde ich Informationen zur Preisstruktur?
{: faq}

Weitere Informationen finden Sie in [Sicherungsspeicher ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/cloud/backup-and-restore){:new_window} und in [EVault on IBM Cloud: Preisstruktur ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/cloud/backup/pricing){:new_window}.

<hr>

## Kann die Kapazität von {{site.data.keyword.backup_notm}} erhöht oder verringert wird, ohne die Sicherungen zu beeinträchtigen?
{: faq}

Sie können die Vault-Größe im [{{site.data.keyword.slportal}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){:new_window} erhöhen oder verringern. Die Änderung der Kapazität wirkt sich nicht auf die Integrität der Daten aus, die in der Vault gespeichert sind. Weitere Informationen finden Sie im Abschnitt zum Thema [Kapazität erhöhen](/docs/infrastructure/Backup?topic=Backup-expandcapacity#expandcapacity).

<hr>

## Was passiert, wenn die Kapazität von {{site.data.keyword.backup_notm}} überschritten wird?
{: faq}

Sie können Ihre Sicherungen auch dann speichern und abrufen, wenn Sie den Grenzwert für die Kapazität erreicht haben, die Sie zuvor erworben haben. In wird jedoch für jedes zusätzlich genutzte GB in der Abrechnung eine zusätzliche Gebühr in Rechnung gestellt.

<hr>

## Wie kann ich Benachrichtigungen im {{site.data.keyword.backup_notm}}-Portal einrichten, die mich darüber informieren, ob meine Sicherungen fehlschlagen? 
{: faq}

Benachrichtigungen können auf der Registerkarte 'Erweitert' eingerichtet werden. Gehen Sie den Anweisungen unter **Quick Links** im {{site.data.keyword.backup_notm}}-Portal entsprechend vor.

<hr>

## Wenn das BMR-Plug-in verwendet wird, kann von einer einzelnen Platte zu einer RAID-Platteneinheit gewechselt werden?

Ja, das funktioniert. Sie müssen jedoch aufgrund der durch das RAID-Array verursachten Größenabnahme eine Einheit mit hoher Kapazität auswählen.

<hr>

## Was passiert, wenn das BMR-Plug-in verwendet wird und das Image auf einer größeren Platte wiederhergestellt wird als der ursprüngliche Datenträger?
{: faq}

Falls Sie das Image auf einem größeren Datenträger als dem ursprünglichen Datenträger wiederherstellen, wird der übrigbleibende Bereich freigegeben. Beispiel: Wenn Sie die Daten eines Laufwerks mit 500-GB GB auf einem 1-TB-Datenträger wiederherstellen, werden 500 GB Plattenspeicherplatz freigegeben. Bei Windows 2008 können Sie das integrierte Datenträgerdienstprogramm verwenden, um die primäre Partition zu vergrößern. In Windows 2003 gibt es hingegen keine ähnliche integrierte Funktionalität, sodass Sie den Speicherbereich auf andere Weise zuordnen müssen.

<hr>

## Kann BMR für reguläre Sicherungen verwendet werden?
{: faq}

Bei einer BMR-Sicherung handelt es sich nicht um ein Plattenimage, sondern um ein Sicherungssystem für Systemdatenträgerimages. Das System ist nicht zur Erstellung regulärer Sicherungen gedacht, sondern dient als Ergänzung zu Systemen für solche Sicherungen.  

<hr>

##Kann BMR für Datenbanksicherungen verwendet werden?
{: faq}

Datenbanksicherungen müssen separat mit den herkömmlichen {{site.data.keyword.backup_notm}}-Methoden vorgenommen werden. BMR macht Plug-ins für SQL oder Oracle keinesfalls überflüssig. BMR verwendet zwar die VSS-Technologie zum Sichern geöffneter Dateien, es kann aber nicht in jedem Fall gewährleistet werden, dass die gesicherten Dateien transaktionskonsistent sind. Für solche Typen von Fachanwendungen empfiehlt sich die Erstellung von zwei Sicherungsjobs, nämlich einem Job zum Sichern der Betriebssystems- und Anwendungsbinärdateien und einem weiteren Job für die Anwendungsdaten.

<hr>

## Welche Arten von Wiederherstellungsjobs können mit BMR ausgeführt werden?

Sie können entweder eine vollständige Systemwiederherstellung durchführen oder einzelne Dateien aus der Sicherung für die Wiederherstellung auswählen. Der BMR-Sicherungsjob kann Ihren aktuellen Dateisicherungsjob ersetzen. Der Wiederherstellungsprozess kann wie ein konventioneller Sicherungsjob innerhalb des Betriebssystems ausgeführt werden.

<hr>

## Besitzt BMR Funktionen für die Sicherung von geöffneten Dateien?
{: faq}

BMR ist mit Funktionen zur Sicherung von geöffneten Dateien ausgestattet. BMR macht jedoch Plug-ins für SQL oder Oracle keinesfalls überflüssig. Klicken Sie [hier](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin), um die Installationsanweisungen für das MS SQL-Plug-in anzuzeigen.

<hr>

## Wie viel Plattenspeicherplatz und Zeit benötigt eine BMR-Wiederherstellung?
{: faq}

Eine Sicherung, die auf Basis einer Standardinstallation erstellt wird, benötigt etwa 6 GB. Die Wiederherstellung einer solchen Sicherung über einen 1-GB-Port dauert ungefähr 15 Minuten. Dieser Prozess wird auch durch die private Portgeschwindigkeit beeinflusst. Falls Sie schnellere Sicherungen und Wiederherstellungen benötigen, ist möglicherweise eine Erhöhung der Portgeschwindigkeit erforderlich.

<hr>

## Wozu wird VSS verwendet?
{: faq}

Die aktuelle Version des Plug-ins für SQL Server verwendet VSS (Volume Shadow Copy Services, Volumenschattenkopie-Dienste) zur Ausführung von Sicherungen. Mit VSS kann das Plug-in für SQL Server SQL-Datenbanken auch dann effektiv sichern, wenn diese mehrere Datenträger umfassen. Sicherungen können durchgeführt werden, während Anwendungen weiterhin Schreiboperationen auf dem Datenträger ausführen. Das Plug-in für SQL Server bietet Ihnen Datenkonsistenz innerhalb von Datenbanken und auch datenbankübergreifend. VSS ermöglicht die gleichzeitige Ausführung von mehreren Sicherungen.

<hr>

## Wird die 32-Bit-Version von EVault for Windows 8 noch unterstützt? 
{: faq}

Nein. Die 32-Bit-Version des Backup-Software-Agenten wurde zusammen mit den Windows Server 2008 Standard und Datacenter Editions im März 2017 zurückgezogen. 
