---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:faq: data-hd-content-type='faq'}


# Häufig gestellte Fragen

## Welche Art von Anwendungen können gesichert werden?
{: faq}

{{site.data.keyword.backup_full}} kann zum Sichern verschiedener Anwendungen verwendet werden. {{site.data.keyword.BluSoftlayer_full}} bietet jedoch Softwareagenten zur Sicherung für einige der gängigeren Softwaresysteme wie beispielsweise Folgende:

- Bare-Metal-Wiederherstellung
- Microsoft Exchange
- Microsoft SQL
- Oracle

Die hier aufgeführten Plug-ins sind nur mit Windows-Servern kompatibel, mit Ausnahme des Oracle-Plug-ins. Jeder Agent ist als Add-on für Ihren Sicherungsservice verfügbar. Wenn Sie einen Agenten zu Ihrem Service hinzufügen wollen, können Sie sich direkt mit einem Mitarbeiter des Vertriebsteams in Verbindung setzen.

<hr>

## Wie oft können die Daten gesichert werden?
{: faq}

Innerhalb von WebCC können Sicherungen manuell erstellt oder als einzelne Instanz geplant oder als wiederholend auszuführend geplant werden. Wiederholte Sicherungen können täglich, wöchentlich, monatlich oder nach einem angepassten Zeitplan erfolgen und jederzeit aktualisiert oder abgebrochen werden.

Sehr häufige Sicherungen, die mehrmals täglich oder stündlich ausgeführt werden, können zur Beschädigung von Sicherungsjobs führen. Diese Beschädigung tritt auf, weil der Sicherungsvault nicht genügend Zeit erhält, um erforderliche Hintergrundwartungstasks auszuführen. Sicherungsjobs haben Vorrang vor Wartungsaufgaben. Im Falle von sehr häufigen Sicherungen führt der Vault weiterhin die Sicherungsjobs aus und das führt dazu, dass die Anzahl der Sicherungsgruppen zunimmt.{:note}

<hr>

## Wie funktionieren die Aufbewahrungsschemas?
{: faq}

{{site.data.keyword.backup_notm}} ermöglicht es Ihnen, die Datenspeicherung davon abhängig zu machen, wie weit zurück Sie eine Rollback-Operation durchführen möchten. Die Aufbewahrungsschemas des Typs **Täglich** behalten Daten für sieben Tage bei, während die Schemas des Typs **Wöchentlich** Daten für einen Monat und die Schemas des Typs **Monatlich** Daten für ein Jahr beibehalten. Am Ende jedes Zeitraums wird der älteste Datenbestand turnusmäßig ausgelagert und die erste erstellte Deltasicherung wird zum ältesten verfügbaren Wiederherstellungspunkt.

Sie können Standardaufbewahrungsschemas ändern und angepasste Aufbewahrungsschemas erstellen. Es wird jedoch dringend empfohlen, Standardaufbewahrungszeiträume als Ausgangspunkt zu verwenden. Wenn Sie ein neues Aufbewahrungsschema erstellen oder ein vorhandenes Aufbewahrungsschema ändern, sollten Sie sicherstellen, dass die Option Archivieren nicht ausgewählt ist. Das Archivieren wird nicht unterstützt.{:tip}

<hr>

## Was ist Delta-Technologie?
{: faq}

Die erste Sicherung, bei der es sich um eine vollständige Gesamtsicherung handelt, ist ein so genannter 'Seed'. Die nächste und alle nachfolgenden Sicherungen werden als 'Deltasicherungen' bezeichnet, weil sie nur Änderungen enthalten, sind jedoch zu Gesamtsicherungen äquivalent und gelten als Gesamtsicherungen. Dies bedeutet, dass Sie aus diesen Sicherungen alle oder einige Dateien wiederherstellen können. Diese Technologie ermöglicht die Durchführung von Gesamtsicherungen in jeder Sitzung, spart jedoch enorm Speicherplatz in der Vault und verringert die Zeit, die zur Ausführung aller nachfolgenden Sicherungen benötigt wird.

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

Systemstatussicherungen umfassen unter anderem die COM- und Klassenregistrierungsdatenbank, die Registry, Bootdateien Systemdateien und Leistungszähler, sind jedoch nicht hierauf beschränkt. Maßgeblich ist jeweils das System. Die Systemdateien variieren nach Betriebssystem und Service-Packs des Systems. Normalerweise gibt es mehrere Tausend dieser Dateien. MS Windows erstellt eine dynamische Liste dieser DLLs, wenn Sie sie in die Sicherung einbeziehen. Durch die Einbeziehung der Systemdateien können Sie eine Wiederherstellung bei beschädigten Systemdateien, bei einer versehentlichen Deinstallation von Service-Packs oder bei einer erforderlichen Bare-Metal-Wiederherstellung vornehmen. Sie können zum Status der Sicherung zurückkehren, ohne das Betriebssystem mit dem Installationskit erneut installieren und anschließend jedes Service-Pack separat installieren zu müssen.

Es ist keine Benutzerdatendatei in der Systemstatussicherung enthalten. Ein Systemstatussicherungsjob muss als eigenständiger Job konfiguriert werden. Es darf keine andere Datenquelle vorhanden sein, die in den Systemstatussicherungsjob eingeschlossen wird.{:important}

<hr>

## Was passiert mit geöffneten Dateien?
{: faq}

Der Basisclient ist standardmäßig mit ausgereifter Technologie ausgestattet, um die meisten geöffneten Dateien im Betriebssystem zu behandeln.

<hr>

## Wo finde ich Informationen zur Preisstruktur?
{: faq}

Weitere Informationen finden Sie unter [Sicherungsspeicher](https://www.ibm.com/cloud/backup-and-restore){:new_window} und [{{site.data.keyword.backup_notm}} on IBM Cloud: Preisstruktur](https://www.ibm.com/cloud/evault/pricing){:new_window}.

<hr>

## Kann die Kapazität von {{site.data.keyword.backup_notm}} erhöht oder verringert wird, ohne die Sicherungen zu beeinträchtigen?
{: faq}

Sie können die Größe Ihrer Vault über das [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} erhöhen oder verringern. Die Änderung der Kapazität wirkt sich nicht auf die Integrität der Daten aus, die in der Vault gespeichert sind. Weitere Informationen finden Sie im Abschnitt zum Thema [Kapazität erhöhen](expanding-capacity.html).

<hr>

## Was passiert, wenn die Kapazität von {{site.data.keyword.backup_notm}} überschritten wird?
{: faq}

Sie können Ihre Sicherungen auch dann speichern und abrufen, wenn Sie den Grenzwert für die Kapazität erreicht haben, die Sie zuvor erworben haben. Beachten Sie jedoch, dass eine zusätzliche Gebühr für jedes zusätzlich genutzte GB in der Abrechnung aufgeführt wird.

<hr>

## Wie kann ich Benachrichtigungen in WebCC einrichten, um informiert zu werden, wenn meine Sicherungen fehlschlagen?
{: faq}

Benachrichtigungen können auf der Registerkarte 'Erweitert' eingerichtet werden. Gehen Sie den Anweisungen unter **Quick Links** in WebCC entsprechend vor.
