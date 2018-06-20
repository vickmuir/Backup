---

copyright:
  years: 2014, 2018
lastupdated: "2018-06-05"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# EVault 백업 서비스 시작하기

백업은 데이터가 디바이스 외부에 안전하게 저장되어 데이터 유실 시에 보호되도록 보장합니다. EVault 백업은 EVault WebCC 브라우저 기반 관리 유틸리티를 통해 관리되는 자동화된 에이전트 기반 백업 시스템이며, {{site.data.keyword.BluSoftlayer_full}} 네트워크의 하나 이상의 데이터 센터에서 서버 간에 데이터를 백업하는 방법을 사용자에게 제공합니다. 관리자는 전체 시스템, 특정 디렉토리 또는 심지어는 개별 파일을 대상으로 하는 시간별, 일별, 주별 또는 사용자 정의 스케줄에 따라 백업을 설정할 수 있습니다. 추가 플러그인은 기타 유형의 써드파티 소프트웨어는 물론 Microsoft Exchange 및 Microsoft SQL 등의 소프트웨어와의 호환성을 허용하며, 사용자는 이를 사용하여 필요 시에 Bare Metal Restore를 수행할 수 있습니다. 

## EVault 주문 

두 가지 방법으로 EVault 백업 서비스를 구매할 수 있습니다. 

- 서버 주문 시 EVault 구매
- 업그레이드로 EVault 구매

### 서버 주문 시 EVault 구매

