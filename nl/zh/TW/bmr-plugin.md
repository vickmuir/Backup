---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-13"

keywords: IBM Cloud backup, bare metal restore, bmr, plug-in, plugin, EVault, Carbonite, baremetal, point-in-time restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 瞭解 Bare Metal Restore 外掛程式
{: #BMRplugin}

BMR 是一個災難回復解決方案。您可以在發生災害（例如，作業系統失敗或硬體故障）之後，使用 BMR 從裸機狀態還原您的伺服器。使用 BMR，您就可以從 {{site.data.keyword.cloud}} 管理的安全位置快速還原系統映像檔。

BMR 是實體伺服器上僅限 Microsoft Windows 的產品。它不適用於虛擬伺服器。不支援 Linux 發行套件的 Bare Metal Restore。只有 Backup 代理程式 8.30 或更早版本才支援 BMR。（2018 年 6 月 30 日）
{:important}

## 提供的功能
{: #BMRcapabilities}

- 將您的系統還原至選取的時間點。
- 從映像檔或檔案型備份還原您的系統。
- 從儲存在 {{site.data.keyword.backup_notm}} 的備份還原系統。
- 可啟動的回復交易，可用來在沒有可開機系統的情況下還原資料。

## 安裝 BMR 外掛程式
{: #installingBMR}

外掛程式是在「Windows 代理程式」安裝期間安裝。外掛程式可以與代理程式同時安裝，也可以稍後安裝，方法是選取**修改**重新執行安裝。

## 配置 BMR 備份工作
{: #configBMRplugin}

如需相關資訊，請參閱[配置 BMR 備份工作](/docs/infrastructure/Backup?topic=Backup-configureBMR)。

## 還原 BMR 系統磁區映像檔
{: #restoringBMimage}
如需相關資訊，請參閱[還原 BMR 系統磁區映像檔](/docs/infrastructure/Backup?topic=Backup-restoreBMR)。

## 下載使用手冊
{: #BMRUserGuide}

使用 {{site.data.keyword.BluVPN}} 連接至 {{site.data.keyword.cloud}} 網路，以便您可以從 [Downloadable {{site.data.keyword.backup_notm}} Documentation ](http://downloads.service.softlayer.com/evault/Documentation/){: external} 存取及下載使用手冊。
