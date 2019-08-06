---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud backup,  EVault, Carbonite, backup, restore

subcollection: Backup

---
{:pre: .pre}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 在不同数据中心内的 VSI 之间复原数据
{: #restoreVSIotherlocation}

有时，您会希望将数据复原到其他服务器。此过程仅适用于非操作系统文件的文件级别复原。要复原系统映像，请遵循 [Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR) 指示信息。

此过程包括在第二个服务器上重新注册备份代理程序以访问第一个服务器的保险库位置，以及完成**从其他计算机复原**。

**先决条件**

- Server1 和 Server2 必须有相同的操作系统。不支持跨平台复原。
- Server1 和 Server2 必须有先前已配置的备份代理程序。有关配置备份代理程序的更多信息，请参阅[在 {{site.data.keyword.backup_notm}} 门户网站中配置备份代理程序](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)。
- Server1 的备份作业已在 Server1 的保险库位置生成了备份。

禁用这两台服务器上的所有已调度的任务以避免发生任何冲突。
{:important}

## 启动 Server2 的 {{site.data.keyword.backup_notm}} 门户网站
{: #startWebCCotherDC}

请务必启动 {{site.data.keyword.BluVPN}} 连接来访问 {{site.data.keyword.cloud}} 专用网络，否则 {{site.data.keyword.backup_notm}} 门户网站链接是不好用的。
{:tip}

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}){: external}。在导航菜单中选择**经典基础架构**。
2. 单击**存储** > **Cloud 备份** 以显示具有备份服务的服务器。
3. 选择 Server2。单击展开箭头以显示 {{site.data.keyword.backup_notm}} 门户网站链接。
4. 单击 **{{site.data.keyword.backup_notm}} 门户网站登录**，以在浏览器中启动门户网站客户机。

## 重新注册保险库
{: #reregistervaultotherDC}

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
{: #runbackuprestoreotherDC}

1. 单击**所有代理程序**。

   您可能需要刷新页面才能在 Server2 的**作业**选项卡下看到 Server1 上定义为可访问和已同步的作业。
   {:tip}
2. 将鼠标悬停在**高级**上，然后选择**从其他计算机复原**。
3. 在**从其他计算机复原**屏幕上，单击**添加**。这些字段会使用缺省值自动填充，因此请更改这些字段。
4. 单击“保险库”字段，选择**输入保险库设置**，然后输入 Server1 的保险库的 IP 地址。单击**添加**。
5. 将凭证更新为 Server1 的凭证。
6. 单击**保存更改**。此操作将连接到 Server1 的保险库。
7. 返回到**从其他计算机复原**屏幕，更新“计算机”和“作业”字段。
  - 计算机 - 选择 Server1 作为要从中进行复原的备份计算机。
  - 作业 - 选择 Server1 中的备份作业。
8. 单击**下一步**以启动复原到其他数据中心内 server2 的过程。
9. 在出现提示时，输入备份密码，然后单击**下一步**。
10. 确认选择的是正确的备份作业，然后单击**下一步**。现在，已在 server2 上配置复原作业。
11. 选择新配置的作业，然后单击**运行复原**。
12. 选择要复原的文件。
13. 单击加号以展开文件选择。
14. 单击要从 server1 复原到 server2 的各个文件或文件夹的复选框。然后，单击**包含**。
15. 这些文件将填充“备份集”窗口。单击**下一步**。
16. 完成数据选择后，继续选择选项。
    - 选择**复原到原始位置**。
    - 选择**覆盖现有文件**。
17. 单击**运行复原**。“过程详细信息”窗口将提供正在运行的备份作业的状态。完成备份后，单击**关闭**。


## 验证复原
{: #verifyrestoreotherDC}

1. 通过 SSH 连接到 Server2 的根目录。
2. 以长格式列出文件和所有目录条目。
  ```
  ls -la
  ```
  {: pre}

3. 对比输出。

## 恢复正常的备份安排。
{: #resumescheduleotherCD}

1. 复原完成后，除去从中复原数据的 Server1 的注册信息。
2. 输入当前 Server2 注册信息并启用调度任务。
