---
title: Lync Server 2013 でのパブリック インスタント メッセンジャーの接続のサポート
TOCTitle: Lync Server 2013 でのパブリック インスタント メッセンジャーの接続のサポート
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59602761
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのパブリック インスタント メッセンジャーの接続のサポート

 

_**トピックの最終更新日:** 2016-12-08_

## パブリック インスタント メッセンジャー接続のサポート

この記事では、パブリック IM 接続 (PIC) のサポートに関する情報を提供します。PIC は、Lync ユーザーが特定のパブリック インスタント メッセージング (IM) サービスのユーザーと、その Lync クライアントや ID 経由で接続できるようにする Microsoft Lync の機能です。

エンドユーザーにとっては、関係する顧客、パートナー、ベンダーと接続できるという利点があります。IT 部門にとっては、Lync の制御、コンプライアンス、アーカイブの機能を管理しながら、1 つのリアルタイム通信クライアントをサポートできるという利点があります。[2013 年 5 月に公開](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)された Lync-Skype 接続では、従来の方式が使用されています。この方式では、MSN/Windows Live、AOL、Yahoo との接続において、Lync/Office Communications Server (OCS)/Live Communications Server (LCS) はまず PIC との接続を確立します。Lync-Skype 接続について詳しくは、「[Lync-Skype 接続](http://office.microsoft.com/ja-jp/lync/lync-skype-connectivity-fx103789635.aspx)」をご覧ください。Windows Live、AOL、Yahoo とのフェデレーションは、それぞれサービスが終了する予定です。このページには、各サービスのステータスが記載されています。

PIC を使用するには、お客様が各パブリック IM サービス プロバイダーのサービスをアクティブ化する必要があります。この操作の要件と方法の詳細は、IM サービス プロバイダーとお客様の基礎となるライセンス プログラムによって異なります。

## Windows Live Messenger

Microsoft は Windows Live Messenger と Skype を統合しました。2013 年 4 月に、Messenger ユーザーはサインイン時に Skype に移行されるようになりました。Messenger とのフェデレーションに依存する Lync ユーザーは、Messenger の連絡先が Skype に更新されても、引き続き通信できます。Lync の管理者やエンドユーザーがサービスの継続性を維持するため操作を行う必要はなく、Lync 内でのこの機能の管理は、Messenger との通信の場合と同じです。

Messenger ユーザーが Microsoft アカウント (Messenger と同じ資格情報など) を使用して Skype にサインインすると、Messenger のすべての連絡先 (フェデレーションされた Lync 連絡先を含む) は Skype に移行されます。これらの連絡先の Skype と Lync の間のプレゼンス共有とインスタント メッセージングは使用できます。 

すべての Lync ユーザーは、Lync と Skype の接続 (Lync ユーザーと Skype ユーザーの間の連絡先の追加、プレゼンス共有、インスタント メッセージング、音声通話) も使用できます。

## Yahoo\! と AOL のインスタント メッセンジャー

Lync (および Office Communications Server) のお客様の Yahoo\! と AOL とのフェデレーションは、終了する予定です。Microsoft がこれらの各サービスを提供できるかどうかは、Yahoo\! と AOL からのサポート次第で、これらの基礎となる契約は終了する予定です。Yahoo\! と AOL のサービスは両方とも 2014 年 6 月まで継続します。

  - **Yahoo** - サービスは 2014 年 6 月まで継続し、お客様は引き続き Microsoft Lync パブリック IM 接続のユーザー サブスクリプション ライセンス (“PIC USL”) のライセンスを持つ必要があります。2012 年 9 月 1 日の時点で、PIC USL は新規または更新契約で購入できなくなりました。この日付より前にライセンスを購入したお客様は、サービスの終了日またはライセンスの有効期限のうち、いずれか早い方の日付まで引き続き Yahoo\! とフェデレーションできます。Lync チーム ブログの[アナウンス](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx)をご覧ください。2014 年 6 月 30 日より後の期間を対象とする契約に基づく PIC ライセンスをお持ちのお客様に対しては、2014 年 6 月 30 日より後の期間分の支払いに応じてクレジットが発行されます。

  - **AOL** - 2014 年 6 月 30 日で、Lync の IM 接続 ("PIC") サービスは使用できなくなります。サービス終了に伴うお客様の混乱を少なくするため、追加の顧客ドメインのプロビジョニングは継続していません。2014 年 6 月 30 日まで、AIM とのフェデレーション通信を継続サポートするためにお客様が特に操作を行う必要はありません。この日を過ぎると (またはこの間に追加ドメインをプロビジョニングしたいお客様向けに)、代替サービスが直接 AOL から提供されます。AOL の新規サービスについて詳しくは、「[Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)」をご覧ください  (AOL.com で新規ページを開きます)。  

## パブリック IM プロバイダーの概要

次の表に、パブリック IM プロバイダーの概要、Lync とのフェデレーション機能、ライセンス要件について示します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>パブリック IM サービス プロバイダー</th>
<th>フェデレーション機能</th>
<th>ライセンス要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>IM、プレゼンス、音声</p></td>
<td><p>Lync Server のクライアント アクセス ライセンス、Lync Online Plan 1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>IM、プレゼンス、音声/ビデオ</p></td>
<td><p>Lync Server のクライアント アクセス ライセンス (WLM が市場にある限りはサポートを継続)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>IM、プレゼンス</p></td>
<td><p>Lync Server のクライアント アクセス ライセンス、既存のお客様を対象に 2014 年 6 月までサポート</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>IM、プレゼンス</p></td>
<td><p>Lync Server のクライアント アクセス ライセンスのほか、追加の Microsoft Lync パブリック IM 接続のユーザー サブスクリプション ライセンス (“PIC USL”) が必要。2012 年 9 月時点の価格表では、PIC USL は購入できなくなっています。アクティブなライセンスをお持ちのお客様は、2014 年 6 月 30 日のサービス終了日まで、引き続き Yahoo! Messenger とフェデレーションできます。</p></td>
</tr>
</tbody>
</table>

