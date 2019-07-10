---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-10"

keywords: IBM Cloud backup,  EVault, Carbonite, backup, restore

subcollection: Backup

---
{:pre: .pre}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 하나의 VSI에서 다른 데이터 센터의 다른 VSI로 데이터 복원
{: #restoreVSIotherlocation}

종종 다른 서버로 데이터를 복원하고자 할 수도 있습니다. 이 프로시저는 비OS 파일의 파일 레벨 복원에만 적용됩니다. 시스템 이미지를 복원하려면 [Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR) 지시사항을 따르십시오.

이 프로세스에는 첫 번째 서버의 저장소 위치에 액세스하기 위한 두 번째 서버의 백업 에이전트 재등록 및 **다른 컴퓨터에서의 복원** 완료가 포함됩니다.

**전제조건**

- Server1 및 Server2는 동일한 OS를 보유해야 합니다. 크로스 플랫폼 복원은 지원되지 않습니다.
- Server1 및 Server2는 이전에 구성된 백업 에이전트를 보유해야 합니다. 백업 에이전트 구성에 대한 자세한 정보는 [{{site.data.keyword.backup_notm}} 포털에서 백업 에이전트 구성](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)을 참조하십시오.
- Server1 저장소 위치로의 백업을 생성한 Server1에 대한 백업 작업.

충돌을 피하려면 두 서버 모두에서 모든 예정된 태스크를 사용 안함으로 설정하십시오.
{:important}

## Server2의 {{site.data.keyword.backup_notm}} 포털 시작
{: #startWebCCotherDC}

반드시 {{site.data.keyword.BluVPN}} 연결을 시작하여 {{site.data.keyword.cloud}} 사설 네트워크에 액세스하십시오. 그렇지 않으면, {{site.data.keyword.backup_notm}} 포털 링크가 작동하지 않습니다.
{:tip}

1. [{{site.data.keyword.cloud_notm}} 콘솔](https://{DomainName}){: external}에 로그인하여 왼쪽 상단의 **메뉴** 아이콘을 클릭하십시오. **클래식 인프라**를 선택하십시오.
2. **스토리지** > **백업**을 클릭하여 백업 서비스의 서버를 표시하십시오.
3. Server2를 선택하십시오. 오른쪽 화살표를 클릭하여 {{site.data.keyword.backup_notm}} 포털 링크를 표시하십시오.
4. **{{site.data.keyword.backup_notm}} 포털 로그인**을 클릭하여 브라우저에서 포털 클라이언트를 시작하십시오.

## 저장소 재등록
{: #reregistervaultotherDC}

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
{: #runbackuprestoreotherDC}

1. **모든 에이전트**를 클릭하십시오.

   Server2 **작업** 탭 아래에서 액세스 가능 및 동기화됨으로 Server1에서 정의된 작업을 보려면 페이지를 새로 고쳐야 할 수 있습니다.
   {:tip}
2. **고급** 위에 마우스 커서를 올려놓고 **다른 컴퓨터에서 복원**을 선택하십시오.
3. **다른 컴퓨터에서 복원** 화면에서 **추가**를 클릭하십시오. 필드가 기본값으로 자동으로 채워져 있으므로 이를 변경하십시오.
4. 저장소 필드를 클릭하고 **저장소 설정 입력**을 선택하고 Server1 저장소의 IP 주소를 입력하십시오. **추가**를 클릭하십시오.
5. 인증 정보를 Server1의 인증 정보로 업데이트하십시오.
6. **변경사항 저장**을 클릭하십시오. 이 조치로 Server1의 저장소에 연결됩니다.
7. **다른 컴퓨터에서 복원** 화면으로 돌아가 컴퓨터 및 작업 필드를 업데이트하십시오.
  - 컴퓨터 - 복원되는 백업 컴퓨터로서 Server1을 선택하십시오.
  - 작업 - Server1의 백업 작업을 선택하십시오.
8. **다음**을 클릭하여 다른 데이터 센터에 있는 server2로의 복원 프로세스를 시작하십시오.
9. 프롬프트에서 백업 비밀번호를 입력하고 **다음**을 클릭하십시오.
10. 오른쪽 백업 작업이 선택되어 있는지 확인하고 **다음**을 클릭하십시오. 이제 server2에서 복원 작업이 구성됩니다.
11. 새로 구성된 작업을 선택하고 **복원 실행**을 클릭하십시오.
12. 복원할 파일을 선택하십시오.
13. 더하기 부호를 클릭하여 파일 선택사항을 펼치십시오.
14. server1에서 server2로 복원할 개별 파일 또는 폴더의 선택란을 클릭하십시오. 그런 다음 **포함**을 클릭하십시오.
15. 파일이 오른쪽의 백업 세트 창을 채웁니다. **다음**을 클릭하십시오.
16. 데이터 선택을 완료한 후 옵션 선택을 진행하십시오.
    - **원래 위치로 복원**을 선택하십시오.
    - **기존 파일 겹쳐쓰기**를 선택하십시오.
17. **복원 실행**을 클릭하십시오. 프로세스 세부사항 창에서는 실행 중인 백업 작업의 상태를 제공합니다. 백업이 완료되면 **닫기**를 클릭하십시오.


## 복원 확인
{: #verifyrestoreotherDC}

1. SSH를 통해 Server2의 루트에 연결하십시오.
2. long 형식으로 파일 및 모든 디렉토리 항목이 포함된 파일을 나열하십시오.
  ```
  ls -la
  ```
  {: pre}

3. 출력을 비교하십시오.

## 일반 백업 스케줄 재개
{: #resumescheduleotherCD}

1. 복원이 완료되면 데이터가 복원된 server1의 등록 정보를 제거하십시오.
2. 현재 server2 등록을 입력하고 스케줄 태스크를 사용하십시오.
