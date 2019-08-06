---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud backup, bare metal restore, bmr, plug-in, plugin, EVault, Carbonite, baremetal, point-in-time restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 了解 Bare Metal Restore 插件
{: #BMRplugin}

Bare Metal Restore 是一种灾难恢复解决方案。您可以使用 BMR 在发生灾难（例如，操作系统或硬件故障）后，从裸机状态复原服务器。通过 BMR，可以从由 {{site.data.keyword.cloud}} 管理的安全位置快速复原系统映像。

BMR 是物理服务器上仅适用于 Windows 的产品。不可用于虚拟服务器。不支持 Bare Metal Restores for Linux 分发版。
{:important}

## 提供的功能
{: #BMRcapabilities}

- 将系统复原到所选时间点。
- 从基于映像或文件的备份复原系统。
- 从存储在 {{site.data.keyword.backup_notm}} 上的备份复原系统。
- 启动恢复事务，可用于在没有可引导系统的情况下复原数据。

## 安装 BMR 插件
{: #installingBMR}

在安装 Windows 代理程序期间安装该插件。该插件可与代理程序同时安装，也可以日后通过使用**修改**选项重新运行安装来进行安装。

## 配置 BMR 备份作业
{: #configBMRplugin}

有关更多信息，请参阅[配置 BMR 备份作业](/docs/infrastructure/Backup?topic=Backup-configureBMR)。

## 复原 BMR 系统卷映像
{: #restoringBMimage}
有关更多信息，请参阅[复原 BMR 系统卷映像](/docs/infrastructure/Backup?topic=Backup-restoreBMR)。

## 下载用户指南
{: #BMRUserGuide}

使用 {{site.data.keyword.BluVPN}} 连接到 {{site.data.keyword.cloud}} 网络，以便可以从[可下载的 {{site.data.keyword.backup_notm}} 文档](http://downloads.service.softlayer.com/evault/Documentation/){: external}中访问并下载用户指南
