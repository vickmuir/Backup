---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:faq: data-hd-content-type='faq'}


# 常见问题

## 可以备份哪类应用程序？
{: faq}

{{site.data.keyword.backup_full}} 可用于对各种应用程序进行备份。但是，{{site.data.keyword.BluSoftlayer_full}} 提供了若干软件代理程序，可用于要备份的某些更常见的软件系统，其中包括：

- Bare Metal Restore
- Microsoft Exchange
- Microsoft SQL
- Oracle

此处列出的插件仅与 Windows 服务器兼容，但 Oracle 插件除外。每个代理程序都作为备份服务的附加组件提供。要将代理程序添加到服务中，请立即联系销售团队的成员。

<hr>

## 备份数据的频率如何？
{: faq}

在 WebCC 中，可以手动进行备份，也可以将备份安排为单个实例备份或周期性备份。周期性备份可以每天、每周、每月或按定制安排执行，并且可以随时更新或取消。

每天或每小时多次运行的高频率备份可能会导致备份作业损坏。发生损坏的原因是备份保险库运行所需后台维护任务的时间不足。备份作业优先于维护任务。因此，在高度频繁备份的情况下，保险库会继续运行备份作业，而导致安全集数量不断增加。
{:note}

<hr>

## 保留方案如何工作？
{: faq}

{{site.data.keyword.backup_notm}} 支持保留数据，具体保留时间取决于您希望回滚多长时间。**每日**保留方案会将数据保留 7 天，**每周**方案将数据保留 1 个月，**每月**方案将数据保留 1 年。在每个周期结束时，最旧的数据集会被淘汰，所执行的第一个“增量备份”会变成最旧的可用复原点。

您可以修改缺省保留方案，也可以创建定制保留方案。但是，强烈建议使用缺省保留作为起始点。创建新的保留方案或修改现有保留时，确保未选中“归档”选项。不支持归档。
{:tip}

<hr>

## 什么是增量技术？
{: faq}

第一个备份是“种子”（完整的完全备份），接下来的后续备份是“增量”（即，仅备份更改），但增量备份等效于且仍被视为“完全备份”。也就是说，您可以从增量备份复原全部或任意文件。此技术支持对每个会话执行“完全备份”，但可节省保险库中的大量空间，并缩短完成每个后续备份所需的时间量。

<hr>

## 备份安全吗？
{: faq}

缺省情况下，所有线上 (OTW) 加密都使用 AES 256 位加密进行加密。您还可以选择使用 AES 256 位的加密格式存储数据。

您必须记住加密密码。没有密码就无法复原数据。如果丢失了密码，将无法恢复数据。
{:important}

压缩比率支持执行零压缩到最大比率压缩；根据文件类型，最大比率压缩可实现 20% 到 30% 范围内的任意压缩比率。


<hr>

## 系统状态备份中存储哪些信息？
{: faq}

系统状态备份包括但不限于 COM + 类注册数据库、注册表、引导文件、系统文件和性能计数器。这完全取决于您的系统。系统文件因系统操作系统和 service pack 而有所不同。通常有数千个系统文件。在备份中包含这些 DLL 时，MS Windows 将生成这些 DLL 的动态列表。通过包含系统文件，可以恢复损坏的系统文件，也适用于意外卸载了某些 service pack，或希望通过裸机复原进行恢复的情况。可以恢复到备份状态，而不必从安装工具包重新安装操作系统，然后分别安装每个 service pack。

系统状态备份中不包含用户数据文件。必须将系统状态备份作业配置为独立作业。“系统状态”备份作业中不能包含其他任何数据源
{:important}

<hr>

## 开放文件有什么变化？
{: faq}

缺省情况下，基本客户机采用最先进的技术来处理操作系统上运行的大多数开放文件。

<hr>

## 何处可找到有关定价的信息？
{: faq}

有关更多信息，请参阅 [Backup storage](https://www.ibm.com/cloud/backup-and-restore){:new_window} 和 [{{site.data.keyword.backup_notm}} on IBM Cloud: Pricing](https://www.ibm.com/cloud/evault/pricing){:new_window}。

<hr>

## 是否可以在不影响备份的情况下增大或减小 {{site.data.keyword.backup_notm}} 容量？
{: faq}

可以通过 [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} 来增大或减小保险库的大小。对容量的修改不会影响保险库中存储的数据的完整性。有关更多信息，请参阅[扩展容量](expanding-capacity.html)。

<hr>

## 超过了 {{site.data.keyword.backup_notm}} 容量时会发生什么情况？
{: faq}

即使已达到您先前购买的容量的限制，也仍可保存和检索备份。但请注意，需要对计费结算表中使用的每个额外 GB 支付额外的费用。

<hr>

## 如何在 WebCC 中设置通知以便了解我的备份是否失败？
{: faq}

可以在“高级”选项卡上设置通知。请按照**快速链接**中的指示信息在 WebCC 中执行操作。
