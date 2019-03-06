---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:codeblock: .codeblock}
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Linux에서 백업 클라이언트 설치
{: #InstallinLinux}

Linux 기반 운영 체제에서 {{site.data.keyword.backup_full}} 클라이언트 설치는 OS 내의 쉘이나 터미널에서 일련의 명령을 통해 수행될 수 있습니다. 이 프로시저에서는 다음의 Linux 기반 운영 체제에서 클라이언트를 설치하는 데 필요한 단계를 간략하게 설명합니다.

- RHEL
- CentOS
- CloudLinux

프로시저를 완료한 후 자동화된 프로세스가 {{site.data.keyword.backup_notm}} 포털에 에이전트 서비스를 등록한 다음 서비스 실행에 필요한 파일을 다운로드하고 설치합니다.

[{{site.data.keyword.cloud_notm}} 카탈로그](https://{DomainName}/catalog/){:new_window} 또는 {{site.data.keyword.slportal}}을 통해 서버를 주문할 때 {{site.data.keyword.backup_notm}}을 구매한 경우에는 소프트웨어가 자동으로 설치됩니다. 이 문서에 설명된 프로시저를 사용하지 않아도 됩니다.
{:tip}

{{site.data.keyword.slportal}}에서 업그레이드로서 {{site.data.keyword.backup_notm}}을 구매한 경우에는 아래의 단계에 따라 소프트웨어를 설치하십시오.

## 대상 디바이스 서버에 로그인
{: #logintargetLin}

1. [{{site.data.keyword.cloud_notm}} 콘솔](https://{DomainName}/){:new_window}에 로그인하여 왼쪽 상단의 **메뉴** 아이콘을 클릭하십시오. **클래식 인프라**를 선택하십시오.<br/>
 또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. 기본 메뉴에서 **디바이스** > **디바이스 목록**을 선택하여 사용 가능한 서버 디바이스의 목록을 보십시오.
3. {{site.data.keyword.backup_notm}} 서비스가 구매된 대상 디바이스를 찾고 이의 공인 IP 주소를 기록하십시오.
  - 이 IP 주소는 다음 단계에서 UNIX 또는 Linux 명령행에서 디바이스에 로그인할 때 사용됩니다. 5단계에 표시된 명령에서 <publicIpAddress>를 실제 공인 IP 주소로 대체하십시오.
4. 오른쪽을 지시하는 화살표를 클릭하여 사용자 이름과 비밀번호를 포함해 디바이스에 대한 자세한 정보를 표시하십시오.
  - 비밀번호가 표시되지 않으면 **비밀번호 표시**를 클릭하여 나타나도록 할 수 있습니다. 사용자 이름과 비밀번호는 다음 단계에서 테스트 디바이스에 로그인하는 데 사용됩니다. `<user name>`을 실제 사용자 이름으로 대체하십시오.
5. UNIX 또는 Linux 명령행에서 다음 명령을 입력하여 대상 디바이스에 로그인하십시오.
   ```
  ssh <user name>@<publicIpAddress>
   ```
   {: pre}

   이전에 이 사용자 이름으로 이 서버에 로그인하지 않은 경우에는 호스트의 진위성에 대한 메시지가 표시됩니다. 또한 계속할지 여부를 묻는 질문이 표시됩니다. 계속하려면 **예**로 응답하십시오.
   {:note}

6. 이 서버에 액세스하기 위한 ssh 키를 이전에 설정하지 않았으면 비밀번호를 입력하라는 프롬프트가 표시됩니다.

## 설치 준비를 위해 OS 업데이트(RHEL만 해당)

이 단계는 RHEL의 경우에는 필수이지만 기타 Linux 배포의 경우에는 선택사항입니다.
{:tip}

- 서버 프롬프트에서 다음 명령을 실행하십시오.
  ```
  yum update
  ```
  {: pre}

  프롬프트가 표시되면 다운로드 크기가 올바른지 확인하십시오. 업데이트가 진행되며 완료되면 "완료" 메시지가 표시됩니다.

## 설치 스크립트 가져오기

- 서버 프롬프트에서 다음 명령을 실행하십시오.
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}

## 설치 스크립트 실행

1. 서버 프롬프트에서 다음 명령을 실행하십시오.
   ```
  sh ./evault_manual.sh
   ```
   {: pre}

2. {{site.data.keyword.backup_notm}} 포털 사용자 이름과 비밀번호를 입력하십시오.

   {{site.data.keyword.backup_notm}} 사용자 이름과 비밀번호 보기에 대한 자세한 정보는 [백업 서비스 시작하기](/docs/infrastructure/Backup?topic=Backup-GettingStarted)를 참조하십시오.
   {:tip}

3. 사용자 이름과 비밀번호 이후에는 추가 입력이 필요하지 않습니다. 설치가 진행되면서 화면에 나타나는 프롬프트는 무시해도 됩니다.

   이는 `evault_manual.sh` 스크립트에서 시작되는 서브스크립트에 의해 생성됩니다. `evault_manual.sh` 스크립트는 이러한 프롬프트에 대한 입력을 제공합니다.
   {:note}

4. 다음 메시지가 표시되면 설치가 완료된 것입니다.

   ```
  Starting VVAgent: [  OK  ]
   Starting buagent: [  OK  ]
   ```
   {: codeblock}

## 설치 완료 확인

1. 설치 출력에 "포털에 등록됨" 메시지가 표시되는지 확인하십시오. 화면의 메시지를 보거나 다음 명령의 출력을 검사하여 확인할 수 있습니다.
   ```
  grep 'Registered'  /opt/BUAgent/Install.log
   ```
   {: pre}

2. 다음 명령을 실행하고 출력을 살펴보십시오.
   ```
  service vvagent status
   ```
   {: pre}

   다음 메시지가 표시됩니다.
   ```
  VVAgent is running (PID xxxxx).
   buagent is running (PID xxxxx).
   ```
   {: codeblock}

  `xxxxx`로 표시되는 프로세스 ID는 각 설치마다 다릅니다.
  {:tip}

**다음 단계**

{{site.data.keyword.backup_notm}} 포털에 로그인하여 백업 에이전트를 구성하고 관리하십시오. 자세한 정보는 [시작하기 튜토리얼](/docs/infrastructure/Backup?topic=Backup-GettingStarted) 및 [Linux에서 단순 파일 레벨 백업 구성](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup)을 참조하십시오.
