---

copyright:
  years: 2014, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# {{site.data.keyword.backup_notm}} 服务入门

通过备份，可确保数据安全地存储在设备外部，以防数据丢失情况发生。{{site.data.keyword.backup_full}} 是一种基于代理程序的自动备份系统，可通过基于浏览器的 {{site.data.keyword.backup_notm}} 门户网站的管理实用程序进行管理。{{site.data.keyword.backup_notm}} 为用户提供在 {{site.data.keyword.BluSoftlayer_full}} 网络上一个或多个数据中心的服务器之间备份数据的方法。管理员可以将备份设置为按每日、每周或定制的时间表进行备份，备份目标可为完整系统、特定目录或个别文件。通过额外的插件，可确保与 Microsoft Exchange 和 Microsoft SQL 等软件以及其他类型的第三方软件兼容，并允许用户在必要时完成裸机复原。

## 订购 {{site.data.keyword.backup_notm}}

您可以通过两种方式购买 {{site.data.keyword.backup_notm}} 服务。

- [订购服务器时购买 {{site.data.keyword.backup_notm}}](#purchasing-ibm-cloud-backup-when-you-order-a-server)。
- [作为升级购买 {{site.data.keyword.backup_notm}}](#purchasing-ibm-cloud-backup-as-an-upgrade)。

有关定价的更多信息，请参阅 [{{site.data.keyword.backup_notm}} storage ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/backup-and-restore){:new_window} 和 [{{site.data.keyword.backup_notm}} on IBM Cloud ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://www.ibm.com/cloud/evault/pricing){:new_window}。

### 订购服务器时购买 {{site.data.keyword.backup_notm}}

1. 登录到 [IBM Cloud 目录 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/catalog/){:new_window} 或 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}
2. 订购按月计费的裸机服务器。有关订购裸机服务器的更多信息，请参阅[构建定制裸机服务器](bare-metal/baremetal-provision.html){:new_window}。
   1. 选择数量和计费选项。输入主机和域名。您可以选择所需的任何主机名和域。

      订购按小时计费的服务器时，{{site.data.keyword.backup_notm}} 服务不可用。但是，日后可以作为升级添加该服务。
   {:tip}
   2. 选择位置。
   3. 选择服务器配置和操作系统映像类型。您还可以选择多个附加组件。
   4. 在**存储磁盘**部分下，单击**附加组件**，然后选择 **{{site.data.keyword.backup_notm}} 备份**。请选择与您的需要匹配的选项。
   5. 在**网络接口**下，选择上行端口速度以及需要的任何附加组件。
3. 在右侧，复查订单摘要。
4. 复查条款和条件之后，选中**我已阅读并同意第三方服务协议**框。
5. 单击**供应**。这会将您重定向到具有供应订单号的屏幕。您可以打印此屏幕，因为这也是您的供应订单收据。

   您还可以通过单击**另存为报价**来保存此订单而不购买。
   {:tip}

系统将向管理员发送一系列电子邮件：确认供应订单、供应订单核准和处理以及供应完成。供应完成电子邮件包含登录到 {{site.data.keyword.cloud_notm}} 后可以访问的*设备详细信息*页面的链接。您还可以直接登录到 {{site.data.keyword.slportal}}。

#### 确认 {{site.data.keyword.backup_notm}} 购买
1. 在 [{{site.data.keyword.cloud_notm}} 控制台 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/){:new_window} 中，单击左上角的**菜单**图标。选择**经典基础架构**。</br>
   或者，可以登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}。
2. 单击**设备** > **设备列表**。
2. 找到您订购的新服务器。
  - 如果 URL 旁边有“时钟”图标，那么您需要稍候才能继续确认 {{site.data.keyword.backup_notm}} 购买信息。您可以刷新此页面，以查看新服务器的更新状态。“时钟”图标不再显示时，您可以继续执行后续步骤以确认 {{site.data.keyword.backup_notm}} 服务购买。
  - 服务器的“时钟”图标不再显示时，请单击相应链接（服务器的 URL）以转至**设备详细信息**页面。
3. 单击**存储**选项卡以显示 {{site.data.keyword.backup_notm}} 信息。
4. 检查 {{site.data.keyword.backup_notm}} 部分，并验证购买过程中选择的大小是否显示。

### 作为升级购买 {{site.data.keyword.backup_notm}}

#### 选择要安装 {{site.data.keyword.backup_notm}} 的服务器

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。</br>
   或者，可以登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}。
2. 从主菜单中选择**设备** > **设备列表**。找到要添加 {{site.data.keyword.cloud_notm}} 备份服务的设备。
3. 单击设备名以转至**设备详细信息**页面。

#### 添加（购买）{{site.data.keyword.backup_notm}} 服务
1. 单击**存储**选项卡，然后向下滚动以找到 {{site.data.keyword.backup_notm}} 部分。
2. 单击**添加**链接。
3. 在窗口中，选择一个位置，然后选择大小。
4. 选择“支付类型”，然后单击**继续**
5. 如果您有促销代码，请输入**促销代码**，然后单击**重新计算**。
6. 复查订单，然后单击链接以阅读条款和条件。
7. 如果您同意条款和条件，请单击相应复选框。
7. 单击**下订单**。

