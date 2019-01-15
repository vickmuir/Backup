---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:codeblock: .codeblock}
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 在 Linux 中安装备份客户机

要在基于 Linux 的操作系统上安装 {{site.data.keyword.backup_full}} 客户机，可通过在操作系统的 shell 或终端中运行一系列命令来完成。此过程概述了在以下任何基于 Linux 的操作系统上安装客户机所需的步骤：

- RHEL
- CentOS
- CloudLinux

完成此过程后，进程会自动向 {{site.data.keyword.backup_notm}} 门户网站注册代理程序服务，然后下载并安装运行该服务所需的文件。

如果通过 [{{site.data.keyword.cloud_notm}} 目录](https://{DomainName}/catalog/){:new_window}或 {{site.data.keyword.slportal}} 订购服务器时购买了 {{site.data.keyword.backup_notm}}，那么会自动为您安装该软件。您不需要使用本文档中所述的过程。
{:tip}

如果您在 {{site.data.keyword.slportal}} 中购买了 {{site.data.keyword.backup_notm}}（作为升级选项），请执行以下步骤来安装该软件。

## 登录到目标设备服务器

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}/){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。<br/>
   或者，可以登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}。
2. 从主菜单中选择**设备** > **设备列表**以查看可用服务器设备的列表。
3. 找到为其购买 {{site.data.keyword.backup_notm}} 服务的设备，并记下其公共 IP 地址。
  - 在以下步骤中，从 Unix 或 Linux 命令行登录到设备时要使用此 IP 地址。在步骤 5 所示的命令中，将 <publicIpAddress> 替换为实际的公共 IP 地址。
4. 单击向右箭头以显示有关设备的更多信息，包括用户名和密码。
  - 如果未显示密码，可通过单击**显示密码**来显示密码。在下一步中，将使用该用户名和密码来登录到测试设备。在下面的命令中，将 `<user name>` 替换为实际的用户名。
5. 通过在 Unix 或 Linux 命令行中输入以下命令，登录到目标设备。
   ```
  ssh <user name>@<publicIpAddress>
  ```
   {: pre}

   如果您之前未使用此用户名登录到此服务器，那么系统会向您显示一条有关主机真实性的消息。系统还会询问您是否要继续。请回答**是**以继续。
   {:note}

6. 系统将提示您输入密码，除非您之前设置了用于访问此服务器的 SSH 密钥。

## 更新操作系统以准备安装（仅针对 RHEL）

此步骤对于 RHEL 是必需的，但是对于其他 Linux 分发版是可选的。
{:tip}

- 在服务器提示符处运行以下命令。
  ```
  yum update
  ```
  {: pre}

  在系统提示时，确认下载大小是否正常。更新将继续，并在完成时显示“完成”消息。

## 获取安装脚本

- 在服务器提示符处运行以下命令。
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}

## 运行安装脚本

1. 在服务器提示符处运行以下命令。
   ```
  sh ./evault_manual.sh
  ```
   {: pre}

2. 输入 {{site.data.keyword.backup_notm}} 门户网站用户名和密码。

   有关查看 {{site.data.keyword.backup_notm}} 用户名和密码的更多信息，请参阅[备份服务入门](index.html#accessing-and-viewing-ibm-cloud-backup-storage-details)。
   {:tip}

3. 在输入用户名和密码之后，再没有任何需要输入的内容了。在安装过程中屏幕上显示的提示可以安全地忽略。

   它们是由 `evault_manual.sh` 脚本所启动的子脚本生成的。`evault_manual.sh` 脚本会提供这些提示的输入内容。
   {:note}

4. 出现以下消息时，说明安装完成。

   ```
  Starting VVAgent: [  OK  ]
  Starting buagent: [  OK  ]
  ```
   {: codeblock}

## 验证安装是否成功

1. 验证安装输出中是否显示“已注册到门户网站”的消息。可通过在屏幕上查找该消息或通过检查以下命令的输出来完成验证。
   ```
  grep 'Registered'  /opt/BUAgent/Install.log
  ```
   {: pre}

2. 运行以下命令并观察输出。
   ```
  service vvagent status
  ```
   {: pre}

   这将显示以下消息。
   ```
  VVAgent is running (PID xxxxx).
  buagent is running (PID xxxxx).
  ```
   {: codeblock}

  由 `xxxxx` 表示的进程标识因各个安装而异。
  {:tip}

**后续步骤**

登录到 {{site.data.keyword.backup_notm}} 门户网站以配置和管理备份代理程序。有关更多信息，请参阅[入门教程](index.html#configuring-the-backup-agent-and-the-backup-schedule)和[在 Linux 上配置简单的文件级别备份](configure-simple-file-backup-linux.html)。
