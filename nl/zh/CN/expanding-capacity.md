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


# 扩展保险库容量

当前 {{site.data.keyword.BluSoftlayer_full}} 用户可以将其保险库的大小扩展到 4000 GB。他们无需创建重复项或手动将数据迁移到更大的卷。限制增加的过程不会导致任何中断和访问权缺乏的问题。

## 订购增加量

1. 登录到 [{{site.data.keyword.cloud_notm}} 控制台](https://{DomainName}/catalog/){:new_window}，然后单击左上角的**菜单**图标。选择**经典基础架构**。<br/>
   或者，可以登录到 [{{site.data.keyword.slportal}} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://control.softlayer.com/){:new_window}。
2. 单击**存储** > **备份**以显示具有备份服务的服务器。
3. 选择要扩展的保险库。
4. 单击**操作**，然后选择**修改 {{site.data.keyword.backup_notm}}**。
5. 在下一个屏幕上，选择新的大小，然后单击**升级**。

## 记帐

对卷的记帐会自动更新，以将新价格的按比例差值添加到当前计费周期。然后，在下一个计费周期中采用整个新金额记帐。

同一过程可以用来减小 {{site.data.keyword.backup_notm}} 的大小。
{:tip}
