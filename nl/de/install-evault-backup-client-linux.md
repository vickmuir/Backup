---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-14"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# EVault Backup-Client unter Linux installieren 

Die Installation des EVault Backup-Clients unter einem Linux-basierten Betriebssystem kann durch eine Reihe von Befehlen über die Shell oder das Terminal im Betriebssystem ausgeführt werden. Im hier beschriebenen Verfahren sind die Schritte aufgeführt, die zur Installation des EVault Backup-Clients unter einem der folgenden Linux-basierten Betriebssysteme erforderlich sind:

- RedHat Enterprise Linux
- CentOS
- CloudLinux

Nachdem die Prozedur ausgeführt wurde, registriert der automatisierte Prozess den Agentenservice bei WebCC, anschließend werden die Dateien heruntergeladen und installiert, die zur Ausführung des Service benötigt werden. Führen Sie die folgenden Schritte aus, um den EVault Backup-Client unter einem Linux-basierten Betriebssystem zu installieren.

**Hinweis**: Falls Sie EVault bei der Bestellung eines Servers im {{site.data.keyword.slportal}} gekauft haben, wird die Software automatisch installiert und Sie müssen die in diesem Dokument beschriebenen Prozeduren nicht ausführen.

Falls Sie EVault als Upgrade im {{site.data.keyword.slportal}} gekauft haben, führen Sie die folgenden Schritte aus, um die Software zu installieren.

## Beim Zielgeräteserver anmelden

1. Melden Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an und wählen Sie im Hauptmenü die Optionen **Geräte** > **Geräteliste** aus, um die Liste der verfügbaren Servereinheiten anzuzeigen.
2. Suchen Sie nach dem Gerät, für das Sie den EVault-Service gekauft haben, und notieren Sie sich seine öffentliche IP-Adresse. Sie verwenden sie in den folgenden Schritten, wenn Sie sich über eine UNIX- oder Linux-Befehlszeile beim Gerät anmelden. Ersetzen Sie in den nachfolgenden Befehlen die Variable <öffentliche_ip-adresse> durch die tatsächliche öffentliche IP-Adresse. 
3. Klicken Sie auf den nach rechts zeigenden Erweiterungspfeil, um zusätzliche Informationen zum Gerät sichtbar zu machen, inklusive Benutzername und Kennwort. Falls das Kennwort nicht angezeigt wird, klicken Sie auf das Kontrollkästchen **Kennwort anzeigen**, damit das Kennwort sichtbar wird. Der Benutzername und das Kennwort werden im nächsten Schritt zur Anmeldung beim Testgerät verwendet. Ersetzen Sie in den nachfolgenden Befehlen die Variable `<user name>` durch den tatsächlichen Benutzernamen.
4. Melden Sie sich beim Zielgerät unter Verwendung von SSH an, indem Sie den folgenden Befehl in einer UNIX oder Linux-Befehlszeile ausführen:
  ```
  ssh <user name>@<öffentliche_ip-adresse>
  ```
  {: pre}
  
 **Hinweis**: Falls Sie sich mit diesem Benutzernamen zuvor noch nicht bei diesem Server angemeldet haben, wird eine Nachricht über die Authentizität des Hosts und mit der Frage ausgegeben, ob Sie den Vorgang fortsetzen wollen. Beantworten Sie die Frage mit **Ja**, um fortzufahren.
5. Sie werden zur Eingabe des Kennworts aufgefordert, sofern Sie zuvor keine SSH-Schlüssel für den Zugriff auf diesen Server konfiguriert haben.

## Linux zur Vorbereitung auf die Installation des EVault-Clients aktualisieren (nur RedHat Linux)
**Hinweis**: Dieser Schritt ist für RedHat Linux erforderlich, für die anderen Linux-Distributionen jedoch optional.

- Geben Sie den folgenden Befehl an der Eingabeaufforderung des Servers ein:
  ```
  yum update
  ```
  {: pre}
   
  Wenn die entsprechende Frage ausgegeben wird, bestätigen Sie, dass die Downloadgröße in Ordnung ist. Die Aktualisierung wird fortgesetzt und ist bei Ausgabe der Nachricht 'Complete!' fertiggestellt.

## Installationsscript für EVault abrufen
- Geben Sie den folgenden Befehl an der Eingabeaufforderung des Servers ein:
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}
   
## Installationsscript für EVault ausführen
1. Führen Sie den folgenden Befehl an der Eingabeaufforderung des Servers aus:
  ```
  sh ./evault_manual.sh
  ```
  {: pre}

2. Geben Sie Ihren Benutzernamen und Ihr Kennwort für WebCC ein.     
  **Hinweis**: Im Artikel [Einführung in Backup Services](/docs/infrastructure/Backup/index.html) finden Sie Anweisungen dazu, wie Sie den Benutzernamen und das Kennwort für EVault Backup anzeigen können.
3. Nach dem Benutzernamen und dem Kennwort ist keine weitere Eingabe erforderlich, auch wenn bei fortschreitender Installation einige Eingabeaufforderungen angezeigt werden. Diese Eingabeaufforderungen können Sie problemlos ignorieren. Sie werden durch ein Unterscript erzeugt, das vom Script *evault_manual.sh* aufgerufen wird. Die Eingaben für diese Eingabeaufforderungen werden durch das Script *evault_manual.sh* bereitgestellt.
4. Wenn Nachrichten ähnlich den Folgenden ausgegeben werden, ist die Installation abgeschlossen:
  ```
  Starting VVAgent: [  OK  ]
  Starting buagent: [  OK  ]
  ```
  {: codeblock}
   
## Erfolg der Installation prüfen
1. Überprüfen Sie, ob die Nachricht 'Registered to The Portal' in der Ausgabe für die Installation enthalten ist. Hierzu können Sie in der Anzeige nach der Nachricht suchen oder die Ausgabe des folgenden Befehls untersuchen:
  ```
  grep 'Registered'  /opt/BUAgent/Install.log
  ```
  {: pre}

2. Führen Sie den folgenden Befehl aus und untersuchen Sie die Ausgabe: 
  ```
  service vvagent status
  ```
  {: pre}
   
  Die folgenden Nachrichten sollten angezeigt werden:
  ```
  VVAgent is running (PID xxxxx).
  buagent is running (PID xxxxx).
  ```
  {: codeblock}
   
  **Hinweis**: Die oben durch 'xxxx' dargestellten Prozess-IDs variieren bei jeder Installation. 
  
## Nächste Schritte

Melden Sie sich bei WebCC an, um Ihre Sicherungsagenten zu konfigurieren und zu verwalten. Anweisungen erhalten Sie im [Lernprogramm 'Einführung'](index.html#configuring-evault-agent-in-webcc).
