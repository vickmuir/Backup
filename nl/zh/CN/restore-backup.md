---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 使用备份进行复原

使用以下步骤来通过 {{site.data.keyword.backup_full}} 完成文件复原。要复原系统映像，请遵循 [Windows BMR](restore-bmr-system-volume-image.html) 指示信息。

## 启动 WebCC

请务必启动 {{site.data.keyword.BluVPN}} 连接来访问 {{site.data.keyword.BluSoftlayer_full}} 专用网络。否则，WebCC 链接将不起作用。
{:important}

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}/catalog/){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。

   或者，可以登录到 [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}。
2. 单击**存储** > **备份**以显示具有备份服务的服务器。
3. 选择要复原的文件所在的服务器。单击箭头以显示 WebCC 链接。
4. 单击 **WebCC** 以在浏览器中启动 WebCC 客户机。

## 复原数据

1. 在左侧导航窗格中，单击**所有代理程序**。
2. 单击代理程序以显示作业。
3. 单击包含所需备份的作业。
4. 单击**运行复原**。
5. 选择复原源。
6. 选择备份版本。
7. 输入加密密码。
8. 单击**下一步**以继续。
9. 选中要包含的文件和目录旁边的复选框，然后单击**包含**以保存您的选择。
10. 可以使用所显示的窗口来进一步过滤您的选择，也可以单击**确定**以按原样使用您所做的选择。您包含所选文件和目录之后，在**数据文件**窗格中将无法再选择这些文件。它们将显示在右侧的**备份集**窗格中。

   您可以重复步骤 10 来添加更多文件或除去先前添加的文件（使用**排除**）。还可以使用**除去**，从**备份集**窗格中删除任何行项。
   {:tip}
11. 在按所需方式配置了备份集之后，单击**下一步**以继续。
12. 保持下一个窗格中的缺省设置不变，或根据自己的喜好来定制复原，然后单击**运行复原**。
13. 当**过程详细信息**屏幕上的“状态”显示为**复原完成**时，表明文件复原完成。
