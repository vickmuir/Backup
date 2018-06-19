---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-03"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# 在 VMware 上安装 EVault Backup 客户机

要在 VMware 服务器上安装 EVault Backup 客户机，可通过在目标 ESX 服务器的 shell 或终端中运行一系列命令来完成。下面列出了在 VMware 服务器上安装 EVault Backup 客户机所需的步骤：

要安装代理程序，请使用以下命令将 `Agent-VMware-ESX-Server-6.71.<version-info>.tar.gz` 软件包下载并复制到目标 ESX 服务器上：

`wget -N http://downloads.service.softlayer.com/evault/archive/Agent-VMware-ESX-Server-6.71.2105.tar.gz`

**注**：以下步骤必须在目标 ESX 服务器上本地执行。

1. 解压缩软件包。要完成此操作，请使用以下命令（其中“PACKAGENAME”可以为“Agent-VMware-ESX-Server-6.71”）：`tar xvfz PACKAGENAME.tar.gz`
2. 转至将软件包解压缩到的目录。
3. 运行安装脚本：`# ./install.sh`

    **注**：安装脚本会以交互方式提示您输入 Web 注册（地址、端口号和认证）和日志文件名等配置信息。
     
    - 输入此服务器的 WebCC 用户名。
    - 输入此服务器的 WebCC 密码。
     
4. 在提示输入 WebCC 用户名时，输入 **EVault Backup 用户名**。 
5. 在提示输入 WebCC 密码时，输入 **EVault Backup 密码**。
6. 安装完成时，将显示一条完成消息，并且会运行代理守护程序。


### 其他安装说明：
如果安装成功，那么 Install.log 将位于安装目录中。例如：`/opt/BUAgent/Install.log`

如果安装失败并已回滚，那么安装日志将位于 `<Installation Failure directory>` 中。如果安装失败但未回滚，那么安装日志将位于 `<Installation Kit directory>` 中。

有关更多信息，请下载 [VMware_Agent_User_Guide](http://downloads.service.softlayer.com/evault/Documentation/VMware_Agent_User_Guide.pdf){:new_window}。要查看此链接，请确保已连接到 {{site.data.keyword.BluVPN}}。
