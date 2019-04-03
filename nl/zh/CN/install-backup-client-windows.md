---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 在 Windows 中安装备份客户机
{: #InstallinWindows}

要在 Windows 中安装 {{site.data.keyword.backup_full}} 客户机，可通过在为 {{site.data.keyword.backup_notm}} 服务指定的服务器上进行一系列交互操作来完成。

有关 Windows 2016 服务器备份的更多信息，请参阅[在 Windows 2016 上配置 {{site.data.keyword.backup_notm}}](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016)。
{:tip}

## 登录到目标设备服务器
{: #logintargetWin}

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}/catalog){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。<br/>
   或者，可以登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}。
2. 从主菜单中选择**设备** > **设备列表**以查看可用服务器的列表。
3. 找到为其购买 {{site.data.keyword.backup_notm}} 服务的设备，并记下其公共 IP 地址。
4. 单击向右箭头以展开并显示有关设备的更多信息，包括用户名和密码。如果未显示密码，可单击**显示密码**来显示密码。
5. 使用“远程桌面连接”登录到目标设备。

## 下载备份客户机

1. 在目标服务器上，打开浏览器会话，然后输入以下 URL 来下载 {{site.data.keyword.backup_notm}} 客户机的可执行文件。<br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}

2. 双击下载的文件。
3. 单击**运行**。


## 安装和注册备份代理程序

1. 输入网络地址：<br />
  ```
  https://ev-webcc01.service.softlayer.com
  ```
  {: pre}

2. 在**用户名**字段中输入用户名。
3. 在**密码**字段中输入密码。
6. 单击**下一步**
7. 单击**安装**以完成安装。

## 配置备份代理程序

登录到 {{site.data.keyword.backup_notm}} 门户网站以配置和管理备份代理程序。有关更多信息，请参阅[入门教程](/docs/infrastructure/Backup?topic=Backup-gettingstarted#getting-started)。
