---
title: DNS の概要 - XMPP (Extensible Messaging and Presence Protocol) フェデレーション
TOCTitle: DNS の概要 - XMPP (Extensible Messaging and Presence Protocol) フェデレーション
ms:assetid: 0f720a2a-8ab5-43cc-882a-ab595ed3cec7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ618368(v=OCS.15)
ms:contentKeyID: 49115199
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS の概要 - XMPP (Extensible Messaging and Presence Protocol) フェデレーション

 

_**トピックの最終更新日:** 2015-03-09_

展開用に Extensible Messaging and Presence Protocol (XMPP) を構成するには、外部のドメイン ネーム システム (DNS) サーバーに 2 つの DNS レコードを作成し、それらのレコードをエッジ サーバーのアクセス エッジ サービスまたはエッジ プールに解決します。

## XMPP の DNS の概要


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
<td><p>アクセス エッジ サービスまたはエッジ プールの XMPP プロキシ外部インターフェイス。Lync 対応ユーザーを含むすべての内部 SIP ドメインに対して必要なだけ繰り返します。この外部 SIP ドメインでは、XMPP 連絡先を持つ連絡先は、グローバル ポリシー、ユーザーが配置されるサイト ポリシー、または Lync 対応ユーザーに適用されるユーザー ポリシーを利用して外部アクセス ポリシーの構成を通じて許可されます。また、許可された XMPP ドメインは XMPP フェデレーション パートナー ポリシーにも構成される必要があります。詳細については、「<strong>関連項目</strong>」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com (例)</p></td>
<td><p>XMPP プロキシをホストしている、エッジ サーバーのアクセス エッジ サービスまたはエッジ プールの IP アドレス</p></td>
<td><p>XMPP プロキシ サービスをホストするアクセス エッジ サービスまたはエッジ プールを指します。通常は、作成する SRV レコードが、このホスト (A または AAAA) レコードを指します。</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### タスク

[Lync Server 2013 XMPP フェデレーションのセットアップ](lync-server-2013-setting-up-xmpp-federation.md)  

#### 概念

[Lync Server 2013 の DNS の要件を確認する](lync-server-2013-determine-dns-requirements.md)

