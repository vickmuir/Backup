---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# 升級 Windows 的備份軟體代理程式

使用這些逐步指示，在 Windows 伺服器上升級 {{site.data.keyword.backup_notm}} 代理程式。

1. 透過 RDP 遠端控制需要 {{site.data.keyword.backup_notm}} 升級的 {{site.data.keyword.BluSoftlayer_full}} 伺服器。
2. 開啟瀏覽器，並移至下列位址。
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
3. 按一下您想要的檔案。（例如，Agent-Windows-x64-6-72-1072a.exe）

   版本號碼在檔名中。請選擇最新的版本。<br/>有個別的 32 位元及 64 位元安裝程式。如果您有 64 位元的作業系統，請下載名稱中有 x64 的檔案。
   {:tip}
4. 在下載畫面中按一下**執行**，然後在下載之後再按一次。
5. 按一下**是**以升級 **EVault Software Agent**。

   安裝程式在載入時可能會消失一會兒。
   {:note}
6. 選取**保留我的現行登錄**，然後按**下一步**。
7. 按**下一步**。代理程式會開始升級處理程序。這可能需要一些時間。
8. 在「完成」畫面中，按一下**完成**。
