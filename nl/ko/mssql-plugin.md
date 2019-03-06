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

# SQL Server 플러그인 설치
{: #MSSQLplugin}

SQL Server 플러그인은 SQL 데이터베이스 호스트에서 Windows 에이전트로 설치됩니다. {{site.data.keyword.backup_notm}} 포털을 통해 작업을 구성하고 안전한 원격 저장소에 SQL 데이터베이스를 백업하며 SQL 데이터베이스를 복원할 수 있습니다.

**제공되는 기능**

- 전체 데이터베이스 백업, 트랜잭션 로그와 함께 전체 데이터베이스 백업 또는 트랜잭션 로그만 백업을 실행할 수 있습니다.
- 동시에 여러 백업을 실행할 수 있습니다.
- 동일한 SQL 인스턴스로 또는 다른 SQL 인스턴스로 SQL 데이터베이스를 복원할 수 있습니다.
- 원래 데이터베이스 이름으로 데이터베이스를 복원하고 기존 데이터베이스를 겹쳐쓰며 복구 없음 옵션을 사용하여 복원할 수 있습니다.

자세한 정보는 [기본 기능](#main-featues) 섹션을 참조하십시오.

## 플러그인 주문
{: #orderingSQLPlugin}

1. [{{site.data.keyword.cloud_notm}} 콘솔 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/){:new_window}에 로그인하여 왼쪽 상단에서 **메뉴** 아이콘을 클릭하십시오. **클래식 인프라**를 선택하십시오.<br/>
 또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. **스토리지** > **백업**을 클릭하여 백업 서비스의 서버를 표시하십시오.
3. 계정을 선택하고 **플러그인 주문**을 클릭하십시오.
4. **{{site.data.keyword.backup_notm}} 플러그인 - MSSQL**을 선택하고 **계속**을 클릭하십시오.
5. 프로모션 코드가 있으면 이를 입력하고 **재계산**을 클릭하십시오.
6. 업데이트된 비용이 표시됩니다. 주문을 검토하십시오.
7. 서드파티 서비스 계약을 읽고 동의한다고 표시하려면 상자를 선택하십시오.
8. **주문하기**를 클릭하십시오.

## MSSQL 플러그인 설치
{: #installSQLPlugin}

플러그인을 설치하려면 에이전트 설치 킷을 실행하십시오. 플러그인은 **사용자 설치** 페이지에서 옵션으로 나타납니다.

Microsoft Windows 서버용 MSSQL 플러그인을 설치하기 전에 `services.msc`에서 두 {{site.data.keyword.backup_notm}} 서비스를 모두 중지하십시오.
{:tip}

1. `c:\installs\evault` 폴더를 찾아보고 상위 개정 번호로 .exe 파일을 실행하십시오.
2. 언어 화면에서 **확인**을 클릭하십시오.
3. 시작 화면에서 **다음**을 클릭하십시오.
4. **설치 수정**을 선택하고 **다음**을 클릭하십시오.
5. **미변경 상태 유지**를 선택하고 **다음**을 클릭하십시오.
6. 사용자 설치 화면에서 구매한 각 플러그인을 선택하십시오.
7. **이 기능이 설치될 위치...**를 선택한 후에 **다음**을 클릭하십시오.
8. **내 현재 등록 유지**를 선택하고 **다음**을 클릭하십시오.
9. **설치**를 클릭하십시오.
10. 일단 설치되면 두 서비스가 모두 사용되고 실행 중인지 확인하십시오.
11. {{site.data.keyword.backup_notm}} 포털에서 데이터베이스를 보고 액세스할 수 있으면 설치가 완료된 것입니다.

## 사용자 안내서 다운로드
{: #SQLUserGuide}

[다운로드 가능 {{site.data.keyword.backup_notm}} 문서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}에서 사용자 안내서를 다운로드할 수 있도록 {{site.data.keyword.BluVPN}}을 사용하여 {{site.data.keyword.BluSoftlayer_full}} 네트워크에 연결하십시오.

## 기본 기능
{: #main-features}

- 와일드카드 문자(별표 및 물음표)를 사용하여 SQL Server 백업 작업에서 포함하고 제외할 데이터베이스의 이름을 지정하는 기능. 백업 작업의 필터와 이름이 일치하는 새 데이터베이스는 작업이 실행될 때 자동으로 포함 또는 제외됩니다.
- 64비트 에이전트 및 SQL Server 플러그인을 사용하여 AlwaysOn 가용성 그룹에서 보조 데이터베이스를 보호하는 기능.
- Granular Restore for Microsoft SharePoint 애플리케이션에서 사용할 SharePoint 2010/2013 컨텐츠 데이터베이스가 포함된 SQL safeset를 공유하는 기능. safeset가 공유되면 Granular Restore 애플리케이션을 사용하여 사이트 콜렉션, 웹 사이트, 목록, 라이브러리, 폴더, 목록 항목 또는 문서를 복원할 수 있습니다.
- 여러 볼륨에 걸쳐 있는 데이터베이스의 델타 친화적 백업 지원.
- 단일 스케줄 항목의 전체 복구 모델에서 데이터베이스를 보호하는 기능. 이 옵션을 사용하여 단일 스케줄 항목에서 트랜잭션 로그의 절삭을 관리하고 데이터베이스를 보호할 수 있습니다.
- SQL Server 플러그인은 전체, 트랜잭션 로그를 포함한 전체 및 트랜잭션 로그 백업을 지원합니다(SQL Server 용어와 맞추기 위해 용어가 업데이트됨). 애플리케이션은 고객이 특정 시점 “트랜잭션 로그” 백업을 선택할 수 있도록 허용하는 단일 패스 복원 기능을 계속해서 지원합니다. {{site.data.keyword.backup_notm}}은 선택된 특정 시점으로 데이터베이스를 복원하는 데 필요한 전체 데이터베이스와 모든 트랜잭션 로그를 복원합니다.
- 백업 작업에는 동일한 단일 SQL Server 인스턴스의 하나 이상의 데이터베이스가 포함될 수 있습니다. 원하는 경우 별도의 작업을 작성하여 동시에 실행될 수 있는 다른 SQL Server 인스턴스에서 기타 데이터베이스를 백업할 수 있습니다.
- SQL Server Management Studio를 통한 추가 복구 옵션의 제공을 위해 "복구 없음"으로 데이터베이스를 복원하는 기능.
- 대체 복원 옵션은 파일로의 복원을 지원하며, 이를 사용하여 데이터베이스 관리자는 SQL System Manager를 통해 데이터베이스를 마운트할 수 있습니다.
- 대체 복원에는 논리 데이터베이스 이름이 일치하지 않아도 하나의 데이터베이스의 복원 경로를 다른 쪽으로 지정하는 기능이 포함됩니다. 불일치하는 오브젝트의 경우, 플러그인은 인스턴스에 대한 기본 데이터베이스 위치에 데이터베이스를 작성합니다.
- 64비트 SQL Server 2008 R2(SP1) 및 SQL Server 2012에서 TDE(Transparent Data Encryption) 지원.
- SQL Server 호스트가 유실된 경우, SQL Server 소프트웨어가 설치될 수 있으며 데이터베이스가 복원될 수 있습니다. (마스터 데이터베이스가 우선적으로 복원되어야 합니다.)
- 백업이 시작되면 데이터베이스 서비스의 실행 여부와 무관하게 백업이 이루어집니다.
- 원래 데이터베이스 이름(기존 데이터베이스 겹쳐쓰기와 무관함), 기존 데이터베이스에서의 복원 또는 디스크의 파일로 복원이 지원됩니다.
