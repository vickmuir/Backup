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

# 在 Linux 中安裝 EVault 備份用戶端 

在 Linux 型作業系統上安裝 EVault 備份用戶端，可透過作業系統內 Shell 或終端機中的一系列指令來完成。此程序概述在下列任何 Linux 型作業系統上安裝 EVault 備份用戶端所需的步驟：

- RedHat Enterprise Linux
- CentOS
- CloudLinux

在完成此程序之後，自動化程序會利用 WebCC 登錄「代理程式」服務，然後下載並安裝執行該服務所需的檔案。請遵循下列步驟，將「EVault 備份」用戶端安裝至您的 Linux 型作業系統。

**附註**：當您在 {{site.data.keyword.slportal}} 中訂購伺服器時，如果您購買了 EVault，則會自動為您安裝軟體，因此您不需要使用本文件所說明的程序。

如果已在 {{site.data.keyword.slportal}} 以升級方式購買了 EVault，請遵循下列步驟來安裝軟體。

## 登入目標裝置伺服器

1. 登入 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}，並從主功能表中選取**裝置** > **裝置清單**，以查看可用伺服器裝置的清單。
2. 找出您已為其購買 EVault 服務的裝置，並記下其公用 IP 位址。從 UNIX 或 Linux 指令行登入裝置時，將在下列步驟使用此位址。將 <publicIpAddress> 取代為後續指令中的實際公用 IP 位址。 
3. 按一下向右展開箭頭來顯示裝置的其他相關資訊，包括使用者名稱及密碼。如果未顯示密碼，則按一下**顯示密碼**勾選框會顯示密碼。在下一步中，使用者名稱和密碼將用來登入測試裝置。將 `<user name>` 取代為後續指令中的實際使用者名稱。
4. 從 UNIX 或 Linux 指令行執行下列指令，以使用 SSH 登入目標裝置：
  ```
  ssh <user name>@<publicIpAddress>
  ```
  {: pre}
  
 **附註**：如果您之前未使用此使用者名稱登入此伺服器，則會呈現關於主機確實性的訊息，而且系統會詢問您是否要繼續。回覆**是**以繼續。
5. 除非您先前已設定 SSH 金鑰來存取此伺服器，否則系統會提示您輸入密碼。

## 更新 Linux 以準備安裝 EVault 用戶端（僅限 RedHat Linux）
**附註**：RedHat Linux 需要此步驟，但其他 Linux 發行套件則為選用。

- 在伺服器提示處執行下列指令：
  ```
  yum update
  ```
  {: pre}
   
  如果要求，請確認下載大小沒問題。更新將繼續，並在完成時顯示「完成！」訊息。

## 取得 EVault 安裝 Script
- 在伺服器提示處執行下列指令：
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}
   
## 執行 EVault 安裝 Script
1. 在伺服器提示處執行下列指令：
  ```
  sh ./evault_manual.sh
  ```
  {: pre}

2. 輸入您的 WebCC 使用者名稱和密碼。     
  **附註**：如需檢視 EVultabackup 使用者名稱及密碼的指示，請參閱[開始使用備份服務](/docs/infrastructure/Backup/index.html)一文。
3. 在使用者名稱及密碼之後，不需要任何進一步輸入，即使您在安裝進行時看到部分提示寫入至畫面也一樣。您可以安心地忽略這些提示。它們是由 *evault_manual.sh* Script 所呼叫之子 Script 所產生的。*evault_manual.sh* Script 提供這些提示的輸入。
4. 當如下的訊息出現時，表示安裝完成：
  ```
  Starting VVAgent: [  OK  ]
  Starting buagent: [  OK  ]
  ```
  {: codeblock}
   
## 驗證安裝是否成功
1. 驗證「已登錄至入口網站。」訊息是否出現在安裝輸出中。作法是在畫面上尋找此訊息，或檢查下列指令的輸出：
  ```
  grep 'Registered'  /opt/BUAgent/Install.log
  ```
  {: pre}

2. 執行下列指令並觀察輸出： 
  ```
  service vvagent status
  ```
  {: pre}
   
  應該顯示下列訊息：
  ```
  VVAgent is running (PID xxxxx).
  buagent is running (PID xxxxx).
  ```
  {: codeblock}
   
  **附註**：上方以 'xxxxx' 表示的程序 ID 將隨著每一個安裝而改變。 
  
## 後續步驟

登入 WebCC 以配置及管理您的備份代理程式。如需指示，請參閱[入門指導教學](index.html#configuring-evault-agent-in-webcc)。
