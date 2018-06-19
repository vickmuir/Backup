---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# 安裝 EVault Exchange 外掛程式

Exchange 外掛程式會與「Windows 代理程式」一起安裝在主機上。使用 WebCC 入口網站，您可以配置工作、將 Oracle 資料庫備份至安全的遠端儲存庫，以及還原 Oracle 資料庫。「Oracle 外掛程式」會整合至現有的架構。

## 提供的功能

- 備份及還原 Microsoft Exchange 資料庫的能力。

## 訂購外掛程式

1. 登入 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}。
2. 按一下**儲存空間**>**備份**。
3. 選取 EVault 帳戶，並按一下**訂購外掛程式**。
4. 選取 **EVault 外掛程式 - Exchange**，然後按一下**繼續**。
5. 如果您有「促銷代碼」，請輸入它，然後按一下**重新計算**。
6. 即會顯示更新的費用。請檢閱您的訂單。
7. 勾選方框以指出您已閱讀「主要服務合約」，並接受「協力廠商軟體條款」。 
8. 按一下**下訂單**。

## 安裝 Exchange 外掛程式

「Exchange 外掛程式」是在「Windows 代理程式」64 位元安裝期間安裝的。您可以在安裝「代理程式」時安裝「外掛程式」，或在稍後安裝它，方法為使用「修改」選項來重新執行安裝。

**附註**：在安裝 Microsoft Windows 伺服器的外掛程式之前，請停止 `services.msc` 中的兩個 EVault 服務。  

1. 瀏覽至 `c:\installs\evault` 資料夾，並執行修訂號碼較高的 .exe 檔。
2. 在語言畫面按一下**確定**。
3. 在歡迎使用畫面按**下一步**。
4. 選取**修改安裝**，然後按**下一步**。
5. 選取**保持不變**，然後按**下一步**。
6. 在自訂設定畫面中，選取您已購買的每一個外掛程式，並選取**此特性將安裝在 ...**，然後按**下一步**。
7. 選取**保留我的現行登錄**圓鈕，然後按**下一步**。
8. 按一下**安裝**。
9. 一旦安裝後，請檢查以確保這兩個服務都已啟用且在執行中。
10. 如果 WebCC 能夠存取（檢視）資料庫，則表示安裝成功。 

## 使用手冊

使用 {{site.data.keyword.BluVPN}} 連接至 {{site.data.keyword.BluSoftlayer_full}} 網路，以便您可以從[可下載的 EVault 文件](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}下載 EVault Agent v8.0 for Microsoft Windows (64-bit) - Exchange Plug-in Guide.pdf。本手冊說明如何使用 Exchange 外掛程式來備份及還原 Microsoft Exchange 資料庫。本手冊也會說明如何共用 DR 備份安全集，讓您可以使用 Granular Restore for Microsoft Exchange 應用程式，將特定信箱、訊息或其他物件還原至 .pst 檔案。


