---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# 백업 에이전트와 WebCC 간의 통신을 허용하도록 포트 구성

서버에 설치된 {{site.data.keyword.backup_full}} 에이전트는 사용자가 구매한 저장소와 통신할 수 있어야 합니다. {{site.data.keyword.backup_notm}} 사용자 계정에 대한 {{site.data.keyword.backup_notm}} Director 호스트 정보는 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} 및 [{{site.data.keyword.cloud_notm}} 콘솔](https://console.bluemix.net/catalog/){:new_window}에서 찾을 수 있습니다. 

이러한 서비스의 IP 주소가 변경될 수 있으므로, 항상 FQDN을 사용하여 에이전트를 WebCC 및 {{site.data.keyword.backup_notm}} Director에 등록하십시오. 

데이터 센터 위치와 무관하게 WebCC가 제대로 작동될 수 있도록 사용자의 서버는 WebCC 및 모든 AMP 프록시 서버와 통신해야 합니다.

```
evregister.service.softlayer.com TCP 8086,8087
```

필요에 따라 AMP 프록시 서버를 더 추가하여 WebCC에 등록된 추가 {{site.data.keyword.backup_notm}} 에이전트를 처리할 수 있습니다. 

TCP 포트 8086, 8087은 10.0.0.0/8에 액세스할 수 있어야 합니다.

보다 제한적인 방화벽 규칙의 사용이 필요한 경우 인프라가 확장되면서 WebCC에 대한 액세스가 유실될 수 있습니다. 현재는 최소한 서버가 TCP 포트 8086, 8087의 10.0.82.0/24 및 10.2.118.0/24 서브넷에 대한 액세스를 허용해야 합니다. 필요하면 나중에 다른 서브넷을 사용할 수 있습니다.

## 상용

*WebCC 및 AMP 프록시 서버*

- ev-webcc01.service.softlayer.com [10.0.82.12] 8086, 8087
- evregister.service.softlayer.com [10.0.82.12] 8086, 8087

*상용 AMP 프록시 서버*

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

## 연방

*WebCC 및 AMP 프록시*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087

에이전트는 사설 네트워크에서 포트 TCP/2548 인바운드를 허용해야 합니다. 이 설정에서는 CentralControl 및 WebCC가 관리를 위해 에이전트에 연결할 수 있도록 허용합니다. 이전 버전의 EVault에서는 포트 808을 사용했습니다.

{{site.data.keyword.backup_notm}} 관리 포트(2548)는 Windows 운영 체제의 `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber`에서 레지스트리 키(`dword`)를 업데이트하여 변경될 수 있습니다. 

연결 설정과 관련하여 데스크탑 CentralControl과 에이전트 간의 차이점에는 종종 애매한 점이 있습니다. 서버 상주 에이전트는 {{site.data.keyword.backup_notm}} 서버에 연결하지만, 데스크탑 활용 CentralControl은 해당 주소 및 이에 액세스하기 위한 서버의 인증 정보를 사용하여 서버에 연결합니다.
{:tip}
