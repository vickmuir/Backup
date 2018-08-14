---

copyright:
  years: 2014, 2018
lastupdated: "2018-07-10"

---
{:new_window: target="_blank"}

# 開始使用 EVault 備份服務

備份可確保您的資料安全地儲存在裝置外部，而且在遺失的情況也受到保護。EVault 備份是一種以代理程式為基礎的自動化備份系統，其管理方式是透過以 EVault WebCC 瀏覽器為基礎的管理公用程式進行。EVault 提供方法讓使用者在「{{site.data.keyword.BluSoftlayer_full}} 網路」的一個以上資料中心內的伺服器之間備份資料。管理者可以設定備份來遵循每小時、每日、每週或自訂排程，且排程是以完整系統、特定目錄或甚至個別檔案為目標。額外的外掛程式確保與 Microsoft Exchange 和 Microsoft SQL 這類軟體以及其他類型的協力廠商軟體相容，並在必要時讓使用者完成 Bare Metal Restore。

## 訂購 EVault 

您可以使用兩種方式來購買 EVault 備份服務。

- 訂購伺服器時購買 EVault
- 以升級方式購買 EVault

如需定價的相關資訊，請參閱[備份儲存空間](https://www.ibm.com/cloud/backup-and-restore){:new_window}及 [EVault on IBM Cloud](https://www.ibm.com/cloud/evault/pricing){:new_window}。

### 訂購伺服器時購買 EVault

1. 登入 [IBM Cloud 型錄](https://console.bluemix.net/catalog/){:new_window}或 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}。
2. 訂購每月裸機伺服器。您可以在[這裡](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html){:new_window}進一步瞭解如何訂購裸機伺服器。
3. 系統會將您重新導向至管理入口網站，以完成訂單。<br/>
   >**附註**：訂購按小時計費的伺服器時，無法使用 EVault 備份服務。不過，稍後可用升級方式新增此服務。 
4. 在**附加程式**區段下，選擇其中一個 EVault 選項（「無」以外）。
6. 向下捲動，然後按一下**新增至訂單**。
7. 尋找「主機及網域名稱」 區段，然後輸入主機及網域名稱。您可以選擇喜歡的任何主機名稱及網域。
8. 在右側，按一下**雲端服務條款**及**協力廠商服務合約**勾選框。
9. 確認或輸入您的付款資訊，然後按一下**提交訂單**。系統會將您重新導向至具有佈建訂單號碼的畫面。您可以列印此畫面，因為它也是您的佈建訂單收據。<br/>**附註**：您也可以按一下**儲存為報價**來儲存此訂單，而不購買。

一系列電子郵件會傳送給您的管理者：確認佈建訂單、佈建訂單核准和處理，以及佈建完成。佈建完成電子郵件會包含*裝置詳細資料* 頁面的鏈結，而您可以在登入 {{site.data.keyword.cloud_notm}} 之後存取該頁面。您也可以直接登入 {{site.data.keyword.slportal}}。

**確認 EVault 服務購買**
1. 在 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} 中，從主功能表中選取**裝置** > **裝置清單**。 
2. 找出您已訂購的新伺服器。
  - 如果 URL 旁邊有時鐘圖示，則您需要等待，以繼續進行 EVault 購買確認。您可以重新整理頁面，以查看新伺服器的更新狀態。不再出現時鐘圖示時，您便可以繼續進行接下來的步驟，以確認 EVault 服務購買。
  - 當您的伺服器不再顯示時鐘圖示時，請按一下鏈結（伺服器的 URL），移至**裝置詳細資料**頁面。 
3. 按一下**儲存空間**標籤，以顯示 EVault 資訊。
4. 檢查 EVault 區段，並驗證 EVault 購買處理程序期間所選取的大小顯示在 EVault 鏈結旁邊。

### 以升級方式購買 EVault

**選取要安裝 EVault 的伺服器**
1. 登入 [IBM Cloud 型錄](https://console.bluemix.net/catalog/){:new_window}或 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}。
2. 從主功能表中選取**裝置** > **裝置清單**。尋找您要為其新增 EVault 服務的裝置。
3. 按一下「裝置」名稱，以移至「裝置詳細資料」頁面。

**新增（購買）EVault 服務**
1. 按一下**儲存空間**標籤，然後向下捲動以找出 EVault 區段。
2. 按一下**新增**鏈結。
3. 在視窗中，選取位置，然後選取大小。
4. 選取「付款」類型，然後按一下**繼續**
5. 如果您有**促銷代碼**，請輸入它，然後按一下**重新計算**。
6. 檢閱您的訂單，然後按一下鏈結來閱讀條款。
7. 如果您同意條款，請按一下勾選框。
7. 按一下**下訂單**。

**確認 EVault 升級購買**
1. 重新整理**裝置詳細資料**頁面，並確定已選取**儲存空間**標籤。
2. 檢查 EVault 區段，並驗證 EVault 購買處理程序期間所選取的大小顯示在 EVault 鏈結旁邊。<br /> **附註**：如果 EVault 儲存空間大小繼續顯示值為零的容量，則可能需要再次重新整理頁面。 

## 存取及檢視 {{site.data.keyword.slportal}} 中的 EVault 備份儲存空間詳細資料

您隨時可以在 {{site.data.keyword.slportal}} 上檢視 EVault 備份服務的儲存空間詳細資料。可檢視的詳細資料包括與所選取 EVault 備份服務相關聯的密碼、儲存空間位址及用量。 

1. 若要存取 **EVault 備份儲存空間**畫面，請使用您的唯一認證登入 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}。
2. 按一下**儲存空間**，然後從清單中選取**備份**。
2. 按一下您要檢視其儲存空間詳細資料的 EVault 備份儲存庫列的任何位置。從這個視圖中，看不到「密碼」。繼續進行下一步，以檢視與 EVault 備份服務相關聯的密碼。
3. 按一下**密碼**欄位旁邊的**顯示**勾選框，以檢視所選取 EVault 備份服務的密碼。

對於許多 {{site.data.keyword.BluSoftlayer_full}} 產品及服務，{{site.data.keyword.slportal}} 內的密碼儲存特性僅用於儲存或追蹤密碼。對於這些供應項目，在 {{site.data.keyword.slportal}} 內對其所做的變更不會套用至產品或服務。 

EVault 備份的情況_不是如此_。在 {{site.data.keyword.slportal}} 內對 EVault 備份密碼所做的變更，會對服務本身進行。當您變更密碼時，請記住它會直接影響您的服務。若要重設密碼，請遵循[如何在 {{site.data.keyword.slportal}} 變更 EVault 備份密碼](/docs/infrastructure/Backup/change-password-evault-backup-service.html)中的步驟。

## 安裝 EVault 代理程式

下列作業系統支援「EVault 代理程式」：

**Windows**
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

**Linux**
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - Red Hat Enterprise Linux 7.x
 - Red Hat Enterprise Linux 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

請遵循適合您作業系統的指示：
- [在 Linux 中安裝 EVault 備份用戶端](install-evault-backup-client-linux.html)
- [在 Windows 中安裝 EVault 備份用戶端](install-evault-backup-client-windows.html)
- [在 Windows 2016 中安裝 EVault 備份用戶端](install-evault-windows2016.html)

## 存取 WebCentralControl (WebCC) 以使用 EVault 備份

WebCentralControl (WebCC) 是用來與 {{site.data.keyword.BluSoftlayer_full}} 所提供之任何 EVault 備份服務互動的用戶端。WebCC 是一種瀏覽器型用戶端，可在 {{site.data.keyword.BluSoftlayer_full}} 專用網路上執行，並容許完全控制任何 EVault 備份服務（包括配置及還原）。請遵循下列步驟來存取 WebCC，以使用 EVault 備份。

1. 透過 VPN 存取「專用網路」。<br/>**附註**：無法透過公用網路存取 WebCC。必須先建立 VPN 連線。
2. 在 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} 中，存取 EVault 備份儲存空間畫面。
3. 按一下想要的 EVault 備份列上的任何位置，來展開視圖。
4. 按一下 **WebCC 登入**，在瀏覽器中啟動 WebCC 用戶端。

