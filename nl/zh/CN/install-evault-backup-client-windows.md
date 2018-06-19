---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-14"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 在 Windows 中安装 EVault Backup 客户机

要在 Windows 中安装 EVault Backup 客户机，可通过登录到为 EVault Backup 服务指定的服务器并进行一系列交互操作来完成。请按照以下步骤在 Windows 中安装 EVault Backup 客户机。

**注**：当前不支持 Windows 2016。

## 登录到目标设备服务器

1. 登录到 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}，并从主菜单中选择**设备** > **设备列表**以查看可用服务器设备的列表。
2. 查找您为其购买 EVault 服务的设备，并记下其公共 IP 地址。
3. 单击指向右方的展开箭头以显示有关设备的更多信息，包括用户名和密码。如果未显示密码，可单击**显示密码**复选框来显示密码。 
4. 使用“远程桌面连接”登录到目标设备。

## 下载 EVault 客户机

1. 在目标服务器上，打开浏览器会话，然后输入以下 URL 来下载 EVault Backup 客户机的可执行文件。<br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}
  
2. 双击下载的文件，然后在显示的弹出框中单击**运行**。


## 安装和注册 EVault 代理程序
 
1. 输入网络地址：<br />
  ```
  ev-webcc01.service.softlayer.com
  ```
  {: pre}
  
2. 在**用户名**字段中，输入 EVault Backup 用户名。 
3. 在**密码**字段中，输入 EVault Backup 密码。 
6. 单击**下一步** 
7. 单击**安装**以完成安装。

## 后续步骤

登录到 WebCC 以配置和管理备份代理程序。相关指示信息请参阅[入门教程](index.html#configuring-evault-agent-in-webcc)。
