---

copyright:
  years: 1994, 2019
lastupdated: "2019-03-29"

keywords: IBM Cloud backup, EVault, Carbonite, backup, getting started, setup, configure, run backup

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:shortdesc: .shortdesc}

# 入门教程
{: #getting-started}

通过备份，可确保数据安全地存储在设备外部，以防数据丢失情况发生。{{site.data.keyword.backup_full}} 是一种基于代理程序的自动备份系统，可通过基于浏览器的 {{site.data.keyword.backup_notm}} 门户网站的管理实用程序进行管理。{{site.data.keyword.backup_notm}} 为用户提供在 {{site.data.keyword.BluSoftlayer_full}} 网络上一个或多个数据中心的服务器之间备份数据的方法。管理员可以将备份设置为按每日、每周或定制的时间表进行备份，备份目标可为完整系统、特定目录或个别文件。通过额外的插件，可确保与 [Microsoft Exchange](/docs/infrastructure/Backup?topic=Backup-Exchangeplugin)、[Microsoft SQL](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin)、[Oracle](/docs/infrastructure/Backup?topic=Backup-Oracleplugin#Oracleplugin) 和 [VMware vSphere](/docs/infrastructure/Backup?topic=Backup-VRA) 等软件兼容，并允许用户在必要时完成[裸机复原](/docs/infrastructure/Backup?topic=Backup-BMRplugin#BMRplugin)。
{:shortdesc}

## 开始之前
{: #prereqs}

必须具有有效的许可证才可以使用 IBM Cloud Backup。您可以通过两种方式购买 {{site.data.keyword.backup_notm}} 服务。

- [订购服务器时购买备份](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingwithserver)。
- [作为升级购买备份](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingasupgrade)。

有关订购和定价的更多信息，请参阅[供应 {{site.data.keyword.backup_notm}}](/docs/infrastructure/Backup?topic=Backup-ordering)。

## 安装 {{site.data.keyword.backup_notm}} 代理程序

以下操作系统上支持 {{site.data.keyword.backup_notm}} 代理程序。

**Windows**
 - Windows Server 2016
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

**Linux**
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - RHEL 7.x
 - RHEL 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

遵循适用于您操作系统的指示信息：
- [在 Linux 中安装备份客户机](/docs/infrastructure/Backup?topic=Backup-InstallinLinux)
- [在 Windows 中安装备份客户机](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)
- [在 Windows 2016 中安装备份客户机](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016)

## 访问 {{site.data.keyword.backup_notm}} 门户网站（以前称为 WebCC）
{: #accessingWebCC}

{{site.data.keyword.backup_notm}} 门户网站用于与由 {{site.data.keyword.BluSoftlayer_full}} 提供的任何 {{site.data.keyword.backup_notm}} 服务进行交互。{{site.data.keyword.backup_notm}} 门户网站是一种基于浏览器的客户机，在 {{site.data.keyword.BluSoftlayer_full}} 专用网络上运行，支持对任何 {{site.data.keyword.backup_notm}} 服务进行完全控制，包括配置和复原。

1. 通过 VPN 访问专用网络。

   {{site.data.keyword.backup_notm}} 门户网站无法通过公用网络进行访问。必须先建立 VPN 连接。
   {:important}
2. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}/){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。<br/>
或者，可以登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}。
2. 单击**存储** > **备份**以显示具有备份服务的服务器。
3. 选择要备份的文件所在的服务器。单击指向右方的展开箭头以显示 {{site.data.keyword.backup_notm}} 门户网站链接。
4. 单击 **{{site.data.keyword.backup_notm}} 门户网站登录**，以在浏览器中启动门户网站客户机。

## 配置备份代理程序和备份调度

订购了 {{site.data.keyword.backup_notm}} 并且在服务器上安装了代理程序之后，即可以开始创建数据备份。执行以下步骤来配置代理程序和保留安排。

1. 登录到 {{site.data.keyword.backup_notm}} 门户网站。
2. 单击**所有代理程序** > **未配置的代理程序**。
3. 单击**这是我要配置的新代理程序**链接。逐步完成该过程并输入以下信息：
   1. 代理程序配置 - 提供代理程序描述，然后单击**下一步**。
   2. 作业类型选择 - 输入作业名、作业描述和备份源类型，然后单击**下一步**。
   3. 选择 - 选择目录，然后单击**包含...**
   4. 选项 - 提供密码
   5. 安排 - 单击**添加**以创建安排，然后单击**下一步**。
   6. 选择缺省保险库，然后单击**确定**。
   7. 单击**保存**。
4. 创建保留安排。
   1. 选择**编辑** > **代理程序设置**。
   2. 单击**添加**。
   3. 填写保留详细信息。
   4. 单击**确定**。
   5. 单击**保存**。

              有关“保留方案”的更多信息，请参阅[常见问题](faqs.html)。
        {:tip}

## 运行第一个备份作业

1. 登录到 {{site.data.keyword.backup_notm}} 门户网站。
2. 单击**所有代理程序**，然后选择已配置的代理程序。
3. 单击**运行备份**。
4. 确认“目标”并选择保留方案。
5. 单击**启动备份**。您可以在进程运行时查看备份详细信息。
6. 完成备份后，单击**关闭**。

有关更多信息，请参阅[在 Linux 上配置简单的文件级别备份](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup)。
{:tip}

## 在控制台中访问并查看 {{site.data.keyword.backup_notm}} 存储器详细信息

可随时在 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}/){:new_window}和 {{site.data.keyword.slportal}} 中查看服务的存储器详细信息。可查看的详细信息包括与所选 {{site.data.keyword.backup_notm}} 服务关联的密码、存储地址和使用情况。

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。</br>
或者，可以登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}。
2. 单击**存储**，然后从列表中选择**备份**。
2. 单击保险库所在行上的任意位置以查看其存储器详细信息。在此视图中，无法查看“密码”。
3. 单击**密码**字段旁边的**显示**复选框，以查看所选 {{site.data.keyword.backup_notm}} 服务的密码。

对 {{site.data.keyword.slportal}} 内的 {{site.data.keyword.backup_notm}} 密码进行的更改将应用于该服务本身。要重置密码，请执行[更改备份服务的密码](/docs/infrastructure/Backup?topic=Backup-changePassword)中的步骤。
{:important}

## 获取更多联机帮助

{{site.data.keyword.backup_notm}} 门户网站的系统已全部记录，并且可在 {{site.data.keyword.backup_notm}} 门户网站内访问对该应用程序的支持。单击右上角含有白色问号的蓝色圆圈以获取**帮助**。单击左侧导航栏中的任何文章或主题以查看更多信息。
