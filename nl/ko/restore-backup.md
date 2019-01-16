---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# 백업에서 복원

다음 단계를 사용하여 {{site.data.keyword.backup_full}}의 파일 복원을 완료하십시오. 시스템 이미지를 복원하려면 [Windows BMR](restore-bmr-system-volume-image.html) 지시사항을 따르십시오.

## {{site.data.keyword.backup_notm}} 포털 시작

반드시 {{site.data.keyword.BluVPN}} 연결을 시작하여 {{site.data.keyword.BluSoftlayer_full}} 사설 네트워크에 액세스하십시오. 그렇지 않으면 {{site.data.keyword.backup_notm}} 포털 링크가 작동하지 않습니다.
{:important}

1. [{{site.data.keyword.cloud_notm}} 콘솔](https://{DomainName}/catalog/){:new_window}에 로그인하여 왼쪽 상단의 **메뉴** 아이콘을 클릭하십시오. **일반 인프라**를 선택하십시오. <br/>
또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. **스토리지** > **백업**을 클릭하여 백업 서비스의 서버를 표시하십시오.
3. 복원할 파일이 있는 서버를 선택하십시오. 화살표를 클릭하여 {{site.data.keyword.backup_notm}} 포털 링크를 표시하십시오.
4. **{{site.data.keyword.backup_notm}} 포털**을 클릭하여 브라우저에서 {{site.data.keyword.backup_notm}} 포털 클라이언트를 시작하십시오.

## 데이터 복원

1. 왼쪽의 탐색 분할창에서 **모든 에이전트**를 클릭하십시오.
2. 에이전트를 클릭하여 작업을 표시하십시오.
3. 원하는 데이터가 포함된 작업을 클릭하십시오.
4. **복원 실행**을 클릭하십시오.
5. 복원 소스를 선택하십시오.
6. 백업 버전을 선택하십시오.
7. 암호화 비밀번호를 입력하십시오.
8. **다음**을 클릭하여 계속하십시오.
9. 포함할 파일과 디렉토리 옆의 선택란을 선택십시오. 그런 다음 **포함**을 클릭하여 선택사항을 저장하십시오.
10. 나타나는 창을 사용하여 선택사항을 추가로 필터링하거나 **확인**을 클릭하여 선택한 항목을 그대로 사용할 수 있습니다.
파일과 디렉토리 선택사항을 포함한 후에는 데이터 파일 분할창에서 더 이상 파일을 선택할 수 없습니다. 이는 오른쪽의 백업 세트 분할창에 표시됩니다.

   10단계를 반복하여 파일을 더 추가하거나 이전에 추가한 파일을 제거(**제외**를 사용하여)할 수 있습니다. 또한 **제거**를 사용하여 **백업 세트** 분할창에서 임의의 항목명을 삭제할 수도 있습니다.
   {:tip}

11. 원하는 방식으로 백업 세트가 구성되면 **다음**을 클릭하여 계속하십시오.
12. 다음 분할창의 기본 설정을 그대로 두거나 원하는 대로 복원을 사용자 정의하십시오. 그런 다음 **복원 실행**을 클릭하십시오.
13. **프로세스 세부사항** 화면에서 상태가 **복원 완료**를 표시하면 파일이 복원된 것입니다.