1. [IBM Cloud 카탈로그](https://console.bluemix.net/catalog/){:new_window} 또는 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}에 로그인하십시오. 
2. 월별 베어메탈 서버를 주문하십시오. [여기서](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html){:new_window} 베어메탈 서버 주문에 대해 자세히 알아볼 수 있습니다. 
3. 사용자는 주문을 완료하기 위해 관리 포털로 경로 재지정됩니다. <br/>
  **참고**: 시간별 비용 청구되는 서버를 주문할 때는 EVault 백업 서비스를 사용할 수 없습니다. 그러나 이 서비스는 나중에 업그레이드로서 추가될 수 있습니다.  
4. **추가 기능** 섹션 아래에서 EVault 옵션 중 하나를 선택하십시오("없음"은 제외). 
6. 페이지 맨 아래에서 **주문에 추가**를 클릭하십시오. 체크아웃 페이지가 표시됩니다. 
7. **체크아웃** 페이지에서 호스트와 도메인 이름 섹션을 찾고 호스트와 도메인 이름을 입력하십시오. 원하는 호스트 이름과 도메인을 선택할 수 있습니다. 
8. **체크아웃** 페이지의 오른쪽에서 **클라우드 서비스 이용 약관** 및 **써드파티 서비스 계약** 선택란을 클릭하십시오. 
9. 지불 정보를 확인하거나 입력하고 **주문 제출**을 클릭하십시오. 사용자는 프로비저닝 주문 번호가 있는 화면으로 경로 재지정됩니다. 프로비저닝 주문 영수증이기도 하므로 사용자는 화면을 인쇄할 수 있습니다. <br/>**참고**: **견적서로 저장**을 클릭하여 구매하지 않고 이 주문을 저장할 수도 있습니다. 

일련의 이메일이 관리자에게 발송됩니다(프로비저닝 주문의 수신확인, 프로비저닝 주문 승인 및 처리, 프로비저닝 완료). 프로비저닝 완료 이메일에는 {{site.data.keyword.cloud_notm}}에 로그인한 이후 *디바이스 세부사항* 페이지에 대한 링크가 포함됩니다. {{site.data.keyword.slportal}}에 직접 로그인할 수도 있습니다. 

**EVault 서비스 구매 확인**
1. [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}의 기본 메뉴에서 **디바이스** > **디바이스 목록**을 선택하십시오.  
2. 주문한 새 서버를 찾으십시오. 
  - url 옆에 시계 아이콘이 있으면 EVault 구매 확인을 계속하기 위해 대기해야 합니다. 페이지를 새로 고쳐서 새 서버에서 업데이트된 상태를 볼 수 있습니다. 시계 아이콘이 더 이상 존재하지 않으면 다음 단계를 진행하여 EVault 서비스 구매를 확인할 수 있습니다. 
  - 시계 아이콘이 더 이상 서버에 대해 표시되지 않으면 링크(서버의 url)를 클릭하여 **디바이스 세부사항** 페이지로 이동하십시오.  
3. **스토리지** 탭을 클릭하여 EVault 정보를 표시하십시오. 
4. EVault 섹션을 살펴보고 EVault 구매 프로세스 중에 선택된 크기가 EVault 링크 옆에 표시되는지 확인하십시오. 

### 업그레이드로 EVault 구매

**EVault가 설치될 서버 선택**
1. [IBM Cloud 카탈로그](https://console.bluemix.net/catalog/){:new_window} 또는 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}에 로그인하십시오. 
2. 기본 메뉴에서 **디바이스** > **디바이스 목록**을 선택하십시오. EVault 서비스가 추가될 디바이스를 찾으십시오. 
3. 디바이스 이름을 클릭하여 디바이스 세부사항 페이지로 이동하십시오. 

**EVault 서비스 추가(구매)**
1. **스토리지** 탭을 클릭하고 페이지 맨 아래에 부근에서 EVault 섹션을 찾으십시오. 
2. **추가** 링크를 클릭하십시오. 
3. 팝업에서 위치를 선택하거나 기본값을 선택하고 크기를 선택하십시오. 
4. **계속**을 클릭하십시오. 
5. 이용 약관에 동의하면 선택란을 클릭하십시오. 
6. **주문하기**를 클릭하십시오. 

**EVault 서비스 구매 확인**
1. **디바이스 세부사항** 페이지를 새로 고치고 **스토리지** 탭이 선택되었는지 확인하십시오. 
2. EVault 섹션을 살펴보고 EVault 구매 프로세스 중에 선택된 크기가 EVault 링크 옆에 표시되는지 확인하십시오. <br /> **참고**: EVault 스토리지 크기가 계속해서 제로(0) 용량을 표시하면 두 번째 페이지를 새로 고쳐야 할 수 있습니다.  

## {{site.data.keyword.slportal}}에서 EVault 백업 스토리지 세부사항 액세스 및 보기

EVault 백업 서비스와 관련된 스토리지 세부사항은 {{site.data.keyword.slportal}}을 사용하여 언제든지 볼 수 있습니다. 볼 수 있는 세부사항에는 비밀번호, 스토리지 주소 및 선택된 EVault 백업 서비스와 연관된 사용법이 포함되어 있습니다.  

1. [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}에서 **EVault 백업 스토리지** 화면에 액세스하려면 고유 신임 정보를 사용하여 로그인하십시오. 
2. **스토리지**를 클릭하고 드롭 다운 목록에서 **백업**을 선택하십시오. 
2. 원하는 EVault 백업에 대한 행에서 임의의 위치를 클릭하여 스토리지 세부사항을 보십시오. 이 보기에서 비밀번호는 보이지 않습니다. 다음 단계를 진행하여 EVault 백업 서비스와 연관된 비밀번호를 보십시오. 
3. **비밀번호** 필드 옆의 **표시** 선택란을 클릭하여 선택된 EVault 백업 서비스에 대한 비밀번호를 보십시오. 

많은 {{site.data.keyword.BluSoftlayer_full}} 제품과 서비스에서 {{site.data.keyword.slportal}} 내의 비밀번호 스토리지 기능은 비밀번호의 스토리지나 추적에만 사용되며 {{site.data.keyword.slportal}} 내에서 비밀번호에 대한 변경사항은 제품이나 서비스에는 적용되지 않습니다. 이는 EVault 백업의 경우에는 해당되지 _않습니다_. {{site.data.keyword.slportal}} 내에서 EVault 백업 비밀번호에 대한 변경사항은 서비스 자체에 적용됩니다. 서비스에 직접 영향을 준다는 사실을 유념하고 비밀번호를 변경하십시오. 비밀번호를 재설정하려면 [{{site.data.keyword.slportal}}에서 EVault 백업 비밀번호를 변경하는 방법](/docs/infrastructure/Backup/change-password-evault-backup-service.html)의 단계를 따르십시오. 

## EVault 에이전트 설치

EVault 에이전트는 다음 OS에서 지원됩니다. 

### Windows
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

### Linux
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - Red Hat Enterprise Linux 7.x
 - Red Hat Enterprise Linux 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

자신의 OS에 해당되는 지시사항을 따르십시오. 
- [Linux에서 EVault 백업 클라이언트 설치](install-evault-backup-client-linux.html)
- [Windows에서 EVault 백업 클라이언트 설치](install-evault-backup-client-windows.html)
- [Windows 2016용 EVault 백업 클라이언트 설치](install-evault-windows2016.html)

## EVault 백업을 위해 WebCentralControl(WebCC)에 액세스

WebCentralControl(WebCC)은 {{site.data.keyword.BluSoftlayer_full}}에서 제공하는 EVault 백업 서비스와의 상호작용 시에 사용되는 클라이언트입니다. WebCC는 구성 및 복원을 포함하여 EVault 백업 서비스의 전체 제어를 허용하는 사설 네트워크에서 실행되는 브라우저 기반 클라이언트입니다. 아래의 단계에 따라 EVault 백업을 위해 WebCC에 액세스하십시오. 

1. VPN 상의 사설 네트워크에 액세스하십시오. <br/>
    **참고**: WebCC는 공용 네트워크 상에서 액세스될 수 없습니다. WebCC에 액세스하려면 VPN 연결을 설정해야 합니다. 
2. [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}에서 EVault 백업 스토리지 화면에 액세스하십시오. 
3. 원하는 EVault 백업에 대한 행의 임의의 위치를 클릭하여 보기를 펼치십시오. 
3. **WebCC 로그인**을 클릭하여 브라우저에서 WebCC 클라이언트를 시작하십시오. 

## WebCC에서 EVault 에이전트 구성

일단 EVault 서비스를 주문하고 에이전트가 서버에 설치되면 데이터의 백업 작성을 시작할 수 있습니다. 아래의 단계에 따라 에이전트, 보유 스케줄을 구성하고 첫 번째 백업 작업을 시작하십시오. 

1. WebCc에 로그인하십시오.
2. **모든 에이전트**> **미구성 에이전트**를 클릭하십시오. 
3. **이 에이전트가 내가 구성하고자 하는 새 에이전트임** 링크를 클릭하십시오. 프로세스를 진행하고 다음을 지정하십시오. 
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
   **참고** - [여기서](evault-backup-faq.html#how-do-the-retention-schemes-work-) 보유 스킴이 작동하는 방법에 대해 추가로 읽으십시오. 
5. 에이전트를 실행하고 백업을 시작하십시오. 
   1. **모든 에이전트**를 클릭한 후에 방금 구성한 에이전트를 선택하십시오. 
   2. **백업 실행**을 클릭하십시오. 
   3. 대상을 확인하고 보유 스킴을 선택하십시오. 
   4. **백업 시작**을 클릭하십시오. 프로세스가 실행 중인 동안 백업 세부사항을 볼 수 있습니다. 
   5. 백업이 완료되면 **닫기**를 클릭하십시오. 
   
**참고**: [여기서](configure-simple-file-backup-linux.html) Linux에서 단순 파일 레벨 백업을 구성할 수 있는 방법에 대해 추가로 읽으십시오. 

## 다음에 발생하는 상황

WebCC의 시스템은 모두 문서화되어 있으며 애플리케이션에 대한 지원은 WebCC 내에서 액세스가 가능합니다. 파란색 원의 흰색 물음표가 표시하는 대로 오른쪽 상단 모서리에서 **도움말**을 클릭하십시오. 팝업 상자 왼쪽의 탐색줄에서 임의의 기사 또는 주제를 클릭하여 자세한 정보를 볼 수 있습니다. 


