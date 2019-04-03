---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, multiple vaults, mulitple locations, disaster recovery

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 多重儲存
{: #multivault}

「多重儲存」是可讓用戶端將伺服器連接至多個儲存庫位置的功能。它提供令人安心的備援，因為即使有一個網站故障，也有備份可用。

**關鍵要點**

1. 多個儲存庫可透過相同的 {{site.data.keyword.backup_notm}} 入口網站進行管理，並以相同的方式進行處理。唯一的差異是您具有不同的儲存庫選項。
2. 外掛程式授權是根據每個儲存庫來進行 - 例如，如果對華盛頓特區中的 MSSQL 外掛程式購買儲存庫，則它無法在西雅圖儲存庫上運作。
3. 在每次購買之後，需要手動將新的儲存庫新增至 {{site.data.keyword.backup_notm}} 入口網站。



**{{site.data.keyword.backup_notm}} Vault Director 位置**

「多重儲存」可跨所有資料中心使用，且在選取遠端儲存庫時沒有地理限制。只要儲存庫配置正確，所有已配置的儲存庫都會出現在儲存庫設定中。

備份至遠端資料中心位置所花費的時間，可能會比備份至伺服器所在相同資料中心所花費的時間還要久。
{:note}

## 將遠端儲存庫新增至帳戶

您必須先將新的遠端儲存庫新增至帳戶，才能在 {{site.data.keyword.backup_notm}} 入口網站中新增備份位置。
{:important}

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}){:new_window}，然後按一下左上角的**功能表**圖示。選取**標準基礎架構**。<br/>
   或者，您也可以登入 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}。
2. 按一下**裝置**
3. 找出並按一下討論中之伺服器的鏈結。
4. 在**裝置詳細資料**下，按一下**儲存空間**。
5. 當「儲存空間」區段開啟時，往下捲動至 **{{site.data.keyword.backup_notm}}**，然後按一下**新增**。
6. 在**訂購 {{site.data.keyword.backup_notm}}** 視窗中，按一下遠端儲存庫在下拉清單中的項目，以選取其位置。
7. 選取儲存空間的大小，然後按一下**繼續**。
8. 勾選**我已閱讀主要...** 方框，然後按一下**下訂單**。

新訂購的儲存庫會自動新增至帳戶。如果沒有，請與業務代表聯絡以取得協助。

當訂購程序完成時，請移至**儲存空間** > **備份**，以查看列出的新儲存庫。

## 在 {{site.data.keyword.backup_notm}} 入口網站中新增額外儲存庫

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}){:new_window}，然後按一下左上角的**功能表**圖示。選取**標準基礎架構**。<br/>
   或者，您也可以登入 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}。
2. 按一下**儲存空間** > **備份**以顯示具有備份服務的伺服器。
3. 選取您要可以備份至多個儲存庫的伺服器。按一下向右箭頭，以顯示 {{site.data.keyword.backup_notm}} 入口網站鏈結。
4. 按一下 **{{site.data.keyword.backup_notm}} 入口網站登入**鏈結，以在瀏覽器中啟動入口網站用戶端。

   只能透過 {{site.data.keyword.BluVPN}} 來存取 {{site.data.keyword.backup_notm}} 入口網站。
{:tip}
5. 在左導覽窗格中，按一下**所有代理程式**。
6. 在右上角，按一下**編輯**，然後選取**儲存庫設定**。
7. 在**儲存庫設定**視窗中，按一下**新增**。
8. 在**新建儲存庫**視窗中，
  1. 在「儲存庫設定檔」功能表中，選擇**輸入儲存庫設定**來建立新項目。請不要更新現有項目，這樣沒有效果。
  2. 儲存庫名稱不能與其他儲存庫名稱相同。請嘗試將 `-2` 標籤新增至其尾端。<br/>

     儲存庫名稱欄位限制為 15 個字元。
     {:important}
  3. IP 位址欄位中會移入 {{site.data.keyword.backup_notm}} Director 位置資訊。例如，`ev-director301.service.softlayer.com` 具有 IP 位址 10.1.114.46，且位於 WDC 中。
  4. 在認證欄位中，輸入帳戶 ID、所選取儲存庫的 {{site.data.keyword.backup_notm}} 使用者名稱，以及所選取儲存庫的密碼。
  5. 按一下**儲存變更**。

幾秒鐘後，新儲存庫就可供使用。如果您收到連線失敗，請檢查您的設定，然後再試一次。請記住，新增一個額外儲存庫，就會顯示一個可讓您為工作選擇的額外目的地。它不會針對這兩個儲存庫自動執行工作。您需要設定工作，才能使用額外的儲存庫。如需相關資訊，請參閱[入門指導教學](/docs/infrastructure/Backup?topic=Backup-gettingstarted#getting-started)。
