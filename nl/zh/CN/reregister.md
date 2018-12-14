---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# 重新注册保险库

这是重新装入服务器的操作系统后最常用的任务。您还可以使用这些步骤来[使用一个服务器的备份在另一个服务器上复原数据](restore-from-another-computer.html)。

1. 启动 WebCC 并登录。有关更多信息，请参阅[入门教程](index.html)。

   请记住，WebCC 只能通过 {{site.data.keyword.BluVPN}} 进行访问。
   {:tip}
2. 单击左侧的**所有代理程序**。
3. 将鼠标悬停在右上角的**编辑**。
4. 选择**保险库设置**。
5. 单击**重新注册**。
6. 填写表单。
  - 保险库名称
  - 保险库地址
  - 帐户

   “帐户”相当于 [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} 中的“帐户名称”。通常，这类似于“SLE[account ID]”。
    {:tip}
  - 用户名
  - 密码
7. 单击**装入计算机**，然后选择要装入的计算机。
8. 单击**保存更改**。
9. 刷新 Web 站点以复原先前的备份作业。
10. 同步每个备份作业以复原安全集历史记录。
11. 如果备份作业是使用加密密码创建的，那么必须输入加密密码才能复原数据或继续进行备份。
12. 单击**关闭**。
