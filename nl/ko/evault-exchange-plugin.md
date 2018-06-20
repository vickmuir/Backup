---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# EVault Exchange 플러그인 설치

Exchange 플러그인은 호스트에서 Windows 에이전트로 설치됩니다. WebCC 포털을 사용하여 작업을 구성하고 안전한 원격 저장소에 Oracle 데이터베이스를 백업하며 Oracle 데이터베이스를 복원할 수 있습니다. Oracle 플러그인은 기존 아키텍처로 통합됩니다. 

## 제공되는 기능

- Microsoft Exchange 데이터베이스를 백업하고 복원하는 기능. 

## 플러그인 주문

1. [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}에 로그인하십시오. 
2. **스토리지** > **백업**을 클릭하십시오. 
3. EVault 계정을 선택하고 **플러그인 주문**을 클릭하십시오. 
4. **EVault 플러그인 - Exchange**를 선택하고 **계속**을 클릭하십시오. 
5. 프로모션 코드가 있으면 이를 입력하고 **재계산**을 클릭하십시오. 
6. 업데이트된 비용이 표시됩니다. 주문을 검토하십시오.  
7. 상자를 선택하여 마스터 서비스 계약을 읽고 써드파티 소프트웨어 이용 약관에 동의함을 표시하십시오.  
8. **주문하기**를 클릭하십시오. 

## Exchange 플러그인 설치

Exchange 플러그인은 Windows 에이전트 64비트 설치 중에 설치됩니다. 플러그인은 에이전트를 설치할 때 설치되거나, 수정을 선택하여 설치를 재실행함으로써 나중에 설치될 수 있습니다. 

**참고**: Microsoft Windows 서버용 플러그인을 설치하기 전에 `services.msc`에서 두 EVault 서비스를 모두 중지하십시오.   

1. `c:\installs\evault` 폴더를 찾아보고 상위 개정 번호로 .exe 파일을 실행하십시오. 
2. 언어 화면에서 **확인**을 클릭하십시오. 
3. 시작 화면에서 **다음**을 클릭하십시오. 
4. **설치 수정**을 선택하고 **다음**을 클릭하십시오. 
5. **미변경 상태 유지**를 선택하고 **다음**을 클릭하십시오. 
6. 사용자 설치 화면에서 구매한 각 플러그인을 선택하고 **이 기능이 설치될 위치...**를 선택한 후에 **다음**을 클릭하십시오. 
7. **내 현재 등록 유지** 단일 선택 단추를 선택하고 **다음**을 클릭하십시오. 
8. **설치**를 클릭하십시오. 
9. 일단 설치되면 두 서비스가 모두 사용되고 실행 중인지 확인하십시오. 
10. WebCC에서 데이터베이스 액세스(보기)가 가능하면 설치가 완료된 것입니다.  

## 사용자 가이드

[다운로드 가능한 EVault 문서](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}에서 EVault Agent v8.0 for Microsoft Windows (64-bit) - Exchange Plug-in Guide.pdf를 다운로드할 수 있도록 {{site.data.keyword.BluVPN}}의 {{site.data.keyword.BluSoftlayer_full}} 네트워크에 연결하십시오. 이 안내서는 Exchange 플러그인을 사용하여 Microsoft Exchange 데이터베이스를 백업하고 복원하는 방법에 대해 설명합니다. 이 안내서는 Granular Restore for Microsoft Exchange 애플리케이션을 사용하여 특정 메일함, 메시지 또는 기타 오브젝트를 .pst 파일로 복원할 수 있도록 DR 백업 safeset를 공유하는 방법도 설명합니다. 


