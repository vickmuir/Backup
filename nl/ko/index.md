---

copyright:
  years: 2014, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# {{site.data.keyword.backup_notm}} 서비스 시작하기

백업은 데이터가 디바이스 외부에 안전하게 저장되어 데이터 유실 시에 보호되도록 보장합니다. {{site.data.keyword.backup_full}}은 {{site.data.keyword.backup_notm}} 포털 브라우저 기반 관리 유틸리티를 통해 관리되는 자동화된 에이전트 기반 백업 시스템입니다. {{site.data.keyword.backup_notm}}은 {{site.data.keyword.BluSoftlayer_full}} 네트워크에서 하나 이상의 데이터 센터의 서버 간에 데이터를 백업하는 방법을 사용자에게 제공합니다. 관리자는 전체 시스템, 특정 디렉토리 또는 심지어 개별 파일을 대상으로 하는 일별, 주별 또는 사용자 정의 스케줄에 따라 백업을 설정할 수 있습니다. 추가 플러그인은 Microsoft Exchange 및 Microsoft SQL 등의 소프트웨어, 기타 유형의 서드파티 소프트웨어와의 호환성을 보장하며, 사용자는 이를 사용하여 필요 시에 Bare Metal Restore를 완료할 수 있습니다.

## {{site.data.keyword.backup_notm}} 주문

두 가지 방법으로 {{site.data.keyword.backup_notm}} 서비스를 구매할 수 있습니다.

