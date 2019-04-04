---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Windows에서 BMR 백업 구성
{: #configureBMR}

BMR 백업을 작성하려면 BMR 플러그인을 구매해야 합니다. BMR은 Windows Bare Metal Server에만 사용 가능합니다. VSI에는 BMR 옵션을 사용할 수 없습니다. 자세한 정보는 [Bare Metal Restore 플러그인 설치](/docs/infrastructure/Backup?topic=Backup-BMRplugin#BMRplugin)를 참조하십시오.
{:important}

## {{site.data.keyword.backup_notm}} 포털 시작
{: #startWebCCBMR}

{{site.data.keyword.backup_notm}} 포털을 시작하려면 {{site.data.keyword.BluSoftlayer_full}} 사설 네트워크에 연결되어 있어야 합니다.
{:important}

1. [{{site.data.keyword.cloud_notm}} 콘솔](https://{DomainName}){:new_window}에 로그인하여 왼쪽 상단의 **메뉴** 아이콘을 클릭하십시오. **클래식 인프라**를 선택하십시오.<br/>
또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. **스토리지** > **백업**을 클릭하여 백업 서비스의 서버를 표시하십시오.
3. 백업할 파일이 있는 서버를 선택하십시오. 오른쪽 화살표를 클릭하여 {{site.data.keyword.backup_notm}} 포털 링크를 표시하십시오.
4. **{{site.data.keyword.backup_notm}} 포털 로그인**을 클릭하여 브라우저에서 포털 클라이언트를 시작하십시오.

   {{site.data.keyword.backup_notm}} 포털이 시작되지 않는 경우에는 VPN 연결에 문제가 있을 수 있습니다. 전송 중인 양식이 안전하지 않음을 알리는 메시지가 표시될 수도 있습니다. 이는 예상된 것입니다. 양식을 전송하여 계속하십시오.
   {:tip}

## BMR 백업 작업 구성

1. 왼쪽 탐색 분할창에서 **모든 에이전트**를 클릭하여 현재 {{site.data.keyword.backup_notm}} 에이전트를 표시하십시오.
2. **이 에이전트가 내가 구성하고자 하는 새 에이전트임**을 클릭하십시오.
3. 작성 중인 작업의 작업 이름과 작업 설명을 입력하십시오.
4. **백업 소스 유형**에 대해 목록에서 파일 시스템 유형을 선택하고 **다음**을 클릭하십시오.
5. **작업 유형 선택** 메뉴가 표시됩니다. **BMR(Bare Metal Restore)** 옆의 상자를 선택하고 **다음**을 클릭하여 계속하십시오.
6. 확인 창에서 **예**를 클릭하십시오.
7. 화면에서 새 작업이 이제 현재 백업 세트에 있음을 표시합니다. **다음**을 클릭하십시오.
8. 화면에서 암호화 옵션과 고급 백업 옵션을 표시합니다. 일반적으로 이러한 옵션은 필요하지 않습니다. **다음**을 클릭하십시오.   
9. **스케줄 작성** 페이지에 두 가지 선택사항이 있습니다.
   - **다음**을 클릭하여 수동 작업을 작성하고 새 작업 실행을 진행하십시오.
   - **추가**를 클릭하여 시간 기반 백업 작업을 스케줄하십시오.
     1. 백업을 실행할 일 수와 시간을 선택하십시오.
     2. 보유 스킴을 선택하십시오.

보유 스킴에 대한 자세한 정보는 [FAQ](/docs/infrastructure/Backup?topic=Backup-faqs)를 참조하십시오.
        {:tip}
     3. 백업 스케줄을 구성한 후 **확인**을 클릭하여 저장하십시오. 스케줄된 작업이 스케줄된 작업 목록에 추가됩니다.
10. 백업 작업의 저장소를 선택하고 **변경사항 저장**을 클릭하십시오.


## BMR 백업 작업 실행

  - 시간 기반 백업 작업을 스케줄한 경우 수행할 다른 작업은 없습니다. 스케줄된 대로 작업이 자동으로 실행됩니다.
  - (시간 기반 스케줄 없이) 수동 작업을 설정한 경우에는 작업 목록에서 해당 행을 선택하고 **백업 실행**을 클릭하여 이를 실행할 수 있습니다. <br/> 시간 기반 작업에서와 같이 **보유 스킴** 및 **고급 백업 옵션**을 선택할 수 있습니다. 구성 선택이 완료되면 **백업 시작**을 클릭하여 작업을 시작하십시오.
