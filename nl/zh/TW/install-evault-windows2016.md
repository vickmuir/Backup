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

目前，Windows 2016 並未正式支援 EVault WebCC。在 Windows 2016 執行的伺服器必須使用「Windows 中央控制」軟體。

## 安裝 EVault 備份代理程式

1. 在目標伺服器上，開啟瀏覽器階段作業，並輸入下列 URL，以下載執行檔。
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
2. 按兩下已下載的檔案，然後在出現的蹦現方框中按一下**執行**。
3. 選取安裝的語言，然後按一下**確定**。
4. 選取**一般**作為「設定類型」。按**下一步**。
5. 在「使用入口網站登錄代理程式」畫面中，選取**跳過登錄**。 
6. 按**下一步**，然後按一下**完成**。

## 安裝 EVault Software CentralControl

1. 在目標伺服器上，開啟瀏覽器階段作業，並輸入下列 URL，以下載執行檔。

   ```
   http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. 按兩下已下載的檔案，然後在出現的蹦現方框中按一下**執行**。
3. 遵循「一般」設定的安裝步驟。

## 配置 CentralControl

此作業是在登入針對 EVault 備份服務指定的伺服器時，透過一系列互動來完成。

1. 透過 RDP 遠端控制您的伺服器。
2. 啟動 CentralControl。
3. 在工作區中，用滑鼠右鍵按一下**代理程式**，並選取**代理程式配置**
4. 按一下**新建**。
5. 選取**登錄為新電腦**，然後按**下一步**。
6. 輸入網址並按一下**新增**，然後按**下一步**。
7. 輸入新埠值並按一下**新增**，然後按**下一步**。
8. 在「連線設定」畫面中，輸入您想要的秒數/分鐘數。 
9. 在「鑑別」畫面中，輸入您的認證並按**下一步**。
10. 「已登錄的電腦」視窗會顯示伺服器的主機名稱。按**下一步**。
11.	「儲存庫配置精靈」已完成收集您的資訊，按一下**完成**來完成登錄。