- [서버 주문 시 {{site.data.keyword.backup_notm}} 구매](#purchasing-ibm-cloud-backup-when-you-order-a-server).
- [업그레이드로서 {{site.data.keyword.backup_notm}} 구매](#purchasing-ibm-cloud-backup-as-an-upgrade).

가격에 관한 자세한 정보는 [{{site.data.keyword.backup_notm}} 스토리지 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/backup-and-restore){:new_window} 및 [{{site.data.keyword.backup_notm}} on IBM Cloud ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/evault/pricing){:new_window}를 참조하십시오.

### 서버 주문 시 {{site.data.keyword.backup_notm}} 구매

1. [IBM Cloud 카탈로그 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/catalog/){:new_window} 또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인하십시오.
2. 월별 베어메탈 서버를 주문하십시오. 베어메탈 서버 주문에 대한 자세한 정보는 [사용자 정의 베어메탈 서버 빌드](bare-metal/baremetal-provision.html){:new_window}를 참조하십시오.
   1. 수량, 청구 옵션을 선택하십시오. 호스트 및 도메인 이름을 입력하십시오. 원하는 호스트 이름과 도메인을 선택할 수 있습니다.

      시간별 비용 청구되는 서버를 주문할 때는 {{site.data.keyword.backup_notm}} 서비스를 사용할 수 없습니다. 그러나 이 서비스는 나중에 업그레이드로서 추가될 수 있습니다.
      {:tip}
   2. 위치를 선택하십시오.
   3. 서버 구성 및 OS 이미지 유형을 선택하십시오. 다수의 추가 기능을 선택할 수도 있습니다.
   4. **스토리지 디스크** 섹션 아래에서 **추가 기능**을 클릭하고 **{{site.data.keyword.backup_notm}} 백업**을 선택하십시오. 필요사항과 일치하는 옵션을 선택하십시오.
   5. **네트워크 인터페이스** 아래에서 원하는 추가 기능과 업링크 포트 속도를 선택하십시오.
3. 오른쪽에서 주문 요약을 검토하십시오.
4. 이용 약관의 검토를 마치면 **서드파티 서비스 계약서를 읽었으며 이에 동의합니다** 상자를 선택하십시오.
5. **프로비저닝**을 클릭하십시오. 사용자는 프로비저닝 주문 번호가 있는 화면으로 경로 재지정됩니다. 프로비저닝 주문 영수증이기도 하므로 사용자는 화면을 인쇄할 수 있습니다.

   **견적서로 저장**을 클릭하여 구매 없이 이 주문을 저장할 수도 있습니다.
   {:tip}

일련의 이메일이 관리자에게 발송됩니다(프로비저닝 주문의 수신확인, 프로비저닝 주문 승인 및 처리, 프로비저닝 완료). 프로비저닝 완료 이메일에는 {{site.data.keyword.cloud_notm}}에 로그인한 후에 액세스할 수 있는 *디바이스 세부사항* 페이지에 대한 링크가 포함됩니다. {{site.data.keyword.slportal}}에 직접 로그인할 수도 있습니다.

#### {{site.data.keyword.backup_notm}} 구매 확인
1. [{{site.data.keyword.cloud_notm}} 콘솔 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/){:new_window}의 왼쪽 상단에서 **메뉴** 아이콘을 클릭하십시오. **일반 인프라**를 선택하십시오.</br>
 또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. **디바이스** > **디바이스 목록**을 클릭하십시오.
2. 주문한 새 서버를 찾으십시오.
  - url 옆에 시계 아이콘이 표시되면 잠시 대기한 후에 {{site.data.keyword.backup_notm}} 구매 확인을 진행해야 합니다. 페이지를 새로 고쳐서 새 서버에서 업데이트된 상태를 볼 수 있습니다. 시계 아이콘이 사라지면 다음 단계를 진행하여 {{site.data.keyword.backup_notm}} 서비스 구매를 확인할 수 있습니다.
  - 시계 아이콘이 더 이상 서버에 대해 표시되지 않으면 링크(서버의 url)를 클릭하여 **디바이스 세부사항** 페이지로 이동하십시오.
3. **스토리지** 탭을 클릭하여 {{site.data.keyword.backup_notm}} 정보를 표시하십시오.
4. {{site.data.keyword.backup_notm}} 섹션을 검사하여 구매 프로세스 중에 선택된 크기가 표시되는지 확인하십시오.

### 업그레이드로서 {{site.data.keyword.backup_notm}} 구매

#### {{site.data.keyword.backup_notm}}이 설치될 서버 선택

1. [{{site.data.keyword.cloud_notm}} 콘솔 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}){:new_window}에 로그인하여 맨 위 왼쪽에서 **메뉴** 아이콘을 클릭하십시오. **일반 인프라**를 선택하십시오.</br>
 또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. 기본 메뉴에서 **디바이스** > **디바이스 목록**을 선택하십시오. {{site.data.keyword.cloud_notm}} 백업 서비스가 추가될 대상 디바이스를 찾으십시오.
3. 디바이스 이름을 클릭하여 **디바이스 세부사항** 페이지로 이동하십시오.

#### {{site.data.keyword.backup_notm}} 서비스 추가(구매)
1. **스토리지** 탭을 클릭하고 스크롤 다운하여 {{site.data.keyword.backup_notm}} 섹션을 찾으십시오.
2. **추가** 링크를 클릭하십시오.
3. 창에서 위치를 선택하고 크기를 선택하십시오.
4. 지불 유형을 선택하고 **계속**을 클릭하십시오.
5. **프로모션 코드**가 있으면 이를 입력하고 **재계산**을 클릭하십시오.
6. 주문을 검토하고 링크를 클릭하여 이용 약관을 읽으십시오.
7. 이용 약관에 동의하면 선택란을 클릭하십시오.
7. **주문하기**를 클릭하십시오.

#### {{site.data.keyword.backup_notm}} 업그레이드 구매 확인
1. **디바이스 세부사항** 페이지를 새로 고치고 **스토리지** 탭이 선택되었는지 확인하십시오.
2. {{site.data.keyword.backup_notm}} 섹션을 검사하여 구매 프로세스 중에 선택된 크기가 표시되는지 확인하십시오.

   백업 스토리지 크기가 계속해서 용량 영(0)을 표시하면 두 번째 페이지를 새로 고쳐야 할 수 있습니다.
   {:tip}

## {{site.data.keyword.backup_notm}} 스토리지 세부사항 액세스 및 보기

{{site.data.keyword.backup_notm}} 서비스의 스토리지 세부사항은 [{{site.data.keyword.cloud_notm}} 콘솔](https://{DomainName}/catalog/){:new_window} 및 {{site.data.keyword.slportal}}에서 언제든지 볼 수 있습니다. 볼 수 있는 세부사항에는 비밀번호, 스토리지 주소 및 선택된 {{site.data.keyword.backup_notm}} 서비스와 연관된 사용량이 포함되어 있습니다.

1. [{{site.data.keyword.cloud_notm}} 콘솔](https://{DomainName}){:new_window}에 로그인하고 맨 위 왼쪽의 **메뉴** 아이콘을 클릭하십시오. **일반 인프라**를 선택하십시오.</br>
 또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. **스토리지**를 클릭하고 목록에서 **백업**을 선택하십시오.
2. 해당 스토리지 세부사항을 보고자 하는 저장소의 행에서 임의의 위치를 클릭하십시오. 이 보기에서 비밀번호는 보이지 않습니다. 다음 단계를 진행하여 {{site.data.keyword.backup_notm}} 서비스와 연관된 비밀번호를 보십시오.
3. **비밀번호** 필드 옆의 **표시** 선택란을 클릭하여 선택된 {{site.data.keyword.backup_notm}} 서비스에 대한 비밀번호를 보십시오.

많은 {{site.data.keyword.BluSoftlayer_full}} 제품과 서비스에서 {{site.data.keyword.slportal}} 내의 비밀번호 스토리지 기능은 비밀번호의 저장 또는 추적에만 사용됩니다. 이러한 오퍼링에 대해 {{site.data.keyword.slportal}} 내 비밀번호 변경사항은 제품이나 서비스에는 적용되지 않습니다.

이는 {{site.data.keyword.backup_notm}}의 경우에는 해당되지 _않습니다_. {{site.data.keyword.slportal}} 내에서 {{site.data.keyword.backup_notm}} 비밀번호에 대한 변경은 서비스 자체에 대해 이루어집니다. 비밀번호를 변경할 때 이 변경이 서비스에 직접적으로 영향을 미친다는 점을 유념하십시오. 비밀번호를 재설정하려면 [{{site.data.keyword.slportal}}에서 {{site.data.keyword.backup_notm}} 비밀번호를 변경하는 방법 ](change-password.html)의 단계를 따르십시오.
{:important}

## {{site.data.keyword.backup_notm}} 에이전트 설치

{{site.data.keyword.backup_notm}} 에이전트는 다음 OS에서 지원됩니다.

**Windows**
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
- [Linux에서 백업 클라이언트 설치](install-backup-client-linux.html)
- [Windows에서 백업 클라이언트 설치](install-backup-client-windows.html)
- [Windows 2016에서 백업 클라이언트 설치](install-windows2016.html)
- [VMware에서 백업 클라이언트 설치](https://{DomainName}/docs/infrastructure/vmware/install-backup-client-vmware.html)

## {{site.data.keyword.backup_notm}} 포털(이전에는 WebCC)에 액세스

{{site.data.keyword.backup_notm}} 포털은 {{site.data.keyword.BluSoftlayer_full}}에서 제공하는 {{site.data.keyword.backup_notm}} 서비스와 상호작용하는 데 사용합니다. {{site.data.keyword.backup_notm}} 포털은 구성 및 복원을 포함하여 {{site.data.keyword.backup_notm}} 서비스의 전체 제어를 허용하며 {{site.data.keyword.BluSoftlayer_full}} 사설 네트워크에서 실행되는 브라우저 기반 클라이언트입니다. 

1. VPN 상의 사설 네트워크에 액세스하십시오.

   {{site.data.keyword.backup_notm}} 포털은 공용 네트워크 상에서 액세스될 수 없습니다. 먼저 VPN 연결을 설정해야 합니다.
   {:important}
2. [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에서 백업 스토리지 화면에 액세스하십시오.
3. 보고자 하는 {{site.data.keyword.backup_notm}} 서비스의 행에서 임의의 위치를 클릭하여 보기를 펼치십시오.
4. **{{site.data.keyword.backup_notm}} 포털 로그인**을 클릭하여 브라우저에서 {{site.data.keyword.backup_notm}} 포털 클라이언트를 시작하십시오.

## 백업 에이전트와 백업 스케줄 구성

{{site.data.keyword.backup_notm}}을 주문하고 에이전트가 서버에 설치되면 데이터의 백업 작성을 시작할 수 있습니다. 아래의 단계에 따라 에이전트, 보유 스케줄을 구성하고 첫 번째 백업 작업을 시작할 수 있습니다.

1. WebCc에 로그인하십시오.
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

        보유 스킴에 대한 자세한 정보는 [FAQ](faqs.html)를 참조하십시오.
      {:tip}
5. 에이전트를 실행하고 백업을 시작하십시오.
   1. **모든 에이전트**를 클릭한 후에 구성한 에이전트를 선택하십시오.
   2. **백업 실행**을 클릭하십시오.
   3. 대상을 확인하고 보유 스킴을 선택하십시오.
   4. **백업 시작**을 클릭하십시오. 프로세스가 실행 중인 동안 백업 세부사항을 볼 수 있습니다.
   5. 백업이 완료되면 **닫기**를 클릭하십시오.

Linux에서 파일 레벨 백업에 대한 자세한 정보는 [Linux에서 단순 파일 레벨 백업 구성](configure-simple-file-backup-linux.html)을 참조하십시오.
{:tip}

## 온라인 도움말 보기

{{site.data.keyword.backup_notm}} 포털의 시스템은 모두 문서화되어 있으며 애플리케이션에 대한 지원은 {{site.data.keyword.backup_notm}} 포털 내에서 액세스가 가능합니다. **도움말**을 보려면 오른쪽 상단에 있는 파란색 원 안의 흰색 물음표를 클릭하십시오. 왼쪽의 탐색줄에서 임의의 기사 또는 주제를 클릭하여 자세한 정보를 보십시오.
