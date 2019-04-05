---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud backup, EVault, Carbonite, backup, backup frequency, backup types, backup retention scheme, plugins, delta technology, open files, pricing

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:faq: data-hd-content-type='faq'}


# FAQ
{: #faqs}

## 백업할 수 있는 애플리케이션의 유형은 무엇입니까?
{: faq}

{{site.data.keyword.backup_full}}을 사용하여 다양한 애플리케이션을 백업할 수 있습니다. {{site.data.keyword.BluSoftlayer_full}}에서는 다음을 포함하여 백업된 추가 공통 소프트웨어 시스템 중 일부에 대한 소프트웨어 에이전트도 제공합니다.

- [Bare Metal Restore](/docs/infrastructure/Backup?topic=Backup-BMRplugin)
- [Microsoft Exchange](/docs/infrastructure/Backup?topic=Backup-Exchangeplugin)
- [Microsoft SQL](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin#MSSQLplugin)
- [Oracle](/docs/infrastructure/Backup?topic=Backup-Oracleplugin#Oracleplugin)
- [VMware VRA](/docs/infrastructure/Backup?topic=Backup-VRA#VRA)

여기에 나열된 플러그인은 Oracle 플러그인을 제외하고 오직 Windows 서버와만 호환 가능합니다. 각 에이전트는 백업 서비스에 대한 추가 기능으로서 무료로 사용 가능합니다.

<hr>

## 얼마나 자주 데이터를 백업할 수 있습니까?
{: faq}

{{site.data.keyword.backup_notm}} 포털 내에서 백업은 수동으로 이루어지거나 단일 인스턴스로서 또는 반복되도록 스케줄될 수 있습니다. 반복 백업은 매일, 매주, 매월 또는 사용자 정의 스케줄에 따라 이루어질 수 있으며, 언제든지 업데이트나 취소가 가능합니다.

일별 또는 시간별로 여러 번 실행되는 매우 빈번한 백업으로 인해 백업 작업이 손상될 수 있습니다. 이러한 손상은 백업 저장소가 필수 백그라운드 유지보수 태스크 실행을 위한 충분한 시간을 갖지 못하기 때문에 발생합니다. 백업 작업은 유지보수 태스크에 우선합니다. 따라서 백업이 매우 빈번하게 수행되는 경우, 저장소는 계속해서 백업 작업을 실행하며 safe-set 수가 증가됩니다.
{:note}

<hr>

## 보유 스킴은 어떻게 작동됩니까?
{: faq}

{{site.data.keyword.backup_notm}}에서는 원하는 롤백 기간에 따른 데이터 보유를 허용합니다. **일별** 보유 스킴은 7일 동안 데이터를 보유하고, **주별** 스킴은 1개월 동안 데이터를 보유하며, **월별** 스킴은 1년 동안 데이터를 보유합니다. 각 기간이 종료되면 가장 오래된 데이터 세트부터 차례로 제거되며 첫 번째 작성된 "델타 백업"이 가장 오래된 사용 가능한 복원 지점이 됩니다.

기본 보유 스킴을 수정하여 사용자 정의 보유 스킴을 작성할 수 있습니다. 그러나 IBM에서는 기본 보유를 시작점으로 사용하도록 권장합니다. 새 보유 스킴을 작성하거나 기존 보유 스킴을 수정할 때 아카이브 옵션을 선택하지 않아야 합니다. 아카이브는 지원되지 않습니다.
{:tip}

<hr>

## 델타 기술은 무엇입니까?
{: faq}

첫 번째 백업은 "시드"(완전한 전체 백업)이고 다음의 후속 백업은 "델타"(즉, 변경사항만 백업)이지만, 이 둘은 동일하며 여전히 "전체 백업"으로 간주됩니다. 즉, 모두를 복원하거나 그 중에서 임의의 파일을 복원할 수 있습니다. 이 기술을 사용하면 각 세션마다 "전체 백업"이 작성되지만 저장소에서 상당한 양의 공간이 절감되며 각 후속 백업을 완료하는 데 걸리는 시간이 감소됩니다.

<hr>

## 백업이 안전합니까?
{: faq}

기본적으로 모든 암호화 OTW(Over The Wire)는 AES 256비트 암호화로 암호화됩니다. AES 256비트를 사용하여 암호화된 형식으로 데이터 저장을 선택할 수도 있습니다.

암호화 비밀번호를 반드시 기억하고 있어야 합니다. 비밀번호가 없으면 데이터를 복원할 수 없습니다. 비밀번호를 유실한 경우 데이터를 다시 가져올 수 없습니다.
{:important}

압축 비율은 제로(zero) 압축에서 최대 비율 압축을 허용하며, 이는 파일 유형에 따라 20퍼센트 - 30퍼센트로 압축될 수 있습니다.

<hr>

## 시스템 상태 백업으로 저장되는 정보는 무엇입니까?
{: faq}

시스템 상태 백업에는 COM + 클래스 등록 데이터베이스, 레지스트리, 부트 파일, 시스템 파일, 성능 카운터 등이 포함되지만 이로 제한되지는 않습니다. 이 모두는 시스템에 따라 다릅니다. 시스템 파일은 시스템 O/S 및 서비스 팩에 따라 다릅니다. 일반적으로 이는 수 천개입니다. 사용자가 백업에 포함할 때 MS Windows는 이러한 DLL의 동적 목록을 작성합니다. 시스템 파일을 포함하면 손상된 시스템 파일에서 또는 실수로 일부 서비스 팩을 제거하거나 Bare Metal Restore으로 복구하고자 할 때 복구가 가능합니다. 설치 킷에서 O/S 재설치 이후 각 서비스 팩을 별도로 설치하지 않아도 백업 상태로 돌아갈 수 있습니다.

사용자 데이터 파일은 시스템 상태 백업에 포함되지 않습니다. 시스템 상태 백업 작업은 독립형 작업으로 구성되어야 합니다. 시스템 상태 백업 작업에 포함된 다른 데이터 소스가 없어야 합니다.
{:important}

<hr>

## 오픈 파일은 어떻게 됩니까?
{: faq}

기본적으로 기본 클라이언트에는 OS에서 실행 중인 대부분의 오픈 파일을 처리하기 위한 첨단 기술이 있습니다.

<hr>

## 가격에 대한 정보를 어디서 찾을 수 있습니까?
{: faq}

자세한 정보는 [백업 스토리지 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/backup-and-restore){:new_window} 및 [EVault on IBM Cloud: 가격 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.ibm.com/cloud/backup/pricing){:new_window}을 참조하십시오.

<hr>

## 백업을 조정하지 않고 {{site.data.keyword.backup_notm}} 용량을 늘리거나 줄일 수 있습니까?
{: faq}

[{{site.data.keyword.slportal}} ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://control.softlayer.com/){:new_window}을 통해 저장소의 크기를 늘리거나 줄일 수 있습니다. 용량 수정은 저장소에 저장된 데이터의 무결성에 영향을 주지 않습니다. 자세한 정보는 [용량 확장](/docs/infrastructure/Backup?topic=Backup-expandcapacity#expandcapacity)을 참조하십시오.

<hr>

## {{site.data.keyword.backup_notm}} 용량이 초과되면 어떻게 됩니까?
{: faq}

이전에 구매한 용량의 한계에 도달한 경우에도 백업을 저장하고 검색할 수 있습니다. 그러나 사용한 추가 GB당 추가 비용을 다음 번 청구서에서 받게 됩니다.

<hr>

## 내 백업이 실패하는 경우 알림을 받으려면 {{site.data.keyword.backup_notm}} 포털에서 알림을 어떻게 설정할 수 있습니까?
{: faq}

고급 탭에서 알림을 설정할 수 있습니다. {{site.data.keyword.backup_notm}} 포털의 **빠른 링크**에 있는 지시사항을 따르십시오.

<hr>

## BMR 플러그인을 사용할 때 단일 디스크에서 RAID 어레이로 이동할 수 있습니까?

예, 그렇습니다. 하지만 RAID 어레이로 인해 크기가 감소되므로 대용량 디바이스를 선택해야 합니다.

<hr>

## BMR 플러그인을 사용할 때 원래 볼륨보다 큰 디스크로 이미지를 복원하면 어떻게 됩니까?
{: faq}

원래 볼륨보다 큰 디스크로 이미지를 복원하면 남은 공간이 할당 해제됩니다. 따라서, 예를 들어 500GB 드라이브를 보유 중이며 1TB 디스크로 해당 데이터를 복원하면 500GB의 디스크 공간이 할당 해제됩니다. Windows 2008에서는 기본 제공 디스크 유틸리티를 사용하여 기본 파티션을 늘릴 수 있습니다. 하지만 Windows 2003에는 유사한 기본 제공 용량이 없으므로 다른 방식으로 공간을 할당해야 합니다.

<hr>

## 일반 백업에 BMR을 사용할 수 있습니까?
{: faq}

BMR 백업은 디스크 이미지가 아니라 시스템 볼륨 이미지 백업 시스템입니다. 시스템은 일반 백업 용도는 아니지만 이와 함께 사용됩니다.  

<hr>

##데이터베이스 백업에 BMR을 사용할 수 있습니까?
{: faq}

데이터베이스 백업은 일반 {{site.data.keyword.backup_notm}} 방법과는 별도로 수행되어야 합니다. BMR이 있어도 SQL 또는 Oracle 플러그인은 여전히 필요합니다. BMR이 VSS 기술을 사용하여 오픈 파일을 백업하지만, 백업 파일의 트랜잭션 일관성을 항상 보장할 수는 없습니다. 이러한 유형의 특수 애플리케이션에 대해 두 개의 백업 작업을 작성하도록 권장합니다(하나는 OS 및 애플리케이션 2진 파일 백업용이며 다른 하나는 애플리케이션 데이터용임).

<hr>

## BMR에서 어떤 유형의 복원 작업을 실행할 수 있습니까?

전체 시스템 복원을 수행하거나 복원할 백업에서 개별 파일을 선정할 수 있습니다. BMR 백업 작업은 현재 파일 백업 작업을 대체할 수 있습니다. 복원 프로세스는 기존의 백업 작업처럼 OS 내에서 수행됩니다.

<hr>

## BMR에 오픈 파일 백업 기능이 있습니까?
{: faq}

BMR에는 오픈 파일 백업 기능이 있습니다. 그러나 BMR이 있어도 SQL 또는 Oracle 플러그인은 여전히 필요합니다. MSSQL 플러그인 설치 지시사항을 보려면 [여기를](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin) 클릭하십시오.

<hr>

## BMR 복원에 필요한 디스크 공간과 시간은 얼마나 됩니까?
{: faq}

기본 설치에서 작성된 백업은 약 6GB를 사용합니다. 이러한 복원은 1GB 포트에서 약 15분 정도 걸립니다. 이 프로세스는 개인용 포트 속도의 영향도 받습니다. 보다 빠른 백업 및 복원이 필요하면 포트 속도를 늘려야 할 수 있습니다.

<hr>

## VSS(Volume Shadow Copy Services)의 역할은 무엇입니까?
{: faq}

SQL Server 플러그인의 현재 버전은 VSS(Volume Shadow Copy Services)를 사용하여 백업을 완료합니다. SQL Server 플러그인은 VSS를 사용하여 SQL 데이터베이스, 심지어 여러 볼륨에 있는 SQL 데이터베이스도 효율적으로 백업합니다. 애플리케이션이 볼륨에 계속 쓰는 동안 백업을 완료할 수 있습니다. SQL Server 플러그인은 데이터베이스 내에서 그리고 전체에서 데이터 일관성을 제공합니다. VSS를 사용하면 동시에 여러 백업을 실행할 수 있습니다.

<hr>

## Windows 8용 EVault의 32비트 버전이 여전히 지원됩니까?
{: faq}

아니요. 백업 소프트웨어 에이전트의 32비트 버전은 Windows Server 2008 Standard 및 Datacenter Edition과 함께 2017년 3월에 사용이 중지되었습니다.
