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

# 安装 Bare Metal Restore 插件
{: #BMRplugin}

BMR 是一种灾难恢复解决方案。可以使用 BMR 在发生灾难（例如，操作系统或硬件故障）后，从裸机状态复原服务器。通过 BMR，可以从由 {{site.data.keyword.cloud}} 管理的安全位置快速复原系统映像。

BMR 是物理服务器上仅适用于 Microsoft Windows 的产品。不可用于虚拟服务器。不支持 Bare Metal Restores for Linux 分发版。仅 Backup Agent 8.30 或更低版本支持 BMR。（2018 年 6 月 30 日）。
{:important}

**提供的功能**

- 将系统复原到所选时间点。
- 从基于映像或文件的备份复原系统。
- 从存储在 {{site.data.keyword.backup_notm}} 上的备份复原系统。
- 可启动的恢复事务，可用于在没有可引导系统的情况下复原数据。

## 订购插件
{: #orderingBMR}

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}){: external}，然后单击左上角的**菜单**图标。选择**经典基础架构**。<br/>
   或者，可以登录到 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}。
2. 单击**存储** > **备份**以显示具有备份服务的服务器。
3. 选择帐户，然后单击**订购插件**。
4. 选择 **{{site.data.keyword.backup_notm}} 插件 - BMR (Bare Metal Restore)**，然后单击**继续**。
5. 如果您有促销代码，请输入促销代码，然后单击**重新计算**。
6. 这将显示更新后的费用。复查订单。
7. 选中此框以指示您已阅读并接受第三方服务协议。
8. 单击**下订单**。

## 下载用户指南
{: #BMRUserGuide}

使用 {{site.data.keyword.BluVPN}} 连接到 {{site.data.keyword.cloud}} 网络，以便可以从[可下载的 {{site.data.keyword.backup_notm}} 文档](http://downloads.service.softlayer.com/evault/Documentation/){: external}中访问并下载用户指南
