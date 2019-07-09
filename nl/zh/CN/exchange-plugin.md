---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-13"

keywords: IBM Cloud backup, Exchange, plug-in, plugin, EVault, Carbonite

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 了解 Exchange 插件
{: #Exchangeplugin}

Exchange 插件随 Windows 代理程序一起安装在主机上。通过 {{site.data.keyword.backup_notm}} 门户网站，可以配置作业，将 Exchange 数据库备份到安全的远程保险库，以及复原 Exchange 数据库。该插件集成到现有体系结构中。

**提供的功能**

- 能够备份和复原 Microsoft Exchange 数据库。

## 安装插件
{: #installExchangePlugin}

Exchange 插件在 Windows 代理程序 64 位安装期间进行安装。该插件可以在安装代理程序时进行安装，也可以日后通过使用**修改**选项重新运行安装来进行安装。

在为 Microsoft Windows 服务器安装该插件之前，请在 `services.msc` 中停止两个 {{site.data.keyword.backup_notm}} 服务。
{:tip}

1. 浏览至 `c:\installs\{{site.data.keyword.backup_notm}}` 文件夹，然后运行具有更高修订版号的 .exe 文件。
2. 在语言屏幕上，单击**确定**
3. 在欢迎屏幕上，单击**下一步**
4. 选择**修改安装**，然后单击**下一步**。
5. 选择**保留不变**，然后单击**下一步**。
6. 在定制安装屏幕上，选择已购买的每个插件。
7. 选择**此功能部件将安装在...**，然后单击**下一步**。
8. 选择**保留我当前的注册**，然后单击**下一步**。
9. 单击**安装**。
10. 安装后，请进行检查以确保这两个服务都已启用并且正在运行。
11. 如果 {{site.data.keyword.backup_notm}} 门户网站能够访问或查看数据库，说明安装成功。

## 下载用户指南
{: #ExchangeUserGuide}

使用 {{site.data.keyword.BluVPN}} 连接到 {{site.data.keyword.cloud}} 网络，以便可以从[可下载的 {{site.data.keyword.backup_notm}} 文档](http://downloads.service.softlayer.com/evault/Documentation/){: external}中访问并下载用户指南。此指南描述了如何使用 Exchange 插件来备份和复原 Microsoft Exchange 数据库。此指南还描述了如何共享 DR 备份安全集。通过 DR 备份安全集，可以使用 Granular Restore for Microsoft Exchange 应用程序将特定邮箱、消息或其他对象复原到 .pst 文件。
