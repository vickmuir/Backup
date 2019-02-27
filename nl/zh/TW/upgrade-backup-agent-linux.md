---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# 升級 Linux 的備份軟體代理程式
{: #UpgradeinLinux}

您可以從 {{site.data.keyword.backup_notm}} 入口網站的「儀表板」快速鏈結區段下載最新的備份代理程式。
{:tip}

遵循升級程序可確保您能夠將 {{site.data.keyword.backup_notm}} 代理程式升級，而不會遺失登錄資料 

1. 在根層次登入主機。
2. 下載最新版代理程式。
   ```
   wget -N downloads.service.softlayer.com/evault/Agent-Linux-x64-8.11.5251.tar.gz2
   ```
   {:pre}

3. 將下載檔案的內容解壓縮。

   ```
   tar -xzvf Agent-Linux-x64-8.11.5251.tar.gz3
   ```
4. 移至最近的安裝目錄。
   ```
   cd Agent-Linux-x64-8.11.5251/4
   ```

5. 執行安裝 Script。
   ```
   ./install.sh
   ```
   {:pre}

6. 依系統提示，選取您的語言；選取 `N`，表示不將電腦登錄為新主機；然後選取 `A`，以使用整合的加密方法來加密資料。

7. 如果安裝成功，則會記錄在 `/opt/BUAgent/Install.log` 中。
