---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Upgrade für Backup-Softwareagenten für Linux durchführen
{: #UpgradeinLinux}

Der aktuelle Sicherungsagent kann von Ihrem {{site.data.keyword.backup_notm}}-Portal-Dashboard-Abschnitt "Quick Links" heruntergeladen werden.
{:tip}

Im Anschluss an den Upgradeprozess wird sichergestellt, dass Sie ein Upgrade für Ihren {{site.data.keyword.backup_notm}}-Agenten durchführen können, ohne dass dabei die Registrierung verloren geht.

1. Melden Sie sich auf der Stammverzeichnisebene bei Ihrem Host an.
2. Laden Sie die neueste Version des Agenten herunter.
   ```
   wget -N downloads.service.softlayer.com/evault/Agent-Linux-x64-8.11.5251.tar.gz2
   ```
   {:pre}

3. Extrahieren Sie den Inhalt der heruntergeladenen Datei.

   ```
   tar -xzvf Agent-Linux-x64-8.11.5251.tar.gz3
   ```
4. Wechseln Sie in das Verzeichnis der aktuellen Installation.
   ```
   cd Agent-Linux-x64-8.11.5251/4
   ```

5. Führen Sie das Installationsscript aus.
   ```
   ./install.sh
   ```
   {:pre}

6. Beantworten Sie die Eingabeaufforderungen, indem Sie die gewünschte Sprache auswählen, `N` auswählen, um den Computer nicht als neuen Host zu registrieren, und `A` auswählen, um Daten mithilfe des integrierten Verschlüsselungsverfahrens zu verschlüsseln.

7. Wenn die Installation erfolgreich ist, wird sie in `/opt/BUAgent/Install.log` aufgezeichnet.
