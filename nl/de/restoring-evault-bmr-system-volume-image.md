---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# Systemdatenträgerimage von EVault BMR wiederherstellen 

Falls Sie eine Bare-Metal-Imagesicherung aus einer EVault-Instanz wiederherstellen müssen, ist dies ohne großen Zeitaufwand über das Rescue-Kernel-System von EVault BMR möglich. Mit EVault BMR können Sie das System wiederherstellen, ohne dass hierzu ein bootfähiges Betriebssystem benötigt wird. Dies ist äußerst hilfreich, falls das Betriebssystem nicht mehr verwendbar ist oder die Laufwerke im System ersetzt wurden.

## Rescue-Kernel-System von EVault BMR starten

Auf das Rescue-Kernel-System von EVault BMR können Sie über das {{site.data.keyword.slportal}} zugreifen.
1. Melden Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an.
2. Klicken Sie auf **Speicher** > **Sicherung**. 
3. Klicken Sie auf den **Pfeil** neben der Vault.
4. Klicken Sie auf **Bare-Metal-Wiederherstellung starten**. Diese Aktion startet eine Transaktion, deren Ausführung einige Minuten dauert. Anschließend können Sie mit den hier beschriebenen Schritten auf den Server zugreifen. Sobald das System den Bootprozess abgeschlossen hat, werden Sie per E-Mail benachrichtigt.


## Aus Rescue-Kernel von EVault BMR wiederherstellen

1. Wenn die Transaktion für den Rescue-Kernel von EVault BMR geladen wird, haben Sie für den Zugriff zwei verschiedene Möglichkeiten. 
  - Sie können einen VNC-Client und die private/öffentliche IP-Adresse Ihres Servers sowie das im {{site.data.keyword.slportal}} aufgelistete Kennwort verwenden. 
  - Sie können die KVM-Konsole Ihrer IPMI-Karte verwenden. 
  Beide Verfahren funktionieren gut. 
2. Wenn Sie sich zum ersten Mal beim Rescue-Kernel von EVault BMR anmelden, werden Sie mit einer Anzeige für die Sprachauswahl begrüßt. Wählen Sie die gewünschte Sprache aus und klicken Sie auf **Weiter**.
<br/>![Abbildung 1 - BMR-Sprachauswahl](/images/bmr1.png)<br/> Die Lizenzvereinbarung für die Software wird angezeigt. 
3. Wenn Sie den Bedingungen zustimmen, wählen Sie das Kontrollkästchen aus und klicken Sie auf **Weiter**, um fortzufahren. <br/> Daraufhin wird das Hauptmenü für die EVault-Systemwiederherstellung angezeigt. 
4. Wählen Sie **Eigenes System wiederherstellen** aus.
<br/>![Abbildung 2 - BMR-Hauptmenü](/images/bmr2.png)
5. Der Assistent für die EVault-Systemwiederherstellung wird aufgerufen. Wählen Sie **Weiter** aus, um fortzufahren.
<br/>![Abbildung 3 - BMR-Assistent](/images/bmr3.png)
6. Wählen Sie einen Sicherungstyp für die Wiederherstellung aus. Wählen Sie **EVault-Software** aus und klicken Sie danach auf **Weiter**, um fortzufahren.
7. Wählen Sie in der Anzeige **Sicherungsposition** die Vault aus und geben Sie die Vaultadresse, die EVault-Kontonummer sowie den Benutzernamen und das Kennwort ein. Klicken Sie anschließend auf **Weiter**, um fortzufahren.
<br/>![Abbildung 4 - Sicherungsposition auswählen](/images/bmr4.png)
8. In der nächsten Anzeige wird Ihr System in der Liste angezeigt. Stellen Sie sicher, dass es hervorgehoben ist, und klicken Sie auf **Weiter**.
<br/>![Abbildung 5 - System auswählen](/images/bmr5.png)
9. Wählen Sie in der Anzeige **Sicherungsjobauswahl** den Job aus, aus dem die Wiederherstellung erfolgen soll, und klicken Sie auf **Weiter**.
<br/>![Abbildung 6 - Wiederherstellungspunkt auswählen](/images/bmr6.png)
10. Wählen Sie im Menü **Wiederherstellungspunkt auswählen** den gewünschten Wiederherstellungspunkt aus und klicken Sie auf **Weiter**.
<br/>![Abbildung 8 - Wiederherstellungspunkt auswählen](/images/bmr8.png)
11. Wählen Sie den Quellen- und den Zieldatenträger aus. Um die Quelle am Ziel wiederherzustellen, ziehen Sie den Quellendatenträger auf den Zieldatenträger.
<br/>![Abbildung 9 - Quellen- und Zieldatenträger auswählen](/images/bmr9.png)
12. Im Bestätigungsfeld für die Formatierung oder Zusammenführung der Daten gibt es zwei Optionen. Wählen Sie die Option **Formatieren** aus, um eine komplette Wiederherstellung durchzuführen, bei der der Datenträger formatiert wird. Falls Sie die Daten auf dem Zieldatenträger zusammenführen wollen, wählen Sie **Zusammenführen** aus.
<br/>![Abbildung 10 - Zusammenführung auswählen](/images/bmr10.png)
13. Klicken Sie in der Hauptanzeige für den Quellen- und Zieldatenträger auf **Weiter**.
14. Wählen Sie in der Anzeige mit der Zusammenfassung des Wiederherstellungsplans das Kontrollkästchen aus, um den Plan zu akzeptieren, und klicken Sie auf **Weiter**.
<br/>![Abbildung 11 - Wiederherstellung starten](/images/bmr11.png)
15. Die Fortschrittsanzeige für die Wiederherstellung wird aufgerufen und gibt jeweils den aktuellen Verarbeitungsfortschritt der Wiederherstellung an.
<br/>![Abbildung 12 - Verarbeitungsfortschritt der Wiederherstellung](/images/bmr12.png)
16. Nach der Fertigstellung wird ein Benachrichtigungsfenster ausgegeben, in dem angegeben ist, dass die Wiederherstellung erfolgreich abgeschlossen wurde. Klicken Sie auf **OK**.
17. Klicken Sie in der Fortschrittsanzeige für die Wiederherstellung auf **Weiter**.
18. Wählen Sie in der Abschlussanzeige das Kontrollkästchen für den Neustart des Systems und dann **Fertigstellen** aus. Der Server lädt jetzt das wiederhergestellte Datenträgerimage. 
  Die Wiederherstellung ist hiermit abgeschlossen. <br/>
    >**Hinweis** - Beim ersten Durchlaufen dieses Vorgangs wird möglicherweise eine Nachricht über eine unerwartete Beendigung ausgegeben. Dies ist bei diesem Sicherungstyp normal; nach dem ersten Boot wird die Nachricht nicht mehr angezeigt. 
