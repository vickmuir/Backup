---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-26"

---
{:new_window: target="_blank"}

# EVault-Instanz erneut registrieren

Diese Task wird am häufigsten nach dem erneuten Laden des Betriebssystems eines Servers verwendet. Mit diesen Schritten können Sie außerdem die [Sicherungen eines Servers zum Wiederherstellen von Daten auf einem anderen Server verwenden](restore-from-another-computer.html).

1. Starten Sie WebCC und melden Sie sich an. Anweisungen hierzu erhalten Sie im Abschnitt zur [Einführung in die Sicherungsservices](/docs/infrastructure/Backup/index.html). <br/>Denken Sie daran, dass WebCC nur über {{site.data.keyword.BluVPN}} zugänglich ist.

2. Klicken Sie links auf **Alle Agenten**.

3. Bewegen Sie den Mauscursor auf das Element **Bearbeiten**, das sich in der rechten oberen Ecke befindet.

4. Wählen Sie **Vaulteinstellungen** aus.

5. Klicken Sie auf **Erneut registrieren**.
 
6. Füllen Sie das Formular aus.
  - Vaultname
  - Vaultadresse
  - Konto <br/>**Hinweis**: 'Konto' ist im [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} gleichbedeutend mit 'Kontoname'. Normalerweise sieht der Wert etwa so aus: SLE[konto-id].
  - Benutzername
  - Kennwort

7. Klicken Sie auf **Computer laden** und wählen Sie aus, welche Computer geladen werden sollen.

8. Klicken Sie auf **Änderungen speichern**.

9. Aktualisieren Sie die Website, um vorherige Sicherungsjobs wiederherzustellen.

10. Synchronisieren Sie jeden Sicherungsjob mit dem Protokoll der Sicherungsgruppe für die Wiederherstellung.

11. Falls die Sicherungsjobs unter Verwendung eines Verschlüsselungskennworts erstellt wurden, müssen Sie das Verschlüsselungskennwort eingeben, um die Daten wiederherzustellen oder weitere Sicherungen zu erstellen.

12. Klicken Sie auf **Schließen**.
