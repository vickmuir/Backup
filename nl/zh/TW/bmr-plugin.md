---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 安裝 Bare Metal Restore 外掛程式

BMR 是適用於 Microsoft Windows 的災難回復解決方案。您可以在發生災害（例如，作業系統失敗或硬體故障）之後，使用 BMR 從裸機狀態還原您的伺服器。使用 BMR，您就可以從 {{site.data.keyword.BluSoftlayer_full}} 管理的安全位置快速還原系統映像檔。

BMR 是實體伺服器上僅限 Microsoft Windows 的產品。它不適用於虛擬伺服器。不支援 Linux 發行套件的 Bare Metal Restore。只有 Backup 代理程式 8.30 或更早版本才支援 BMR。（2018 年 6 月 30 日）。
{:important}

**提供的功能**

- 將您的系統還原至選取的時間點。
- 從映像檔或檔案型備份還原您的系統。
- 從儲存在 IBM Cloud Backup 的備份還原您的系統。
- 可啟動的回復交易，可用來在沒有可開機系統的情況下還原資料。.
## 訂購外掛程式

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}/catalog/){:new_window}，然後按一下左上角的**功能表**圖示。選取**標準基礎架構**。

   或者，您也可以登入 [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}。
2. 按一下**儲存空間** > **備份**以顯示具有備份服務的伺服器。
3. 選取您的帳戶，然後按一下**訂購外掛程式**。
4. 選取 **{{site.data.keyword.backup_notm}} 外掛程式 - BMR (Bare Metal Restore)**，然後按一下**繼續**。
5. 如果您有「促銷代碼」，請輸入它，然後按一下**重新計算**。
6. 即會顯示更新的費用。請檢閱您的訂單。
7. 勾選此方框，指出您已閱讀並接受「協力廠商服務合約」。
8. 按一下**下訂單**。

## 下載使用手冊

使用 {{site.data.keyword.BluVPN}} 連接至 {{site.data.keyword.BluSoftlayer_full}} 網路，以便您可以從 [Downloadable {{site.data.keyword.backup_notm}} Documentation ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window} 存取及下載使用手冊。

## 常見問題

**我是否可以從單一磁碟移至 RAID 陣列？**

是，可以。不過，因為 RAID 陣列會導致大小減少，所以您需要選取大容量的裝置。

**將映像檔還原到比原始磁區更大的磁碟時，會發生什麼情況？**

如果您將映像檔還原到比原始磁區更大的磁碟，則會取消配置剩下的空間。因此，例如，當您有一個 500 GB 磁碟並將其資料還原到 1 TB 磁碟時，則最後會有 500 GB 取消配置的磁碟空間。使用 Windows 2008，您可以使用內建磁碟公用程式來增加主要分割區。不過，Windows 2003 中沒有類似的內建功能，因此您必須以另一種方式配置空間。

**可以使用 BMR 進行定期備份嗎？**

BMR 備份不是磁碟映像檔，而是系統磁區映像檔備份系統。此系統並非預期用於定期備份，而是與其搭配使用。  

**可以使用 BMR 進行資料庫備份嗎？**

資料庫備份必須與一般 IBM Cloud Backup 方法分開執行。BMR 並不會取代 SQL 或 Oracle 外掛程式的需求。雖然 BMR 使用 VSS 技術來備份開啟檔案，但無法永遠保證備份的檔案為交易一致。這些特殊化應用程式類型的建議是您建立兩個備份工作：一個用於備份作業系統及應用程式二進位檔，另一個用於應用程式資料。在 BMR 使用手冊結尾處，有此影響的附註。

**哪種類型的還原工作可以與 BMR 搭配執行？**

您可以執行整個系統還原，也可以從備份中挑選個別檔案來進行還原。BMR 備份工作可以取代您的現行檔案備份工作。還原處理程序是在作業系統內執行，就像傳統備份工作一樣。

**BMR 具有開啟檔案備份功能嗎？**

BMR 具有開啟檔案備份功能。不過，BMR 並不會取代 SQL 或 Oracle 外掛程式的需求。如需 MSSQL 外掛程式的相關資訊，請參閱[這裡](mssql-plugin.html)。

**BMR 還原需要多少磁碟空間和時間？**

從預設安裝所進行的備份使用大約 6 GB。這類還原在 1 GB 埠上大約需要 15 分鐘。此程序也會受到專用埠速度影響。如果您需要更快速的備份及還原，可能需要增加埠速度。
