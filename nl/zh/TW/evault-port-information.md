---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-26"

---
{:new_window: target="_blank"}

# 配置埠以容許在 EVault 代理程式與 WebCC 之間進行通訊

安裝在伺服器上的 EVault 代理程式必須能夠與您所購買的儲存庫通訊。您可以在 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} 中找到 EVault 使用者帳戶的「EVault 引導器」主機資訊。 

請一律使用 FQDN 將代理程式登錄至 WebCC 及 EVault 引導器，因為這些服務的 IP 位址可能會變更。 


```
evregister.service.softlayer.com TCP 8086,8087
```

您的伺服器必須與 WebCC 和所有 AMP Proxy 伺服器通訊，WebCC 才能正確運作，不論資料中心位置為何。可以視需要新增額外的 AMP Proxy 伺服器，以處理更多登錄至 WebCC 的 EVault 代理程式。 

TCP 埠 8086、8087 必須有權存取 10.0.0.0/8。 

如果您需要使用限制更嚴格的防火牆規則，則可能會在擴充基礎架構時失去 WebCC 的存取權。目前，您的伺服器至少必須容許 TCP 埠 8086、8087 存取 10.0.82.0/24 和 10.2.118.0/24 子網路。未來可能會視需要使用其他子網路。

**商業**

*WebCC 及 AMP Proxy 伺服器*

- ev-webcc01.service.softlayer.com [10.0.82.12] 8086, 8087
- evregister.service.softlayer.com [10.0.82.12] 8086, 8087

*商務 AMP Proxy 伺服器*

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

**聯邦**

*WebCC 及 AMP Proxy*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087
 
代理程式必須在專用網路上容許入埠的埠 TCP/2548。此設定可讓 CentralControl 和 WebCC 連接至代理程式，以進行管理。舊版 EVault 使用埠 808。

可以變更 EVault 管理埠 (2548)，方法為在 Windows 作業系統中更新登錄機碼：`HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber`（這是一個 `dword`）。

**說明**。如果是連線設定，則桌面 CentralControl 與代理程式之間的差異經常會造成混淆。位於伺服器的代理程式會連接至 EVault 伺服器，而利用桌面的 CentralControl 會連接至您的伺服器，方法是使用其位址及伺服器的認證來存取它。
