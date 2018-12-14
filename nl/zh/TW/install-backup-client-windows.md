---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 在 Windows 中安裝備份用戶端

在 Windows 中安裝 {{site.data.keyword.backup_full}} 用戶端，是在針對 {{site.data.keyword.backup_notm}} 服務指定的伺服器上透過一系列互動來完成。

如需 Windows 2016 伺服器備份的相關資訊，請參閱[在 Windows 2016 上配置 {{site.data.keyword.backup_notm}}](install-backup-client-windows2016.html)。
{:tip}

## 登入目標裝置伺服器

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}/catalog/){:new_window}，然後按一下左上角的**功能表**圖示。選取**標準基礎架構**。

   或者，您也可以登入 [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}。
2. 從主功能表選取**裝置** > **裝置清單**，以查看可用伺服器裝置的清單。
3. 找出您已為其購買 {{site.data.keyword.backup_notm}} 服務的裝置，並記下其公用 IP 位址。
4. 按一下指向右方的箭頭來展開並顯示裝置的相關資訊，包括使用者名稱和密碼。如果未顯示密碼，則按一下**顯示密碼**即會顯示密碼。
5. 使用「遠端桌面連線」登入目標裝置。

## 下載備份用戶端

1. 在目標伺服器上，開啟瀏覽器階段作業，並輸入下列 URL，以下載 {{site.data.keyword.backup_notm}} 用戶端的執行檔。<br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}

2. 按兩下已下載的檔案。
3. 按一下**執行**。


## 安裝及登錄備份代理程式

1. 輸入網址：<br />
  ```
  ev-webcc01.service.softlayer.com
  ```
  {: pre}

2. 在**使用者名稱**欄位中，輸入使用者名稱。
3. 在**密碼**欄位中，輸入密碼。
6. 按**下一步**。
7. 按一下**安裝**來完成安裝。

## 配置備份代理程式

登入 WebCC，以配置及管理您的備份代理程式。如需相關資訊，請參閱[入門指導教學](index.html#configuring-the-backup-agent-in-webcc)。
