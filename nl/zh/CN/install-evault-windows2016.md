---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-05"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 在 Windows 2016 上配置 EVault

目前，Windows 2016 还未正式支持 EVault WebCC。在 Windows 2016 上运行的服务器必须使用 Windows Central Control 软件。

## 安装 EVault Backup 代理程序

1. 在目标服务器上，打开浏览器会话，然后输入以下 URL 来下载可执行文件
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
2. 双击下载的文件，然后在显示的弹出框中单击**运行**。
3. 选择用于安装的语言，然后单击**确定**。
4. 对于“安装类型”，选择**典型**。单击**下一步**。
5. 在“向门户网站注册代理程序”屏幕中，选择**跳过注册**。 
6. 单击**下一步**，然后单击**完成**。

## 安装 EVault 软件 CentralControl

1. 在目标服务器上，打开浏览器会话，然后输入以下 URL 来下载可执行文件。

   ```
   http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. 双击下载的文件，然后在显示的弹出框中单击**运行**。
3. 按照“典型”安装的安装步骤来执行操作。

## 配置 CentralControl

可通过登录到为 EVault Backup 服务指定的服务器并进行一系列交互操作来完成此任务。

1. 通过 RDP 远程控制您的服务器。
2. 启动 CentralControl。
3. 在工作空间中，右键单击**代理程序**，然后选择**代理程序配置**。
4. 单击**新建**。
5. 选择**注册为新计算机**，然后单击**下一步**。
6. 输入网络地址，单击**添加**，然后单击**下一步**。
7. 输入新的端口值，单击**添加**，然后单击**下一步**。
8. 在“连接设置”屏幕中，输入所需的秒数/分钟数。 
9. 在“认证”屏幕中，输入您的凭证，然后单击**下一步**。
10. “已注册的计算机”窗口会显示您的服务器主机名。单击**下一步**。
11.	当保险库配置向导收集完您的信息后，单击**完成**以完成注册。