#### 确认 {{site.data.keyword.backup_notm}} 升级购买
1. 刷新**设备详细信息**页面，并确保已选择**存储**选项卡。
2. 检查 {{site.data.keyword.backup_notm}} 部分，并验证购买过程中选择的大小是否显示。

   如果备份存储器大小的容量仍然显示为零，说明可能需要再次刷新页面。
   {:tip}

## 访问和查看 {{site.data.keyword.backup_notm}} 存储器详细信息

可随时在 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}/catalog/){:new_window}和 {{site.data.keyword.slportal}} 中查看 {{site.data.keyword.backup_notm}} 服务的存储器详细信息。可查看的详细信息包括与所选 {{site.data.keyword.backup_notm}} 服务关联的密码、存储地址和使用情况。

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。</br>
   或者，可以登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}。
2. 单击**存储**，然后从列表中选择**备份**。
2. 单击保险库所在行上的任意位置以查看其存储器详细信息。在此视图中，无法查看“密码”。请继续执行下一步以查看与 {{site.data.keyword.backup_notm}} 服务关联的密码。
3. 单击**密码**字段旁边的**显示**复选框，以查看所选 {{site.data.keyword.backup_notm}} 服务的密码。

对于许多 {{site.data.keyword.BluSoftlayer_full}} 产品和服务，{{site.data.keyword.slportal}} 内的密码存储功能仅用于存储或跟踪密码。对于其他产品，对 {{site.data.keyword.slportal}} 中的密码进行的更改不会应用于相应产品或服务。

但对于 {{site.data.keyword.backup_notm}}，情况_并非_如此。对 {{site.data.keyword.slportal}} 内的 {{site.data.keyword.backup_notm}} 密码进行的更改将应用于该服务本身。更改密码时，请记住这会直接影响服务。要重置密码，请执行[如何在 {{site.data.keyword.slportal}} 中更改 {{site.data.keyword.backup_notm}} 密码](change-password.html)中的步骤。
{:important}

## 安装 {{site.data.keyword.backup_notm}} 代理程序

以下操作系统上支持 {{site.data.keyword.backup_notm}} 代理程序。

**Windows**
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
- [在 Linux 中安装备份客户机](install-backup-client-linux.html)
- [在 Windows 中安装备份客户机](install-backup-client-windows.html)
- [在 Windows 2016 中安装备份客户机](install-windows2016.html)
- [在 VMware 中安装备份客户机](https://{DomainName}/docs/infrastructure/vmware/install-backup-client-vmware.html)

## 访问 {{site.data.keyword.backup_notm}} 门户网站（以前称为 WebCC）

{{site.data.keyword.backup_notm}} 门户网站用于与由 {{site.data.keyword.BluSoftlayer_full}} 提供的任何 {{site.data.keyword.backup_notm}} 服务进行交互。{{site.data.keyword.backup_notm}} 门户网站是一种基于浏览器的客户机，在 {{site.data.keyword.BluSoftlayer_full}} 专用网络上运行，支持对任何 {{site.data.keyword.backup_notm}} 服务进行完全控制，包括配置和复原。

1. 通过 VPN 访问专用网络。

   {{site.data.keyword.backup_notm}} 门户网站无法通过公用网络进行访问。必须先建立 VPN 连接。
   {:important}
2. 访问 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window} 中的“备份存储器”屏幕。
3. 单击想要查看的 {{site.data.keyword.backup_notm}} 服务所在行上的任意位置以展开视图。
4. 单击 **{{site.data.keyword.backup_notm}} 门户网站登录**，以在浏览器中启动 {{site.data.keyword.backup_notm}} 门户网站客户机。

## 配置备份代理程序和备份调度

订购了 {{site.data.keyword.backup_notm}} 并且在服务器上安装了代理程序之后，即可以开始创建数据备份。您可以按照以下步骤配置代理程序、保留安排以及启动第一个备份作业。

1. 登录到 WebCC。
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
5. 运行代理程序并启动备份。
   1. 单击**所有代理程序**，然后选择已配置的代理程序。
   2. 单击**运行备份**。
   3. 确认“目标”并选择保留方案。
   4. 单击**启动备份**。您可以在进程运行时查看备份详细信息。
   5. 完成备份后，单击**关闭**。

有关 Linux 上文件级别备份的更多信息，请参阅[在 Linux 上配置简单的文件级别备份](configure-simple-file-backup-linux.html)。
{:tip}

## 获取联机帮助

{{site.data.keyword.backup_notm}} 门户网站的系统已全部记录，并且可在 {{site.data.keyword.backup_notm}} 门户网站内访问对该应用程序的支持。单击右上角含有白色问号的蓝色圆圈以获取**帮助**。单击左侧导航栏中的任何文章或主题以查看更多信息。
