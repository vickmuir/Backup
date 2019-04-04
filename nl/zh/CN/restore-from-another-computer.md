---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup,  EVault, Carbonite, backup, restore

subcollection: Backup

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 在同一数据中心内的不同 VSI 之间复原数据
{: #restorefromotherVSI}

有时，您会希望将数据复原到同一数据中心内的其他服务器上。此过程仅适用于非操作系统文件的文件级别复原。要复原系统映像，请遵循 [Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR) 指示信息。

此过程包括在第二个服务器上重新注册备份代理程序以访问第一个服务器的保险库位置，以及完成**从其他计算机复原**。

**先决条件**

- Server1 和 Server2 必须有相同的操作系统。不支持跨平台复原。
- Server1 和 Server2 必须有先前已配置的备份代理程序。有关配置备份代理程序的更多信息，请参阅[在 {{site.data.keyword.backup_notm}} 门户网站中配置备份代理程序](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)。
- Server1 的备份作业已在 Server1 的保险库位置生成了备份。

禁用这两台服务器上的所有已调度的任务以避免发生任何冲突。
{:important}

## 启动 Server2 的 {{site.data.keyword.backup_notm}} 门户网站
{: #startWebCC}

请务必启动 {{site.data.keyword.BluVPN}} 连接来访问 {{site.data.keyword.BluSoftlayer_full}} 专用网络，否则 {{site.data.keyword.backup_notm}} 门户网站链接是不好用的。
{:tip}

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。<br/>
   或者，可以登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}。
2. 单击**存储** > **备份**以显示具有备份服务的服务器。
3. 选择 Server2。单击指向右方的展开箭头以显示 {{site.data.keyword.backup_notm}} 门户网站链接。
4. 单击 **{{site.data.keyword.backup_notm}} 门户网站登录**，以在浏览器中启动门户网站客户机。

## 重新注册保险库
{: #reregistervault}

1. 单击**所有代理程序**，然后打开要修改的特定代理程序。
2. 单击**编辑**，然后选择**保险库设置**。
3. 单击**重新注册**以将 Server1 连接到 Server2。
4. 在**重新注册保险库**屏幕上，对于**使用保险库概要文件**条目，选择**输入保险库设置**。
5. 输入保险库名称，该名称与 Server1 的保险库名称相同。
6. 输入 Server1 的凭证以登录到 Server1 的保险库。
7. 单击**装入计算机**，此操作将显示与保险库位置连接的服务器。
8. 单击**保存更改**。
9. 在出现提示时，单击**是**以确认重新注册保险库。

## 从 Server1 运行在 Server2 上作为复原作业的备份作业
{: #runbackuprestore}

1. 单击**所有代理程序**。

   您可能需要刷新页面才能在 Server2 的**作业**选项卡下看到 Server1 上定义为可访问和已同步的作业。
   {:tip}
2. 将鼠标悬停在**高级**上，然后选择**从其他计算机复原**。
3. 在**从其他计算机复原**屏幕上，进行以下选择。
  - 保险库 - 此条目的缺省值为 Server1 的保险库。
  - 计算机 - 选择 Server1 作为要从中进行复原的备份计算机。
  - 作业 - 选择 Server1 中的备份作业。
4. 单击**下一步**
5. 确认源信息
  - **安全集位置**是 Server1 的保险库位置。
  - 在**选择备份版本**部分中，将来自 Server1 的备份指定为备份版本。
  - 加密密码是您在创建 Server1 备份时使用的密码。
6. 单击**下一步**
7. 选择需要从 Server1 备份复原的文件。选中要复原的文件和目录旁边的复选框，然后单击**包含**以保存您的选择。
8. 单击**下一步**以移至复原选项。
9. 在“选项”中
  - 目标 - 选择**复原到原始位置**
  - 文件覆盖 - 选择**覆盖现有文件**
10. 单击**运行复原**。
11. “过程详细信息”屏幕上会显示复原作业的状态。


## 验证复原
{: #verifyrestore}

1. 通过 SSH 连接到 Server2 的根目录。
2. 以长格式列出文件和所有目录条目。
  ```
  ls -la
  ```
  {: pre}

3. 对比输出。

## 恢复正常的备份安排。
{: #resumeschedule}

1. 复原完成后，除去从中复原数据的 Server1 的注册信息。
2. 输入当前 Server2 注册信息并启用调度任务。
