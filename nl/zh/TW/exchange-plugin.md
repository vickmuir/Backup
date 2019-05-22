---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, Exchange, plug-in, plugin, EVault, Carbonite

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 安裝 Exchange 外掛程式
{: #Exchangeplugin}

Exchange 外掛程式會與「Windows 代理程式」一起安裝在主機上。透過 {{site.data.keyword.backup_notm}} 入口網站，您可以配置工作、將 Exchange 資料庫備份至安全的遠端儲存庫，以及還原 Exchange 資料庫。外掛程式會整合至現有的架構。

**提供的功能**

- 備份及還原 Microsoft Exchange 資料庫的能力。

## 訂購外掛程式
{: #orderingExchangePlugin}

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}){: external}，然後按一下左上方的**功能表**圖示。選取**標準基礎架構**。<br/>
      或者，您也可以登入 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}。
2. 按一下**儲存空間** > **備份**以顯示具有備份服務的伺服器。
3. 選取您的帳戶，然後按一下**訂購外掛程式**。
4. 選取 **{{site.data.keyword.backup_notm}} 外掛程式 - Exchange**，然後按一下**繼續**。
5. 如果您有「促銷代碼」，請輸入它，然後按一下**重新計算**。
6. 即會顯示更新的費用。請檢閱您的訂單。
7. 勾選此方框，指出您已閱讀並接受「協力廠商服務合約」。
8. 按一下**下訂單**。

## 安裝外掛程式
{: #installExchangePlugin}

Exchange 外掛程式是在「Windows 代理程式」64 位元安裝期間安裝。外掛程式可以與代理程式同時安裝，也可以稍後安裝，方法是選取**修改**重新執行安裝。

在安裝 Microsoft Windows 伺服器的外掛程式之前，請停止 `services.msc` 中的兩個 {{site.data.keyword.backup_notm}} 服務。
{:tip}

1. 瀏覽至 `c:\installs\{{site.data.keyword.backup_notm}}` 資料夾，並執行修訂號碼較高的 .exe 檔。
2. 在語言畫面中，按一下**確定**
3. 在歡迎使用畫面中，按**下一步**
4. 選取**修改安裝**，然後按**下一步**。
5. 選取**保持不變**，然後按**下一步**。
6. 在自訂設定畫面中，選取您已購買的每個外掛程式。
7. 選取**此特性將安裝在 ...**，然後按**下一步**。
8. 選取**保留我的現行登錄**，然後按**下一步**。
9. 按一下**安裝**。
10. 安裝後，請檢查以確定這兩個服務都已啟用並在執行中。
11. 如果 {{site.data.keyword.backup_notm}} 入口網站能夠存取或檢視資料庫，即表示安裝成功。

## 下載使用手冊
{: #ExchangeUserGuide}

使用 {{site.data.keyword.BluVPN}} 連接至 {{site.data.keyword.BluSoftlayer_full}} 網路，以便您可以從 [Downloadable {{site.data.keyword.backup_notm}} Documentation](http://downloads.service.softlayer.com/evault/Documentation/){: external} 存取及下載使用手冊。本手冊說明如何使用 Exchange 外掛程式來備份及還原 Microsoft Exchange 資料庫。本手冊也會說明如何共用 DR 備份安全集。使用 DR 備份安全集，您可以使用 Granular Restore for Microsoft Exchange 應用程式，將特定信箱、訊息或其他物件還原至 .pst 檔案。
