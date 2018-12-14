---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# 升级 Windows 的备份软件代理程序

使用以下逐步指示信息来升级 Windows 服务器上的 {{site.data.keyword.backup_notm}} 代理程序。

1. 远程控制需要通过 RDP 进行 {{site.data.keyword.backup_notm}} 升级的 {{site.data.keyword.BluSoftlayer_full}} 服务器。
2. 打开浏览器，然后转至以下地址。
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
3. 单击所需的文件。（例如，Agent-Windows-x64-6-72-1072a.exe）

   文件名中含有版本号。请选择最新版本。<br/>提供了单独的 32 位和 64 位安装程序。如果您使用的是 64 位操作系统，请下载名称中含有 x64 的文件。
   {:tip}
4. 在下载屏幕上单击**运行**，然后在下载后再次单击“运行”。
5. 单击**是**以升级 **EVault Software Agent**。

   安装程序在装入期间可能会消失片刻。
   {:note}
6. 选择**保留我当前的注册**，然后单击**下一步**。
7. 单击**下一步**。代理程序将开始升级过程。这可能需要数分钟时间。
8. 在完成屏幕上，单击**完成**。
