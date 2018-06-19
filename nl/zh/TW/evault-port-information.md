---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-30"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# EVault 埠資訊

安裝在伺服器上的 EVault 代理程式必須能夠與您所購買的儲存庫通訊。在客戶入口網站中可以找到 EVault 使用者帳戶的「EVault 引導器」主機資訊。一律使用 FQDN，將代理程式登錄至 WebCC 及「EVault 引導器」，因為這些服務的 IP 可能會變更。 

您的伺服器必須與 WebCC 和所有 AMP Proxy 伺服器通訊， WebCC 才能正確運作，而不考慮資料中心位置：evregister.service.softlayer.com TCP 8086,8087。 

可以視需要新增額外 AMP Proxy 伺服器，以處理其他已登錄至 WebCC 的 EVault 代理程式。 

「TCP 埠」8086、8087 應該有權存取 10.0.0.0/8。 

如果您需要使用更嚴格的防火牆規則，則在擴充基礎架構時，您可能會失去 WebCC 的存取權。目前，您的伺服器至少應該容許存取 TCP 埠 8086、8087 的 10.0.82.0/24 和 10.2.118.0/24 子網路。未來可能會視需要使用其他子網路。

## 商務：

### WebCC 和 AMP Proxy 伺服器：

- ev-webcc01.service.softlayer.com [10.0.82.12] 8086, 8087
- evregister.service.softlayer.com [10.0.82.12] 8086, 8087

### 商務 AMP Proxy 伺服器：

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

## 聯邦：

### WebCC 和 AMP Proxy：

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087
 
代理程式必須容許在專用網路上執行埠 TCP/2548 入埠。如此可讓 CentralControl 和 WebCC 連接至代理程式來管理它。舊版 EVault 使用埠 808。

可以變更 EVault 管理埠 (2548)，方法為在 Windows 作業系統中，更新 HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber 中的登錄機碼（即 dword）。

**其他說明**：使用桌面 CentralControl 和與連線設定相關的「代理程式」之間的差異通常是一個混淆點。伺服器常駐代理程式將連接至我們的 EVault 伺服器，而桌面所使用的 CentralControl 實際上會使用該位址以及伺服器的認證來存取您的伺服器，以實際連接至您的伺服器。
