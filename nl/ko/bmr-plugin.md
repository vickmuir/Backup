---

copyright:
  years: 1994, 2019
lastupdated: "2019-03-26"

keywords: IBM Cloud backup, bare metal restore, bmr, plug-in, plugin, EVault, Carbonite, baremetal, point-in-time restore

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# BMR(Bare Metal Restore) 플러그인 설치
{: #BMRplugin}

BMR은 재해 복구 솔루션입니다. BMR을 사용하여 운영 체제나 하드웨어 장애 등의 재해가 발생한 후에 베어메탈 상태에서 서버를 복원할 수 있습니다. BMR을 사용하면 {{site.data.keyword.BluSoftlayer_full}}에서 관리하는 안전한 보안 위치에서 시스템 이미지를 빠르게 복원할 수 있습니다.

BMR은 실제 서버의 Microsoft Windows 전용 제품입니다. 이는 가상 서버에는 사용할 수 없습니다. Linux용 BMR(Bare Metal Restore) 배포는 지원되지 않습니다. 백업 에이전트 8.30 이하 버전에서만 BMR을 지원합니다. (2018년 6월 30일).
{:important}

**제공되는 기능**

- 선택된 특정 시점으로 시스템을 복원합니다.
- 이미지 또는 파일 기반 백업에서 시스템을 복원합니다.
- {{site.data.keyword.backup_notm}}에 저장된 백업에서 시스템을 복원합니다.
- 부트 가능한 시스템이 없는 경우 데이터를 복원하는 데 사용할 수 있는 실행 가능한 복구 트랜잭션.

## 플러그인 주문
{: #orderingBMR}

1. [{{site.data.keyword.cloud_notm}} 콘솔 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}){:new_window}에 로그인하여 왼쪽 상단에서 **메뉴** 아이콘을 클릭하십시오. **클래식 인프라**를 선택하십시오. <br/>
 또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. **스토리지** > **백업**을 클릭하여 백업 서비스의 서버를 표시하십시오.
3. 계정을 선택하고 **플러그인 주문**을 클릭하십시오.
4. **{{site.data.keyword.backup_notm}} 플러그인 - BMR(Bare Metal Restore)**을 선택하고 **계속**을 클릭하십시오.
5. 프로모션 코드가 있으면 이를 입력하고 **재계산**을 클릭하십시오.
6. 업데이트된 비용이 표시됩니다. 주문을 검토하십시오.
7. 서드파티 서비스 계약을 읽고 동의한다고 표시하려면 상자를 선택하십시오.
8. **주문하기**를 클릭하십시오.

## 사용자 안내서 다운로드
{: #BMRUserGuide}

[다운로드 가능 {{site.data.keyword.backup_notm}} 문서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}에서 사용자 안내서에 액세스하여 다운로드할 수 있도록 {{site.data.keyword.BluVPN}}을 사용하여 {{site.data.keyword.BluSoftlayer_full}} 네트워크에 연결하십시오.
