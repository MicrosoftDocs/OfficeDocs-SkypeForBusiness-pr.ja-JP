---
title: 証明書の概要  - XMPP (Extensible Messaging and Presence Protocol) フェデレーション
TOCTitle: 証明書の概要  - XMPP (Extensible Messaging and Presence Protocol) フェデレーション
ms:assetid: b059a34e-99df-40af-91fe-fe2aa52841f6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ618374(v=OCS.15)
ms:contentKeyID: 49115243
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 証明書の概要 - XMPP (Extensible Messaging and Presence Protocol) フェデレーション

 

_**トピックの最終更新日:** 2015-03-09_

Extensible Messaging and Presence Protocol (XMPP) パートナーとの通信を有効にして確立するための証明書要件では、XMPP ドメインの追加レコードが必要になります。サブジェクトの別名 (SAN) として証明書に含まれているレコードは、XMPP 通信に参加できるドメインになります。ドメイン全体に対して XMPP を有効にする場合はドメインをルートレベル ドメイン (例: contoso.com) とし、ユーザーのサブセットに対して XMPP を有効にする場合は子ドメイン (例: corp.contoso.com、finance.contoso.com) を選択できます。

## Extensible Messaging and Presence Protocol の証明書の概要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>コンポーネント</th>
<th>サブジェクト名</th>
<th>サブジェクトの別名 (SAN)/順序</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>エッジ サーバーまたはエッジ プールのアクセス エッジ サービスに割り当て</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>contoso.com</p></td>
<td><p>最初の 3 つの SAN 項目は、フル エッジ サーバー向けの通常の SAN 項目です。contoso.com は、ルート ドメイン レベルでの XMPP パートナーとのフェデレーションに必要な項目です。この項目により、末尾が contoso.com のすべてのドメインで XMPP が許可されます。</p></td>
</tr>
</tbody>
</table>


## 関連項目

#### タスク

[Lync Server 2013 での XMPP 構成の例 - Google Talk との XMPP フェデレーション](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### 概念

[Lync Server 2013 でエッジ サーバー証明書を計画する](lync-server-2013-plan-for-edge-server-certificates.md)  

#### その他のリソース

[Lync Server 2013 用のエッジ証明書のセットアップ](lync-server-2013-set-up-edge-certificates.md)  
[Request-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Request-CsCertificate)  
[Set-CsCertificate](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)

