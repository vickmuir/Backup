---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 配置端口以允许备份代理程序与 {{site.data.keyword.backup_notm}} 门户网站之间进行通信

服务器上安装的 {{site.data.keyword.backup_full}} 代理程序需要能够与购买的保险库进行通信。{{site.data.keyword.backup_notm}} 用户帐户的 {{site.data.keyword.backup_notm}} 导向器主机信息可以在 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window} 和 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}/catalog/){:new_window}中找到。

请始终使用 FQDN 向 {{site.data.keyword.backup_notm}} 门户网站和 {{site.data.keyword.backup_notm}} 导向器注册代理程序，因为这些服务的 IP 地址可能会更改。

不管数据中心位置，服务器都必须与 {{site.data.keyword.backup_notm}} 门户网站以及 {{site.data.keyword.backup_notm}} 门户网站的所有 AMP 代理服务器进行通信，才能正确运行。

```
evregister.service.softlayer.com TCP 8086,8087
```

可以根据需要添加额外的 AMP 代理服务器，用于处理向 {{site.data.keyword.backup_notm}} 门户网站注册的更多 {{site.data.keyword.backup_notm}} 代理程序。

TCP 端口 8086 和 8087 必须有权访问 10.0.0.0/8。

如果您需要使用限制更严格的防火墙规则，那么在扩展基础架构时可能会失去对 {{site.data.keyword.backup_notm}} 门户网站的访问权。目前，服务器必须至少允许访问 TCP 端口 8086 和 8087 的 10.0.82.0/24 和 10.2.118.0/24 子网。未来可根据需要使用其他子网。

## 商用

*{{site.data.keyword.backup_notm}} 门户网站和 AMP 代理服务器*

- ev-webcc01.service.softlayer.com [10.0.82.12] 8086, 8087
- evregister.service.softlayer.com [10.0.82.12] 8086, 8087

*商用 AMP 代理服务器*

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

## 联邦

*{{site.data.keyword.backup_notm}} 门户网站和 AMP 代理*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087

代理程序必须允许 TCP 端口 2548 在专用网络上入站。此设置允许 CentralControl 和 {{site.data.keyword.backup_notm}} 门户网站连接到代理程序以进行管理。较旧版本的 EVault 使用的是 808 端口。

通过在 Windows 操作系统中更新注册表键 `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber`（这是一个 `dword`），可以更改 {{site.data.keyword.backup_notm}} 管理端口 (2548)。

使用桌面 CentralControl 和使用代理程序在连接设置方面有差异，这通常是让人混淆的地方。在利用桌面的 CentralControl 连接到您的服务器时，服务器常驻代理程序连接到 {{site.data.keyword.backup_notm}} 服务器，方法是使用其地址和服务器的凭证进行访问。
{:tip}
