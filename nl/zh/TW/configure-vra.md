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

# 配置 VRA 備份工作
{: #ConfigureVRA}

在 {{site.data.keyword.backup_notm}} 入口網站中新增 VMware vSphere 環境之後，您可以建立一個備份工作，用來指定要備份的虛擬機器 (VM)，以及備份資料的儲存位置。若要備份資料，您可以手動執行備份工作或排定要執行的備份工作。

您必須先配置儲存庫設定和 vCenter 資訊，才能新增一個備份工作。
{:important}

## 啟動 {{site.data.keyword.backup_notm}} 入口網站
{: #startWebCCVRA}

您需要連接至 {{site.data.keyword.BluSoftlayer_full}} 專用網路，才能啟動 {{site.data.keyword.backup_notm}} 入口網站。
{:important}

1. 登入 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}/){:new_window}，然後按一下左上角的**功能表**圖示。選取**標準基礎架構**。<br/>
   或者，您也可以登入 [{{site.data.keyword.slportal}} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://control.softlayer.com/){:new_window}。
2. 按一下**儲存空間** > **備份**，以顯示具有備份服務的伺服器。
3. 選取要備份之檔案所在的伺服器。按一下指向右方的展開箭頭，以顯示 {{site.data.keyword.backup_notm}} 入口網站鏈結。
4. 按一下 **{{site.data.keyword.backup_notm}} 入口網站登入**，以在瀏覽器中啟動入口網站用戶端。

   如果 {{site.data.keyword.backup_notm}} 入口網站未啟動，可能是 VPN 連線有問題。您可能也會看到一則訊息，指出您傳送的表單不安全。這是預期的情況 - 請傳送表單來繼續進行。
   {:tip}

## 新增 vSphere 備份工作

1. 在導覽列上，按一下**電腦**。電腦頁面會顯示已登錄的電腦和環境。
2. 按一下**工作**。
3. 在「選取工作作業」功能表中，按一下**建立新的 VMware vCenter 工作**。
4. 指定下列資訊。
   * 在**名稱**欄位中，為備份工作鍵入一個名稱。
   * 在**說明**欄位中，選擇性地為備份工作鍵入說明。
   * 在**目的地**清單中，選取您要在其中儲存備份資料的儲存庫。
   * 在**密碼**和**確認密碼**欄位中，鍵入加密密碼。您也可以在「密碼提示」欄位中鍵入密碼提示。
   只有在儲存庫已指派給使用者，或是使用者已將它新增至電腦的「儲存庫設定」中時，儲存庫才會出現在清單中。<br/>
   對於新的備份工作，加密方法是 AES 256 位元。現有工作可能使用其他加密方法。
   {:note}

5.	在**包括在備份中**欄位中，執行下列一個以上步驟，直到「備份集」欄位顯示您要包括在備份工作中的 VM 為止。

   * 若要將特定 VM 新增至備份工作，請選取每個 VM，然後按一下**包括**。
   * 若要從備份工作中排除特定 VM，請選取每個 VM，然後按一下**排除**。
   * 若要依據名稱將 VM 新增至備份工作，請檢查「虛擬機器」方框，然後按一下**包括**。
   * 若要從「備份集」方框中移除併入或排除的記錄，請按一下記錄旁的**刪除**。

6. 如果需要套用變更，請按一下**立即套用**，以合併並簡化「備份集」方框中的記錄。
7. 按一下**建立工作**。

## 設定排程

在建立備份工作之後，您可以新增一個以上排程，以自動執行工作。

1. 按一下**建立工作**之後，「排程」視窗即會出現，並提供一個選項用來設定備份工作的自訂排程。

   依預設，會針對工作選取「每日」保留。您可以在此視窗中變更「保留」和「工作」排程，還可以為備份工作指派多個「保留」方案。
   {:note}
2. 按一下**儲存**，以儲存新的排程。新的工作即會顯示在「工作」區段的「電腦」標籤下。「上一個備份狀態」顯示工作從未執行。排定的備份工作會在排定的時間自動執行。

## 執行排定的工作

排定的備份工作也可以立即執行。

1. 按一下**選取動作**，然後選取**執行工作**。「執行工作」視窗即會出現，並提供已指派給工作之「目的地儲存庫」和「保留方案」的相關資訊。

   如果已將多個儲存庫和保留方案指派給工作，則可以按一下「執行工作」視窗中的「目的地」和「保留方案」功能表選項來變更這些選項。
   {:note}
2. 按一下**開始備份工作**，立即執行備份工作。進度視窗會顯示備份工作的狀態，當工作完成時，工作狀態會從「從未執行」變更為「已完成」。

若要查看執行的上一個備份工作的狀態，請按一下「工作」標籤。您可以從動作功能表存取所有工作日誌。按一下**動作**，然後選取**歷程/日誌**。
{:tip}

如需還原 VM 或檔案和資料夾的相關資訊，請參閱[還原 vSphere 資料](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore)。
