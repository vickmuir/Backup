---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-28"

keywords: EVault, Carbonite, IBM Cloud Backup, Enterprise Backup

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 供应 {{site.data.keyword.backup_notm}}
{: #ordering}

您可以通过两种方式购买 {{site.data.keyword.backup_notm}} 服务。

- [订购服务器时购买备份](#purchasingwithserver)。
- [作为升级购买备份](#purchasingasupgrade)。

有关定价的更多信息，请参阅 [{{site.data.keyword.backup_notm}} storage ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/backup-and-restore){:new_window} 和 [{{site.data.keyword.backup_notm}} on IBM Cloud ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/backup/pricing){:new_window}。

## 订购服务器时购买 {{site.data.keyword.backup_notm}}
{: #purchasingwithserver}

1. 登录到 [IBM Cloud 目录 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/catalog){:new_window} 或 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}
2. 订购按月计费的裸机服务器。有关订购裸机服务器的更多信息，请参阅[构建定制裸机服务器](https://{DomainName}/docs/bare-metal/baremetal-provision.html){:new_window}。
   1. 选择数量和计费选项。输入主机和域名。您可以选择所需的任何主机名和域。

      订购按小时计费的服务器时，{{site.data.keyword.backup_notm}} 服务不可用。但是，日后可以作为升级添加该服务。
   {:tip}
   2. 选择位置。
   3. 选择服务器配置和操作系统映像类型。您还可以选择多个附加组件。
   4. 在**存储磁盘**部分下，单击**附加组件**，然后选择 **{{site.data.keyword.backup_notm}}**。请选择与您的需要匹配的选项。
   5. 在**网络接口**下，选择上行端口速度以及需要的任何附加组件。
3. 在右侧，复查订单摘要。
4. 复查条款和条件之后，选中**我已阅读并同意第三方服务协议**框。
5. 单击**供应**。这会将您重定向到具有供应订单号的屏幕。您可以打印此屏幕，因为这也是您的供应订单收据。

   您还可以通过单击**另存为报价**来保存此订单而不购买。
   {:tip}

系统将向管理员发送一系列电子邮件：确认供应订单、供应订单核准和处理以及供应完成。供应完成电子邮件包含登录到 {{site.data.keyword.cloud_notm}} 后可以访问的*设备详细信息*页面的链接。您还可以直接登录到 {{site.data.keyword.slportal}}。

### 确认 {{site.data.keyword.backup_notm}} 购买
1. 在 [{{site.data.keyword.cloud_notm}} 控制台 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/){:new_window} 中，单击左上角的**菜单**图标。选择**经典基础架构**。</br>
   或者，可以登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}。
2. 单击**设备** > **设备列表**。
2. 找到您订购的新服务器。
  - 如果 URL 旁边有“时钟”图标，那么您需要稍候才能继续确认 {{site.data.keyword.backup_notm}} 购买信息。您可以刷新此页面，以查看新服务器的更新状态。“时钟”图标不再显示时，您可以继续执行后续步骤以确认 {{site.data.keyword.backup_notm}} 服务购买。
  - 服务器的“时钟”图标不再显示时，请单击相应链接（服务器的 URL）以转至**设备详细信息**页面。
3. 单击**存储**选项卡以显示 {{site.data.keyword.backup_notm}} 信息。
4. 检查 {{site.data.keyword.backup_notm}} 部分，并验证购买过程中选择的大小是否显示。

## 作为升级购买 {{site.data.keyword.backup_notm}}
{: #purchasingasupgrade}

### 选择要安装 {{site.data.keyword.backup_notm}} 的服务器

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。</br>
   或者，可以登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}。
2. 从主菜单中选择**设备** > **设备列表**。找到要添加备份服务的设备。
3. 单击设备名以转至**设备详细信息**页面。

### 添加（购买）{{site.data.keyword.backup_notm}} 服务
1. 单击**存储**选项卡，然后向下滚动以找到 {{site.data.keyword.backup_notm}} 部分。
2. 单击**添加**链接。
3. 在窗口中，选择一个位置，然后选择大小。
4. 选择“支付类型”，然后单击**继续**
5. 如果您有促销代码，请输入**促销代码**，然后单击**重新计算**。
6. 复查订单，然后单击链接以阅读条款和条件。
7. 如果您同意条款和条件，请单击相应复选框。
7. 单击**下订单**。

### 确认 {{site.data.keyword.backup_notm}} 升级购买
1. 刷新**设备详细信息**页面，并确保已选择**存储**选项卡。
2. 检查 {{site.data.keyword.backup_notm}} 部分，并验证购买过程中选择的大小是否显示。

   如果备份存储器大小的容量仍然显示为零，说明可能需要再次刷新页面。
   {:tip}
