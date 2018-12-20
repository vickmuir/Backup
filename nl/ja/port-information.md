---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# バックアップ・エージェントと {{site.data.keyword.backup_notm}} ポータル間の通信を可能にするためのポートの構成

サーバーにインストールされている {{site.data.keyword.backup_full}} エージェントが、購入したボールトと通信できる必要があります。 {{site.data.keyword.backup_notm}} ユーザー・アカウント用の {{site.data.keyword.backup_notm}} Director のホスト情報は、[{{site.data.keyword.slportal}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){:new_window} と [{{site.data.keyword.cloud_notm}} コンソール](https://{DomainName}/catalog/){:new_window} で参照できます。

{{site.data.keyword.backup_notm}} ポータルおよび {{site.data.keyword.backup_notm}} Director にエージェントを登録する際には、必ず FQDN を使用します。これらのサービスの IP アドレスが変更される可能性があるためです。

{{site.data.keyword.backup_notm}} ポータルが適切に動作するためには、データ・センターの場所に関係なく、サーバーが {{site.data.keyword.backup_notm}} ポータルおよびすべての AMP プロキシー・サーバーと通信する必要があります。

```
evregister.service.softlayer.com TCP 8086,8087
```

{{site.data.keyword.backup_notm}} ポータルに登録されているより多くの {{site.data.keyword.backup_notm}} エージェントを処理するために、必要に応じて、AMP プロキシー・サーバーをさらに追加できます。

TCP Port 8086、8087 から 10.0.0.0/8 にアクセスできる必要があります。

より限定的なファイアウォール・ルールを使用する必要がある場合は、インフラストラクチャーが拡張されるのに伴い {{site.data.keyword.backup_notm}} ポータルにアクセスできなくなる可能性があります。 現時点では、TCP ポート 8086、8087 について、最低でも 10.0.82.0/24 サブネットおよび 10.2.118.0/24 サブネットへのアクセスがサーバーにより許可されている必要があります。 将来的に、必要に応じてその他のサブネットも使用できます。

## 商用

*{{site.data.keyword.backup_notm}} ポータルおよび AMP プロキシー・サーバー*

- ev-webcc01.service.softlayer.com [10.0.82.12] 8086、8087
- evregister.service.softlayer.com [10.0.82.12] 8086、8087

*商用 AMP プロキシー・サーバー*

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

## 官公庁

*{{site.data.keyword.backup_notm}} ポータルおよび AMP プロキシー*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086、8087

エージェントは、プライベート・ネットワーク上の TCP ポート 2548 インバウンドを許可する必要があります。 この設定により、CentralControl および {{site.data.keyword.backup_notm}} ポータルは、エージェントに接続してこれを管理できます。 旧バージョンの EVault では、ポート 808 が使用されていました。

{{site.data.keyword.backup_notm}} 管理ポート (2548) を変更するには、Windows オペレーティング・システムのレジストリー・キー `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber` (`dword`) を更新します。

接続設定に関して、デスクトップ CentralControl とエージェントの違いは、誤解されやすい点です。 サーバー常駐エージェントは {{site.data.keyword.backup_notm}} サーバーに接続しますが、デスクトップで使用される CentralControl は、サーバーのアドレスとそのアドレスにアクセスするためのサーバーの資格情報を使用して、サーバーに接続します。
{:tip}
