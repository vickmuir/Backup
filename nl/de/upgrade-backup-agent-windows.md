---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, upgrade agent, Windows

subcollection: Backup

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Upgrade für Backup-Softwareagenten für Windows durchführen
{: #UpgradeinWindows}

Der aktuelle Sicherungsagent kann von Ihrem {{site.data.keyword.backup_notm}}-Portal-Dashboard-Abschnitt "Quick Links" heruntergeladen werden.
{:tip}

1. Nutzen Sie die Fernsteuerung für den {{site.data.keyword.cloud}}-Server, für den ein {{site.data.keyword.backup_notm}}-Upgrade erforderlich ist.
2. Öffnen Sie einen Browser und rufen Sie die folgenden Adresse auf.
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
3. Klicken Sie auf die gewünschte Datei (z. B. Agent-Windows-x64-6-72-1072a.exe).

   Die Versionsnummer ist der Dateiname. Wählen Sie die neueste Version aus. <br/>{{site.data.keyword.cloud}} bietet separate 32-Bit-und 64-Bit-Installationsprogramme. Falls Sie ein 64-Bit-Betriebssystem verwenden, laden Sie eine Datei herunter, deren Name die Angabe 'x64' enthält.
   {:tip}
4. Klicken Sie in der Downloadanzeige auf **Ausführen**. Wiederholen Sie dies nach Abschluss des Downloads.
5. Klicken Sie auf **Ja**, um ein Upgrade für den **{{site.data.keyword.backup_notm}}-Softwareagenten** durchzuführen.

   Das Installationsprogramm wird während des Ladens möglicherweise ca. eine Minute lang nicht angezeigt.
   {:note}
6. Wählen Sie **Aktuelle Registrierung beibehalten** aus und klicken Sie auf **Weiter**.
7. Klicken Sie auf **Weiter**. Daraufhin beginnt der Agent mit dem Upgradeprozess. Dieser Vorgang kann einige Minuten dauern.
8. Klicken Sie in der Abschlussanzeige auf **Fertigstellen**.
