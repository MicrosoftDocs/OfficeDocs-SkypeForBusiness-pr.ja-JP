---
title: DNS の概要 - SIP、XMPP フェデレーション、パブリック インスタント メッセージング
TOCTitle: DNS の概要 - SIP、XMPP フェデレーション、パブリック インスタント メッセージング
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49115205
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS の概要 - SIP、XMPP フェデレーション、パブリック インスタント メッセージング

 

_**トピックの最終更新日:** 2017-03-09_

Office Communications Server または Lync Server パートナーとのフェデレーションに必要なドメイン ネーム システム (DNS) レコードは、他の潜在的なパートナーによるドメインの自動 DNS 検出を許可するかどうかという判断によって決まります。\_sipfederationtls.\_tcp.\<SIP ドメイン名\> SRV レコードを公開すると、他の SIP フェデレーション ドメインがこのフェデレーションを "検出" できるようになります。通信できるフェデレーション ドメインは、Lync Server コントロール パネルの許可ドメインおよび禁止ドメインの設定を使用して制御できます。また、Lync Server 管理シェルと **Get**、**Set**、**New**、**Remove-CsAllowedDomain**、および **-CsBlockedDomain** の各 PowerShell コマンドレットを使用して許可ドメインと禁止ドメインの構成を設定することによって制御することもできます。これらの設定の構成方法および PowerShell コマンドレットの使用の詳細については、このトピックの最後にある**関連トピック**を参照してください。

DNS レコードの概要の表には、開いている、つまり検出可能なフェデレーションに必要なエントリが示されています。フェデレーションの検出を実装しない場合は、\_sipfederationtls.\_tcp.\<SIP ドメイン名\> レコードを構成する必要はありません。


> [!IMPORTANT]
> _sipfederationtls._tcp. <EM>&lt;SIP domain name&gt;</EM> SRV レコードは必要だが、フェデレーションの検出は不要という特定のシナリオがあります。ユーザーに対してモビリティが展開されている場合が、このようなケースにあたります。モビリティの Push Notification Clearinghouse (PNCH) は、Apple iPhone 上の Microsoft Lync Mobile クライアント、Lync 2010 Mobile クライアントを使用している iPad、Lync 2010 Mobile または Lync 2013 モバイル クライアントを使用している Windows Phone で使用される特別な種類のフェデレーションファイルです。sipfederationtls._tcp. <EM>&lt;SIP ドメイン名&gt;</EM> SRV レコードは、モビリティとプッシュ通知で使用されています。この問題を軽減し、検出性を制御するには、[<STRONG>パートナー ドメインの検出を有効にする</STRONG>] をオフにして、検出を無効にします。



展開用に Extensible Messaging and Presence Protocol (XMPP) を構成するには、外部のドメイン ネーム システム (DNS) サーバーに 2 つの DNS レコードを作成し、それらのレコードを エッジ サーバーの アクセス エッジ サービスまたは エッジ プールに解決します。

パブリック IM 接続用のドメイン ネーム システム (DNS) を構成する場合、外部ユーザーをサポートする構成がパブリック IM 接続をサポートします。 エッジ サーバーまたは エッジ プールを既に構成している場合は、パブリック IM 接続のサポートに必要な DNS レコードを既に保持しています。

## DNS の概要 - SIP フェデレーション


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>場所/種類/ポート</th>
<th>FQDN</th>
<th>IP アドレス/FQDN ホスト レコード</th>
<th>マッピング先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>アクセス エッジ サービスの外部インターフェイス。他の潜在的なフェデレーション パートナーによるフェデレーションの自動 DNS 検出に必要で、&quot;許可されている SIP ドメイン&quot; と呼ばれています (以前のリリースでは拡張フェデレーションと呼ばれていました)。Lync 対応ユーザーがいるすべての SIP ドメインに対して、必要なだけ繰り返します。</p>
<div>

> [!IMPORTANT]
> この SRV レコードは、モビリティおよび Push Notification Clearing House (PNCH) で必要です。SIP ドメインが複数ある場合は、Lync Mobile クライアントを持つドメインごとに、SRV レコードを作成し、公開します。展開がサポートする各 SIP ドメインの明示的な SRV レコードがない場合、プッシュ通知サービスおよび Apple プッシュ通知サービスは期待どおりに動作しない可能性があります。


</div></td>
</tr>
</tbody>
</table>


## DNS の概要 - XMPP (Extensible Messaging and Presence Protocol)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>場所/種類/ポート</th>
<th>FQDN</th>
<th>IP アドレス/FQDN ホスト レコード</th>
<th>マッピング先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>アクセス エッジ サービスまたは エッジ プールの XMPP プロキシ外部インターフェイス。Lync 対応ユーザーを含むすべての内部 SIP ドメインに対して必要なだけ繰り返します。この外部 SIP ドメインでは、XMPP 連絡先を持つ連絡先は、グローバル ポリシー、ユーザーが配置されるサイト ポリシー、または Lync 対応ユーザーに適用されるユーザー ポリシーを利用して外部アクセス ポリシーの構成を通じて許可されます。また、許可された XMPP ドメインは XMPP フェデレーション パートナー ポリシーにも構成される必要があります。詳細については、<strong>関連項目</strong>を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com (例)</p></td>
<td><p>XMPP プロキシをホストする エッジ サーバーまたは エッジ プールの アクセス エッジ サービスの IP アドレス</p></td>
<td><p>XMPP プロキシ サービスをホストする アクセス エッジ サービスまたは エッジ プールを参照します。通常、作成する SRV レコードは、このホスト (A または AAAA) レコードを参照します。</p></td>
</tr>
</tbody>
</table>


## DNS の概要 - パブリック インスタント メッセージング接続


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>場所/種類/ポート</th>
<th>FQDN/DNS レコード</th>
<th>IP アドレス/FQDN</th>
<th>マッピング先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>アクセス エッジ サービス インターフェイス</p></td>
<td><p>アクセス エッジ サービス外部インターフェイス (Contoso)。必要に応じて、Lync が有効なユーザーを持つすべての SIP ドメインに対してこの手順を繰り返します。</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### タスク

[Lync Server 2013 XMPP フェデレーションのセットアップ](lync-server-2013-setting-up-xmpp-federation.md)  
[Lync Server 2013 でプッシュ通知を構成する](lync-server-2013-configuring-for-push-notifications.md)  
[Lync Server 2013 でのフェデレーション パートナーの検出の有効化または無効化](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  

#### 概念

[Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)  
[Lync Server 2013 の DNS の要件を確認する](lync-server-2013-determine-dns-requirements.md)  

#### その他のリソース

[Lync Server 2013 での組織の SIP フェデレーション ドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