## 在 WebCC 中配置 EVault 代理程式

在您訂購 EVault 服務並在伺服器上安裝代理程式之後，即可開始建立資料備份。請遵循下列步驟來配置代理程式、配置保留排程，以及啟動第一個備份工作。

1. 登入 WebCc。
2. 按一下**所有代理程式** > **未配置的代理程式**。
3. 按一下**這是我想要配置的新代理程式**鏈結。逐步執行處理程序，並輸入下列資訊：
   1. 代理程式配置 - 提供代理程式說明，並按**下一步**。
   2. 工作類型選取 - 輸入工作名稱、工作說明和備份來源類型，然後按**下一步**。
   3. 選取 - 選取目錄並按一下**包含...**。
   4. 選項 - 提供密碼
   5. 排程 - 按一下**新增**以建立排程，並按**下一步**。
   6. 選取預設儲存庫，並按一下**確定**。
   7. 按一下**儲存**。
4. 建立保留排程。
   1. 選取**編輯** > **代理程式設定**。
   2. 按一下**新增**。
   3. 完成您的保留詳細資料。
   4. 按一下**確定**。
   5. 按一下**儲存**。
   **附註**：在[這裡](evault-backup-faq.html)進一步閱讀「保留方案」的運作方式。
5. 執行代理程式並啟動備份。
   1. 按一下**所有代理程式**，然後選取您已配置的代理程式。
   2. 按一下**執行備份**。
   3. 確認「目的地」，並選取保留方案。
   4. 按一下**啟動備份**。您可以在處理程序執行時檢視備份詳細資料。
   5. 當備份完成時，請按一下**關閉**。
   
>**附註**：在[這裡](configure-simple-file-backup-linux.html)進一步閱讀如何在 Linux 上配置簡單的檔案層次備份。

## 取得線上說明

WebCC 的系統有完整的文件說明，並且可在 WebCC 內存取應用程式的支援。按一下位在**說明**右上角之藍色圓圈中的白色問號。按一下左側導覽列中的任何文章或主題，以檢視相關資訊。


