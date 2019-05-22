---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup,  EVault, Carbonite, backup, restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 還原 BMR 系統磁區映像檔
{: #restoreBMR}

如果需要從 {{site.data.keyword.backup_full}} 還原「裸機伺服器」映像檔備份，您可以從 BMR Rescue Kernel 系統快速還原它。使用 BMR，您可以在不需要可開機作業系統的情況下還原系統。如果作業系統無法再使用，或已更換系統中的磁碟機，則這十分有用。

## 起始 BMR Rescue Kernel 系統

您可以透過 {{site.data.keyword.slportal}} 存取 BMR Rescue Kernel 系統。
1. 登入 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}){: external}，然後按一下左上角的**功能表**圖示。選取**標準基礎架構**。<br/>
      或者，您也可以登入 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}。
2. 按一下**儲存空間** > **備份**以顯示具有備份服務的伺服器。
3. 按一下儲存庫旁邊的**箭頭**。
4. 按一下**起始 Bare Metal Restore**。這個動作會啟動需要幾分鐘才能完成的交易。之後您就可以遵循這裡詳述的步驟來存取伺服器。當系統完成開機處理程序時，將會傳送電子郵件給您。


## 從 BMR Rescue Kernel 還原

1. 載入 BMR Rescue Kernel 交易時，您可以選擇以兩種不同的方式來存取它。
  - VNC 用戶端及伺服器的專用或公用 IP 位址，以及 {{site.data.keyword.slportal}} 中列出的密碼
  - IPMI 卡的 KVM 主控台。
  這兩種方式都可正常運作。
2. 第一次登入 BMR Rescue Kernel 時，會為您顯示語言選取畫面。選取您選擇的語言，然後按**下一步**。
<br/>![圖 1 - BMR 語言選項](/images/bmr1.png)<br/> 即會顯示軟體的授權合約。
3. 如果您接受條款，請選取勾選框，然後按**下一步**繼續。<br/> 即會呈現主要 {{site.data.keyword.backup_notm}} 系統還原功能表。
4. 選取**還原我的系統**。
<br/>![圖 2 - BMR 主功能表](/images/bmr2.png)
5. 系統還原精靈即會出現。選取**下一步**繼續。
<br/>![圖 3 - BMR 精靈](/images/bmr3.png)
6. 選取要從中還原的備份類型。選取 **EVault 軟體**，然後按**下一步**繼續。
7. 在**備份位置**畫面上，選取儲存庫，並輸入儲存庫位址、帳戶號碼、使用者名稱和密碼。然後，按**下一步**繼續。
<br/>![圖 4 - 選擇備份位置](/images/bmr4.png)
8. 下一個畫面會將您的系統顯示在清單中。請確定已強調顯示它，然後按**下一步**。
<br/>![圖 5 - 選擇您的系統](/images/bmr5.png)
9. 在**備份工作選取**畫面上，選取您要從中還原的「工作」，然後按**下一步**。
<br/>![圖 6 - 選擇您的還原點](/images/bmr6.png)
10. 從**選取還原點**功能表中，選取您要的還原點，然後按**下一步**。
<br/>![圖 8 - 選擇還原點](/images/bmr8.png)
11. 選取來源和目的地磁區。若要將來源還原至目的地，請將來源磁區拖曳至目的地磁區。
<br/>![圖 9 - 選取來源及目的地磁區](/images/bmr9.png)
12. 在格式化或合併資料確認框上，您可以從兩個選項進行選取。選取**格式化**，以進行格式化磁碟的全新還原。如果您要合併目的地磁區上的資料，請選取**合併**。
<br/>![圖 10 - 選擇合併](/images/bmr10.png)
13. 在主要來源及目的地磁區畫面上，按**下一步**。
14. 在還原計劃摘要畫面上，勾選方框以接受計劃，然後按**下一步**。
<br/>![圖 11 - 啟動還原](/images/bmr11.png)
15. 還原進度畫面即會出現，且會在還原發生時顯示其進度。
<br/>![圖 12 - 還原進度](/images/bmr12.png)
16. 完成時，您會收到通知視窗，指出還原已順利完成。按一下**確定**。
17. 在還原進度畫面上，按**下一步**。
18. 在最後一個畫面上，勾選重新啟動系統的方框，然後選取**完成**，伺服器就會載入已還原的磁區映像檔。還原現在已完成。<br/>

  伺服器第一次重新啟動時，您可能會看到非預期的關機訊息。對於此備份類型，這是正常情況，而且在第一次開機之後就會消失。
  {:tip}
