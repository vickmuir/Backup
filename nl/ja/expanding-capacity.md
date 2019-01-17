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


# ボールトの容量の拡大

現在の {{site.data.keyword.BluSoftlayer_full}} ユーザーはボールトのサイズを最大 4000 GB まで拡張できます。 複製を作成したり、大きなボリュームにデータを手動で移行したりする必要はありません。 限度の増量処理を行っても、障害やアクセス中断が発生することはりません。

## 増量の注文

1. [{{site.data.keyword.cloud_notm}} コンソール](https://{DomainName}/catalog/){:new_window}にログインして、左上にある**「メニュー」**アイコンをクリックします。**「クラシック・インフラストラクチャー」**を選択します。<br/>
   あるいは、[{{site.data.keyword.slportal}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){:new_window} にログインします。
2. **「ストレージ」**>**「バックアップ」**をクリックして、バックアップ・サービスを備えたサーバーを表示します。
3. 拡大するボールトを選択します。
4. **「アクション」**をクリックし、**「{{site.data.keyword.backup_notm}} の変更」**を選択します。
5. 次の画面で新しいサイズを選択し、**「アップグレード (Upgrade)」**をクリックします。

## 請求処理

ボリュームに対する請求は自動更新されて、新価格の差額が日割り計算で現在の請求サイクルに追加されます。 そして、次の請求サイクルでは新しい価格が全額請求されます。

{{site.data.keyword.backup_notm}} のサイズを削減する場合にも同じプロセスを使用できます。
{:tip}
