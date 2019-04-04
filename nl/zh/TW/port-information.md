---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, port information, configure, configuring,

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 配置「埠」，讓備份代理程式與 {{site.data.keyword.backup_notm}} 入口網站之間能夠進行通訊
{: #portinfo}

安裝在伺服器上的 {{site.data.keyword.backup_full}} 代理程式必須能夠與您所購買的儲存庫通訊。您可以在 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window} 及 [{{site.data.keyword.cloud_notm}} 主控台 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://{DomainName}){:new_window} 找到 {{site.data.keyword.backup_notm}} 使用者帳戶的 Director 主機資訊。

請一律使用 FQDN 將代理程式登錄至 {{site.data.keyword.backup_notm}} 入口網站和 Director，因為這些服務的 IP 位址可能會變更。

不論資料中心位置為何，您的伺服器必須與 {{site.data.keyword.backup_notm}} 入口網站和所有 AMP Proxy 伺服器通訊，{{site.data.keyword.backup_notm}} 入口網站才能正確運作。

```
https://evregister.service.softlayer.com TCP 8086,8087
```

您可以視需要新增額外的 AMP Proxy 伺服器，以處理更多登錄至 {{site.data.keyword.backup_notm}} 入口網站的 {{site.data.keyword.backup_notm}} 代理程式。

TCP 埠 8086、8087 必須有權存取 10.0.0.0/8。
{:important}

如果您需要使用限制更嚴格的防火牆規則，可能會隨著基礎架構擴充，而失去 {{site.data.keyword.backup_notm}} 入口網站的存取權。目前，您的伺服器至少必須容許 TCP 埠 8086、8087 存取 10.0.82.0/24 和 10.2.118.0/24 子網路。未來可能會視需要使用其他子網路。

## 商業

*{{site.data.keyword.backup_notm}} 入口網站和 AMP Proxy 伺服器*

- `https://ev-webcc01.service.softlayer.com` [10.0.82.12] 8086, 8087
- `https://evregister.service.softlayer.com` [10.0.82.12] 8086, 8087

*商務 AMP Proxy 伺服器*

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

## 聯邦政府

*{{site.data.keyword.backup_notm}} 入口網站和 AMP Proxy*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087

代理程式必須在專用網路上容許 TCP 埠 2548 入埠。此設定可讓 Central Control 和 {{site.data.keyword.backup_notm}} 入口網站連接至代理程式，以進行管理。舊版 EVault 使用埠 808。

可以變更 {{site.data.keyword.backup_notm}} 管理埠 (2548)，方法為在 Windows 作業系統中更新登錄機碼：`HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber`（這是一個 `dword`）。

如果是連線設定，則桌面 Central Control 與代理程式之間的差異經常會造成混淆。位於伺服器的代理程式會連接至 {{site.data.keyword.backup_notm}} 伺服器，而利用桌面的 Central Control 會連接至您的伺服器，方法是使用其位址及伺服器的認證來存取它。
{:tip}
