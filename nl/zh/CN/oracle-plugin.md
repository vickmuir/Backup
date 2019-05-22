---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, oracle, plug-in, plugin, EVault, Carbonite

subcollection: Backup

---
{:pre: .pre}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 安装 Oracle 插件
{: #Oracleplugin}

Oracle 插件是一个附加组件，它随 Windows 代理程序或 Linux 代理程序一起安装在 Oracle 数据库主机上。通过 {{site.data.keyword.backup_notm}} 门户网站，可以配置作业，将 Oracle 数据库备份到安全的远程保险库，以及复原 Oracle 数据库。该 Oracle 插件集成到现有体系结构中。

**提供的功能**

- 支持 Oracle 数据库备份和恢复。
- Oracle 插件提供了对整个联机数据库实例的基于 ARCHIVELOG 的非 RMAN 备份。所有非临时表空间和实例参数文件都会自动备份。Oracle Corporation 建议在数据库活动较低的时间段执行备份。
- 可通过标准用户管理的 Oracle 恢复机制来复原完整数据库和部分数据库。

**限制**
- 仅备份本地、单实例和基于磁盘的数据库。
- 不备份数据库集群。
- 不备份原始设备。
- 不备份远程数据库。
- 数据库必须以 ARCHIVELOG 方式运行，并且配置了备份的用户必须具有 SYSDBA 特权。
- 数据库密码通过基于脚本的方法进行了加密，以增强安全性。

## 订购插件
{: #orderingOraclePlugin}

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}){: external}，然后单击左上角的**菜单**图标。选择**经典基础架构**。<br/>
      或者，可以登录到 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}。
2. 单击**存储** > **备份**以显示具有备份服务的服务器。
3. 选择帐户，然后单击**订购插件**。
4. 选择 **{{site.data.keyword.backup_notm}} 插件 - Oracle**，然后单击**继续**。
5. 如果您有促销代码，请输入促销代码，然后单击**重新计算**。
6. 这将显示更新后的费用。复查订单。
7. 选中此框以指示您已阅读并接受第三方服务协议。
8. 单击**下订单**。

## 安装适用于 Windows 的插件
{: #installOracleWin}

适用于 Windows 的 Oracle 插件随 32 位或 64 位 Windows 代理程序一起安装。要安装插件，请运行代理程序安装工具包。该插件在**定制安装**页面上显示为选项。有关更多信息，请参阅[在 Windows 中安装 {{site.data.keyword.backup_notm}} 客户机](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)

在安装插件之前，请在 `services.msc` 中停止两个 {{site.data.keyword.backup_notm}} 服务。
{:tip}

1. 浏览至 `c:\installs\evault` 文件夹，然后运行具有更高修订版号的 .exe 文件。
2. 在语言屏幕上，单击**确定**
3. 在欢迎屏幕上，单击**下一步**
4. 选择**修改安装**，然后单击**下一步**。
5. 选择**保留不变**，然后单击**下一步**。
6. 在定制安装屏幕上，选择已购买的每个插件，然后选择**此功能部件将安装在...**，然后单击**下一步**。
7. 选择**保留我当前的注册**，然后单击**下一步**。
8. 单击**安装**。
9. 安装完成后，请进行检查以确保这两个服务都已启用并且正在运行。
10. 如果 {{site.data.keyword.backup_notm}} 门户网站能够访问或查看数据库，说明安装成功。

## 安装适用于 Linux 的插件
{: #installOracleLin}

Oracle 插件是 Linux 代理程序的附加组件，随该代理程序一起安装在数据库主机上。Linux 代理应用程序必须在安装插件之前进行安装。代理程序以 32 位应用程序和 64 位应用程序形式提供。有关更多信息，请参阅[在 Linux 中安装 {{site.data.keyword.backup_notm}} 客户机](/docs/infrastructure/Backup?topic=Backup-InstallinLinux)。

Oracle 插件安装工具包以 tar.gz 文件形式提供。

1. 在主机上，下载安装软件包。
   ```
   http://downloads.softlayer.com/evault/Oracle-Plugin-Linux-x64-8.10.5249.tar.gz
   ```
   {: pre}

2. 解压缩软件包。
   ```
   # cd /tmp
   # tar xvf Oracle-Plugin-Linux-x64-8.10.5249.tar
   ```
   {: pre}

3. 转至文件夹。
   ```
   # cd Oracle-Plugin-Linux-x64-8.10.5249.xxxx
   ```
   {: pre}

4. 运行安装脚本。
   ```
   # ./install.sh
   ```
   {: pre}

5. 按照屏幕上的安装指示信息进行操作。

Oracle 插件会执行“不一致”的完整数据库备份，这要求数据库以 ARCHIVELOG 方式运行。在开始备份之前，DBA 需要确保数据库处于 ARCHIVELOG 方式。有关更多信息，请参阅《用户指南》。
{:important}


## 下载用户指南
{: #OracleUserGuide}

使用 {{site.data.keyword.BluVPN}} 连接到 {{site.data.keyword.BluSoftlayer_full}} 网络，以便可以从[可下载的 {{site.data.keyword.backup_notm}} 文档](http://downloads.service.softlayer.com/evault/Documentation/){: external} 中下载用户指南
