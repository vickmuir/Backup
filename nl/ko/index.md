---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-28"

keywords: IBM Cloud backup, EVault, Carbonite, IBM Cloud backup, Enterprise backup

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# {{site.data.keyword.backup_notm}} 프로비저닝
{: #ordering}

두 가지 방법으로 {{site.data.keyword.backup_notm}} 서비스를 구매할 수 있습니다.

- [서버 주문 시 백업 구매](#purchasingwithserver).
- [업그레이드로서 백업 구매](#purchasingasupgrade).

가격에 관한 자세한 정보는 [{{site.data.keyword.backup_notm}} 스토리지 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/backup-and-restore){:new_window} 및 [{{site.data.keyword.backup_notm}} on IBM Cloud ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/backup/pricing){:new_window}를 참조하십시오.

## 서버 주문 시 {{site.data.keyword.backup_notm}} 구매
{: #purchasingwithserver}

1. [IBM Cloud 카탈로그 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/catalog){:new_window} 또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인하십시오.
2. 월별 베어메탈 서버를 주문하십시오. 베어메탈 서버 주문에 대한 자세한 정보는 [사용자 정의 Bare Metal Server 빌드](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server#ordering-baremetal-server){:new_window}를 참조하십시오.
   1. 수량, 청구 옵션을 선택하십시오. 호스트 및 도메인 이름을 입력하십시오. 원하는 호스트 이름과 도메인을 선택할 수 있습니다.

      시간별 비용 청구되는 서버를 주문할 때는 {{site.data.keyword.backup_notm}} 서비스를 사용할 수 없습니다. 그러나 이 서비스는 나중에 업그레이드로서 추가될 수 있습니다.
      {:tip}
   2. 위치를 선택하십시오.
   3. 서버 구성 및 OS 이미지 유형을 선택하십시오. 다수의 추가 기능을 선택할 수도 있습니다.
   4. **스토리지 디스크** 섹션 아래에서 **추가 기능**을 클릭하고 **{{site.data.keyword.backup_notm}}**을 선택하십시오. 필요사항과 일치하는 옵션을 선택하십시오.
   5. **네트워크 인터페이스** 아래에서 원하는 추가 기능과 업링크 포트 속도를 선택하십시오.
3. 오른쪽에서 주문 요약을 검토하십시오.
4. 이용 약관의 검토를 마치면 **서드파티 서비스 계약서를 읽었으며 이에 동의합니다** 상자를 선택하십시오.
5. **프로비저닝**을 클릭하십시오. 사용자는 프로비저닝 주문 번호가 있는 화면으로 경로 재지정됩니다. 프로비저닝 주문 영수증이기도 하므로 사용자는 화면을 인쇄할 수 있습니다.

   **견적서로 저장**을 클릭하여 구매 없이 이 주문을 저장할 수도 있습니다.
   {:tip}

일련의 이메일이 관리자에게 발송됩니다(프로비저닝 주문의 수신확인, 프로비저닝 주문 승인 및 처리, 프로비저닝 완료). 프로비저닝 완료 이메일에는 {{site.data.keyword.cloud_notm}}에 로그인한 후에 액세스할 수 있는 *디바이스 세부사항* 페이지에 대한 링크가 포함됩니다. {{site.data.keyword.slportal}}에 직접 로그인할 수도 있습니다.

### {{site.data.keyword.backup_notm}} 구매 확인
1. [{{site.data.keyword.cloud_notm}} 콘솔 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}){:new_window}의 왼쪽 상단에서 **메뉴** 아이콘을 클릭하십시오. **클래식 인프라**를 선택하십시오. </br>
    또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. **디바이스** > **디바이스 목록**을 클릭하십시오.
2. 주문한 새 서버를 찾으십시오.
  - url 옆에 시계 아이콘이 표시되면 잠시 대기한 후에 {{site.data.keyword.backup_notm}} 구매 확인을 진행해야 합니다. 페이지를 새로 고쳐서 새 서버에서 업데이트된 상태를 볼 수 있습니다. 시계 아이콘이 사라지면 다음 단계를 진행하여 {{site.data.keyword.backup_notm}} 서비스 구매를 확인할 수 있습니다.
  - 시계 아이콘이 더 이상 서버에 대해 표시되지 않으면 링크(서버의 url)를 클릭하여 **디바이스 세부사항** 페이지로 이동하십시오.
3. **스토리지** 탭을 클릭하여 {{site.data.keyword.backup_notm}} 정보를 표시하십시오.
4. {{site.data.keyword.backup_notm}} 섹션을 검사하여 구매 프로세스 중에 선택된 크기가 표시되는지 확인하십시오.

## 업그레이드로서 {{site.data.keyword.backup_notm}} 구매
{: #purchasingasupgrade}

### {{site.data.keyword.backup_notm}}이 설치될 서버 선택

1. [{{site.data.keyword.cloud_notm}} 콘솔 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}){:new_window}에 로그인하여 왼쪽 상단에서 **메뉴** 아이콘을 클릭하십시오. **클래식 인프라**를 선택하십시오. </br>
    또는 [{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다.
2. 기본 메뉴에서 **디바이스** > **디바이스 목록**을 선택하십시오. 백업 서비스를 추가하려는 디바이스를 찾으십시오.
3. 디바이스 이름을 클릭하여 **디바이스 세부사항** 페이지로 이동하십시오.

### {{site.data.keyword.backup_notm}} 서비스 추가(구매)
1. **스토리지** 탭을 클릭하고 스크롤 다운하여 {{site.data.keyword.backup_notm}} 섹션을 찾으십시오.
2. **추가** 링크를 클릭하십시오.
3. 창에서 위치를 선택하고 크기를 선택하십시오.
4. 지불 유형을 선택하고 **계속**을 클릭하십시오.
5. **프로모션 코드**가 있으면 이를 입력하고 **재계산**을 클릭하십시오.
6. 주문을 검토하고 링크를 클릭하여 이용 약관을 읽으십시오.
7. 이용 약관에 동의하면 선택란을 클릭하십시오.
7. **주문하기**를 클릭하십시오.

### {{site.data.keyword.backup_notm}} 업그레이드 구매 확인
1. **디바이스 세부사항** 페이지를 새로 고치고 **스토리지** 탭이 선택되었는지 확인하십시오.
2. {{site.data.keyword.backup_notm}} 섹션을 검사하여 구매 프로세스 중에 선택된 크기가 표시되는지 확인하십시오.

   백업 스토리지 크기가 계속해서 용량 영(0)을 표시하면 두 번째 페이지를 새로 고쳐야 할 수 있습니다.
   {:tip}

준비가 완료되면 서버에 소프트웨어 에이전트를 설치하고 {{site.data.keyword.backup_notm}} 포털에서 백업 스케줄을 설정하십시오. 자세한 정보는 [시작하기 튜토리얼](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started)을 참조하십시오.
