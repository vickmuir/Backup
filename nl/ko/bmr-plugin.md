---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-13"

keywords: IBM Cloud backup, bare metal restore, bmr, plug-in, plugin, EVault, Carbonite, baremetal, point-in-time restore

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# BMR(Bare Metal Restore) 플러그인에 대해 알아보기
{: #BMRplugin}

BMR은 재해 복구 솔루션입니다. BMR을 사용하여 운영 체제나 하드웨어 장애 등의 재해가 발생한 후에 베어메탈 상태에서 서버를 복원할 수 있습니다. BMR을 사용하면 {{site.data.keyword.cloud}}에서 관리하는 안전한 보안 위치에서 시스템 이미지를 빠르게 복원할 수 있습니다.

BMR은 실제 서버의 Microsoft Windows 전용 제품입니다. 이는 가상 서버에는 사용할 수 없습니다. Linux용 BMR(Bare Metal Restore) 배포는 지원되지 않습니다. 백업 에이전트 8.30 이하 버전에서만 BMR을 지원합니다. (2018년 6월 30일).
{:important}

## 제공되는 기능
{: #BMRcapabilities}

- 선택된 특정 시점으로 시스템을 복원합니다.
- 이미지 또는 파일 기반 백업에서 시스템을 복원합니다.
- {{site.data.keyword.backup_notm}}에 저장된 백업에서 시스템을 복원합니다.
- 부트 가능한 시스템이 없는 경우 데이터를 복원하는 데 사용할 수 있는 실행 가능한 복구 트랜잭션.

## BMR 플러그인 설치
{: #installingBMR}

플러그인은 Windows 에이전트 설치 중에 설치됩니다. 플러그인은 에이전트와 동시에 설치되거나, **수정**을 선택하여 설치를 재실행함으로써 나중에 설치될 수 있습니다.

## BMR 백업 작업 구성
{: #configBMRplugin}

자세한 정보는 [BMR 백업 작업 구성](/docs/infrastructure/Backup?topic=Backup-configureBMR)을 참조하십시오.

## BMR 시스템 볼륨 이미지 복원
{: #restoringBMimage}
자세한 정보는 [BMR 시스템 볼륨 이미지 복원](/docs/infrastructure/Backup?topic=Backup-restoreBMR)을 참조하십시오.

## 사용자 안내서 다운로드
{: #BMRUserGuide}

[다운로드 가능 {{site.data.keyword.backup_notm}} 문서](http://downloads.service.softlayer.com/evault/Documentation/){: external}에서 사용자 안내서에 액세스하여 다운로드할 수 있도록 {{site.data.keyword.BluVPN}}을 사용하여 {{site.data.keyword.cloud}} 네트워크에 연결하십시오.
