---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-28"

keywords: IBM Cloud backup, EVault, Carbonite, IBM Cloud backup, Enterprise backup

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 佈建 {{site.data.keyword.backup_notm}}
{: #ordering}

您可以使用兩種方式來購買 {{site.data.keyword.backup_notm}} 服務。

- [訂購伺服器時購買備份](#purchasingwithserver)。
- [以升級方式購買備份](#purchasingasupgrade)。

如需定價的相關資訊，請參閱 [{{site.data.keyword.backup_notm}} 儲存空間 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.ibm.com/cloud/backup-and-restore){:new_window} 和 [{{site.data.keyword.backup_notm}} on IBM Cloud ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://www.ibm.com/cloud/backup/pricing){:new_window}。

## 訂購伺服器時購買 {{site.data.keyword.backup_notm}}
{: #purchasingwithserver}

1. 登入 [IBM Cloud 型錄 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://{DomainName}/catalog){:new_window} 或 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}
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

### 確認 {{site.data.keyword.backup_notm}} 購買
1. 在 [{{site.data.keyword.cloud_notm}} 主控台 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://{DomainName}){:new_window} 中，按一下左上方的**功能表**圖示。選取**標準基礎架構**。</br>
   或者，您也可以登入 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}。
2. 按一下**裝置** > **裝置清單**。
2. 找出您已訂購的新伺服器。
  - 如果您看到 URL 旁邊有時鐘圖示，則您需要等待，以繼續進行 {{site.data.keyword.backup_notm}} 購買確認。您可以重新整理頁面，以查看新伺服器的更新狀態。不再出現時鐘圖示時，您便可以繼續進行接下來的步驟，以確認 {{site.data.keyword.backup_notm}} 服務購買。
  - 當您的伺服器不再顯示時鐘圖示時，請按一下鏈結（伺服器的 URL），移至**裝置詳細資料**頁面。
3. 按一下**儲存空間**標籤，以顯示 {{site.data.keyword.backup_notm}} 資訊。
4. 檢查 {{site.data.keyword.backup_notm}} 區段，並驗證有顯示購買處理程序期間所選取的大小。

## 以升級方式購買 {{site.data.keyword.backup_notm}}
{: #purchasingasupgrade}

### 選取要安裝 {{site.data.keyword.backup_notm}} 的伺服器

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://{DomainName}){:new_window}，然後按一下左上方的**功能表**圖示。選取**標準基礎架構**。</br>
   或者，您也可以登入 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}。
2. 從主功能表中選取**裝置** > **裝置清單**。尋找您要為其新增備份服務的裝置。
3. 按一下「裝置」名稱，以移至**裝置詳細資料**頁面。

### 新增（購買）{{site.data.keyword.backup_notm}} 服務
1. 按一下**儲存空間**標籤，然後向下捲動以找出 {{site.data.keyword.backup_notm}} 區段。
2. 按一下**新增**鏈結。
3. 在視窗中，選取位置，然後選取大小。
4. 選取「付款」類型，然後按一下**繼續**
5. 如果您有**促銷代碼**，請輸入它，然後按一下**重新計算**。
6. 檢閱您的訂單，然後按一下鏈結來閱讀條款。
7. 如果您同意條款，請按一下勾選框。
7. 按一下**下訂單**。

### 確認 {{site.data.keyword.backup_notm}} 升級購買
1. 重新整理**裝置詳細資料**頁面，並確定已選取**儲存空間**標籤。
2. 檢查 {{site.data.keyword.backup_notm}} 區段，並驗證有顯示購買處理程序期間所選取的大小。

   如果備份儲存空間大小繼續顯示值為零的容量，則可能需要再次重新整理頁面。
   {:tip}

備妥時，請繼續在伺服器上安裝軟體代理程式，並在 {{site.data.keyword.backup_notm}} 入口網站中設定備份排程。如需相關資訊，請參閱[入門指導教學](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)。
