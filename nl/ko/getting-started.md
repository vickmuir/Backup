---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud backup, EVault, Carbonite, backup, getting started, setup, configure, run backup

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:shortdesc: .shortdesc}

# 시작하기 튜토리얼
{: #getting-started}

백업은 데이터가 디바이스 외부에 안전하게 저장되어 데이터 유실 시에 보호되도록 보장합니다. {{site.data.keyword.backup_full}}은 {{site.data.keyword.backup_notm}} 포털 브라우저 기반 관리 유틸리티를 통해 관리되는 자동화된 에이전트 기반 백업 시스템입니다. {{site.data.keyword.backup_notm}}은 {{site.data.keyword.BluSoftlayer_full}} 네트워크에서 하나 이상의 데이터 센터의 서버 간에 데이터를 백업하는 방법을 사용자에게 제공합니다. 관리자는 전체 시스템, 특정 디렉토리 또는 심지어 개별 파일을 대상으로 하는 일별, 주별 또는 사용자 정의 스케줄에 따라 백업을 설정할 수 있습니다. 추가 플러그인은 [Microsoft Exchange](/docs/infrastructure/Backup?topic=Backup-Exchangeplugin), [Microsoft SQL](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin), [Oracle](/docs/infrastructure/Backup?topic=Backup-Oracleplugin#Oracleplugin), [VMware vSphere](/docs/infrastructure/Backup?topic=Backup-VRA) 등의 소프트웨어와의 호환성을 보장하며 사용자는 이를 사용하여 필요 시에 [Bare Metal Restore](/docs/infrastructure/Backup?topic=Backup-BMRplugin#BMRplugin)를 완료할 수 있습니다.
{:shortdesc}

## 시작하기 전에
{: #prereqs}

IBM Cloud Backup을 사용하려면 유효한 라이센스가 있어야 합니다. 두 가지 방법으로 {{site.data.keyword.backup_notm}} 서비스를 구매할 수 있습니다.

- [서버 주문 시 백업 구매](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingwithserver).
- [업그레이드로서 백업 구매](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingasupgrade).

주문 및 가격에 대한 자세한 정보는 [{{site.data.keyword.backup_notm}} 프로비저닝](/docs/infrastructure/Backup?topic=Backup-ordering)을 참조하십시오.

## {{site.data.keyword.backup_notm}} 에이전트 설치

{{site.data.keyword.backup_notm}} 에이전트는 다음 OS에서 지원됩니다.

**Windows**
 - Windows Server 2016
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

**Linux**
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - RHEL 7.x
 - RHEL 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

자신의 OS에 해당되는 지시사항을 따르십시오.
- [Linux에서 백업 클라이언트 설치](/docs/infrastructure/Backup?topic=Backup-InstallinLinux)
- [Windows에서 백업 클라이언트 설치](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)
- [Windows 2016에서 백업 클라이언트 설치](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016)

## {{site.data.keyword.backup_notm}} 포털(이전에는 WebCC)에 액세스
{: #accessingWebCC}

{{site.data.keyword.backup_notm}} 포털은 {{site.data.keyword.BluSoftlayer_full}}에서 제공하는 {{site.data.keyword.backup_notm}} 서비스와 상호작용하는 데 사용합니다. {{site.data.keyword.backup_notm}} 포털은 구성 및 복원을 포함하여 {{site.data.keyword.backup_notm}} 서비스의 전체 제어를 허용하며 {{site.data.keyword.BluSoftlayer_full}} 사설 네트워크에서 실행되는 브라우저 기반 클라이언트입니다.

1. VPN 상의 사설 네트워크에 액세스하십시오.

   {{site.data.keyword.backup_notm}} 포털은 공용 네트워크 상에서 액세스될 수 없습니다. 먼저 VPN 연결을 설정해야 합니다.
   {:important}
2. [{{site.data.keyword.cloud_notm}} 콘솔]https://{DomainName}){:new_window}에 로그인하여 왼쪽 상단의 **메뉴** 아이콘을 클릭하십시오. **클래식 인프라**를 선택하십시오.<br/>
   또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. **스토리지** > **백업**을 클릭하여 백업 서비스의 서버를 표시하십시오.
3. 백업할 파일이 있는 서버를 선택하십시오. 오른쪽 화살표를 클릭하여 {{site.data.keyword.backup_notm}} 포털 링크를 표시하십시오.
4. **{{site.data.keyword.backup_notm}} 포털 로그인**을 클릭하여 브라우저에서 포털 클라이언트를 시작하십시오.

## 백업 에이전트와 백업 스케줄 구성

{{site.data.keyword.backup_notm}}을 주문하고 에이전트가 서버에 설치되면 데이터의 백업 작성을 시작할 수 있습니다. 아래의 단계에 따라 에이전트 및 보유 스케줄을 구성하십시오.

1. {{site.data.keyword.backup_notm}} 포털에 로그인하십시오.
2. **모든 에이전트**> **미구성 에이전트**를 클릭하십시오.
3. **이 에이전트가 내가 구성하고자 하는 새 에이전트임** 링크를 클릭하십시오. 프로세스를 진행하고 다음 정보를 입력하십시오.
   1. 에이전트 구성 - 에이전트 설명을 제공하고 **다음**을 클릭하십시오.
   2. 작업 유형 선택 - 작업 이름, 작업 설명 및 백업 소스 유형을 입력하고 **다음**을 클릭하십시오.
   3. 선택 - 디렉토리를 선택하고 **포함...**을 클릭하십시오.
   4. 옵션 - 비밀번호를 입력하십시오.
   5. 스케줄 - **추가**를 클릭하여 스케줄을 작성하고 **다음**을 클릭하십시오.
   6. 기본 저장소를 선택하고 **확인**을 클릭하십시오.
   7. **저장**을 클릭하십시오.
4. 보유 스케줄을 작성하십시오.
   1. **편집** > **에이전트 설정**을 선택하십시오.
   2. **추가**를 클릭하십시오.
   3. 보유 세부사항을 채우십시오.
   4. **확인**을 클릭하십시오.
   5. **저장**을 클릭하십시오.

              보유 스킴에 대한 자세한 정보는 [FAQ](/docs/infrastructure/Backup?topic=Backup-faqs#faqs)를 참조하십시오.
      {:tip}

## 첫 번째 백업 작업 실행

1. {{site.data.keyword.backup_notm}} 포털에 로그인하십시오.
2. **모든 에이전트**를 클릭한 후에 구성한 에이전트를 선택하십시오.
3. **백업 실행**을 클릭하십시오.
4. 대상을 확인하고 보유 스킴을 선택하십시오.
5. **백업 시작**을 클릭하십시오. 프로세스가 실행 중인 동안 백업 세부사항을 볼 수 있습니다.
6. 백업이 완료되면 **닫기**를 클릭하십시오.

자세한 정보는 [Linux에서 단순 파일 레벨 백업 구성](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup)을 참조하십시오.
{:tip}

## 콘솔에서 {{site.data.keyword.backup_notm}} 스토리지 세부사항 액세스 및 보기

서비스의 스토리지 세부사항은 [{{site.data.keyword.cloud_notm}} 콘솔]https://{DomainName}){:new_window} 및 {{site.data.keyword.slportal}}에서 언제든지 볼 수 있습니다. 볼 수 있는 세부사항에는 비밀번호, 스토리지 주소 및 선택된 {{site.data.keyword.backup_notm}} 서비스와 연관된 사용량이 포함되어 있습니다.

1. [{{site.data.keyword.cloud_notm}} 콘솔](https://{DomainName}){:new_window}에 로그인하여 왼쪽 상단의 **메뉴** 아이콘을 클릭하십시오. **클래식 인프라**를 선택하십시오.</br>
   또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. **스토리지**를 클릭하고 목록에서 **백업**을 선택하십시오.
2. 해당 스토리지 세부사항을 보고자 하는 저장소의 행에서 임의의 위치를 클릭하십시오. 이 보기에서 비밀번호는 보이지 않습니다.
3. **비밀번호** 필드 옆의 **표시** 선택란을 클릭하여 선택된 {{site.data.keyword.backup_notm}} 서비스에 대한 비밀번호를 보십시오.

{{site.data.keyword.slportal}} 내에서 {{site.data.keyword.backup_notm}} 비밀번호에 대한 변경은 서비스 자체에 대해 이루어집니다. 비밀번호를 재설정하려면 [백업 서비스를 위해 비밀번호 변경](/docs/infrastructure/Backup?topic=Backup-changePassword)의 단계를 따르십시오.
{:important}

## 더 많은 온라인 도움말 보기

{{site.data.keyword.backup_notm}} 포털의 시스템은 모두 문서화되어 있으며 애플리케이션에 대한 지원은 {{site.data.keyword.backup_notm}} 포털 내에서 액세스가 가능합니다. **도움말**을 보려면 오른쪽 상단에 있는 파란색 원 안의 흰색 물음표를 클릭하십시오. 왼쪽의 탐색줄에서 임의의 기사 또는 주제를 클릭하여 자세한 정보를 보십시오.
