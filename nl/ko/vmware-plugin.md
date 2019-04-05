---

copyright:
  years: 1994, 2019
lastupdated: "2019-03-29"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# vSphere 복구 에이전트 설치
{: #VRA}

VRA(vSphere Recovery Agent)는 Windows 애플리케이션이며 10TB까지 VMDK를 백업하고 복원할 수 있습니다. 보호할 vCenter에 대한 로컬 네트워크 액세스가 있는 실제 또는 가상 머신에 vSphere Recovery Agent를 설치할 수 있습니다. 최고의 성능을 위해 vCenter와 동일한 서브넷에 있는 머신에 VRA를 설치하십시오. 워크로드를 분배하기 위해 최대 다섯 개의 VRA가 단일 vCenter에 연결된 VM을 보호할 수 있습니다.

vSAN 확장 클러스터에서 각 VM이 선호하는 사이트가 있습니다. 하나의 로컬 VRA가 해당 사이트의 선호하는 VM을 백업하는 각 사이트에 설치되는 것이 이상적입니다. 유지보수 또는 장애로 인해 VM이 다른 사이트로 이동되는 경우, 백업 성능이 저하될 수 있으나 허용 가능한 정도입니다.


## 플러그인 주문
{: #orderingVRAPlugin}

{{site.data.keyword.cloud_notm}}에서는 무료로 VRA(vSphere Recovery Agent)를 제공합니다. 현재 {{site.data.keyword.backup_notm}} 구독이 있으면 {{site.data.keyword.backup_notm}} 포털에서 플러그인을 다운로드할 수 있습니다.

## 플러그인 설치
{: #installVRAPlugin}

VRA를 설치하는 서버에서 전원 관리를 사용 안함으로 설정해야 합니다.
{: important}

1. `http://downloads.service.softlayer.com/evault/`에서 설치 킷을 다운로드하십시오. 그런 다음 설치 킷을 두 번 클릭하십시오.
2. 확인 메시지가 표시되면 **예**를 클릭하십시오.
3. 시작 페이지에서 **다음**을 클릭하십시오.
4. 일반 사용자 라이센스 계약 페이지에서 라이센스 계약을 읽으십시오. 조항에 동의하면 **라이센스 계약의 조항에 동의함**을 클릭하고 **다음**을 클릭하십시오.
5. 대상 폴더 페이지에서 다음 단계 중 하나를 수행하십시오.
   * 기본 위치에 VRA를 설치하려면 **다음**을 클릭하십시오.
   * 다른 위치에 VRA를 설치하려면 **변경**을 클릭하십시오. 대상 폴더 변경 대화 상자에서 새 설치 폴더를 찾거나 폴더 이름 상자에 폴더 이름을 입력하십시오. **확인**을 클릭하십시오. 대상 폴더 페이지에서 **다음**을 클릭하십시오.
6. 포털 페이지에 에이전트 등록에서 다음 정보를 지정하십시오.
   * **네트워크 주소** 필드에 `ev-webcc01.service.softlayer.com`을 입력하십시오.
   * **포트** 필드에 `8086`을 입력하십시오.
   * **사용자 이름** 필드에 VRA를 관리할 {{site.data.keyword.backup_notm}} 사용자 이름을 입력하십시오.
   * **비밀번호** 필드에 지정된 {{site.data.keyword.backup_notm}} 사용자의 비밀번호를 입력하십시오.
7.	**다음**을 클릭하십시오. 설치가 완료되면 **완료**를 클릭하십시오.

## vSphere 복구 에이전트 구성
{: #configureVRA}

VRA가 설치된 후에 {{site.data.keyword.backup_notm}} 포털에서 이를 구성해야 합니다.

1. {{site.data.keyword.backup_notm}} 포털에 로그인하십시오. {{site.data.keyword.backup_notm}} 포털에 액세스하는 방법에 대한 자세한 정보는 [시작하기 튜토리얼](/docs/infrastructure/Backup?topic=Backup-gettingstarted#accessingWebCC)을 참조하십시오.
2. 컴퓨터 탭에서 백업할 서버를 선택하십시오.
3. 저장소 정보를 구성하십시오.

   저장소 정보는 두 가지 방법, 즉, **자동** 또는 **수동**으로 구성할 수 있습니다.<br/>에이전트를 처음으로 구성하는 경우, [자동 구성](#VRAautoconfig) 옵션을 사용하여 구성할 수 있습니다.<br/>컴퓨터가 이전에 저장소에 등록된 경우, 자동 구성이 작동하지 않으며 저장소를 [수동으로 구성](#VRAmanualconfig)해야 합니다.
   {: tip}

4. [vCenter 설정](#vCenterSettingsconfig) 구성   

### 저장소 자동 구성
{: #VRAautoconfig}

저장소 설정을 자동으로 구성하려면 **자동으로 구성**을 클릭하십시오. 구성 마법사가 실행되고 사용자를 대신하여 저장소를 구성합니다. 완료되면 **에이전트로 이동**을 클릭하여 **저장소 설정** 탭의 정보를 확인하십시오.

### 저장소 수동 구성
{: #VRAmanualconfig}

저장소 설정을 수동으로 구성하려면 **수동으로 구성**을 클릭하십시오.   
1. **저장소 설정**을 클릭하십시오.
2. **저장소 추가**를 클릭하십시오. 저장소 설정 창이 나타납니다. **저장소 프로파일** 옵션에서 적절한 저장소를 선택하십시오.
   컴퓨터가 이전에 {{site.data.keyword.backup_notm}} 저장소에 등록된 경우, 저장소 프로파일에서 저장소가 선택되면 모든 정보가 자동으로 채워집니다.
   {:note}

3. 저장소 설정 페이지의 모든 정보를 확인하고 **저장**을 클릭하십시오.
4. 저장소 설정을 저장하면 **저장소 설정** 탭에서 저장소 정보를 볼 수 있습니다.


### vCenter 에이전트 설정 구성
{: #vCenterSettingsconfig}
저장소 등록이 완료된 후에 vCenter 설정을 구성해야만 백업 작업을 작성하고 실행할 수 있습니다.

1. **vCenter 설정** 탭을 클릭하십시오.
2. vCenter IP 주소, 도메인 이름 및 보호할 vCenter의 인증 정보를 제공하십시오.
   이 태스크를 수행하려면 사용자가 vCenter에 대한 관리 액세스 권한을 갖고 있어야 합니다.
   {:note}

3. 체크 표시를 제거하여 CBT(Change Block Tracking)를 사용 안함으로 설정하십시오. CBT는 변경된 디스크 섹터를 추적하고 VM 백업의 성능을 개선하는 VMware 기능이며 vSphere Agent에 의해 자동으로 사용 가능으로 설정되어 있습니다.
4. **vCenter 연결 테스트**를 클릭하십시오. 새 창에 결과가 표시됩니다. 제공된 로그인 정보가 올바르면 “The vCenter credentials have been validated successfully” 메시지가 표시됩니다.
5. **저장**을 클릭하여 설정을 저장하십시오. 

## 다음 단계
{: #VRAnextteps}
1. [백업 작업 구성, 스케줄 및 실행](/docs/infrastructure/Backup?topic=Backup-ConfigureVRA#VConfigureVRA)
2. [vSphere 데이터 복원](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore)

[다운로드 가능 {{site.data.keyword.backup_notm}} 문서 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}에서 사용자 안내서에 액세스하여 다운로드할 수 있도록 {{site.data.keyword.BluVPN}}을 사용하여 {{site.data.keyword.BluSoftlayer_full}} 네트워크에 연결하십시오.
{:tip}
