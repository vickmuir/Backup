---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-03"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# 安裝 EVault Backup Client for VMware

在 VMware 伺服器上安裝「EVault 備份」用戶端，可透過目標 ESX 伺服器內 Shell 或終端機中的一系列指令來完成。此程序概述在 VMware 伺服器上安裝「EVault 備份」用戶端所需的步驟：

若要安裝「代理程式」，請使用下列指令，下載 `Agent-VMware-ESX-Server-6.71.<version-info>.tar.gz` 套件，並複製至目標「ESX 伺服器」：

`wget -N http://downloads.service.softlayer.com/evault/archive/Agent-VMware-ESX-Server-6.71.2105.tar.gz`

**附註**：您必須在目標「ESX 伺服器」本端執行下列步驟。

1. 從套件解壓縮檔案。若要這麼做，請使用此指令（其中 "PACKAGENAME" 可以是 "Agent-VMware-ESX-Server-6.71"）：
    `tar xvfz PACKAGENAME.tar.gz`
2. 移至您已解壓縮套件的目錄。
3. 執行安裝 Script：
    `# ./install.sh`

    **附註**：安裝 Script 會以互動方式提示您輸入 Web 登錄（位址、埠號及鑑別）和日誌檔名稱之類的配置資訊。
     
    - 輸入此伺服器的 WebCC 使用者名稱。
    - 輸入此伺服器的 WebCC 密碼。
     
4. 輸入 **EVault 備份使用者名稱**，作為要求 WebCC 使用者名稱的提示輸入。 
5. 輸入 **EVault 備份密碼**，作為要求 WebCC 密碼的提示輸入。
6. 安裝完成時，會出現完成訊息，且「代理程式」常駐程式將在執行中。


### 其他安裝注意事項：
如果安裝成功，Install.log 將會出現在安裝目錄中。
例如：`/opt/BUAgent/Install.log`

如果安裝失敗並回復，則安裝日誌將出現在 `<Installation Failure directory>` 中。
如果安裝失敗且未回復，則安裝日誌將出現在 `<Installation Kit directory>` 中。

如需相關資訊，請下載 [VMware_Agent_User_Guide](http://downloads.service.softlayer.com/evault/Documentation/VMware_Agent_User_Guide.pdf){:new_window}。請確定您已連接至 {{site.data.keyword.BluVPN}}，才能檢視此鏈結。
