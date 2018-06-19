---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# 安装 EVault Exchange 插件

Exchange 插件随 Windows 代理程序一起安装在主机上。通过使用 WebCC 门户网站，可以配置作业，将 Oracle 数据库备份到安全的远程保险库，以及复原 Oracle 数据库。该 Oracle 插件集成到现有体系结构中。

## 提供的功能

- 能够备份和复原 Microsoft Exchange 数据库。

## 订购插件

1. 登录到 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}。
2. 单击**存储** > **备份**。
3. 选择 EVault 帐户，然后单击**订购插件**。
4. 选择 **EVault 插件 - Exchange**，然后单击**继续**。
5. 如果您有促销代码，请输入促销代码，然后单击**重新计算**。
6. 这将显示更新后的费用。复查订单。
7. 选中相应框以指示您已阅读“主服务协议”并接受“第三方软件条款”。 
8. 单击**下单**。

## 安装 Exchange 插件

Exchange 插件在 Windows 代理程序 64 位安装期间进行安装。该插件可以在安装代理程序时进行安装，也可以日后通过使用“修改”选项重新运行安装来进行安装。

**注**：在为 Microsoft Windows 服务器安装该插件之前，请停止 `services.msc` 中的两个 EVault 服务。  

1. 浏览至 `c:\installs\evault` 文件夹，然后运行具有更高修订版号的 .exe 文件。
2. 在语言屏幕上，单击**确定**。
3. 在欢迎屏幕上，单击**下一步**。
4. 选择**修改安装**，然后单击**下一步**。
5. 选择**保留不变**，然后单击**下一步**。
6. 在定制设置屏幕上，选择已购买的每个插件，然后选择**此功能部件将安装在...**，然后单击**下一步**。
7. 选中**保留我当前的注册**单选按钮，然后单击**下一步**。
8. 单击**安装**。
9. 安装后，请进行检查以确保先前停止的两个服务都已启用并且正在运行。
10. 如果 WebCC 能够访问（查看）数据库，说明安装成功。 

## 用户指南

使用 {{site.data.keyword.BluVPN}} 连接到 {{site.data.keyword.BluSoftlayer_full}} 网络，以便可以从[可下载的 EVault 文档](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}下载 EVault Agent v8.0 for Microsoft Windows (64-bit) - Exchange Plug-in Guide.pdf。此指南描述了如何使用 Exchange 插件来备份和复原 Microsoft Exchange 数据库。此指南还描述了如何共享 DR 备份安全集，以便可以使用 Granular Restore for Microsoft Exchange 应用程序将特定邮箱、消息或其他对象复原到 .pst 文件。


