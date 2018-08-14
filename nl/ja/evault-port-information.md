---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-26"

---
{:new_window: target="_blank"}

# EVault エージェントと WebCC 間の通信を可能にするためのポートの構成

サーバーにインストールされている EVault エージェントが、購入したボールトと通信できる必要があります。 EVault ユーザー・アカウント用の EVault Director のホスト情報は、[{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}で参照できます。 

WebCC および EVault Director にエージェントを登録する際には、必ず FQDN を使用します。これらのサービスの IP アドレスが変更される可能性があるためです。 


```
evregister.service.softlayer.com TCP 8086,8087
```

WebCC が適切に動作するためには、データ・センターの場所に関係なく、サーバーが WebCC およびすべての AMP プロキシー・サーバーと通信する必要があります。 WebCC に登録されているより多くの EVault エージェントを処理するために、必要に応じて、AMP プロキシー・サーバーをさらに追加できます。 

TCP Port 8086、8087 から 10.0.0.0/8 にアクセスできる必要があります。 

より限定的なファイアウォール・ルールを使用する必要がある場合は、インフラストラクチャーが拡張されるのに伴い WebCC にアクセスできなくなる可能性があります。 現時点では、TCP ポート 8086、8087 について、最低でも 10.0.82.0/24 サブネットおよび 10.2.118.0/24 サブネットへのアクセスがサーバーにより許可されている必要があります。 将来的に、必要に応じてその他のサブネットも使用できます。

**商用**

*WebCC および AMP プロキシー・サーバー*

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

**連邦政府**

*WebCC および AMP プロキシー*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086、8087
 
エージェントは、プライベート・ネットワーク上のポート TCP/2548 インバウンドを許可する必要があります。 この設定により、CentralControl および WebCC は、エージェントに接続してこれを管理できます。 旧バージョンの EVault では、ポート 808 が使用されていました。

EVault 管理ポート (2548) を変更するには、Windows オペレーティング・システムのレジストリー・キー `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber` (`dword`) を更新します。

**説明**。接続設定に関して、デスクトップ CentralControl とエージェントの違いは、誤解されやすい点です。サーバー常駐エージェントは EVault サーバーに接続しますが、デスクトップで使用される CentralControl は、サーバーのアドレスとそのアドレスにアクセスするためのサーバーの資格情報を使用して、サーバーに接続します。
