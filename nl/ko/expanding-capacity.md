---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}


# 저장소 용량 확장

현재 {{site.data.keyword.BluSoftlayer_full}} 사용자는 저장소의 크기를 4000GB까지 확장할 수 있습니다. 복제본을 작성하거나 데이터를 더 큰 볼륨으로 수동으로 마이그레이션하지 않아도 됩니다. 한계 증가가 적용되면 저장소에 대한 액세스 부족 또는 가동 중단이 없습니다.

## 증가 주문

1. [{{site.data.keyword.cloud_notm}} 콘솔](https://console.bluemix.net/catalog/){:new_window}에 로그인하여 왼쪽 상단의 **메뉴** 아이콘을 클릭하십시오. **일반 인프라**를 선택하십시오. 

   또는 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}에 로그인할 수 있습니다. 
2. **스토리지** > **백업**을 클릭하여 백업 서비스의 서버를 표시하십시오. 
3. 확장할 저장소를 선택하십시오.
4. **조치**를 클릭하고 **{{site.data.keyword.backup_notm}} 수정**을 선택하십시오.
5. 다음 화면에서 새 크기를 선택하고 **업그레이드**를 클릭하십시오.

## 비용 청구

볼륨에 대한 비용 청구는 현재 청구 주기에 새 가격의 일할 계산된 차이를 추가하도록 자동으로 업데이트됩니다. 다음 청구 주기에는 전체 새 금액이 청구됩니다.

동일한 프로세스를 {{site.data.keyword.backup_notm}}의 다운사이징에 사용할 수 있습니다.
{:tip}
