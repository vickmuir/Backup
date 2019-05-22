---

copyright:
  years: 1994, 2019
lastupdated: "2019-03-26"

keywords: IBM Cloud backup, bare metal restore, bmr, plug-in, plugin, EVault, Carbonite, baremetal, point-in-time restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 安裝 Bare Metal Restore 外掛程式
{: #BMRplugin}

BMR 是一個災難回復解決方案。您可以在發生災害（例如，作業系統失敗或硬體故障）之後，使用 BMR 從裸機狀態還原您的伺服器。使用 BMR，您就可以從 {{site.data.keyword.BluSoftlayer_full}} 管理的安全位置快速還原系統映像檔。

BMR 是實體伺服器上僅限 Microsoft Windows 的產品。它不適用於虛擬伺服器。不支援 Linux 發行套件的 Bare Metal Restore。只有 Backup 代理程式 8.30 或更早版本才支援 BMR。（2018 年 6 月 30 日）
{:important}

**提供的功能**

- 將您的系統還原至選取的時間點。
- 從映像檔或檔案型備份還原您的系統。
- 從儲存在 {{site.data.keyword.backup_notm}} 的備份還原系統。
- 可啟動的回復交易，可用來在沒有可開機系統的情況下還原資料。

## 訂購外掛程式
{: #orderingBMR}

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}){: external}，然後按一下左上方的**功能表**圖示。選取**標準基礎架構**。<br/>
      或者，您也可以登入 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}。
2. 按一下**儲存空間** > **備份**以顯示具有備份服務的伺服器。
3. 選取您的帳戶，然後按一下**訂購外掛程式**。
4. 選取 **{{site.data.keyword.backup_notm}} 外掛程式 - BMR (Bare Metal Restore)**，然後按一下**繼續**。
5. 如果您有「促銷代碼」，請輸入它，然後按一下**重新計算**。
6. 即會顯示更新的費用。請檢閱您的訂單。
7. 勾選此方框，指出您已閱讀並接受「協力廠商服務合約」。
8. 按一下**下訂單**。

## 下載使用手冊
{: #BMRUserGuide}

使用 {{site.data.keyword.BluVPN}} 連接至 {{site.data.keyword.BluSoftlayer_full}} 網路，以便您可以從 [Downloadable {{site.data.keyword.backup_notm}} Documentation](http://downloads.service.softlayer.com/evault/Documentation/){: external} 存取及下載使用手冊。
