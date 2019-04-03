---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 安裝 vSphere Recovery Agent
{: #VRA}

vSphere Recovery Agent (VRA) 是一個 Windows 應用程式，可以備份及還原最多 10 TB 的 VMDK。您可以在對要保護的 vCenter 具有本端網路存取權的實體機器或虛擬機器上安裝 vSphere Recovery Agent。若要取得最佳效能，請將 VRA 安裝在與 vCenter 位於相同子網路的機器上。若要配送工作負載，最多可以使用五個 VRA 來保護連接至單一 vCenter 的 VM。

在 vSAN 延伸叢集中，每個 VM 都有偏好的站台。理想狀況下，在每個站台中安裝一個本端 VRA，用來備份該站台的偏好 VM。如果 VM 移至不同的站台（由於維護或故障），備份效能可能會降低但仍可接受。


## 訂購外掛程式
{: #orderingVRAPlugin}

{{site.data.keyword.cloud_notm}} 提供免費的 vSphere Recovery Agent (VRA)。如果您有現行的 {{site.data.keyword.backup_notm}} 訂閱，則可以從 {{site.data.keyword.backup_notm}} 入口網站下載外掛程式。

## 安裝外掛程式
{: #installVRAPlugin}

確定在安裝 VRA 的伺服器上已停用電源管理。
{: important}

1. 從 `http://downloads.service.softlayer.com/evault/` 下載安裝套件。然後，按兩下此安裝套件。
2. 在確認訊息上，按一下**是**。
3. 在歡迎使用頁面上，按**下一步**。
4. 在「一般使用者授權合約」頁面上，閱讀授權合約。如果您同意這些條款，請按一下**我接受授權合約的條款**，然後按**下一步**。
5. 在「目的地資料夾」頁面上，執行下列其中一個動作。
   * 若要在預設位置安裝 VRA，請按**下一步**。
   * 若要在其他位置安裝 VRA，請按一下**變更**。在「變更目的地資料夾」對話框中，瀏覽至新的安裝資料夾，或在「資料夾名稱」方框中鍵入。按一下**確定**。在「目的地資料夾」頁面上，按**下一步**。
6. 在「使用入口網站登錄代理程式」頁面上，指定下列資訊。
   * 在**網址**欄位中，鍵入 `ev-webcc01.service.softlayer.com`。
   * 在**埠**欄位中，鍵入 `8086`。
   * 在**使用者名稱**欄位中，鍵入用來管理 VRA 的 {{site.data.keyword.backup_notm}} 使用者名稱。
   * 在**密碼**欄位中，鍵入指定的 {{site.data.keyword.backup_notm}} 使用者的密碼。
7.	按**下一步**。安裝完成後，請按一下**完成**。

## 配置 vSphere Recovery Agent
{: #configureVRA}

在安裝 VRA 之後，您需要在 {{site.data.keyword.backup_notm}} 入口網站中進行配置。

1. 登入 {{site.data.keyword.backup_notm}} 入口網站。如需如何存取 {{site.data.keyword.backup_notm}} 入口網站的相關資訊，請參閱[入門指導教學](/docs/infrastructure/Backup?topic=Backup-gettingstarted#getting-started#accessingWebCC)。
2. 在「電腦」標籤上，選取您要備份的伺服器。
3. 配置您的儲存庫資訊。

   可以利用以下兩種方式配置儲存庫資訊：**自動**或**手動**。<br/>如果代理程式是第一次進行配置，則可以使用[自動配置](#VRAautoconfig)選項予以配置。<br/>如果電腦先前已登錄「儲存庫」，則自動配置無法運作，儲存庫需要[手動配置](#VRAmanualconfig)。
   {: tip}

4. 配置 [vCenter 設定](#vCenterSettingsconfig)   

### 自動配置儲存庫
{: #VRAautoconfig}

若要自動配置儲存庫設定，請按一下**自動配置**。「配置精靈」即會執行，並為您配置「儲存庫設定」。當它完成時，請按一下**移至代理程式**，以驗證**儲存庫設定**標籤中的資訊。
 

### 手動配置儲存庫
{: #VRAmanualconfig}

若要手動配置儲存庫設定，請按一下**手動配置**。   
1. 按一下**儲存庫設定**。
2. 按一下**新增儲存庫**。即會出現「儲存庫設定」視窗。從**儲存庫設定檔**選項中，選取適當的儲存庫。
   如果電腦先前已登錄 {{site.data.keyword.backup_notm}} 儲存庫，則從「儲存庫設定檔」中選取「儲存庫」時，會自動移入所有資訊。
{:note}

3. 驗證「儲存庫設定」頁面中的所有資訊，然後按一下**儲存**。
4. 當您儲存儲存庫設定時，即可在**儲存庫設定**標籤中看見儲存庫資訊。


### 配置 vCenter 代理程式設定
{: #vCenterSettingsconfig}
順利完成儲存庫登錄之後，您必須先配置「vCenter 設定」，才能建立及執行任何備份工作。

1. 按一下 **vCenter 設定**標籤。
2. 提供 vCenter IP 位址、網域名稱及您要保護的 vCenter 認證。
   使用者必須具有 vCenter 的管理存取權，才能順利執行這項作業。
   {:note}

3. 藉由移除勾號來停用 Change Block Tracking (CBT)。CBT 是一項 VMware 特性，用於追蹤變更的磁碟磁區並改善 VM 備份效能，它是由 vSphere 代理程式自動啟用。
4. 按一下**測試 vCenter 連線**。新視窗會顯示結果。如果提供的登入資訊正確無誤，即會出現「vCenter 認證已順利驗證」訊息。
5. 按一下**儲存**，以儲存設定。

## 後續步驟
{: #VRAnextteps}
1. [配置、排程及執行備份工作](/docs/infrastructure/Backup?topic=Backup-ConfigureVRA#VConfigureVRA)
2. [還原 vSphere 資料](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore)

使用 {{site.data.keyword.BluVPN}} 連接至 {{site.data.keyword.BluSoftlayer_full}} 網路，以便您可以從 [Downloadable {{site.data.keyword.backup_notm}} Documentation ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window} 存取及下載使用手冊。
{:tip}
