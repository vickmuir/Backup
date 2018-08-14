---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-12"

---
{:new_window: target="_blank"}

# Wiederherstellung anhand einer Sicherung durchführen

Verwenden Sie die nachfolgenden Schritte, um mit EVault eine Dateiwiederherstellung durchzuführen. Anweisungen zum Wiederherstellen eines Systemimages enthält der Abschnitt zu [Windows BMR](restoring-evault-bmr-system-volume-image.html).

## WebCC starten

**Hinweis**: Denken Sie daran, Ihre {{site.data.keyword.BluVPN}}-Verbindung zu starten, damit Sie Zugang zum privaten {{site.data.keyword.BluSoftlayer_full}}-Netz erhalten. Andernfalls funktioniert der Link zu WebCC nicht.

1. Melden Sie sich beim [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} an und klicken Sie im Hauptmenü auf **Speicher** > **Sicherung**, um die Server mit EVault Backup-Service anzuzeigen.
2. Wählen Sie den Server aus, auf dem sich die wiederherzustellenden Dateien befinden. Klicken Sie auf den Pfeil, um den Link zu WebCC sichtbar zu machen.
3. Klicken Sie auf **WebCC**, um den WebCC-Client in Ihrem Browser zu starten.

## Daten wiederherstellen

1. Klicken Sie auf der linken Seite im Navigationsbereich auf **Alle Agenten**.
2. Klicken Sie auf den Agenten, um die Jobs anzuzeigen.
3. Klicken Sie auf den Job, der die gewünschte Sicherung enthält.
4. Klicken Sie auf **Wiederherstellung durchführen**.
5. Wählen Sie eine Wiederherstellungsquelle aus.
6. Wählen Sie eine Sicherungsversion aus.
7. Geben Sie das Verschlüsselungskennwort ein.
8. Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.
9. Wählen Sie die Kontrollkästchen neben den Dateien und Verzeichnissen aus, die Sie einbeziehen wollen, und klicken Sie anschließend auf **Einschließen**, um Ihre Auswahl zu speichern.
10. Sie können Ihre Auswahl mit dem aufgerufenen Fenster weiter filtern oder auf **OK** klicken, um die getroffene Auswahl unverändert zu verwenden.<br/>
Nachdem Sie Ihre Datei- und Verzeichnisauswahl einbezogen haben, können die Dateien nicht mehr im Fenster **Datendateien** ausgewählt werden. Sie werden im Fenster **Sicherungsgruppe** auf der rechten Seite angezeigt. <br/>**Hinweis**: Sie können Schritt 10 wiederholen, um weitere Dateien hinzuzufügen oder um bereits hinzugefügte Dateien (mithilfe von **Ausschließen**) zu entfernen. <br/>Mit der Schaltfläche **Entfernen** können Sie außerdem jede Position im Fenster **Sicherungsgruppe** löschen.
11. Sobald Ihre Sicherungsgruppe wie von Ihnen gewünscht konfiguriert ist, klicken Sie auf **Weiter**, um fortzufahren.
12. Behalten Sie im nächsten Fenster die Standardeinstellungen bei oder passen Sie die Wiederherstellung an Ihre Vorgaben an. Klicken Sie anschließend auf **Wiederherstellung durchführen**.
13. Die Dateien sind wiederhergestellt, sobald in der Anzeige **Prozessdetails** der Status **Wiederherstellung abgeschlossen** angezeigt wird.
