---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 安装 vSphere Recovery Agent
{: #VRA}

vSphere Recovery Agent (VRA) 是 Windows 应用程序，可以备份和复原最高 10 TB 的 VMDK。可以将 vSphere Recovery Agent 安装在对您希望保护的 vCenter 具备本地网络访问权的物理机器或虚拟机上。要获得最佳性能，请将 VRA 安装在与 vCenter 位于相同子网的机器上。要分发工作负载，最多可以有 5 个 VRA 来保护连接到单个 vCenter 的 VM。

在 vSAN 延伸集群中，每个 VM 都有首选站点。理想情况下，会在备份该站点的首选 VM 的每个站点中安装一个本地 VRA。如果 VM 移至其他站点（由于维护或故障），备份性能可能会降低，但仍处于可接受的水平。


## 订购插件
{: #orderingVRAPlugin}

{{site.data.keyword.cloud_notm}} 免费提供 vSphere Recovery Agent (VRA)。如果您有当前 {{site.data.keyword.backup_notm}} 预订，可以从 {{site.data.keyword.backup_notm}} 门户网站下载该插件。

## 安装插件
{: #installVRAPlugin}

确保在您安装 VRA 的服务器上禁用电源管理。
{: important}

1. 从 `http://downloads.service.softlayer.com/evault/` 下载安装工具包。然后，双击安装工具包。
2. 在确认消息上，单击**是**。
3. 在欢迎页面上，单击**下一步**。
4. 在“最终用户许可协议”页面上，阅读许可协议。如果您同意其中的条款，请单击**我接受许可协议中的条款**，然后单击**下一步**。
5. 在“目标文件夹”页面上，执行以下某个操作。
   * 要将 VRA 安装在缺省位置，请单击**下一步**。
   * 要将 VRA 安装在其他位置，请单击**切换**。在“切换目标文件夹”对话框中，浏览至新的安装文件夹，或在“文件夹名称”框中进行输入。单击**确定**。在“目标文件夹”页面上，单击**下一步**。
6. 在“向门户网站注册代理程序”页面上，指定以下信息。
   * 在**网络地址**字段中，输入 `ev-webcc01.service.softlayer.com`。
   * 在**端口**字段中，输入 `8086`。
   * 在**用户名**字段中，输入用于管理 VRA 的 {{site.data.keyword.backup_notm}} 用户名。
   * 在**密码**字段中，输入指定 {{site.data.keyword.backup_notm}} 用户的密码。
7.	单击**下一步**。安装完成后，单击**完成**。

## 配置 vSphere Recovery Agent
{: #configureVRA}

安装 VRA 之后，您需要在 {{site.data.keyword.backup_notm}} 门户网站中对其进行配置。

1. 登录到 {{site.data.keyword.backup_notm}} 门户网站。有关如何访问 {{site.data.keyword.backup_notm}} 门户网站的更多信息，请参阅[入门教程](/docs/infrastructure/Backup?topic=Backup-getting-started#accessingWebCC)。
2. 在“计算机”选项卡上，选择要备份的服务器。
3. 配置保险库信息。

   保险库信息可以通过以下两种方式进行配置：**自动**或**手动**。<br/>如果这是首次配置代理程序，那么可以使用[自动配置](#VRAautoconfig)选项进行配置。<br/>如果先前已使用保险库注册了计算机，那么自动配置将不起作用，该保险库需要进行[手动配置](#VRAmanualconfig)。
   {: tip}

4. 配置 [vCenter 设置](#vCenterSettingsconfig)   

### 自动配置保险库
{: #VRAautoconfig}

要自动配置保险库设置，请单击**自动配置**。将运行配置向导，并为您配置保险库设置。向导完成后，请单击**转至代理程序**以验证**保险库设置**选项卡中的信息。
 

### 手动配置保险库
{: #VRAmanualconfig}

要手动配置保险库设置，请单击**手动配置**。   
1. 单击**保险库设置**。
2. 单击**添加保险库**。这将显示“保险库设置”窗口。从**保险库概要文件**选项，选择合适的保险库。
   如果先前使用 {{site.data.keyword.backup_notm}} 保险库注册了计算机，那么在从“保险库概要文件”选择该保险库时将自动填充所有信息。
   {:note}

3. 验证“保险库设置”页面中的所有信息，然后单击**保存**。
4. 保存保险库设置后，保险库信息将显示在**保险库设置**选项卡中。


### 配置 vCenter 代理程序设置
{: #vCenterSettingsconfig}
保险库注册成功之后，需要配置 vCenter 设置，然后才能创建和运行任何备份作业。

1. 单击 **vCenter 设置**选项卡
2. 提供您要保护的 vCenter 的 vCenter IP 地址、域名和凭证。
   用户必须具备对 vCenter 的管理访问权才能成功执行此任务。
   {:note}

3. 通过除去复选标记来禁用更改块跟踪 (CBT)。CBT 是一个 VMware 功能部件，用于跟踪更改的磁盘扇区并提高 VM 备份的性能，由 vSphere 代理程序自动启用。
4. 单击**测试 vCenter 连接**。将在新的窗口中显示结果。如果提供了正确的登录信息，将显示消息“已成功验证 vCenter 凭证”。
5. 单击**保存**以保存设置。

## 后续步骤
{: #VRAnextteps}
1. [配置、安排和运行备份作业](/docs/infrastructure/Backup?topic=Backup-ConfigureVRA)
2. [复原 vSphere 数据](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore)

使用 {{site.data.keyword.BluVPN}} 连接到 {{site.data.keyword.BluSoftlayer_full}} 网络，以便可以从[可下载的 {{site.data.keyword.backup_notm}} 文档](http://downloads.service.softlayer.com/evault/Documentation/){: external} 中访问并下载用户指南。
{:tip}
