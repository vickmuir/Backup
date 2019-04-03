---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 在 Windows 上配置 BMR 备份作业
{: #configureBMR}

您需要购买 BMR 插件才能创建 BMR 备份。BMR 仅可用于 Windows 裸机服务器。没有 BMR 选项可用于 VSI。有关更多信息，请参阅[安装 Bare Metal Restore 插件](/docs/infrastructure/Backup?topic=Backup-BMRplugin#BMRplugin)
{:important}

## 启动 {{site.data.keyword.backup_notm}} 门户网站
{: #startWebCCBMR}

您需要连接到 {{site.data.keyword.BluSoftlayer_full}} 专用网络才能启动 {{site.data.keyword.backup_notm}} 门户网站。
{:important}

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}/){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。<br/>
   或者，可以登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}。
2. 单击**存储** > **备份**以显示具有备份服务的服务器。
3. 选择要备份的文件所在的服务器。单击指向右方的展开箭头以显示 {{site.data.keyword.backup_notm}} 门户网站链接。
4. 单击 **{{site.data.keyword.backup_notm}} 门户网站登录**，以在浏览器中启动门户网站客户机。

   如果 {{site.data.keyword.backup_notm}} 门户网站未启动，那么可能是 VPN 连接存在问题。您还可能会看到一条消息，指示您要发送的表单不安全。这是预期行为 - 请通过发送表单以继续。
   {:tip}

## 配置 BMR 备份作业

1. 在左侧导航窗格中，单击**所有代理程序**以显示当前的 {{site.data.keyword.backup_notm}} 代理程序。
2. 单击**这是我要配置的新代理程序**。
3. 输入您正在创建的作业的“作业名”和“作业描述”。
4. 对于**备份源类型**，请选择文件系统类型，然后单击**下一步**
5. 这将显示**作业类型选择**菜单。选中**裸机复原**旁边的框，然后单击**下一步**以继续。
6. 在“确认”窗口上单击**是**。
7. 屏幕将显示新作业现在位于备份集内。单击**下一步**。
8. 屏幕将显示加密选项和高级备份选项。通常情况下，不需要这些选项。单击**下一步**。   
9. 在**创建安排**页面上，您有两个选项。
   - 单击**下一步**以创建手动作业，然后继续运行新作业。
   - 单击**添加**以安排基于时间的备份作业。
     1. 选择运行备份的日期和时刻。
     2. 选择“保留方案”。

        有关“保留方案”的更多信息，请参阅[常见问题](/docs/infrastructure/Backup?topic=Backup-faqs)。
        {:tip}
     3. 配置备份安排后，单击**确定**以保存该备份安排。安排的作业会添加到已安排作业列表中。
10. 为备份作业选择保险库，然后单击**保存更改**。


## 运行 BMR 备份作业

  - 如果安排了基于时间的备份作业，那么无需执行其他任何操作。您的作业将自动按安排运行。
  - 如果设置的是手动作业（没有基于时间的安排），那么可以通过在作业列表中选择该作业所在行，然后单击**运行备份**来运行该作业。<br/> 对于基于时间的作业，可以选择**保留方案**和**高级备份选项**。完成配置选项后，单击**启动备份**以启动作业。
