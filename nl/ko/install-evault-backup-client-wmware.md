---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-03"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# VMware용 EVault 백업 클라이언트 설치

VMware 서버에 EVault 백업 클라이언트 설치는 대상 ESX 서버 내의 쉘이나 터미널에서 일련의 명령을 통해 수행될 수 있습니다. 이 프로시저에서는 VMware 서버에 EVault 백업 클라이언트를 설치하는 데 필요한 단계를 간략하게 설명합니다. 

에이전트를 설치하려면 다음 명령을 사용하여 `Agent-VMware-ESX-Server-6.71.<version-info>.tar.gz` 패키지를 다운로드하고 대상 ESX 서버에 복사하십시오. 

`wget -N http://downloads.service.softlayer.com/evault/archive/Agent-VMware-ESX-Server-6.71.2105.tar.gz`

**참고**: 대상 ESX 서버에서 로컬로 다음 단계를 수행해야 합니다. 

1. 패키지에서 파일의 압축을 푸십시오. 이를 수행하려면 다음 명령을 사용하십시오(여기서 “PACKAGENAME”은 “Agent-VMware-ESX-Server-6.71”일 수 있음).
    `tar xvfz PACKAGENAME.tar.gz`
2. 패키지의 압축이 풀린 디렉토리로 이동하십시오. 
3. 설치 스크립트를 실행하십시오.
    `# ./install.sh`

    **참고**: 설치 스크립트는 웹 등록(주소, 포트 번호와 인증) 및 로그 파일 이름 등의 구성 정보에 대해 대화식으로 프롬프트합니다. 
     
    - 이 서버의 WebCC 사용자 이름을 입력하십시오. 
    - 이 서버의 WebCC 비밀번호를 입력하십시오. 
     
4. WebCC 사용자 이름을 묻는 프롬프트에 대해 입력으로 **EVault 백업 사용자 이름**을 입력하십시오.  
5. WebCC 비밀번호를 묻는 프롬프트에 대해 입력으로 **EVault 백업 비밀번호**를 입력하십시오. 
6. 설치가 완료되면 완료 메시지가 나타나며 에이전트 디먼이 실행됩니다. 


### 기타 설치 참고사항: 
설치가 완료된 경우, Install.log는 설치 디렉토리에 있습니다.
예: `/opt/BUAgent/Install.log`

설치에 실패하고 롤백되는 경우, 설치 로그는 다음 위치에 있습니다. `<Installation Failure directory>`.
설치에 실패하고 롤백되지 않은 경우, 설치 로그는 다음 위치에 있습니다. `<Installation Kit directory>`.

자세한 정보를 보려면 [VMware_Agent_User_Guide](http://downloads.service.softlayer.com/evault/Documentation/VMware_Agent_User_Guide.pdf){:new_window}를 다운로드하십시오. 이 링크를 보려면 {{site.data.keyword.BluVPN}}에 연결되어 있는지 확인하십시오. 
