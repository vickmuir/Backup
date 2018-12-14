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

# 安装 Bare Metal Restore 插件

BMR 是一种用于 Microsoft Windows 的灾难恢复解决方案。可以使用 BMR 在发生灾难（例如，操作系统或硬件故障）后，从裸机状态复原服务器。通过 BMR，可以从由 {{site.data.keyword.BluSoftlayer_full}} 管理的安全位置快速复原系统映像。

BMR 是物理服务器上仅适用于 Microsoft Windows 的产品。不可用于虚拟服务器。不支持 Bare Metal Restores for Linux 分发版。仅 Backup Agent 8.30 或更低版本支持 BMR。（2018 年 6 月 30 日）。
{:important}

**提供的功能**

- 将系统复原到所选时间点。
- 从基于映像或文件的备份复原系统。
- 从存储在 IBM Cloud Backup 上的备份复原系统。
- 可启动的恢复事务，可用于在没有可引导系统的情况下复原数据。.
## 订购插件

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}/catalog/){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。

   或者，可以登录到 [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}。
2. 单击**存储** > **备份**以显示具有备份服务的服务器。
3. 选择帐户，然后单击**订购插件**。
4. 选择 **{{site.data.keyword.backup_notm}} 插件 - BMR (Bare Metal Restore)**，然后单击**继续**。
5. 如果您有促销代码，请输入促销代码，然后单击**重新计算**。
6. 这将显示更新后的费用。复查订单。
7. 选中此框以指示您已阅读并接受第三方服务协议。
8. 单击**下订单**。

## 下载用户指南

使用 {{site.data.keyword.BluVPN}} 连接到 {{site.data.keyword.BluSoftlayer_full}} 网络，以便可以从[可下载的 {{site.data.keyword.backup_notm}} 文档 ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}访问并下载用户指南。

## 常见问题

**可以从单个磁盘迁移到 RAID 阵列吗？**

可以，支持此迁移。但是，由于 RAID 阵列会导致容量大小减少，因此需要选择大容量设备。

**将映像复原到比原始卷更大的磁盘会发生什么情况？**

如果将映像复原到比原始卷更大的磁盘，那么会释放剩余的空间。例如，如果您拥有 500-GB 驱动器，并将其数据复原到 1-TB 磁盘，那么将释放 500 GB 的磁盘空间。对于 Windows 2008，可以使用内置磁盘实用程序来增大主分区。但是，在 Windows 2003 中没有类似的内置功能，因此您必须以另一种方式分配空间。

**可以将 BMR 用于定期备份吗？**

BMR 备份不是磁盘映像备份系统，而是系统卷映像备份系统。此系统的目的不是用于定期备份，但是可以与定期备份一起使用。  

**可以将 BMR 用于数据库备份吗？**

数据库备份必须与标准 IBM Cloud Backup 方法分开执行。BMR 并不能取代对 SQL 或 Oracle 插件的需求。尽管 BMR 使用 VSS 技术来备份开放文件，但不一定能保证备份的文件保持事务一致性。针对这些类型的专用应用程序的建议是创建两个备份作业：一个用于备份操作系统和应用程序二进制文件，另一个用于备份应用程序数据。BMR 用户指南末尾对此影响作了说明。

**可以使用 BMR 运行哪类复原作业？**

可以执行整个系统复原，也可以从备份中选择个别文件进行复原。BMR 备份作业可以替换当前文件备份作业。复原过程可以在操作系统内部完成，就像传统的备份作业一样。

**BMR 具有开放文件备份功能吗？**

BMR 具有开放文件备份功能。但是，BMR 并不能取代对 SQL 或 Oracle 插件的需求。有关 MSSQL 插件的更多信息，请参阅[此处](mssql-plugin.html)。

**BMR 复原需要多大磁盘空间和多长时间？**

通过缺省安装进行备份大约使用 6 GB。此类复原在 1-GB 端口上大约需要 15 分钟。此过程还受专用端口速度的影响。如果需要更快的备份和复原，可能需要提高端口速度。
