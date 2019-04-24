---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup,  EVault, Carbonite, backup, restore

subcollection: Backup

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 하나의 VSI에서 동일한 데이터 센터 내의 다른 VSI로 데이터 복원
{: #restorefromotherVSI}

종종 동일한 데이터 센터의 다른 서버로 데이터를 복원하고자 할 수도 있습니다. 이 프로시저는 비OS 파일의 파일 레벨 복원에만 적용됩니다. 시스템 이미지를 복원하려면 [Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR) 지시사항을 따르십시오.

이 프로세스에는 첫 번째 서버의 저장소 위치에 액세스하기 위한 두 번째 서버의 백업 에이전트 재등록 및 **다른 컴퓨터에서의 복원** 완료가 포함됩니다.

**전제조건**

- Server1 및 Server2는 동일한 OS를 보유해야 합니다. 크로스 플랫폼 복원은 지원되지 않습니다.
- Server1 및 Server2는 이전에 구성된 백업 에이전트를 보유해야 합니다. 백업 에이전트 구성에 대한 자세한 정보는 [{{site.data.keyword.backup_notm}} 포털에서 백업 에이전트 구성](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)을 참조하십시오.
- Server1 저장소 위치로의 백업을 생성한 Server1에 대한 백업 작업.

충돌을 피하려면 두 서버 모두에서 모든 예정된 태스크를 사용 안함으로 설정하십시오.
{:important}

## Server2의 {{site.data.keyword.backup_notm}} 포털 시작
{: #startWebCC}

반드시 {{site.data.keyword.BluVPN}} 연결을 시작하여 {{site.data.keyword.BluSoftlayer_full}} 사설 네트워크에 액세스하십시오. 그렇지 않으면, {{site.data.keyword.backup_notm}} 포털 링크가 작동하지 않습니다.
{:tip}

1. [{{site.data.keyword.cloud_notm}} 콘솔](https://{DomainName}){:new_window}에 로그인하여 왼쪽 상단의 **메뉴** 아이콘을 클릭하십시오. **클래식 인프라**를 선택하십시오. <br/>
      또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. **스토리지** > **백업**을 클릭하여 백업 서비스의 서버를 표시하십시오.
3. Server2를 선택하십시오. 오른쪽 화살표를 클릭하여 {{site.data.keyword.backup_notm}} 포털 링크를 표시하십시오.
4. **{{site.data.keyword.backup_notm}} 포털 로그인**을 클릭하여 브라우저에서 포털 클라이언트를 시작하십시오.

## 저장소 재등록
{: #reregistervault}

1. **모든 에이전트**를 클릭하고 수정할 특정 에이전트를 여십시오.
2. **편집**을 클릭하고 **저장소 설정**을 선택하십시오.
3. **재등록**을 클릭하여 Server1을 Server2에 연결하십시오.
4. **저장소 프로파일 사용** 항목에 대해 **저장소 재등록** 화면에서 **저장소 설정 입력**을 선택하십시오.
5. Server1의 저장소 이름과 동일한 저장소 이름을 입력하십시오.
6. Server1의 저장소에 로그인하기 위한 Server1의 인증 정보를 입력하십시오.
7. **컴퓨터 로드**를 클릭하십시오. 이 조치로 인해 저장소 위치에 연결된 서버가 표시됩니다.
8. **변경사항 저장**을 클릭하십시오.
9. 프롬프트가 표시되면 **예**를 클릭하여 저장소의 재등록을 확인하십시오.

## Server2에서 복원 작업으로서 Server1의 백업 작업 실행
{: #runbackuprestore}

1. **모든 에이전트**를 클릭하십시오.

   Server2 **작업** 탭 아래에서 액세스 가능 및 동기화됨으로 Server1에서 정의된 작업을 보려면 페이지를 새로 고쳐야 할 수 있습니다.
   {:tip}
2. **고급** 위에 마우스 커서를 올려놓고 **다른 컴퓨터에서 복원**을 선택하십시오.
3. **다른 컴퓨터에서 복원** 화면에서 다음을 선택하십시오.
  - 저장소 - 이 항목의 기본값은 Server1의 저장소입니다.
  - 컴퓨터 - 복원되는 백업 컴퓨터로서 Server1을 선택하십시오.
  - 작업 - Server1의 백업 작업을 선택하십시오.
4. **다음**을 클릭하십시오.
5. 소스 정보 확인
  - **Safeset 위치**는 Server1의 저장소 위치입니다.
  - **백업 버전 선택** 섹션에서 백업 버전으로서 Server1의 백업을 지정하십시오.
  - 암호화 비밀번호는 Server1의 백업을 작성할 때 사용한 비밀번호입니다.
6. **다음**을 클릭하십시오.
7. Server1 백업에서 복원되어야 하는 파일을 선택하십시오. 복원할 파일과 디렉토리 옆의 선택란을 선택한 후에 **포함**을 클릭하여 선택사항을 저장하십시오.
8. **다음**을 클릭하여 복원 옵션으로 이동하십시오.
9. 옵션
  - 대상 - **원래 위치로 복원**을 선택하십시오.
  - 파일 겹쳐쓰기 - **기존 파일 겹쳐쓰기**를 선택하십시오.
10. **복원 실행**을 클릭하십시오.
11. 프로세스 세부사항 화면에서 복원 작업의 상태를 표시합니다.


## 복원 확인
{: #verifyrestore}

1. SSH를 통해 Server2의 루트에 연결하십시오.
2. long 형식으로 파일 및 모든 디렉토리 항목이 포함된 파일을 나열하십시오.
  ```
  ls -la
  ```
  {: pre}

3. 출력을 비교하십시오.

## 일반 백업 스케줄 재개
{: #resumeschedule}

1. 복원이 완료되면 데이터가 복원된 server1의 등록 정보를 제거하십시오.
2. 현재 server2 등록을 입력하고 스케줄 태스크를 사용하십시오.
