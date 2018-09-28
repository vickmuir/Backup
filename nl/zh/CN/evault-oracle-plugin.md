---

copyright:
  years: 1994, 2018
lastupdated: "2018-08-10"

---
{:pre: .pre}
{:new_window: target="_blank"}

# 安装 EVault Oracle 插件

Oracle 插件是一个附加组件，它随 Windows 代理程序或 Linux 代理程序一起安装在 Oracle 数据库主机上。通过 WebCC 门户网站，可以配置作业，将 Oracle 数据库备份到安全的远程保险库，以及复原 Oracle 数据库。该 Oracle 插件集成到现有体系结构中。

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

1. 登录到 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}。
2. 单击**存储** > **备份**。
3. 选择 EVault 帐户，然后单击**订购插件**。
4. 选择 **EVault 插件 - Oracle**，然后单击**继续**。
5. 如果您有促销代码，请输入促销代码，然后单击**重新计算**。
6. 这将显示更新后的费用。复查订单。
7. 选中此框以指示您已阅读并接受第三方服务协议。 
8. 单击**下订单**。

## 安装适用于 Windows 的 Oracle 插件

适用于 Windows 的 Oracle 插件随 32 位或 64 位 Windows 代理程序一起安装。要安装适用于 Windows 的 Oracle 插件，请运行代理程序安装工具箱。该 Oracle 插件在**定制安装**页面上显示为选项。

>**注** - 在为 Microsoft Windows 服务器安装该插件之前，请停止 `services.msc` 中的两个 EVault 服务。  

1. 浏览至 `c:\installs\evault` 文件夹，然后运行具有更高修订版号的 .exe 文件。
2. 在语言屏幕上，单击**确定**。
3. 在欢迎屏幕上，单击**下一步**。
4. 选择**修改安装**，然后单击**下一步**。
5. 选择**保留不变**，然后单击**下一步**。
6. 在定制安装屏幕上，选择已购买的每个插件，然后选择**此功能部件将安装在...**，然后单击**下一步**。
7. 选择**保留我当前的注册**，然后单击**下一步**。
8. 单击**安装**。
9. 安装完成后，请进行检查以确保这两个服务都已启用并且正在运行。
10. 如果 WebCC 能够访问/查看数据库，说明安装成功。 

## 安装适用于 Unix 的 Oracle 插件

Oracle 插件是 Linux 代理程序的附加组件，随该代理程序一起安装在数据库主机上。Linux 代理应用程序必须在安装 Oracle 插件之前进行安装。Linux 代理程序以 32 位应用程序和 64 位应用程序形式提供。有关 Linux 代理程序安装的更多信息，请参阅[在 Linux 中安装 EVault Backup 客户机](install-evault-backup-client-linux.html)。

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
   
>**注**：Oracle 插件会执行“不一致”的完整数据库备份，这要求数据库以 ARCHIVELOG 方式运行。在开始备份之前，DBA 需要确保数据库处于 ARCHIVELOG 方式。有关更多信息，请参阅 EVault Agent v8.0 for Linux and Oracle Plug-in - User Guide。


## 下载用户指南

使用 {{site.data.keyword.BluVPN}} 连接到 {{site.data.keyword.BluSoftlayer_full}} 网络，以便从[可下载的 EVault 文档](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}下载 EVault Agent v8.0 for Microsoft Windows - Oracle plug-in Guide.pdf 和 EVault Agent v8.0 for Linux and Oracle Plug-in - User Guide.pdf。




