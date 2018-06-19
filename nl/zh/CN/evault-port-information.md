---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-30"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# EVault 端口信息

服务器上安装的 EVault 代理程序需要能够与购买的保险库进行通信。EVault 用户帐户的 EVault Director 主机信息可以在客户门户网站中找到。务必使用 FQDN 向 WebCC 和 EVault Director 注册代理程序，因为这些服务的 IP 可能会更改。 

无论数据中心位置如何，服务器都必须与 WebCC 及 WebCC 的所有 AMP 代理服务器进行通信：evregister.service.softlayer.com TCP 8086,8087。 

可以根据需要添加额外的 AMP 代理服务器，用于处理向 WebCC 注册的更多 EVault 代理程序。 

TCP 端口 8086 和 8087 应该有权访问 10.0.0.0/8。 

如果您需要使用限制更严格的防火墙规则，那么在扩展基础架构时可能会失去对 WebCC 的访问。目前，服务器应至少允许访问 TCP 端口 8086 和 8087 的 10.0.82.0/24 和 10.2.118.0/24 子网。未来可根据需要使用其他子网。

## 商用：

### WebCC 和 AMP 代理服务器：

- ev-webcc01.service.softlayer.com [10.0.82.12] 8086, 8087
- evregister.service.softlayer.com [10.0.82.12] 8086, 8087

### 商用 AMP 代理服务器：

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

## 联邦：

### WebCC 和 AMP 代理：

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087
 
代理程序必须允许专用网络上的入站端口 TCP/2548。这将允许 CentralControl 和 WebCC 连接到代理程序以进行管理。较旧版本的 EVault 使用的是 808 端口。

通过在 Windows 操作系统中更新注册表键 HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber（这是一个 dword），可以更改 EVault 管理端口 (2548)。

**其他说明**：使用桌面 CentralControl 和代理程序在连接设置方面有差异，这通常是让人混淆的地方。使用该地址和服务器的凭证进行访问时，服务器常驻代理程序将连接到我们的 EVault 服务器，而利用桌面的 CentralControl 实际是连接到您的服务器。
