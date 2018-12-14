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

# BMR(Bare Metal Restore) 플러그인 설치

BMR은 Microsoft Windows의 재해 복구 솔루션입니다. BMR을 사용하여 운영 체제나 하드웨어 장애 등의 재해가 발생한 후에 베어메탈 상태에서 서버를 복원할 수 있습니다. BMR을 사용하면 {{site.data.keyword.BluSoftlayer_full}}에서 관리하는 안전한 보안 위치에서 시스템 이미지를 빠르게 복원할 수 있습니다.

BMR은 실제 서버의 Microsoft Windows 전용 제품입니다. 이는 가상 서버에는 사용할 수 없습니다. Linux용 BMR(Bare Metal Restore) 배포는 지원되지 않습니다. 백업 에이전트 8.30 이하 버전에서만 BMR을 지원합니다. (2018년 6월 30일).
{:important}

**제공되는 기능**

- 선택된 특정 시점으로 시스템을 복원합니다.
- 이미지 또는 파일 기반 백업에서 시스템을 복원합니다.
- IBM Cloud 백업에 저장된 백업으로부터 시스템을 복원합니다.
- 부트 가능한 시스템이 없는 경우 데이터를 복원하는 데 사용할 수 있는 실행 가능한 복구 트랜잭션.
.
## 플러그인 주문

1. [{{site.data.keyword.cloud_notm}} 콘솔](https://{DomainName}/catalog/){:new_window}에 로그인하여 왼쪽 상단의 **메뉴** 아이콘을 클릭하십시오. **일반 인프라**를 선택하십시오.

   또는 [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. **스토리지** > **백업**을 클릭하여 백업 서비스의 서버를 표시하십시오.
3. 계정을 선택하고 **플러그인 주문**을 클릭하십시오.
4. **{{site.data.keyword.backup_notm}} 플러그인 - BMR(Bare Metal Restore)**을 선택하고 **계속**을 클릭하십시오.
5. 프로모션 코드가 있으면 이를 입력하고 **재계산**을 클릭하십시오.
6. 업데이트된 비용이 표시됩니다. 주문을 검토하십시오.
7. 서드파티 서비스 계약을 읽고 동의한다고 표시하려면 상자를 선택하십시오.
8. **주문하기**를 클릭하십시오.

## 사용자 안내서 다운로드

[다운로드 가능한 {{site.data.keyword.backup_notm}} 문서 ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}에서 사용자 안내서에 액세스하고 이를 다운로드할 수 있도록 {{site.data.keyword.BluVPN}}으로 {{site.data.keyword.BluSoftlayer_full}} 네트워크에 연결하십시오.

## 자주 묻는 질문

**단일 디스크에서 RAID 어레이로 이동할 수 있습니까?**

예, 그렇습니다. 하지만 RAID 어레이로 인해 크기가 감소되므로 대용량 디바이스를 선택해야 합니다.

**원래 볼륨보다 큰 디스크로 이미지를 복원하면 어떻게 됩니까?**

원래 볼륨보다 큰 디스크로 이미지를 복원하면 남은 공간이 할당 해제됩니다. 따라서, 예를 들어 500GB 드라이브를 보유 중이며 1TB 디스크로 해당 데이터를 복원하면 500GB의 디스크 공간이 할당 해제됩니다. Windows 2008에서는 기본 제공 디스크 유틸리티를 사용하여 기본 파티션을 늘릴 수 있습니다. 하지만 Windows 2003에는 유사한 기본 제공 용량이 없으므로 다른 방식으로 공간을 할당해야 합니다.

**일반 백업에 BMR을 사용할 수 있습니까?**

BMR 백업은 디스크 이미지가 아니라 시스템 볼륨 이미지 백업 시스템입니다. 시스템은 일반 백업 용도는 아니지만 이와 함께 사용됩니다.  

**데이터베이스 백업에 BMR을 사용할 수 있습니까?**

데이터베이스 백업은 일반적인 IBM Cloud 백업 방법과는 별도로 수행되어야 합니다. BMR이 있어도 SQL 또는 Oracle 플러그인은 여전히 필요합니다. BMR이 VSS 기술을 사용하여 오픈 파일을 백업하지만, 백업 파일의 트랜잭션 일관성을 항상 보장할 수는 없습니다. 이러한 유형의 특수 애플리케이션에 대해 두 개의 백업 작업을 작성하도록 권장합니다(하나는 OS 및 애플리케이션 2진 파일 백업용이며 다른 하나는 애플리케이션 데이터용임). BMR 사용자 안내서의 맨 뒤쪽에 이러한 영향에 대한 설명이 있습니다.

**BMR에서 어떤 유형의 복원 작업을 실행할 수 있습니까?**

전체 시스템 복원을 수행하거나 복원할 백업에서 개별 파일을 선정할 수 있습니다. BMR 백업 작업은 현재 파일 백업 작업을 대체할 수 있습니다. 복원 프로세스는 기존의 백업 작업처럼 OS 내에서 수행됩니다.

**BMR에 오픈 파일 백업 기능이 있습니까?**

BMR에는 오픈 파일 백업 기능이 있습니다. 그러나 BMR이 있어도 SQL 또는 Oracle 플러그인은 여전히 필요합니다. MSSQL 플러그인에 대한 자세한 정보는 [여기](mssql-plugin.html)를 참조하십시오.

**BMR 복원에 필요한 디스크 공간과 시간은 얼마나 됩니까? **

기본 설치에서 작성된 백업은 약 6GB를 사용합니다. 이러한 복원은 1GB 포트에서 약 15분 정도 걸립니다. 이 프로세스는 개인용 포트 속도의 영향도 받습니다. 보다 빠른 백업 및 복원이 필요하면 포트 속도를 늘려야 할 수 있습니다.
