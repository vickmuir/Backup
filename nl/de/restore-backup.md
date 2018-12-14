---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Wiederherstellung anhand einer Sicherung durchführen

Verwenden Sie die nachfolgenden Schritte, um mit {{site.data.keyword.backup_full}} eine Dateiwiederherstellung durchzuführen. Anweisungen zum Wiederherstellen eines Systemimages enthält der Abschnitt zu [Windows BMR](restore-bmr-system-volume-image.html).

## WebCC starten

Denken Sie daran, Ihre {{site.data.keyword.BluVPN}}-Verbindung zu starten, um Zugriff auf das private {{site.data.keyword.BluSoftlayer_full}}-Netz zu erhalten. Andernfalls funktioniert der Link zu WebCC nicht.
{:important}

1. Melden Sie sich an der [{{site.data.keyword.cloud_notm}}-Konsole](https://console.bluemix.net/catalog/){:new_window} an und klicken Sie oben links auf das Symbol **Menü**. Wählen Sie **Klassische Infrastruktur** aus.

   Alternativ können Sie sich beim [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} anmelden.
2. Klicken Sie auf **Speicher** > **Sicherung**, um die Server mit Backup-Service anzuzeigen.
3. Wählen Sie den Server aus, auf dem sich die wiederherzustellenden Dateien befinden. Klicken Sie auf den Pfeil, um den Link zu WebCC sichtbar zu machen.
4. Klicken Sie auf **WebCC**, um den WebCC-Client in Ihrem Browser zu starten.

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
10. Sie können Ihre Auswahl mit dem aufgerufenen Fenster weiter filtern oder auf **OK** klicken, um die getroffene Auswahl unverändert zu verwenden.
Nachdem Sie Ihre Datei- und Verzeichnisauswahl einbezogen haben, können die Dateien nicht mehr im Fenster **Datendateien** ausgewählt werden. Sie werden im Fenster **Sicherungsgruppe** auf der rechten Seite angezeigt.

   Sie können Schritt 10 wiederholen, um weitere Dateien hinzuzufügen oder Dateien zu entfernen, die Sie zuvor hinzugefügt haben (mit **Exclude**). Mit der Schaltfläche **Entfernen** können Sie außerdem jede Position im Fenster **Sicherungsgruppe** löschen.
   {:tip}
11. Sobald Ihre Sicherungsgruppe wie von Ihnen gewünscht konfiguriert ist, klicken Sie auf **Weiter**, um fortzufahren.
12. Behalten Sie im nächsten Fenster die Standardeinstellungen bei oder passen Sie die Wiederherstellung an Ihre Vorgaben an. Klicken Sie anschließend auf **Wiederherstellung durchführen**.
13. Die Dateien sind wiederhergestellt, sobald in der Anzeige **Prozessdetails** der Status **Wiederherstellung abgeschlossen** angezeigt wird.
