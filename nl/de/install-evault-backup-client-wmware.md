---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-03"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# EVault Backup-Client für VMware installieren

Die Installation des EVault Backup-Clients auf einem VMware-Server kann durch eine Reihe von Befehlen über die Shell oder das Terminal im EXS-Zielserver ausgeführt werden. Im hier beschriebenen Verfahren sind die Schritte aufgeführt, die zur Installation des EVault Backup-Clients auf einem VMware-Server erforderlich sind:

Laden Sie zur Installation des Agenten das Paket `Agent-VMware-ESX-Server-6.71.<version-info>.tar.gz` auf den ESX-Zielserver herunter und kopieren Sie das Paket. Verwenden Sie hierzu den folgenden Befehl:

`wget -N http://downloads.service.softlayer.com/evault/archive/Agent-VMware-ESX-Server-6.71.2105.tar.gz`

**Hinweis**: Die folgenden Schritte müssen lokal auf dem ESX-Zielserver ausgeführt werden.

1. Extrahieren Sie die Dateien aus dem Paket. Verwenden Sie hierzu den Befehl
    `tar xvfz PAKETNAME.tar.gz` (PAKETNAME könnte hier für 'Agent-VMware-ESX-Server-6.71' stehen).
2. Wechseln Sie in das Verzeichnis, in dem Sie das Paket extrahiert haben.
3. Führen Sie das Installationsscript aus:
    `# ./install.sh`

    **Hinweis**: Das Installationsscript fordert interaktiv von Ihnen Konfigurationsinformationen wie beispielsweise die Webregistrierung (Adresse, Portnummer und Authentifizierung) und den Protokolldateinamen an.
     
    - Geben Sie den WebCC-Benutzernamen für diesen Server ein.
    - Geben Sie das WebCC-Kennwort für diesen Server ein.
     
4. Geben Sie den **EVault Backup-Benutzernamen** als Eingabe bei der Aufforderung ein, die den WebCC-Benutzernamen anfordert. 
5. Geben Sie das **EVault Backup-Kennwort** als Eingabe bei der Aufforderung ein, die das WebCC-Kennwort anfordert.
6. Nach Abschluss der Installation wird eine Beendigungsnachricht angezeigt und der Agentendämon wird ausgeführt.


### Weitere Installationshinweise:
Die Datei 'Install.log' befindet sich nach einer erfolgreichen Installation im Installationsverzeichnis.
Beispiel: `/opt/BUAgent/Install.log`

Falls die Installation fehlschlägt und rückgängig gemacht wird, befindet sich das Installationsprotokoll im Verzeichnis `<Installation Failure>`.
Falls sie fehlschlägt und nicht rückgängig gemacht wird, befindet sich das Installationsprotokoll im Verzeichnis für das `<Installation Kit>`.

Wenn Sie weitere Informationen benötigen, laden Sie das [Benutzerhandbuch für den VMware-Agenten](http://downloads.service.softlayer.com/evault/Documentation/VMware_Agent_User_Guide.pdf){:new_window} herunter. Achten Sie darauf, dass Sie mit dem {{site.data.keyword.BluVPN}} verbunden sind, damit dieser Link angezeigt wird.
