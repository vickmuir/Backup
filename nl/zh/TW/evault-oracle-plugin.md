---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# 安裝 EVault Oracle 外掛程式

Oracle 外掛程式會與「Windows 代理程式」一起安裝在 Oracle 資料庫主機上。透過 WebCC 入口網站，您可以配置工作、將 Oracle 資料庫備份至安全的遠端儲存庫，以及還原 Oracle 資料庫。Oracle 外掛程式會整合至現有的架構。

**提供的功能**

- 支援 Oracle 資料庫備份及回復。
- Oracle 外掛程式對整個線上資料庫實例，提供以 ARCHIVELOG 為基礎的非 RMAN 備份。系統會自動備份所有非暫存的表格空間及實例參數檔案。Oracle Corporation 建議在低資料庫活動的時段進行備份。
- 完整和局部資料庫是透過使用者管理的一般 Oracle 回復機制來還原。

**限制**
- 只會備份本端、單一實例、以磁碟為基礎的資料庫。
- 不會備份資料庫叢集。
- 不會備份原始裝置。
- 不會備份遠端資料庫。
- 資料庫必須在 ARCHIVELOG 模式下執行，且以其身分配置備份的使用者必須具有 SYSDBA 專用權。
- 資料庫密碼會透過以 Script 為基礎的方法來加密，以加強安全。

## 訂購外掛程式

1. 登入 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}。
2. 按一下**儲存空間** > **備份**。
3. 選取 EVault 帳戶，然後按一下**訂購外掛程式**。
4. 選取 **EVault 外掛程式 - Oracle**，然後按一下**繼續**。
5. 如果您有「促銷代碼」，請輸入它，然後按一下**重新計算**。
6. 即會顯示更新的費用。請檢閱您的訂單。
7. 勾選此方框，指出您已閱讀並接受「協力廠商服務合約」。 
8. 按一下**下訂單**。

## 安裝 Oracle 外掛程式

適用於 Windows 的 Oracle 外掛程式會與 32 位元或 64 位元「Windows 代理程式」一起安裝。若要安裝適用於 Windows 的 Oracle 外掛程式，請執行「代理程式」安裝套件。Oracle 外掛程式會以選項形式出現在**自訂設定**頁面上。

>**附註**：在安裝 Microsoft Windows 伺服器的外掛程式之前，請停止 `services.msc` 中的兩個 EVault 服務。  

1. 瀏覽至 `c:\installs\evault` 資料夾，並執行修訂號碼較高的 .exe 檔。
2. 在語言畫面中，按一下**確定**
3. 在歡迎使用畫面中，按**下一步**
4. 選取**修改安裝**，然後按**下一步**。
5. 選取**保持不變**，然後按**下一步**。
6. 在自訂設定畫面中，選取您已購買的每個外掛程式，選取**此特性將安裝在 ...**，然後按**下一步**。
7. 選取**保留我的現行登錄**，然後按**下一步**。
8. 按一下**安裝**。
9. 安裝完成後，請檢查以確定這兩個服務都已啟用且在執行中。
10. 如果 WebCC 能夠存取/檢視資料庫，即表示安裝成功。 

## 下載使用手冊

使用 {{site.data.keyword.BluVPN}} 連接至 {{site.data.keyword.BluSoftlayer_full}} 網路，您就可以從[可下載的 EVault 文件](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}下載 EVault Agent v8.0 for Microsoft Windows - Oracle plug-in Guide.pdf。




