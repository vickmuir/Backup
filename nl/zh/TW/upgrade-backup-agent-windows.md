---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, upgrade agent, Windows

subcollection: Backup

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# 升級 Windows 的備份軟體代理程式
{: #UpgradeinWindows}

您可以從 {{site.data.keyword.backup_notm}} 入口網站的「儀表板」快速鏈結區段下載最新的備份代理程式。
{:tip}

1. 從遠端控制需要進行 {{site.data.keyword.backup_notm}} 升級的 {{site.data.keyword.cloud}} 伺服器。
2. 開啟瀏覽器，並移至下列位址。
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
3. 按一下您想要的檔案。（例如，Agent-Windows-x64-6-72-1072a.exe）

   版本號碼在檔名中。請選擇最新的版本。<br/>{{site.data.keyword.cloud}} 提供個別的 32 位元及 64 位元安裝程式。如果您有 64 位元的作業系統，請下載名稱中有 x64 的檔案。
   {:tip}
4. 在下載畫面中按一下**執行**，然後在下載之後再按一次。
5. 按一下**是**，以升級 **{{site.data.keyword.backup_notm}} Software Agent**。

   安裝程式在載入時可能會消失一會兒。
   {:note}
6. 選取**保留我的現行登錄**，然後按**下一步**。
7. 按**下一步**。代理程式會開始升級處理程序。這可能需要一些時間。
8. 在「完成」畫面中，按一下**完成**。
