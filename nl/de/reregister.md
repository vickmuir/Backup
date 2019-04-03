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

# Vault erneut registrieren
{: #reregister}

Diese Task wird am häufigsten nach dem erneuten Laden des Betriebssystems eines Servers verwendet. Mit diesen Schritten können Sie außerdem die [Sicherungen eines Servers zum Wiederherstellen von Daten auf einem anderen Server verwenden](/docs/infrastructure/Backup?topic=Backup-restorefromotherVSI).
{:tip}

1. Starten Sie das {{site.data.keyword.backup_notm}}-Portal und melden Sie sich an. Weitere Informationen enthält das [Lernprogramm - Einführung](/docs/infrastructure/Backup?topic=Backup-gettingstarted#getting-started).

   Denken Sie daran, dass das {{site.data.keyword.backup_notm}}-Portal nur über {{site.data.keyword.BluVPN}} zugänglich ist.
   {:tip}
2. Klicken Sie links auf **Alle Agenten**.
3. Bewegen Sie den Mauscursor auf das Element **Bearbeiten**, das sich in der rechten oberen Ecke befindet.
4. Wählen Sie **Vaulteinstellungen** aus.
5. Klicken Sie auf **Erneut registrieren**.
6. Füllen Sie das Formular aus.
  - Vaultname
  - Vaultadresse
  - Konto

    "Konto" ist gleichbedeutend mit dem "Kontonamen" im [{{site.data.keyword.slportal}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){:new_window}. Normalerweise sieht der Wert etwa so aus: SLE[konto-id].
    {:tip}
  - Benutzername
  - Kennwort
7. Klicken Sie auf **Computer laden** und wählen Sie aus, welche Computer geladen werden sollen.
8. Klicken Sie auf **Änderungen speichern**.
9. Aktualisieren Sie die Website, um vorherige Sicherungsjobs wiederherzustellen.
10. Synchronisieren Sie jeden Sicherungsjob mit dem Protokoll der Sicherungsgruppe für die Wiederherstellung.
11. Falls die Sicherungsjobs unter Verwendung eines Verschlüsselungskennworts erstellt wurden, müssen Sie das Verschlüsselungskennwort eingeben, um die Daten wiederherzustellen oder weitere Sicherungen zu erstellen.
12. Klicken Sie auf **Schließen**.
