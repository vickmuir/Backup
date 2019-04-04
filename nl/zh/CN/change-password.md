---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, password, password reset

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 更改备份服务的密码
{: #changePassword}

每个 {{site.data.keyword.backup_full}} 服务都有一个关联的密码，用于在 {{site.data.keyword.backup_notm}} 门户网站内访问保险库。

对于许多 {{site.data.keyword.BluSoftlayer_full}} 产品和服务，{{site.data.keyword.slportal}} 内的密码存储功能仅用于跟踪密码。对于其他产品和服务，对 {{site.data.keyword.slportal}} 中的密码进行的更改不会应用于相应产品或服务。但对于 {{site.data.keyword.backup_notm}}，情况**并非**如此。

对 {{site.data.keyword.slportal}} 内的 {{site.data.keyword.backup_notm}} 密码进行的更改将应用于该服务本身。更改密码时，请记住这会直接影响服务。
{:important}

## 更改密码

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}/catalog){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。<br/>
   或者，可以登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}。
2. 单击**存储** > **备份**以显示具有备份服务的服务器。
3. 单击保险库所在行上的任意位置以展开视图。
4. 单击**显示**以查看当前密码。
5. 在**密码**字段中输入新密码。
6. 单击**更新**。
