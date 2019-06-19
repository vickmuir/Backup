---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-10"

keywords: IBM Cloud backup, EVault, Carbonite, backup, restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 使用备份进行复原
{: #simplerestore}

使用以下步骤来通过 {{site.data.keyword.backup_full}} 完成文件复原。要复原系统映像，请遵循 [Windows BMR](https://cloud.ibm.com/docs/infrastructure/Backup?topic=Backup-restoreBMR#restoreBMR) 指示信息。

## 启动 {{site.data.keyword.backup_notm}} 门户网站
{: #startWebCCsimple}

请务必启动 {{site.data.keyword.BluVPN}} 连接来访问 {{site.data.keyword.cloud}} 专用网络。否则，{{site.data.keyword.backup_notm}} 门户网站链接是不好用的。
{:important}

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}){: external}，然后单击左上角的**菜单**图标。选择**经典基础架构**。
2. 单击**存储** > **备份**以显示具有备份服务的服务器。
3. 选择要复原的文件所在的服务器。单击箭头以显示 {{site.data.keyword.backup_notm}} 门户网站链接。
4. 单击 **{{site.data.keyword.backup_notm}} 门户网站**，以在浏览器中启动 {{site.data.keyword.backup_notm}} 门户网站客户机。

## 复原数据

1. 在左侧导航窗格中，单击**所有代理程序**。
2. 单击代理程序以显示作业。
3. 单击包含所需数据的作业。
4. 单击**运行复原**。
5. 选择复原源。
6. 选择备份版本。
7. 输入加密密码。
8. 单击**下一步**以继续。
9. 选择要将其包含的文件和目录旁边的复选框。然后，单击**包含**以保存您的选择。
10. 可以使用所显示的窗口来进一步过滤您的选择，也可以单击**确定**以按原样使用您所做的选择。包含选择的文件和目录之后，在数据文件窗格中将无法再选择这些文件。它们将显示在右侧的备份集窗格中。

   您可以重复步骤 10 来添加更多文件或除去先前添加的文件（使用**排除**）。还可以使用**除去**，从**备份集**窗格中删除任何行项。
   {:tip}

11. 在按所需方式配置了备份集之后，单击**下一步**以继续。
12. 在下一个窗格中保留缺省设置，或根据首选项自定义复原。然后，单击**运行复原**。
13. 当**过程详细信息**屏幕上的“状态”显示为**复原完成**时，表明文件复原完成。
