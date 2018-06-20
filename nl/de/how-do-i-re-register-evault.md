---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-30"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# EVault-Instanz erneut registrieren

Diese Task muss am häufigsten nach dem erneuten Laden des Betriebssystems eines Servers ausgeführt werden. Sie können die folgenden Schritte aber auch verwenden, um eine [Sicherung für einen Server auf einem anderen Server wiederherzustellen](restore-from-another-computer.html).

1. Melden Sie sich als Benutzer bei WebCC an. Entsprechende Anweisungen finden Sie unter [Einführung in Backup Services](/docs/infrastructure/Backup/index.html). Denken Sie daran, dass WebCC nur über {{site.data.keyword.BluVPN}} zugänglich ist.

2. Klicken Sie links auf **Alle Agenten**.

3. Berühren Sie mit dem Mauscursor **Bearbeiten** in der rechten oberen Ecke.

4. Wählen Sie **Vaulteinstellungen** aus.

5. Klicken Sie auf **Erneut registrieren**.

6. Geben Sie Folgendes an: 
  - Vaultname
  - Vaultadresse
  - Konto
  - Benutzername
  - Kennwort<br/>
  **Hinweis**: 'Konto' ist hier derselbe Wert wie bei 'Kontoname' auf der Seite [Einführung in Backup Services](index.html). Normalerweise sieht der Wert etwa so aus: SLE[konto-id].

7. Klicken Sie auf **Computer laden** und wählen Sie aus, welche Computer geladen werden sollen.

8. Klicken Sie auf **Änderungen speichern**.

9. Aktualisieren Sie die Website, um vorherige Sicherungsjobs wiederherzustellen.

10. Synchronisieren Sie jeden Sicherungsjob mit dem Protokoll der Sicherungsgruppe für die Wiederherstellung. 

11. Falls die Sicherungsjobs unter Verwendung eines Verschlüsselungskennworts erstellt wurden, müssen Sie das Verschlüsselungskennwort eingeben, um Daten wiederherzustellen oder weitere Sicherungen zu erstellen.

12. Klicken Sie auf **Schließen**. Sie haben hiermit alle erforderlichen Schritte ausgeführt.
