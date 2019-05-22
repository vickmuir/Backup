---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, multiple vaults, mulitple locations, disaster recovery

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Multi-vaulting
{: #multivault}

Multi-vaulting은 둘 이상의 저장소 위치에 서버를 연결하는 클라이언트의 기능입니다. 이는 중복성을 제공하며 하나의 사이트에서 장애가 발생해도 백업이 사용 가능하기 때문에 심적 안정감을 제공합니다.

**키 포인트**

1. 다중 저장소는 동일한 {{site.data.keyword.backup_notm}} 포털을 통해 관리될 수 있으며 이는 동일한 방법으로 처리됩니다. 유일한 차이점은 저장소 선택이 서로 다르다는 점입니다.
2. 플러그인 라이센싱은 저장소별 기준입니다. 예를 들어, 워싱턴 DC에 있는 저장소의 MSSQL 플러그인을 구매한 경우 이는 시애틀의 저장소에서는 작동하지 않습니다.
3. 새 저장소는 구매했을 때마다 {{site.data.keyword.backup_notm}} 포털에 수동으로 추가해야 합니다.



**{{site.data.keyword.backup_notm}} Vault Director 위치**

Multi-vaulting은 모든 데이터 센터에서 사용 가능하며, 원격 저장소의 선택에는 지리적 제한사항이 없습니다. 저장소가 올바르게 구성되면 구성된 모든 저장소가 저장소 설정에 나타납니다.

원격 데이터 센터 위치에 백업하는 시간은 서버가 위치한 동일 데이터 센터에 백업하는 시간보다 오래 걸릴 수 있습니다.
{:note}

## 계정에 원격 저장소 추가

{{site.data.keyword.backup_notm}} 포털에서 새 백업 위치를 추가하려면 우선 새 원격 저장소를 계정에 추가해야 합니다.
{:important}

1. [{{site.data.keyword.cloud_notm}} 콘솔](https://{DomainName}){: external}에 로그인하여 왼쪽 상단의 **메뉴** 아이콘을 클릭하십시오. **클래식 인프라**를 선택하십시오. <br/>
   또는 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}에 로그인할 수 있습니다.
2. **디바이스**를 클릭하십시오.
3. 문제의 서버에 대한 링크를 찾아서 클릭하십시오.
4. **디바이스 세부사항**에서 **스토리지**를 클릭하십시오.
5. 스토리지 섹션이 열리면 **{{site.data.keyword.backup_notm}}**로 스크롤 다운하고 **추가**를 클릭하십시오.
6. **{{site.data.keyword.backup_notm}} 주문** 창에서 풀다운 목록의 항목을 클릭하여 원격 저장소 위치를 선택하십시오.
7. 스토리지의 크기를 선택한 후에 **계속**을 클릭하십시오.
8. **마스터를 읽었습니다...** 상자를 선택하고 **주문하기**를 클릭하십시오.

새로 주문한 저장소가 자동으로 계정에 추가됩니다. 그렇지 않으면, 영업 담당자에게 문의하여 도움을 받으십시오.

주문 프로세스가 완료되면 **스토리지** > **백업**으로 이동하여 나열된 새 저장소를 보십시오.

## 추가 저장소를 {{site.data.keyword.backup_notm}} 포털에 추가

1. [{{site.data.keyword.cloud_notm}} 콘솔](https://{DomainName}){: external}에 로그인하여 왼쪽 상단의 **메뉴** 아이콘을 클릭하십시오. **클래식 인프라**를 선택하십시오. <br/>
   또는 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}에 로그인할 수 있습니다.
2. **스토리지** > **백업**을 클릭하여 백업 서비스의 서버를 표시하십시오.
3. 여러 저장소에 백업하려는 서버를 선택하십시오. 오른쪽 화살표를 클릭하여 {{site.data.keyword.backup_notm}} 포털 링크를 표시하십시오.
4. **{{site.data.keyword.backup_notm}} 포털 로그인** 링크를 클릭하여 브라우저에서 포털 클라이언트를 시작하십시오.

   {{site.data.keyword.backup_notm}} 포털은 {{site.data.keyword.BluVPN}}을 통해서만 액세스가 가능합니다.
   {:tip}
5. 왼쪽 탐색 분할창에서 **모든 에이전트**를 클릭하십시오.
6. 오른쪽 상단에서 **편집**을 클릭하고 **저장소 설정**을 선택하십시오.
7. **저장소 설정** 창에서 **추가**를 클릭하십시오.
8. **새 저장소** 창에서
  1. 저장소 프로파일 메뉴에서 **저장소 설정 입력**을 선택하여 새 항목을 작성하십시오. 기존 항목은 업데이트하지 마십시오. 이는 작동하지 않습니다.
  2. 저장소 이름은 기타 저장소 이름과 달라야 합니다. 끝에 `-2` 태그를 추가해 보십시오. <br/>

     저장소 이름 필드의 한계는 15자입니다.
     {:important}
  3. IP 주소 필드는 {{site.data.keyword.backup_notm}} Director 위치 정보로 채워집니다. 예를 들어, `ev-director301.service.softlayer.com`에는 IP 주소 10.1.114.46이 있으며 WDC에 있습니다.
  4. 인증 정보 필드에 계정 ID, 선택된 저장소의 {{site.data.keyword.backup_notm}} 사용자 이름 및 선택된 저장소의 비밀번호를 입력하십시오.
  5. **변경사항 저장**을 클릭하십시오.

잠시 후에 새 저장소를 사용할 수 있습니다. 연결에 실패하는 경우 설정을 확인하고 다시 시도하십시오. 저장소 추가는 작업에 대해 선택할 추가 대상을 사용자에게 제시할 뿐이라는 점을 유념하십시오. 이로 인해 두 저장소 모두에 대해 작업이 자동 실행되지는 않습니다. 추가 저장소를 이용하려면 작업을 설정해야 합니다. 자세한 정보는 [시작하기 튜토리얼](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)을 참조하십시오.
