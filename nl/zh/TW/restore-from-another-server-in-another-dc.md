---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup,  EVault, Carbonite, backup, restore

subcollection: Backup

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 將一個 VSI 中的資料還原至不同資料中心中的另一個 VSI
{: #restoreVSIotherlocation}

有時，您想要將資料還原至不同的伺服器。此程序僅適用於非作業系統檔案的檔案層次還原。若要還原系統映像檔，請遵循 [Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR) 指示。

此處理程序包括在第二部伺服器上重新登錄備份代理程式，以存取第一部伺服器的儲存庫位置，以及完成**從另一部電腦還原**。

**必要條件**

- Server1 和 Server2 必須具有相同的作業系統。不支援跨平台還原。
- Server1 和 Server2 必須具有先前配置的備份代理程式。如需配置備份代理程式的相關資訊，請參閱[在 {{site.data.keyword.backup_notm}} 入口網站中配置備份代理程式](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)。
- 已對 Server1 的儲存庫位置產生備份的 Server1 備份工作。

請停用這兩部伺服器上的所有排定工作，以避免發生任何衝突。
{:important}

## 啟動 Server2 的 {{site.data.keyword.backup_notm}} 入口網站
{: #startWebCCotherDC}

請記得啟動您的 {{site.data.keyword.BluVPN}} 連線，以存取 {{site.data.keyword.BluSoftlayer_full}} 專用網路，否則 {{site.data.keyword.backup_notm}} 入口網站鏈結無法運作。
{:tip}

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}/){:new_window}，然後按一下左上角的**功能表**圖示。選取**標準基礎架構**。<br/>
   或者，您也可以登入 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}。
2. 按一下**儲存空間** > **備份**以顯示具有備份服務的伺服器。
3. 選取 Server2。按一下指向右方的展開箭頭，以顯示 {{site.data.keyword.backup_notm}} 入口網站鏈結。
4. 按一下 **{{site.data.keyword.backup_notm}} 入口網站登入**，以在瀏覽器中啟動入口網站用戶端。

## 重新登錄儲存庫
{: #reregistervaultotherDC}

1. 按一下**所有代理程式**，然後開啟您要修改的特定代理程式。
2. 按一下**編輯**，然後選取**儲存庫設定**。
3. 按一下**重新登錄**，將 Server1 連接至 Server2。
4. 在**使用儲存庫設定檔**項目的**重新登錄儲存庫**畫面上，選取**輸入儲存庫設定**。
5. 輸入「儲存庫名稱」，其與 Server1 的儲存庫名稱相同。
6. 輸入 Server1 的認證以登入 Server1 的儲存庫。
7. 按一下**載入電腦**，此動作會顯示連接至儲存庫位置的伺服器。
8. 按一下**儲存變更**。
9. 出現提示時，請按一下**是**以確認重新登錄儲存庫。

## 從 Server1 執行備份工作，以作為 Server2 上的還原工作
{: #runbackuprestoreotherDC}

1. 按一下**所有代理程式**。

   您可能需要重新整理頁面，才能在 Server2 的**工作**標籤下，看到在 Server1 上定義為可存取且已同步的工作。
   {:tip}
2. 將滑鼠移至**進階**上，並選取**從另一部電腦還原**。
3. 在**從另一部電腦還原**畫面上，按一下**新增**。欄位中會自動移入預設值，因此請變更它們。
4. 按一下「儲存庫」欄位，並選取**輸入儲存庫設定**，然後鍵入 Server1 之儲存庫的 IP 位址。按一下**新增**。
5. 將認證更新為 Server1 的認證。
6. 按一下**儲存變更**。此動作會將您連接至 Server1 的儲存庫。
7. 回到**從另一部電腦還原**畫面，更新「電腦」及「工作」欄位。
  - 電腦 - 選取 Server1 作為要從該處還原的備份電腦。
  - 工作 - 選取來自 Server1 的備份工作。
8. 按**下一步**，將還原處理程序啟動到另一個資料中心內的 server2。
9. 系統提示時，請輸入備份密碼，然後按**下一步**。
10. 確認已選取正確的備份工作，然後按**下一步**。現在已在 server2 上配置還原工作。
11. 選取新配置的工作，然後按一下**執行還原**。
12. 選取您要還原的檔案。
13. 按一下加號以展開檔案選擇。
14. 按一下要從 server1 還原到 server2 之個別檔案或資料夾的勾選框。然後，按一下**包含**。
15. 檔案會移入右側的「備份集」視窗。按**下一步**。
16. 完成資料選擇之後，請繼續選取您的選項。
    - 選取**還原至原始位置**。
    - 選取**改寫現有檔案**。
17. 按一下**執行還原**。「處理程序詳細資料」視窗提供執行中備份工作的狀態。備份完成之後，請按一下**關閉**。


## 驗證還原
{: #verifyrestoreotherDC}

1. 透過 SSH 連接至 Server2 的根目錄。
2. 以長格式列出檔案及所有目錄項目。
  ```
  ls -la
  ```
  {: pre}

3. 比較輸出。

## 繼續一般備份排程。
{: #resumescheduleotherCD}

1. 當還原完成時，請移除 server1（資料還原的來源）的登錄資訊。
2. 輸入現行 server2 登錄並啟用「排程」作業。
