---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere, backups

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# vSphere-Daten wiederherstellen
{: #VRARestore}

Wenn VMs in der vSphere-Umgebung geschützt sind, können Sie [vSphere-VMs](#restoreVMs) und [Dateien und Ordner](#restoreFFVRA) mit vSphere Recovery Agent wiederherstellen.

## vSphere-VMs wiederherstellen
{: #restoreVMs}

1.	Klicken Sie in der Navigationsleiste auf **Computer**. In einem Raster werden die verfügbaren Computer aufgelistet.
2.	Suchen Sie die vSphere-Umgebung mit der VM, die Sie wiederherstellen möchten, und erweitern Sie die zugehörige Ansicht, indem Sie auf die Zeile klicken.
3.	Klicken Sie auf **Jobs**.
4.	Suchen Sie den Sicherungsjob mit der VM, die Sie wiederherstellen möchten, und klicken Sie im Menü **Aktion auswählen** des Jobs auf **Wiederherstellen**.
5.	Im Dialogfenster für die Auswahl der wiederherzustellenden Elemente**** wählen Sie **Virtuelle Maschinen** aus.
6.	Klicken Sie auf **Weiter**. Im Dialog für Wiederherstellen wird die neueste Sicherungsgruppe für den Job angezeigt.
    * Wenn Sie Daten aus einer anderen Quelle wiederherstellen möchten, klicken Sie auf eine Quelle (Vault) in der Liste **Quelleneinheit**.
    *	Um Daten aus einer älteren Sicherungsgruppe wiederherzustellen, klicken Sie auf die Schaltfläche zum**** Durchsuchen von Sicherungsgruppen. Klicken Sie im angezeigten Kalender auf das Datum der Sicherungsgruppen, aus denen Sie Daten wiederherstellen möchten.
7.	Wählen Sie in der Anzeige **Wiederherzustellende Elemente** jede VM aus, die Sie wiederherstellen möchten.
8.	Geben Sie im Feld **Verschlüsselungskennwort** das Datenverschlüsselungskennwort ein.
9.	Klicken Sie in der Liste **Zieldatenspeicher** auf den Datenspeicher für die wiederhergestellten VMs.
10.	Wählen Sie eine der folgenden Optionen für die Wiederherstellung von VMs in dem ausgewählten Datenspeicher aus:
  * **Alle ausgewählten virtuellen Maschinen nur in dem ausgewählten Datenspeicher wiederherstellen. **
  * **Nur im ausgewählten Datenspeicher wiederherstellen, wenn der ursprüngliche Datenspeicher einer virtuellen Maschine nicht verfügbar ist.** Enthält die gesicherte VM mehrere VMDKs, die in zwei oder mehr Datenspeichern gespeichert sind, und ist mindestens ein Datenspeicher nicht verfügbar, wird die gesamte VM im ausgewählten Datenspeicher wiederhergestellt.

  Stellen Sie eine VM oder Vorlage in einem vCenter wieder her und ist die ursprüngliche VM vorhanden, wird die VM als Klon der ursprünglichen VM mit dem folgenden Namen wiederhergestellt: <VMname>-vra-restored-<Date>. Die VM wird als Klon wiederhergestellt, wenn die ursprüngliche VM eingeschaltet, ausgeschaltet oder ausgesetzt ist. Wenn die ursprüngliche VM eingeschaltet ist und eine statische IP-Adresse verwendet, kann ein IP-Adresskonflikt auftreten, wenn die wiederhergestellte, geklonte VM eingeschaltet wird.
  {:note}

13.	Klicken Sie in der Liste **Zielhost** auf den Host, bei dem die VMs registriert werden sollen. In der Liste werden nur die Hosts angezeigt, die Zugriff auf den ausgewählten Datenspeicher haben.
14.	Wählen Sie eine der folgenden Optionen für die Registrierung der wiederhergestellten VMs bei den von Ihnen ausgewählten Hosts aus:
  * **Alle ausgewählten virtuellen Maschinen nur bei den ausgewählten Hosts registrieren. **
  * **Nur bei den ausgewählten Hosts registrieren, wenn die ursprünglichen Hosts einer virtuellen Maschine nicht verfügbar sind. **
15.	Wenn die VMs nach ihrer Wiederherstellung eingeschaltet werden sollen, wählen Sie **VMs nach Wiederherstellung einschalten** aus.
16.	Behalten Sie unter **Leistungsoptionen** die Standardeinstellung bei.
17.	Klicken Sie auf **Wiederherstellung durchführen**.

## Dateien und Ordner wiederherstellen
{: #restoreFFVRA}

Mit vSphere Recovery Agent (VRA) können Sie Dateien und Ordner aus einer geschützten Windows-VM wiederherstellen. Sie können Dateien und Ordner von mehreren VMs gleichzeitig wiederherstellen. Mit VRA können Sie keine Dateien und Ordner aus Linux-VMs wiederherstellen.
{:important}

Während einer Wiederherstellung von Dateien und Ordnern werden Datenträger der ausgewählten VM als Laufwerke auf der Maschine angehängt, auf der VRA ausgeführt wird. Anschließend können Sie einige oder alle angehängten Laufwerke freigeben, sodass Benutzer Dateien und Ordner von den Laufwerken kopieren können. Sie können sich auch bei der VRA-Maschine anmelden und Dateien und Ordner von den angehängten Laufwerken kopieren.

Die Dateien und Ordner auf den Platten sind für jeden Benutzer auf dem VRA-System zugänglich, auch für Benutzer ohne Administratorberechtigung. Wenn Sie über die Sicherheit besorgt sind, schützen Sie die Agentenmaschine und verhindern Sie, dass Benutzer sich lokal bei der Maschine anmelden.
{:tip}

1. Klicken Sie in der Navigationsleiste auf **Computer**. In dem Raster werden die verfügbaren Computer aufgelistet.
2. Suchen Sie die vSphere-Umgebung mit der VM, die Sie wiederherstellen möchten, und erweitern Sie die zugehörige Ansicht, indem Sie auf die Zeile klicken.
3. Klicken Sie auf **Jobs**.
4. Suchen Sie den Sicherungsjob mit der VM, die Sie wiederherstellen möchten, und klicken Sie im Menü **Aktion auswählen** des Jobs auf **Wiederherstellen**.
5. Im Dialog für die Auswahl der wiederherzustellenden Elemente**** wählen Sie **Dateien und Ordner** aus.
6. Klicken Sie auf **Weiter**. Im Dialog für Wiederherstellen wird die neueste Sicherungsgruppe für den Job angezeigt.
  * Wenn Sie Daten aus einer anderen Ressource wiederherstellen möchten, klicken Sie in der Liste für die Quelleneinheit (Vault) auf eine Quelle.
  * Um Daten aus einer älteren Sicherungsgruppe wiederherzustellen, klicken Sie auf die Schaltfläche zum Durchsuchen von Sicherungsgruppen. Klicken Sie im angezeigten Kalender auf das Datum der Sicherungsgruppe, aus der Sie Daten wiederherstellen möchten. Klicken Sie rechts neben dem Kalender auf die Sicherungsgruppe, aus der Sie Daten wiederherstellen möchten.
7. Wählen Sie in der Anzeige **Wiederherzustellende Elemente** die VM mit den wiederherzustellenden Dateien oder Ordnern aus.
8. Geben Sie im Feld **Verschlüsselungskennwort** das Datenverschlüsselungskennwort ein.
9. Geben Sie im Feld **Leerlaufzeit** die Anzahl der Minuten der Inaktivität ein, nach denen die Freigabe des Laufwerks automatisch aufgehoben werden soll. Die Leerlaufzeit kann im Bereich von 2 bis 180 Minuten liegen. 

    Die Freigabe des Laufwerks wird nicht aufgehoben, solange neue Daten kopiert werden. Wenn Sie dieselben Daten mehrfach von einem gemeinsam genutzten Laufwerk kopieren, kann eine Zeitlimitüberschreitung bei dem System auftreten, da keine neuen Daten gelesen werden.
    {:note}

10.	Wählen Sie unter **Leistungsoptionen** die Verwendung der gesamten verfügbaren Bandbreite aus.
11.	Klicken Sie auf **Wiederherstellung durchführen**.
12. Die wiederhergestellten Datenträger aus der ausgewählten VM werden als Laufwerke auf der Maschine zugeordnet, auf der VRA ausgeführt wird, und sind in einem Mountordner für die Wiederherstellung verfügbar.  Führen Sie einen der folgenden Schritte aus.
  * Kopieren Sie die Dateien und Ordner, die Sie wiederherstellen möchten, von den zugeordneten Laufwerken.
  * Geben Sie mindestens ein zugeordnetes Laufwerk für andere Benutzer frei. Die Benutzer können dann auf die UNC-Freigabe zugreifen und die Dateien und Ordner kopieren, die sie wiederherstellen möchten.
  * Geben Sie mindestens ein Verzeichnis im Mountordner für die Wiederherstellung auf der VRA-Maschine frei. Die Benutzer können dann auf die UNC-Freigabe zugreifen und die Dateien und Ordner kopieren, die sie wiederherstellen möchten.
