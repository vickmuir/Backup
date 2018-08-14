---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-10"

---
{:new_window: target="_blank"}


# Häufig gestellte Fragen zu EVault Backup

**Welche Arten von Anwendungen können mit EVault gesichert werden?**

EVault ermöglicht die Sicherung von verschiedenen Anwendungen. {{site.data.keyword.BluSoftlayer_full}} bietet jedoch Softwareagenten zur Sicherung für einige der gängigeren Softwaresysteme wie beispielsweise Folgende:

- Bare-Metal-Wiederherstellung
- Microsoft SQL
- Oracle

Die hier aufgeführten Plug-ins sind nur mit Windows-Servern kompatibel. Jeder Agent ist als Add-on für den EVault Backup-Service verfügbar. Wenn Sie einen Agenten zu Ihrem Service hinzufügen wollen, können Sie sich direkt mit einem Mitarbeiter des Vertriebsteams in Verbindung setzen. 

<hr>

**Wie oft können die Daten mit EVault gesichert werden?**

Sie können Ihre Daten so oft sichern, wie Sie möchten. In WebCC können Sicherungen manuell ausgeführt bzw. zur einmaligen oder wiederholten Ausführung geplant werden. Wiederholte Sicherungen können täglich, wöchentlich, monatlich oder nach einem angepassten Zeitplan erfolgen und jederzeit aktualisiert oder abgebrochen werden.

>**Hinweis** - Sehr häufige Sicherungen, die mehrmals täglich oder stündlich ausgeführt werden, können zur Beschädigung von Sicherungsjobs führen. Dies liegt daran, dass die Vault möglicherweise nicht in der Lage ist, zwischen den Sicherungsläufen alte Sicherungsgruppen zu entfernen oder andere erforderliche Hintergrundtask vollständig auszuführen.

<hr>

**Wie funktionieren Aufbewahrungsschemas?**

EVault ermöglicht es Ihnen, Daten so lange aufzubewahren, wie Sie in der Lage zu einer Rollback-Operation sein wollen. Die Aufbewahrungsschemas des Typs **Täglich** behalten Daten für sieben Tage bei, während die Schemas des Typs **Wöchentlich** Daten für einen Monat und die Schemas des Typs **Monatlich** Daten für ein Jahr beibehalten. Am Ende jedes Zeitraums wird der älteste Datenbestand turnusmäßig ausgelagert und die erste erstellte Deltasicherung wird zum ältesten verfügbaren Wiederherstellungspunkt. 

<hr>

**Was ist unter 'Deltatechnologie' zu verstehen?**

Die erste Sicherung, bei der es sich um eine vollständige Gesamtsicherung handelt, ist ein so genannter 'Seed'. Die nächste und alle nachfolgenden Sicherungen werden als 'Deltasicherungen' bezeichnet, weil sie nur Änderungen enthalten, sind jedoch zu Gesamtsicherungen äquivalent und gelten als Gesamtsicherungen. Dies bedeutet, dass Sie aus diesen Sicherungen alle oder einige Dateien wiederherstellen können. Diese Technologie ermöglicht die Durchführung von Gesamtsicherungen in jeder Sitzung, spart jedoch enorm Speicherplatz in der Vault und verringert die Zeit, die zur Ausführung aller nachfolgenden Sicherungen benötigt wird.

<hr>

**Sind die Sicherungen geschützt?**

Standardmäßig findet die gesamte Verschlüsselung über die Verbindung unter Verwendung des Verschlüsselungstyps 'AES 256-Bit' statt. Sie können außerdem auswählen, dass Daten in einem verschlüsselten Format unter Verwendung von AES 256-Bit gespeichert werden. 

>**Hinweis** - Sie müssen sich Ihr Verschlüsselungskennwort merken. Ohne Ihr Kennwort können Ihre Daten nicht wiederhergestellt werden. Falls Sie Ihr Kennwort vergessen, sind Sie nicht in der Lage, Ihre Daten wiederherzustellen. 

Komprimierungsverhältnisse ermöglichen die Verwendung von keiner Komprimierung bis hin zu einem maximalen Komprimierungsverhältnis, das je nach Dateityp zwischen 20 und 30 Prozent liegen kann.

<hr>

**Welche Informationen werden mit Systemstatussicherungen gespeichert?**

Systemstatussicherungen umfassen unter anderem die COM- und Klassenregistrierungsdatenbank, die Registry, Bootdateien Systemdateien und Leistungszähler, sind jedoch nicht hierauf beschränkt. Maßgeblich ist jeweils das System. Systemdateien variieren nach Betriebssystem und Service-Packs des Systems. Normalerweise gibt es mehrere Tausend dieser Dateien. MS Windows erstellt eine dynamische Liste dieser DLLs, wenn Sie sie in die Sicherung einbeziehen. Durch die Einbeziehung der Systemdateien können Sie eine Wiederherstellung bei beschädigten Systemdateien, bei einer versehentlichen Deinstallation von Service-Packs oder bei einer erforderlichen Bare-Metal-Wiederherstellung vornehmen. Sie können zum Status der Sicherung zurückkehren, ohne das Betriebssystem mit dem Installationskit erneut installieren und anschließend jedes Service-Pack separat installieren zu müssen.

>**Hinweis** - Eine Systemstatussicherung bezieht keine Benutzerdatendateien ein. Ein Systemstatussicherungsjob muss als eigenständiger Job konfiguriert werden. Es darf keine andere Datenquelle vorhanden sein, die in den Systemstatussicherungsjob eingeschlossen wird.

<hr>

**Was passiert mit geöffneten Dateien?**

Der Basisclient ist standardmäßig mit ausgereifter Technologie ausgestattet, um die meisten geöffneten Dateien im Betriebssystem zu behandeln.

<hr>

**Wo finde ich Informationen zur Preisstruktur?**

Weitere Informationen zu diesem Thema finden Sie im Abschnitt zum [Sicherungsspeicher](https://www.ibm.com/cloud/backup-and-restore){:new_window} und unter [EVault on IBM Cloud: Preisstruktur](https://www.ibm.com/cloud/evault/pricing){:new_window}.

<hr>

**Kann ich meine EVault-Kapazität erhöhen/verringern, ohne meine Sicherungen zu beeinträchtigen?**

Sie können die EVault-Größe im [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} erhöhen oder verringern. Die Änderung der EVault-Kapazität wirkt sich nicht auf die Integrität der Daten aus, die in der Vault gespeichert sind. Weitere Informationen zu diesem Thema finden Sie im Abschnitt zum [Erweitern der EVault-Kapazität](expanding-evault-capacity.html).

<hr>

**Was passiert, wenn meine EVault-Kapazität überschritten wird?**

Sie können Ihre Sicherungen auch dann speichern und abrufen, wenn Sie den Grenzwert für die Kapazität erreicht haben, die Sie zuvor erworben haben. Beachten Sie hierbei, dass zusätzliche Gebühren für jedes zusätzliche Gigabyte (GB) erhoben werden, das von Ihnen belegt wird.
