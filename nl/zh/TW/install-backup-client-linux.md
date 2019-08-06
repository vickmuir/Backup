---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud backup, EVault, Carbonite, backup, install agent, Linux

subcollection: Backup

---
{:codeblock: .codeblock}
{:pre: .pre}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 在 Linux 中安裝備份用戶端
{: #InstallinLinux}

在 Linux 型作業系統上安裝 {{site.data.keyword.backup_full}} 用戶端，可透過作業系統內 Shell 或終端機中的一系列指令來完成。此程序概述在下列任何作業系統上安裝用戶端所需的步驟：

- RHEL
- CentOS
- CloudLinux

在完成此程序之後，自動化處理程序會向 {{site.data.keyword.backup_notm}} 入口網站登錄「代理程式」服務，然後下載並安裝執行該服務所需的檔案。

當您透過 [{{site.data.keyword.cloud_notm}} 型錄](https://{DomainName}/catalog){: external}或 {{site.data.keyword.cloud_notm}} 主控台訂購伺服器時，如果您已購買 {{site.data.keyword.backup_notm}}，則會自動為您安裝軟體。您不需要使用本文件所述的程序。
{:tip}

如果已在 {{site.data.keyword.cloud_notm}} 主控台以升級方式購買了 {{site.data.keyword.backup_notm}}，請遵循下列步驟來安裝軟體。

## 登入目標裝置伺服器
{: #logintargetLin}

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}){: external}。從「導覽功能表」中，選取**標準基礎架構**。
2. 從主功能表選取**裝置** > **裝置清單**，以查看可用伺服器裝置的清單。
3. 找出您已為其購買 {{site.data.keyword.backup_notm}} 服務的裝置，並記下其公用 IP 位址。
  - 此 IP 位址要在從指令行登入裝置時使用。在步驟 5 顯示的指令中，將 <publicIpAddress> 取代為實際公用 IP 位址。
4. 按一下箭頭來顯示裝置的相關資訊，包括使用者名稱及密碼。
  - 如果未顯示密碼，則按一下**顯示密碼**即可顯示密碼。在下一步中，使用者名稱和密碼會用來登入測試裝置。將 `<user name>` 取代為實際使用者名稱。
5. 從指令行輸入下列指令，以登入目標裝置。
   ```
   ssh <user name>@<publicIpAddress>
   ```
   {: pre}

   如果您之前未使用此使用者名稱登入此伺服器，則會看到關於主機確實性的訊息。系統也會詢問您是否要繼續。回覆**是**以繼續。
   {:note}

6. 除非您先前已設定 SSH 金鑰來存取此伺服器，否則系統會提示您輸入密碼。

## 更新 OS 以準備進行安裝（僅適用 RHEL）

這是 RHEL 的必要步驟，但對於其他發行套件則是選用步驟。
{:tip}

- 在伺服器提示處執行下列指令。
  ```
  yum update
  ```
  {: pre}

  如果系統提示您，請確認下載大小沒問題。更新會繼續，並在完成時顯示「完成」訊息。

## 取得安裝 Script

- 在伺服器提示處執行下列指令。
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}

## 執行安裝 Script

1. 在伺服器提示處執行下列指令。
   ```
   sh ./evault_manual.sh
   ```
   {: pre}

2. 輸入您的 {{site.data.keyword.backup_notm}} 入口網站使用者名稱和密碼。

   如需檢視 {{site.data.keyword.backup_notm}} 使用者名稱及密碼的相關資訊，請參閱[開始使用備份服務](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)。
   {:tip}

3. 在使用者名稱和密碼之後，不需要再進行任何輸入。隨著安裝繼續進行而寫入畫面的提示都可以放心略過。

   它們是由 `evault_manual.sh` Script 所啟動的子 Script 所產生。`evault_manual.sh` Script 會提供這些提示的輸入。
   {:note}

4. 出現下列訊息時，即表示安裝完成。

   ```
   Starting VVAgent: [  OK  ]
   Starting buagent: [  OK  ]
  ```
   {: codeblock}

## 驗證安裝成功

1. 確認 `Registered to The Portal` 訊息已出現在安裝輸出中。在畫面上尋找此訊息，或檢查下列指令的輸出，都可以進行驗證。
   ```
   grep 'Registered'  /opt/BUAgent/Install.log
   ```
   {: pre}

2. 執行下列指令並觀察輸出。
   ```
   service vvagent status
   ```
   {: pre}

   即會顯示下列訊息。
   ```
   VVAgent is running (PID xxxxx).
   buagent is running (PID xxxxx).
  ```
   {: codeblock}

  以 `xxxxx` 表示的處理程序 ID 會隨每個安裝而不同。
{:tip}

**後續步驟**

登入 {{site.data.keyword.backup_notm}} 入口網站，以配置及管理您的備份代理程式。如需相關資訊，請參閱[入門指導教學](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)和[在 Linux 上配置簡單的檔案層次備份](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup)。
