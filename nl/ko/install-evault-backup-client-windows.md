---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-14"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Windows에서 EVault 백업 클라이언트 설치

Windows에서 EVault 백업 클라이언트 설치는 EVault 백업 서비스용으로 지정된 서버에 로그인하는 동안 일련의 상호작용을 통해 완료됩니다. 아래의 단계에 따라 Windows에서 EVault 백업 클라이언트를 설치하십시오. 

**참고**: Windows 2016은 현재 지원되지 않습니다. 

## 대상 디바이스 서버에 로그인

1. [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}에 로그인하고 기본 메뉴에서 **디바이스** > **디바이스 목록**을 선택하여 사용 가능한 서버 디바이스의 목록을 보십시오. 
2. EVault 서비스가 구매된 대상 디바이스를 찾고 이의 공인 IP 주소를 기록하십시오. 
3. 오른쪽을 지시하는 확장 화살표를 클릭하여 사용자 이름과 비밀번호를 포함하여 디바이스에 대한 추가 정보를 표시하십시오. 비밀번호가 표시되지 않은 경우, **비밀번호 표시** 선택란을 클릭하면 비밀번호가 표시됩니다.  
4. 원격 데스크탑 연결을 사용하여 대상 디바이스에 로그인하십시오. 

## EVault 클라이언트 다운로드

1. 대상 서버에서 브라우저 세션을 열고 다음의 URL을 입력하여 EVault 백업 클라이언트에 대한 실행 파일을 다운로드하십시오. <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}
  
2. 다운로드된 파일을 두 번 클릭하고 나타나는 팝업 상자에서 **실행**을 클릭하십시오. 


## EVault 에이전트 설치 및 등록
 
1. 네트워크 주소를 입력하십시오. <br />
  ```
  ev-webcc01.service.softlayer.com
  ```
  {: pre}
  
2. **사용자 이름** 필드에 EVault 백업 사용자 이름을 입력하십시오.  
3. **비밀번호** 필드에 EVault 백업 비밀번호를 입력하십시오.  
6. **다음**을 클릭하십시오.  
7. **설치**를 클릭하여 설치를 완료하십시오. 

## 다음 단계

WebCC에 로그인하여 백업 에이전트를 구성하고 관리합니다. 지시사항은 [시작하기 튜토리얼](index.html#configuring-evault-agent-in-webcc)을 참조하십시오. 
