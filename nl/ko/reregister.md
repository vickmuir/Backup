---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, reregister

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# 저장소 재등록
{: #reregister}

이 태스크는 일반적으로 서버의 운영 체제가 다시 로드된 후에 사용됩니다. 또한 다음 단계를 사용하여 [한 서버의 백업으로 다른 서버에서 데이터를 복원](/docs/infrastructure/Backup?topic=Backup-restorefromotherVSI)할 수도 있습니다.
{:tip}

1. {{site.data.keyword.backup_notm}} 포털을 시작하고 로그인하십시오. 자세한 정보는 [시작하기 튜토리얼](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)을 참조하십시오.

   {{site.data.keyword.backup_notm}} 포털은 {{site.data.keyword.BluVPN}}을 통해서만 액세스가 가능하다는 점을 기억하십시오.
   {:tip}
2. 왼쪽에서 **모든 에이전트**를 클릭하십시오.
3. 오른쪽 상단에서 **편집** 위에 마우스 커서를 올려놓으십시오.
4. **저장소 설정**을 선택하십시오.
5. **재등록**을 클릭하십시오.
6. 양식을 완성하십시오.
  - 저장소 이름
  - 저장소 주소
  - 계정

    "계정"은 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}의 "계정 이름"과 동일합니다. 일반적으로 이는 "SLE[account ID]"와 유사합니다.
    {:tip}
  - 사용자 이름
  - 비밀번호
7. **컴퓨터 로드**를 클릭하고 로드할 컴퓨터를 선택하십시오.
8. **변경사항 저장**을 클릭하십시오.
9. 웹 사이트를 새로 고쳐서 이전 백업 작업을 복원하십시오.
10. 각 백업 작업을 동기화하여 safe-set 히스토리를 복원하십시오.
11. 백업 작업이 암호화 비밀번호를 사용하여 작성된 경우 암호화 비밀번호를 입력하여 데이터를 복원하거나 백업을 계속해야 합니다.
12. **닫기**를 클릭하십시오.
