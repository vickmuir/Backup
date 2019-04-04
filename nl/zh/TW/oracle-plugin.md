---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, oracle, plug-in, plugin, EVault, Carbonite

subcollection: Backup

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 安裝 Oracle 外掛程式
{: #Oracleplugin}

Oracle 外掛程式是一種附加程式，並與「Windows 代理程式」或「Linux 代理程式」一起安裝在 Oracle 資料庫主機上。透過 {{site.data.keyword.backup_notm}} 入口網站，您可以配置工作、將 Oracle 資料庫備份至安全的遠端儲存庫，以及還原 Oracle 資料庫。Oracle 外掛程式會整合至現有的架構。

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
{: #orderingOraclePlugin}

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://{DomainName}){:new_window}，然後按一下左上方的**功能表**圖示。選取**標準基礎架構**。<br/>
   或者，您也可以登入 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}。
2. 按一下**儲存空間** > **備份**以顯示具有備份服務的伺服器。
3. 選取您的帳戶，然後按一下**訂購外掛程式**。
4. 選取 **{{site.data.keyword.backup_notm}} 外掛程式 - Oracle**，然後按一下**繼續**。
5. 如果您有「促銷代碼」，請輸入它，然後按一下**重新計算**。
6. 即會顯示更新的費用。請檢閱您的訂單。
7. 勾選此方框，指出您已閱讀並接受「協力廠商服務合約」。
8. 按一下**下訂單**。

## 安裝適用於 Windows 的外掛程式
{: #installOracleWin}

適用於 Windows 的 Oracle 外掛程式會與 32 位元或 64 位元「Windows 代理程式」一起安裝。若要安裝外掛程式，請執行「代理程式」安裝套件。此外掛程式會以選項形式出現在**自訂設定**頁面上。如需相關資訊，請參閱[在 Windows 中安裝 {{site.data.keyword.backup_notm}} 用戶端](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)。

在安裝外掛程式之前，請停止 `services.msc` 中的兩個 {{site.data.keyword.backup_notm}} 服務。
{:tip}

1. 瀏覽至 `c:\installs\evault` 資料夾，並執行修訂號碼較高的 .exe 檔。
2. 在語言畫面中，按一下**確定**
3. 在歡迎使用畫面中，按**下一步**
4. 選取**修改安裝**，然後按**下一步**。
5. 選取**保持不變**，然後按**下一步**。
6. 在自訂設定畫面中，選取您已購買的每個外掛程式，選取**此特性將安裝在 ...**，然後按**下一步**。
7. 選取**保留我的現行登錄**，然後按**下一步**。
8. 按一下**安裝**。
9. 安裝完成後，請檢查以確定這兩個服務都已啟用且在執行中。
10. 如果 {{site.data.keyword.backup_notm}} 入口網站能夠存取或檢視資料庫，即表示安裝成功。

## 安裝適用於 Linux 的外掛程式
{: #installOracleLin}

Oracle 外掛程式是「Linux 代理程式」的附加程式，並與「代理程式」一起安裝在資料庫主機上。必須先安裝「Linux 代理程式」應用程式，才會進行外掛程式安裝。此代理程式以 32 位元應用程式和 64 位元應用程式提供。如需相關資訊，請參閱[在 Linux 中安裝 {{site.data.keyword.backup_notm}} 用戶端](/docs/infrastructure/Backup?topic=Backup-InstallinLinux)。

Oracle 外掛程式安裝套件是以 tar.gz 檔案提供。

1. 在主機上，下載安裝套件。
   ```
   http://downloads.softlayer.com/evault/Oracle-Plugin-Linux-x64-8.10.5249.tar.gz
   ```
   {: pre}

2. 從套件解壓縮檔案。
   ```
   # cd /tmp
   # tar xvf Oracle-Plugin-Linux-x64-8.10.5249.tar
   ```
   {: pre}

3. 移至資料夾。
   ```
   # cd Oracle-Plugin-Linux-x64-8.10.5249.xxxx
   ```
   {: pre}

4. 執行安裝 Script。
   ```
   # ./install.sh
   ```
   {: pre}

5. 遵循畫面上的安裝指示。

Oracle 外掛程式會執行「不一致」的整個資料庫備份，這需要以 ARCHIVELOG 模式執行資料庫。DBA 需要先確定資料庫處於 ARCHIVELOG 模式，再啟動備份。如需相關資訊，請參閱使用手冊。
{:important}


## 下載使用手冊
{: #OracleUserGuide}

使用 {{site.data.keyword.BluVPN}} 連接至 {{site.data.keyword.BluSoftlayer_full}} 網路，以便您可以從 [Downloadable {{site.data.keyword.backup_notm}} Documentation ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window} 下載使用手冊。
