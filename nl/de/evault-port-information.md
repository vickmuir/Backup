---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-26"

---
{:new_window: target="_blank"}

# Ports für Kommunikation zwischen dem EVault-Agenten und WebCC konfigurieren

Der auf Ihrem Server installierte EVault-Agent muss mit der von Ihnen gekauften Vault kommunizieren können. Die Hostinformationen von EVault Director für ein EVault-Benutzerkonto sind im [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} zu finden. 

Agenten müssen für WebCC und EVault Director-Instanzen stets unter Verwendung des vollständig qualifizierten Domänennamens registriert werden, weil sich die IP-Adressen für diese Services ändern können. 


```
evregister.service.softlayer.com TCP 8086,8087
```

Ihre Server müssen mit WebCC und allen AMP-Proxy-Servern kommunizieren, damit WebCC ordnungsgemäß funktioniert, und zwar ungeachtet des Rechenzentrumsstandorts. Zusätzliche AMP-Proxy-Server können bei Bedarf hinzugefügt werden, um weitere EVault-Agenten auszuführen, die für WebCC registriert werden. 

TCP-Port 8086, 8087 muss Zugriff auf 10.0.0.0/8 besitzen. 

Falls Sie restriktivere Firewallregeln verwenden müssen, verlieren Sie möglicherweise den Zugriff auf WebCC, wenn die Infrastruktur erweitert wird. Gegenwärtig müssen Ihre Server mindestens den Zugriff auf die Teilnetze 10.0.82.0/24 und 10.2.118.0/24 für die TCP-Ports 8086, 8087 zulassen. Weitere Teilnetze können künftig bei Bedarf hinzugefügt werden.

**Kostenpflichtige Komponenten**

*WebCC und AMP-Proxy-Server*

- ev-webcc01.service.softlayer.com [10.0.82.12] 8086, 8087
- evregister.service.softlayer.com [10.0.82.12] 8086, 8087

*Kostenpflichtige AMP-Proxy-Server*

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

**Federal-Komponenten**

*WebCC und AMP-Proxy*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087
 
Der Agent muss den eingehenden TCP-Port 2548 im privaten Netz zulassen. Diese Einstellung ermöglicht CentralControl und WebCC, im Agenten eine Verbindung zu dessen Verwaltung herzustellen. Ältere Versionen von EVault nutzten Port 808.

Der EVault-Management-Port (2548) kann durch eine Aktualisierung des Registrierungsschlüssels unter `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber` (`dword`) in Windows-Betriebssystemen geändert werden.

**Erläuterung**. In Bezug auf die Verbindungseinstellungen bestehen häufig Unklarheiten hinsichtlich des Unterschieds zwischen der CentralControl-Desktopinstanz und dem Agenten. Der auf dem Server implementierte Agent stellt eine Verbindung zu den EVault-Servern her, während die auf dem Desktop verwendete CentralControl-Instanz Verbindungen zu Ihrem Server herstellt und hierbei seine Adresse und die Serverberechtigungsnachweise für den Zugriff verwendet.
