---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 開始使用 {{site.data.keyword.backup_notm}} 服務
{: #GettingStarted}

備份可確保您的資料安全地儲存在裝置外部，而且在遺失的情況也受到保護。{{site.data.keyword.backup_full}} 是一種以代理程式為基礎的自動化備份系統，可透過 {{site.data.keyword.backup_notm}} 入口網站的瀏覽器型管理公用程式進行管理。{{site.data.keyword.backup_notm}} 提供方法讓使用者在 {{site.data.keyword.BluSoftlayer_full}} 網路的一個以上資料中心內的伺服器之間備份資料。管理者可以將備份設定為遵循每日、每週或自訂排程，且排程是以完整系統、特定目錄或甚至個別檔案為目標。額外的外掛程式確保與 Microsoft Exchange 和 Microsoft SQL 這類軟體以及其他類型的協力廠商軟體相容，並在必要時讓使用者完成 Bare Metal Restore。

## 訂購 {{site.data.keyword.backup_notm}}

您可以使用兩種方式來購買 {{site.data.keyword.backup_notm}} 服務。

- [訂購伺服器時購買備份](#purchasingwithserver)。
- [以升級方式購買備份](#purchasingasupgrade)。

如需定價的相關資訊，請參閱 [{{site.data.keyword.backup_notm}} 儲存空間 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.ibm.com/cloud/backup-and-restore){:new_window} 和 [{{site.data.keyword.backup_notm}} on IBM Cloud ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.ibm.com/cloud/evault/pricing){:new_window}。

### 訂購伺服器時購買 {{site.data.keyword.backup_notm}}
{: #purchasingwithserver}

1. 登入 [IBM Cloud 型錄 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://{DomainName}/catalog/){:new_window} 或 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}
2. 訂購每月裸機伺服器。如需訂購裸機伺服器的相關資訊，請參閱[建置自訂裸機伺服器](https://{DomainName}/docs/bare-metal/baremetal-provision.html){:new_window}。
   1. 選取數量、計費選項。輸入主機及網域名稱。您可以選擇喜歡的任何主機名稱及網域。

      訂購按小時計費的伺服器時，無法使用 {{site.data.keyword.backup_notm}} 服務。不過，稍後可用升級方式新增此服務。
   {:tip}
   2. 選取位置。
   3. 選取伺服器配置及 OS 映像檔類型。您也可以選擇多個附加程式。
   4. 在**儲存空間磁碟**區段下，按一下**附加程式**，然後選取 **{{site.data.keyword.backup_notm}}**。選擇符合您需要的選項。
   5. 在**網路介面**下，選取上行鏈路速度，及您要的任何附加程式。
3. 在右邊，檢閱您的訂單摘要。
4. 檢閱條款之後，勾選**我已閱讀並同意協力廠商服務合約**方框。
5. 按一下**佈建**。系統會將您重新導向至具有佈建訂單號碼的畫面。您可以列印此畫面，因為它也是您的佈建訂單收據。

   您也可以按一下**另存為報價**，儲存此訂單而不採購。
   {:tip}

一系列電子郵件會傳送給您的管理者：確認佈建訂單、佈建訂單核准和處理，以及佈建完成。佈建完成電子郵件會包含*裝置詳細資料* 頁面的鏈結，而您可以在登入 {{site.data.keyword.cloud_notm}} 之後存取該頁面。您也可以直接登入 {{site.data.keyword.slportal}}。

#### 確認 {{site.data.keyword.backup_notm}} 購買
1. 在 [{{site.data.keyword.cloud_notm}} 主控台 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://{DomainName}/){:new_window} 中，按一下左上方的**功能表**圖示。選取**標準基礎架構**。</br>
   或者，您也可以登入 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}。
2. 按一下**裝置** > **裝置清單**。
2. 找出您已訂購的新伺服器。
  - 如果您看到 URL 旁邊有時鐘圖示，則您需要等待，以繼續進行 {{site.data.keyword.backup_notm}} 購買確認。您可以重新整理頁面，以查看新伺服器的更新狀態。不再出現時鐘圖示時，您便可以繼續進行接下來的步驟，以確認 {{site.data.keyword.backup_notm}} 服務購買。
  - 當您的伺服器不再顯示時鐘圖示時，請按一下鏈結（伺服器的 URL），移至**裝置詳細資料**頁面。
3. 按一下**儲存空間**標籤，以顯示 {{site.data.keyword.backup_notm}} 資訊。
4. 檢查 {{site.data.keyword.backup_notm}} 區段，並驗證有顯示購買處理程序期間所選取的大小。

### 以升級方式購買 {{site.data.keyword.backup_notm}}
{: #purchasingasupgrade}

#### 選取要安裝 {{site.data.keyword.backup_notm}} 的伺服器

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://{DomainName}){:new_window}，然後按一下左上方的**功能表**圖示。選取**標準基礎架構**。</br>
   或者，您也可以登入 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}。
2. 從主功能表中選取**裝置** > **裝置清單**。尋找您要為其新增備份服務的裝置。
3. 按一下「裝置」名稱，以移至**裝置詳細資料**頁面。

#### 新增（購買）{{site.data.keyword.backup_notm}} 服務
1. 按一下**儲存空間**標籤，然後向下捲動以找出 {{site.data.keyword.backup_notm}} 區段。
2. 按一下**新增**鏈結。
3. 在視窗中，選取位置，然後選取大小。
4. 選取「付款」類型，然後按一下**繼續**
5. 如果您有**促銷代碼**，請輸入它，然後按一下**重新計算**。
6. 檢閱您的訂單，然後按一下鏈結來閱讀條款。
7. 如果您同意條款，請按一下勾選框。
7. 按一下**下訂單**。

#### 確認 {{site.data.keyword.backup_notm}} 升級購買
1. 重新整理**裝置詳細資料**頁面，並確定已選取**儲存空間**標籤。
2. 檢查 {{site.data.keyword.backup_notm}} 區段，並驗證有顯示購買處理程序期間所選取的大小。

   如果備份儲存空間大小繼續顯示值為零的容量，則可能需要再次重新整理頁面。
   {:tip}

## 存取及檢視 {{site.data.keyword.backup_notm}} 儲存空間詳細資料

您隨時可以在 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}/){:new_window}和 {{site.data.keyword.slportal}} 上檢視服務的儲存空間詳細資料。可檢視的詳細資料包括與所選取 {{site.data.keyword.backup_notm}} 服務相關聯的密碼、儲存空間位址及用量。

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}){:new_window}，然後按一下左上角的**功能表**圖示。選取**標準基礎架構**。</br>
   或者，您也可以登入 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}。
2. 按一下**儲存空間**，然後從清單中選取**備份**。
2. 按一下您要檢視其儲存空間詳細資料的儲存庫列的任何位置。從這個視圖中，看不到「密碼」。
3. 按一下**密碼**欄位旁邊的**顯示**勾選框，以檢視所選取 {{site.data.keyword.backup_notm}} 服務的密碼。

在 {{site.data.keyword.slportal}} 內對 {{site.data.keyword.backup_notm}} 密碼所做的變更，會對服務本身進行。若要重設密碼，請遵循[變更備份服務的密碼](/docs/infrastructure/Backup?topic=Backup-changePassword)中的步驟。
{:important}

## 安裝 {{site.data.keyword.backup_notm}} 代理程式

下列作業系統可支援「{{site.data.keyword.backup_notm}} 代理程式」。

**Windows**
 - Windows Server 2016
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
 - RHEL 7.x
 - RHEL 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

請遵循適合您作業系統的指示：
- [在 Linux 中安裝備份用戶端](/docs/infrastructure/Backup?topic=Backup-InstallinLinux)
- [在 Windows 中安裝備份用戶端](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)
- [在 Windows 2016 中安裝備份用戶端](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016)

## 存取 {{site.data.keyword.backup_notm}} 入口網站（先前稱為 WebCC）

{{site.data.keyword.backup_notm}} 入口網站可用來與 {{site.data.keyword.BluSoftlayer_full}} 所提供之任何 {{site.data.keyword.backup_notm}} 服務互動。{{site.data.keyword.backup_notm}} 入口網站是一種瀏覽器型用戶端，其執行於 {{site.data.keyword.BluSoftlayer_full}} 專用網路，可供完全控制任何 {{site.data.keyword.backup_notm}} 服務，包括配置和還原。

1. 透過 VPN 存取「專用網路」。

   無法透過公用網路存取 {{site.data.keyword.backup_notm}} 入口網站。必須先建立 VPN 連線。
   {:important}
2. 在 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window} 中，存取「備份儲存空間」畫面。
3. 按一下想要查看之 {{site.data.keyword.backup_notm}} 服務列上的任何位置，來展開視圖。
4. 按一下 **{{site.data.keyword.backup_notm}} 入口網站登入**，以在瀏覽器中啟動入口網站用戶端。

## 配置備份代理程式和備份排程

在您訂購 {{site.data.keyword.backup_notm}} 並在伺服器上安裝代理程式之後，即可開始建立資料備份。請遵循下列步驟來配置代理程式、配置保留排程，以及啟動第一個備份工作。

1. 登入 {{site.data.keyword.backup_notm}} 入口網站。
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

        如需「保留方案」的相關資訊，請參閱[常見問題](faqs.html)。
        {:tip}
5. 執行代理程式並啟動備份。
   1. 按一下**所有代理程式**，然後選取您已配置的代理程式。
   2. 按一下**執行備份**。
   3. 確認「目的地」，並選取保留方案。
   4. 按一下**啟動備份**。您可以在處理程序執行時檢視備份詳細資料。
   5. 當備份完成時，請按一下**關閉**。

如需相關資訊，請參閱[在 Linux 上配置簡單的檔案層次備份](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup)。
{:tip}

## 取得線上說明

{{site.data.keyword.backup_notm}} 入口網站的系統有完整的文件說明，並且可在  {{site.data.keyword.backup_notm}} 入口網站中存取應用程式的支援。按一下位在**說明**右上角之藍色圓圈中的白色問號。按一下左側導覽列中的任何文章或主題，以檢視相關資訊。
