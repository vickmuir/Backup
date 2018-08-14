---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-26"

---
{:pre: .pre}
{:new_window: target="_blank"}

# 在 Windows 中安裝 EVault 備份用戶端

在 Windows 中安裝 EVault 備份用戶端，是在針對 EVault 備份服務指定的伺服器上透過一系列互動來完成。

**附註**：目前不支援 Windows 2016。請參閱 [Windows 2016](install-evault-windows2016.html) 的指示。

## 登入目標裝置伺服器

1. 登入 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}，從主功能表中選取**裝置** > **裝置清單**，以查看可用伺服器的清單。
2. 找出您已為其購買 EVault 服務的裝置，並記下其公用 IP 位址。
3. 按一下指向右方的箭頭來展開並顯示裝置的相關資訊，包括使用者名稱和密碼。如果未顯示密碼，則按一下**顯示密碼**即會顯示密碼。 
4. 使用「遠端桌面連線」登入目標裝置。

## 下載 EVault 用戶端

1. 在目標伺服器上，開啟瀏覽器階段作業，並輸入下列 URL，以下載 EVault 備份用戶端的執行檔。<br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}
  
2. 按兩下已下載的檔案。
3. 按一下**執行**。


## 安裝及登錄 EVault 代理程式
 
1. 輸入網址：<br />
  ```
  ev-webcc01.service.softlayer.com
  ```
  {: pre}
  
2. 在**使用者名稱**欄位中，輸入 EVault 使用者名稱。 
3. 在**密碼**欄位中，輸入 EVault 密碼。 
6. 按**下一步**。 
7. 按一下**安裝**來完成安裝。

## 配置備份代理程式

登入 WebCC，以配置及管理您的備份代理程式。如需指示，請參閱[入門指導教學](index.html#configuring-evault-agent-in-webcc)。
