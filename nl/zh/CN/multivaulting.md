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

# 多保险库技术

通过多保险库技术，客户机/服务器能够连接到多个保险库位置。该技术提供了冗余功能，可让您高枕无忧，就算某个站点发生故障，也仍有备份可用。

**要点**

1. 多个保险库可通过同一个 WebCC 进行管理，并以相同方式进行处理。唯一的区别是保险库选项不同。
2. 插件许可按保险库进行发放。例如，如果在华盛顿为某个保险库购买了 MSSQL 插件，那么此插件并不能用于西雅图的保险库。
3. 每次购买新的保险库后，都需要手动将其添加到 WebCC 中。

**{{site.data.keyword.backup_notm}} 保险库导向器位置**

多保险库技术在所有数据中心内可用，并且在选择远程保险库时没有地域限制。如果保险库是按照本文档中所述的步骤进行配置的，那么所有配置的保险库都会显示在保险库设置中。

备份到远程数据中心位置所需的时间可能要比备份到服务器所在数据中心的时间长。
{:note}

## 向帐户添加远程保险库

在 WebCC 中添加新的备份位置之前，必须先将新的远程 {{site.data.keyword.backup_notm}} 保险库添加到帐户中。

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}/catalog/){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。

   或者，可以登录到 [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}。
2. 单击**设备**
3. 找到并单击相关服务器的链接。
4. 在**设备详细信息**下，单击**存储**。
5. 当“存储”部分打开时，向下滚动到 **{{site.data.keyword.backup_notm}}**，然后单击**添加**。
6. 在**订购 {{site.data.keyword.backup_notm}}** 窗口中，单击下拉列表中的相应条目来选择远程保险库位置。
7. 选择存储量大小，然后单击**继续**
8. 选中**我已阅读主...** 复选框，然后单击**下订单**。

新订购的保险库会自动添加到帐户中。如果没有，请联系销售人员以寻求帮助。

订购过程完成后，可以转至**存储** > **备份**来查看新保险库是否已列出。

## 在 WebCC 中添加其他保险库

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}/catalog/){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。

   或者，可以登录到 [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}。
2. 单击**存储** > **备份**以显示具有备份服务的服务器。
3. 选择您希望能够备份到多个保险库的服务器。单击向右箭头以显示 WebCC 链接。
4. 单击 **WebCC 登录**链接，以在浏览器中启动 WebCC 客户机。

   WebCC 只能通过 {{site.data.keyword.BluVPN}} 进行访问。
   {:tip}
5. 在左侧导航窗格中，单击**所有代理程序**。
6. 单击右上角的**编辑**，然后选择**保险库设置**。
7. 在**保险库设置**窗口中，单击**添加**。
8. 在**新建保险库**窗口中：
  1. 在“保险库概要文件”菜单中，选择**输入保险库设置**来创建新条目。不要更新现有条目，这样做是没用的。
  2. 保险库名称不能与其他保险库同名。若同名，请尝试在名称末尾添加 -2 标记。<br/>

     此字段的字符数限制为 15。
     {:important}
  3. “IP 地址”字段中会填充 {{site.data.keyword.backup_notm}} 导向器位置信息。例如，`ev-director301.service.softlayer.com` 的 IP 地址为 10.1.114.46，位于 WDC。
  4. 在“凭证”字段中，输入帐户标识、所选保险库的 {{site.data.keyword.backup_notm}} 用户名和所选保险库的密码。
  5. 单击**保存更改**。

新的保险库将在几秒钟后可用。如果连接失败，请检查设置，然后重试。请记住，添加额外的保险库仅为您提供了额外的作业目标可供选择。系统并不会自动对这两个保险库运行作业。您需要将作业设置为使用此额外的保险库。有关更多信息，请参阅[入门教程](index.html)。
