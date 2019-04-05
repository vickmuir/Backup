---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, upgrade agent, Linux

subcollection: Backup

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Linux용 백업 소프트웨어 에이전트 업그레이드
{: #UpgradeinLinux}

최신 백업 에이전트는 {{site.data.keyword.backup_notm}} 포털 대시보드 빠른 링크 섹션에서 다운로드할 수 있습니다.
{:tip}

업그레이드 프로세스 다음에 등록을 잃지 않고 {{site.data.keyword.backup_notm}} 에이전트를 업그레이드할 수 있는지 확인하십시오.

1. 루트 레벨에서 호스트에 로그인하십시오.
2. 에이전트의 최신 버전을 다운로드하십시오.
   ```
   wget -N downloads.service.softlayer.com/evault/Agent-Linux-x64-8.11.5251.tar.gz2
   ```
   {:pre}

3. 다운로드한 파일의 컨텐츠를 추출하십시오.

   ```
   tar -xzvf Agent-Linux-x64-8.11.5251.tar.gz3
   ```
4. 최근 설치 디렉토리로 이동하십시오.
   ```
   cd Agent-Linux-x64-8.11.5251/4
   ```

5. 설치 스크립트를 실행하십시오.
   ```
   ./install.sh
   ```
   {:pre}

6. 프롬프트에 응답하여 컴퓨터를 새 호스트로 등록하지 않게 `N`을 선택하고, 통합 암호화 방법을 사용하여 데이터를 암호화하도록 `A`를 선택하십시오.

7. 설치에 성공하면 `/opt/BUAgent/Install.log`에 기록됩니다.
