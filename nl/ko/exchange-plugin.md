---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, Exchange, plug-in, plugin, EVault, Carbonite

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Exchange 플러그인 설치
{: #Exchangeplugin}

Exchange 플러그인은 호스트에서 Windows 에이전트로 설치됩니다. {{site.data.keyword.backup_notm}} 포털을 통해 작업을 구성하고 안전한 원격 저장소에 Exchange 데이터베이스를 백업하며 Exchange 데이터베이스를 복원할 수 있습니다. 플러그인은 기존 아키텍처에 통합됩니다.

**제공되는 기능**

- Microsoft Exchange 데이터베이스를 백업하고 복원하는 기능.

## 플러그인 주문
{: #orderingExchangePlugin}

1. [{{site.data.keyword.cloud_notm}} 콘솔 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")]https://{DomainName}){:new_window}에 로그인하여 왼쪽 상단에서 **메뉴** 아이콘을 클릭하십시오. **클래식 인프라**를 선택하십시오.<br/>
 또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. **스토리지** > **백업**을 클릭하여 백업 서비스의 서버를 표시하십시오.
3. 계정을 선택하고 **플러그인 주문**을 클릭하십시오.
4. **{{site.data.keyword.backup_notm}} 플러그인 - Exchange**를 선택하고 **계속**을 클릭하십시오.
5. 프로모션 코드가 있으면 이를 입력하고 **재계산**을 클릭하십시오.
6. 업데이트된 비용이 표시됩니다. 주문을 검토하십시오.
7. 서드파티 서비스 계약을 읽고 동의한다고 표시하려면 상자를 선택하십시오.
8. **주문하기**를 클릭하십시오.

## 플러그인 설치
{: #installExchangePlugin}

Exchange 플러그인은 Windows 에이전트 64비트 설치 중에 설치됩니다. 플러그인은 에이전트와 동시에 설치되거나, **수정**을 선택하여 설치를 재실행함으로써 나중에 설치될 수 있습니다.

Microsoft Windows 서버용 플러그인을 설치하기 전에 `services.msc`에서 두 {{site.data.keyword.backup_notm}} 서비스를 모두 중지하십시오.
{:tip}

1. `c:\installs\{{site.data.keyword.backup_notm}}` 폴더를 찾아보고 상위 개정 번호의 .exe 파일을 실행하십시오.
2. 언어 화면에서 **확인**을 클릭하십시오.
3. 시작 화면에서 **다음**을 클릭하십시오.
4. **설치 수정**을 선택하고 **다음**을 클릭하십시오.
5. **미변경 상태 유지**를 선택하고 **다음**을 클릭하십시오.
6. 사용자 설치 화면에서 구매한 각 플러그인을 선택하십시오.
7. **이 기능이 설치될 위치...**를 선택한 후에 **다음**을 클릭하십시오.
8. **내 현재 등록 유지**를 선택하고 **다음**을 클릭하십시오.
9. **설치**를 클릭하십시오.
10. 일단 설치되면 두 서비스가 모두 사용되고 실행 중인지 확인하십시오.
11. {{site.data.keyword.backup_notm}} 포털에서 데이터베이스 액세스 또는 보기가 가능하면 설치가 완료된 것입니다.

## 사용자 안내서 다운로드
{: #ExchangeUserGuide}

[다운로드 가능 {{site.data.keyword.backup_notm}} 문서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}에서 사용자 안내서에 액세스하여 다운로드할 수 있도록 {{site.data.keyword.BluVPN}}을 사용하여 {{site.data.keyword.BluSoftlayer_full}} 네트워크에 연결하십시오. 이 안내서는 Exchange 플러그인을 사용하여 Microsoft Exchange 데이터베이스를 백업하고 복원하는 방법에 대해 설명합니다. 또한 DR 백업 safe-set를 공유하는 방법에 대해서도 설명합니다. DR 백업 safe-set를 사용하면 Granular Restore for Microsoft Exchange 애플리케이션을 사용하여 특정 메일함, 메시지 또는 기타 오브젝트를 .pst 파일로 복원할 수 있습니다.
