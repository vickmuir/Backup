---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-10"

keywords: IBM Cloud backup, EVault, Carbonite, backup, reregister

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}

# 重新登錄儲存庫
{: #reregister}

重新載入伺服器的「作業系統」之後，最常使用此作業。您也可以使用下列步驟，[使用某部伺服器的備份，在另一部伺服器上還原資料](/docs/infrastructure/Backup?topic=Backup-restorefromotherVSI)。
{:tip}

1. 啟動 {{site.data.keyword.backup_notm}} 入口網站並登入。如需相關資訊，請參閱[入門指導教學](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)。

   請記得，只能透過 {{site.data.keyword.BluVPN}} 來存取 {{site.data.keyword.backup_notm}} 入口網站。
   {:tip}
2. 在左邊，按一下**所有代理程式**。
3. 在右上角，將滑鼠移至**編輯**上方。
4. 選取**儲存庫設定**。
5. 按一下**重新登錄**。
6. 完成表單。
  - 儲存庫名稱。
  - 儲存庫位址。
  - 帳戶。

    「帳戶」等同於 [{{site.data.keyword.cloud_notm}} 主控台](https://{DomainName}/classic/storage/backup){: external}中的「帳戶名稱」。通常，它看起來像是 "SLE[account ID]"
    {:tip}
  - 使用者名稱。
  - 密碼
7. 按一下**載入電腦**，然後選取您要載入的電腦。
8. 按一下**儲存變更**。
9. 重新整理網站，以還原先前的備份工作。
10. 同步化每一個備份工作，以還原安全集歷程。
11. 如果備份工作是使用加密密碼所建立，則您必須輸入加密密碼，才能還原資料或繼續備份。
12. 按一下**關閉**。
