---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 將一個 VSI 中的資料還原至相同資料中心中的另一個 VSI
{: #restorefromotherVSI}

有時，您想要將資料還原至相同資料中心內的不同伺服器。此程序僅適用於非作業系統檔案的檔案層次還原。若要還原系統映像檔，請遵循 [Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR) 指示。

此處理程序包括在第二部伺服器上重新登錄備份代理程式，以存取第一部伺服器的儲存庫位置，以及完成**從另一部電腦還原**。

**必要條件**

- Server1 和 Server2 必須具有相同的作業系統。不支援跨平台還原。
- Server1 和 Server2 必須具有先前配置的備份代理程式。如需配置備份代理程式的相關資訊，請參閱[在 {{site.data.keyword.backup_notm}} 入口網站中配置備份代理程式](/docs/infrastructure/Backup?topic=Backup-GettingStarted)。
- 已對 Server1 的儲存庫位置產生備份的 Server1 備份工作。

請停用這兩部伺服器上的所有排定工作，以避免發生任何衝突。
{:important}

## 啟動 Server2 的 {{site.data.keyword.backup_notm}} 入口網站
{: #startWebCC}

請記得啟動您的 {{site.data.keyword.BluVPN}} 連線，以存取 {{site.data.keyword.BluSoftlayer_full}} 專用網路，否則 {{site.data.keyword.backup_notm}} 入口網站鏈結無法運作。
{:tip}

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}/){:new_window}，然後按一下左上角的**功能表**圖示。選取**標準基礎架構**。<br/>
   或者，您也可以登入 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}。
2. 按一下**儲存空間** > **備份**以顯示具有備份服務的伺服器。
3. 選取 Server2。按一下指向右方的展開箭頭，以顯示 {{site.data.keyword.backup_notm}} 入口網站鏈結。
4. 按一下 **{{site.data.keyword.backup_notm}} 入口網站登入**，以在瀏覽器中啟動入口網站用戶端。

## 重新登錄儲存庫
{: #reregistervault}

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
{: #runbackuprestore}

1. 按一下**所有代理程式**。

   您可能需要重新整理頁面，才能在 Server2 的**工作**標籤下，看到在 Server1 上定義為可存取且已同步的工作。
   {:tip}
2. 將滑鼠移至**進階**上，並選取**從另一部電腦還原**。
3. 在**從另一部電腦還原**畫面上，選取下列各項。
  - 儲存庫 - 此項目預設為 Server1 的儲存庫。
  - 電腦 - 選取 Server1 作為要從該處還原的備份電腦。
  - 工作 - 選取來自 Server1 的備份工作。
4. 按**下一步**。
5. 確認來源資訊
  - **安全集位置**是 Server1 的「儲存庫」位置。
  - 在**選取備份版本**區段中，將 Server1 中的備份指定為備份版本。
  - 加密密碼是您在建立 Server1 的備份時所使用的密碼。
6. 按**下一步**。
7. 選取需要從 Server1 備份還原的檔案。請勾選您要還原之檔案和目錄旁邊的方框，然後按一下**包含**以儲存您的選項。
8. 按**下一步**以移至還原選項。
9. 在「選項」中，
  - 目的地 - 選取**還原至原始位置**
  - 檔案改寫 - 選取**改寫現有檔案**
10. 按一下**執行還原**。
11. 「處理程序詳細資料」畫面即會顯示還原工作的狀態。


## 驗證還原
{: #verifyrestore}

1. 透過 SSH 連接至 Server2 的根目錄。
2. 以長格式列出檔案及所有目錄項目。
  ```
  ls -la
  ```
  {: pre}

3. 比較輸出。

## 繼續一般備份排程。
{: #resumeschedule}

1. 當還原完成時，請移除 server1（資料還原的來源）的登錄資訊。
2. 輸入現行 server2 登錄並啟用「排程」作業。
