---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:codeblock: .codeblock}
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Sicherungsclient unter Linux installieren

Die Installation des {{site.data.keyword.backup_full}}-Clients unter einem Linux-basierten Betriebssystem kann über eine Reihe von Befehlen in der Shell oder einem Terminalfenster im Betriebssystem erfolgen. Die Prozedur umreißt die Schritte, die erforderlich sind, um den {{site.data.keyword.backup_notm}}-Client auf einem beliebigen der folgenden Linux-basierten Betriebssysteme zu installieren:

- RHEL
- CentOS
- CloudLinux

Nachdem die Prozedur ausgeführt wurde, registriert der automatisierte Prozess den Agentenservice beim {{site.data.keyword.backup_notm}}-Portal. Anschließend werden die Dateien heruntergeladen und installiert, die zur Ausführung des Service benötigt werden.

Wenn Sie {{site.data.keyword.backup_notm}} bei der Bestellung eines Servers über den [{{site.data.keyword.cloud_notm}}-Katalog](https://{DomainName}/catalog/){:new_window} oder das {{site.data.keyword.slportal}} gekauft haben, dann wird die Software automatisch für Sie installiert. Sie müssen die Prozeduren, die in diesem Dokument beschrieben werden, nicht verwenden.
{:tip}

Wenn Sie {{site.data.keyword.backup_notm}} als Upgrade im {{site.data.keyword.slportal}} gekauft haben, befolgen Sie diese Schritte, um die Software zu installieren.

## Beim Zielgeräteserver anmelden

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}/){:new_window} an und klicken Sie oben links auf das Symbol **Menü**. Wählen Sie **Klassische Infrastruktur** aus.<br/>
   Alternativ können Sie sich am [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} anmelden.
2. Wählen Sie im Hauptmenü **Geräte** > **Geräteliste** aus, um die Liste der verfügbaren Servereinheiten anzuzeigen.
3. Suchen Sie das Gerät, für das Sie den {{site.data.keyword.backup_notm}}-Service gekauft haben, und notieren Sie die zugehörige öffentliche IP-Adresse.
  - Sie verwenden diese IP-Adresse in den folgenden Schritten, wenn Sie sich über eine UNIX- oder Linux-Befehlszeile beim Gerät anmelden. Ersetzen Sie in dem in Schritt 4 dargestellten Befehl die Variable <öffentliche_ip-adresse> durch die tatsächliche öffentliche IP-Adresse.
4. Klicken Sie auf den nach rechts zeigenden Pfeil, um zusätzliche Informationen zum Gerät (einschließlich Benutzername und Kennwort) anzuzeigen.
  - Falls das Kennwort nicht angezeigt wird, klicken Sie auf **Kennwort anzeigen**, damit das Kennwort sichtbar wird. Der Benutzername und das Kennwort werden im nächsten Schritt zur Anmeldung beim Testgerät verwendet. Ersetzen Sie `benutzername` durch den tatsächlichen Benutzernamen.
5. Melden Sie sich beim Zielgerät an, indem Sie den folgenden Befehl in einer UNIX oder Linux-Befehlszeile eingeben.
   ```
   ssh <benutzername>@<öffentliche_ip-adresse>
   ```
   {: pre}

   Wenn Sie sich zuvor bei diesem Server nicht mit diesem Benutzernamen angemeldet haben, erhalten Sie eine Nachricht über die Authentizität des Hosts. Sie werden auch gefragt, ob Sie fortfahren möchten. Beantworten Sie die Frage mit **Ja**, um fortzufahren.
   {:note}

6. Sie werden zur Eingabe des Kennworts aufgefordert, sofern Sie zuvor keine SSH-Schlüssel für den Zugriff auf diesen Server konfiguriert haben.

## Betriebssystem für die Vorbereitung auf die Installation aktualisieren (nur RHEL)

Dieser Schritt ist für RHEL erforderlich, aber für andere Linux-Distributionen optional.
{:tip}

- Führen Sie den folgenden Befehl an der Eingabeaufforderung des Servers aus.
  ```
  yum update
  ```
  {: pre}

  Wenn die entsprechende Eingabeaufforderung ausgegeben wird, bestätigen Sie, dass die Downloadgröße korrekt ist. Die Aktualisierung wird fortgesetzt. Nach Abschluss der Verarbeitung wird eine Nachricht angezeigt, in der Sie darüber informiert werden, dass die Aktualisierung abgeschlossen ist.

## Installationsscript abrufen

- Führen Sie den folgenden Befehl an der Eingabeaufforderung des Servers aus.
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}

## Installationsscript ausführen

1. Führen Sie den folgenden Befehl an der Eingabeaufforderung des Servers aus.
   ```
   sh ./evault_manual.sh
   ```
   {: pre}

2. Geben Sie Ihren Benutzernamen und Ihr Kennwort für das {{site.data.keyword.backup_notm}}-Portal ein.

   Weitere Informationen zum Anzeigen des Benutzernamens und Kennworts für {{site.data.keyword.backup_notm}} finden Sie unter [Einführung in die Sicherungsservices](index.html#accessing-and-viewing-ibm-cloud-backup-storage-details).
   {:tip}

3. Nach dem Benutzernamen und dem Kennwort ist keine weitere Eingabe erforderlich. Die Eingabeaufforderungen, die während der Installation angezeigt werden, können gefahrlos ignoriert werden.

   Sie werden durch ein Subskript erzeugt, das vom Script `evault_manual.sh` gestartet wird. Die Eingaben für diese Eingabeaufforderungen werden durch das Script `evault_manual.sh` bereitgestellt.
   {:note}

4. Die Installation ist abgeschlossen, wenn die folgenden Nachrichten angezeigt werden.

   ```
   Starting VVAgent: [  OK  ]
   Starting buagent: [  OK  ]
   ```
   {: codeblock}

## Erfolg der Installation prüfen

1. Überprüfen Sie, ob die Nachricht 'Registered to The Portal' in der Ausgabe für die Installation enthalten ist. Zur Überprüfung können Sie in der Anzeige nach der Nachricht suchen oder die Ausgabe des folgenden Befehls untersuchen.
   ```
   grep 'Registered'  /opt/BUAgent/Install.log
   ```
   {: pre}

2. Führen Sie den folgenden Befehl aus und untersuchen Sie die Ausgabe.
   ```
   service vvagent status
   ```
   {: pre}

   Die folgenden Nachrichten werden angezeigt.
   ```
   VVAgent is running (PID xxxxx).
   buagent is running (PID xxxxx).
   ```
   {: codeblock}

  Die Prozess-ID, die durch `xxxxx` dargestellt ist, variiert je nach Installation.
  {:tip}

**Nächste Schritte**

Melden Sie sich beim {{site.data.keyword.backup_notm}}-Portal an, um Ihre Sicherungsagenten zu konfigurieren und zu verwalten. Weitere Informationen finden Sie im [Lernprogramm 'Einführung'](index.html#configuring-the-backup-agent-and-the-backup-schedule) und [Einfache Sicherung auf Dateiebene unter Linux konfigurieren](configure-simple-file-backup-linux.html).
