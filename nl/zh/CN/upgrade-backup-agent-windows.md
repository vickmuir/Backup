---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# 升级 Windows 的备份软件代理程序
{: #UpgradeinWindows}

最新的备份代理程序可以从 {{site.data.keyword.backup_notm}} 门户网站仪表板快速链接部分进行下载。
{:tip}

1. 远程控制需要进行 {{site.data.keyword.backup_notm}} 升级的 {{site.data.keyword.BluSoftlayer_full}} 服务器。 
2. 打开浏览器，然后转至以下地址。
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
3. 单击所需的文件。（例如，Agent-Windows-x64-6-72-1072a.exe）

   文件名中含有版本号。请选择最新版本。<br/>{{site.data.keyword.BluSoftlayer_full}} 提供了单独的 32 位和 64 位安装程序。如果您使用的是 64 位操作系统，请下载名称中含有 x64 的文件。
   {:tip}
4. 在下载屏幕上单击**运行**，然后在下载后再次单击“运行”。
5. 单击**是**以升级 **{{site.data.keyword.backup_notm}} 软件代理程序**。

   安装程序在装入期间可能会消失片刻。
   {:note}
6. 选择**保留我当前的注册**，然后单击**下一步**。
7. 单击**下一步**。代理程序将开始升级过程。这可能需要数分钟时间。
8. 在完成屏幕上，单击**完成**。
