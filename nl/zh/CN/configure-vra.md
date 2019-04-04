---

copyright:
  years: 1994, 2019
lastupdated: "2019-03-29"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 配置 VRA 备份作业 
{: #ConfigureVRA}
 
在 VMware vSphere 环境添加到 {{site.data.keyword.backup_notm}} 门户网站中之后，您可以创建备份作业以指定要备份哪些虚拟机 (VM) 以及要将备份数据保存到何处。要备份数据，可以手动运行备份作业或安排运行备份作业。 

您必须先配置保险库设置和 vCenter 信息，然后才能添加备份作业。
{:important}

## 启动 {{site.data.keyword.backup_notm}} 门户网站
{: #startWebCCVRA}

您需要连接到 {{site.data.keyword.BluSoftlayer_full}} 专用网络才能启动 {{site.data.keyword.backup_notm}} 门户网站。
{:important}

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。<br/>
或者，可以登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}。
2. 单击**存储** > **备份**以显示具有备份服务的服务器。
3. 选择要备份的文件所在的服务器。单击指向右方的展开箭头以显示 {{site.data.keyword.backup_notm}} 门户网站链接。
4. 单击 **{{site.data.keyword.backup_notm}} 门户网站登录**，以在浏览器中启动门户网站客户机。

   如果 {{site.data.keyword.backup_notm}} 门户网站未启动，那么可能是 VPN 连接存在问题。您还可能会看到一条消息，指示您要发送的表单不安全。这是预期行为 - 请通过发送表单以继续。
   {:tip}

## 添加 vSphere 备份作业

1. 单击导航中的**计算机**。“计算机”页面显示已注册的计算机和环境。 
2. 单击**作业**。 
3. 在“任务”菜单“选择作业”中，单击**新建 VMware vCenter 作业**。 
4. 指定以下信息。
   * 在**名称**字段中，输入备份作业的名称。 
   * 在**描述**字段中，可选择输入备份作业的描述。 
   * 在**目标**列表中，选择要在其中保存备份数据的保险库。
   * 在**密码**和**确认密码**字段中，输入加密密码。还可以在“密码提示”字段中输入密码提示。
   仅当保险库分配给用户时，或者用户将其添加到计算机的“保险库设置”时，该保险库才会显示在列表中。<br/> 
   对于新的备份作业，加密方法为 AES 256 位。现有作业可以有其他加密方法。
   {:note}

5.	在**包含在备份中**字段中，执行以下一个或多个步骤，直至“备份集”字段显示您要包含在备份作业中的 VM 为止：

   * 要向备份作业添加特定 VM，请选择每个 VM，然后单击**包含**。
   * 要从备份作业排除特定 VM，请选择每个 VM，然后单击**排除**。
   * 要按名称向备份作业添加 VM，请选中“虚拟机”框，然后单击**包含**。
   * 要从“备份集”框除去包含或排除记录，请单击该记录旁边的**删除**。 

6. 单击**立即应用**以合并和简化“备份集”框中的记录（如果需要应用更改）。
7. 单击**创建作业**。
 
## 设置安排

创建备份作业后，可以添加一个或多个自动运行该作业的安排。 

1. 单击**创建作业**时，将显示“安排”窗口，并提供选项用于为备份作业设置定制安排。

   缺省情况下，为作业选择了“每天”保留时间。可以在此窗口中更改保留时间和作业安排，并且还可以将多个保留时间方案分配给备份作业。
   {:note}
2. 单击**保存**以保存新的安排。新的作业将显示在“计算机”选项卡下的“作业”部分中。“上次备份状态”显示该作业从未运行过。安排的备份作业会在安排的时间自动运行。 

## 运行安排的作业

还可以立即执行安排的备份作业。 

1. 单击**选择操作**并选择**运行作业**。将显示“运行作业”窗口，并提供有关分配给该作业的目标保险库和保留时间方案的信息。

   如果有多个保险库和保留时间方案分配给该作业，可以通过在“运行作业”窗口中单击“目标”和“保留时间方案”菜单选项来更改这些选项。
   {:note}
2. 单击**启动备份作业**以立即执行备份作业。将有进度窗口显示备份作业的状态，作业完成时，作业状态将从“从未运行”更改为“已完成”。 
 
要查看上次运行的备份作业的状态，请单击“作业”选项卡。所有作业日志都可以从操作菜单进行访问。单击**操作**并选择**历史记录/日志**。
{:tip}

有关复原 VM 或文件和文件夹的更多信息，请参阅[复原 vSphere 数据](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore)。
