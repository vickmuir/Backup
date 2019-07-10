---

copyright:
  years: 1994, 2019
lastupdated: "2019-06-10"

keywords: IBM Cloud backup, EVault, Carbonite, backup, expanding vault

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}


# 저장소 용량 확장
{: #expandcapacity}

현재 {{site.data.keyword.cloud}} 사용자는 저장소의 크기를 4000GB까지 확장할 수 있습니다. 복제본을 작성하거나 데이터를 더 큰 볼륨으로 수동으로 마이그레이션하지 않아도 됩니다. 한계 늘리기 프로세스를 수행해도 가동 중단 또는 액세스 권한 부족이 발생하지 않습니다.

## 증가 주문

1. [{{site.data.keyword.cloud_notm}} 콘솔](https://{DomainName}){: external}에 로그인하여 왼쪽 상단의 **메뉴** 아이콘을 클릭하십시오. **클래식 인프라**를 선택하십시오.
2. **스토리지** > **백업**을 클릭하여 백업 서비스의 서버를 표시하십시오.
3. 확장할 저장소를 선택하십시오.
4. **조치**를 클릭하고 **{{site.data.keyword.backup_notm}} 수정**을 선택하십시오.
5. 다음 화면에서 새 크기를 선택하고 **업그레이드**를 클릭하십시오.

## 비용 청구

볼륨에 대한 비용 청구는 현재 청구 주기에 새 가격의 일할 계산된 차이를 추가하도록 자동으로 업데이트됩니다. 다음 청구 주기에는 전체 새 금액이 청구됩니다.

동일한 프로세스를 {{site.data.keyword.backup_notm}}의 다운사이징에 사용할 수 있습니다.
{:tip}
