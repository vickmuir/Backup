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

# 安裝 SQL Server 外掛程式

SQL Server 外掛程式會與「Windows 代理程式」一起安裝在 SQL 資料庫主機上。透過 {{site.data.keyword.backup_notm}} 入口網站，您可以配置工作、將 SQL 資料庫備份至安全的遠端儲存庫，以及還原 SQL 資料庫。

**提供的功能**

- 您可以執行完整資料庫備份、具有交易日誌備份的完整資料庫，或僅交易日誌備份。
- 您可以同時執行多個備份。
- 您可以將 SQL 資料庫還原至相同的 SQL 實例，或還原至不同的 SQL 實例。
- 您可以使用原始資料庫名稱來還原資料庫、改寫現有資料庫，以及使用「無回復」選項進行還原。

如需相關資訊，請參閱[主要特性](#main-featues)小節。

## 訂購外掛程式

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://{DomainName}/){:new_window}，然後按一下左上方的**功能表**圖示。選取**標準基礎架構**。<br/>
   或者，您也可以登入 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}。
2. 按一下**儲存空間** > **備份**以顯示具有備份服務的伺服器。
3. 選取您的帳戶，然後按一下**訂購外掛程式**。
4. 選取 **{{site.data.keyword.backup_notm}} 外掛程式 - MSSQL**，然後按一下**繼續**。
5. 如果您有「促銷代碼」，請輸入它，然後按一下**重新計算**。
6. 即會顯示更新的費用。請檢閱您的訂單。
7. 勾選此方框，指出您已閱讀並接受「協力廠商服務合約」。
8. 按一下**下訂單**。

## 安裝 MSSQL 外掛程式

若要安裝外掛程式，請執行「代理程式」安裝套件。此外掛程式會以選項形式出現在**自訂設定**頁面上。

在安裝 Microsoft Windows 伺服器的 MSSQL 外掛程式之前，請停止 `services.msc` 中的兩個 {{site.data.keyword.backup_notm}} 服務。
{:tip}

1. 瀏覽至 `c:\installs\evault` 資料夾，並執行修訂號碼較高的 .exe 檔。
2. 在語言畫面中，按一下**確定**。
3. 在歡迎使用畫面中，按**下一步**。
4. 選取**修改安裝**，然後按**下一步**。
5. 選取**保持不變**，然後按**下一步**。
6. 在自訂設定畫面中，選取您已購買的每個外掛程式。
7. 選取**此特性將安裝在 ...**，然後按**下一步**。
8. 選取**保留我的現行登錄**，然後按**下一步**。
9. 按一下**安裝**。
10. 安裝後，請檢查以確定這兩個服務都已啟用並在執行中。
11. 如果 {{site.data.keyword.backup_notm}} 入口網站能夠檢視及存取資料庫，即表示安裝成功。

## 下載使用手冊

使用 {{site.data.keyword.BluVPN}} 連接至 {{site.data.keyword.BluSoftlayer_full}} 網路，以便您可以從 [Downloadable {{site.data.keyword.backup_notm}} Documentation ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window} 下載使用手冊。

## 主要特性

- 能夠使用萬用字元（星號和問號），指定要在 SQL Server 備份工作中包含及排除的資料庫名稱。執行工作時，會自動包含或排除名稱符合備份工作過濾器的新資料庫。
- 能夠在「AlwaysOn 可用性群組」中使用 64 位元代理程式及 SQL Server 外掛程式保護次要資料庫。
- 能夠共用包含 SharePoint 2010/2013 內容資料庫的 SQL 安全集，以與 Granular Restore for Microsoft SharePoint 應用程式搭配使用。共用安全集之後，就可以使用 Granular Restore 應用程式來還原站台集合、網站、清單、檔案庫、資料夾、清單項目或文件。
- 支援對跨越磁區的資料庫進行易於使用的差異備份。
- 能夠利用單一排程項目來保護完整回復模型中的資料庫。此選項容許在單一排程項目中保護資料庫，以及管理交易日誌的截斷。
- SQL Server 外掛程式支援「完整備份」、「搭配包含交易日誌的完整備份」，以及「交易日誌」備份（更新的術語，以符合 SQL Server 術語）。應用程式會繼續支援「單次作業還原」功能，讓客戶可選取時間點「交易日誌」備份。{{site.data.keyword.backup_notm}} 會還原完整資料庫，以及將資料庫還原至所選取時間點所需的所有交易日誌。
- 備份工作可以包含來自相同單一 SQL Server 實例的一個以上資料庫。您可以建立個別工作，從可以在想要時同步執行的不同 SQL Server 實例中備份其他資料庫。
- 能夠使用「無回復」來還原資料庫，以透過 SQL Server Management Studio 提供其他回復選項。
- 替代還原選項可支援還原至檔案，這可讓資料庫管理者透過 SQL System Manager 來裝載資料庫。
- 替代還原能夠將某個資料庫的還原導向另一個資料庫，即使是在邏輯資料庫名稱不符的情況。對於不符的物件，外掛程式會在實例的預設資料庫位置中建立資料庫。
- 支援 64 位元 SQL Server 2008 R2 (SP1) 及 SQL Server 2012 的「透明資料加密 (TDE)」。
- 如果 SQL Server 主機遺失，則可以安裝 SQL Server 軟體，並還原資料庫。（首先必須還原「主要」資料庫。）
- 啟動備份時，不論是否執行資料庫服務，都會進行備份。
- 支援還原至原始資料庫名稱（不論是否改寫現有資料庫）、透過現有資料庫還原，或還原至磁碟上的檔案。
