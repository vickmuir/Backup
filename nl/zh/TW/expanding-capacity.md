---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, expanding vault

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}


# 擴充儲存庫容量
{: #expandcapacity}

現行 {{site.data.keyword.BluSoftlayer_full}} 使用者可以將其儲存庫的大小擴充到最多 4000 GB。他們不需要建立重複項目，或手動將資料移轉至較大的磁區。提高限制的程序不會導致任何運作中斷或缺少存取權的情況。

## 訂購增加

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}){:new_window}，然後按一下左上方的**功能表**圖示。選取**標準基礎架構**。<br/>
      或者，您也可以登入 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}。
2. 按一下**儲存空間** > **備份**以顯示具有備份服務的伺服器。
3. 選取您要擴充的儲存庫。
4. 按一下**動作**，然後選取**修改 {{site.data.keyword.backup_notm}}**。
5. 在下一個畫面中，選取新的大小，然後按一下**升級**。

## 計費

會自動更新磁區的計費，以將新價格的按比例差額新增至現行計費週期。然後，在下一個計費週期中收取完整的新金額。

您可以使用相同的處理程序來降級 {{site.data.keyword.backup_notm}}。
{:tip}
