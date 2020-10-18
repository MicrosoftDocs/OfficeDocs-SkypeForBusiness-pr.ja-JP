---
title: DNS の概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング
description: DNS の概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f40013b8346cc049f844a827b21bef81a66f6950
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572763"
---
# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Lync Server 2013 の DNS の概要-SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2017-03-09_

Office Communications Server または Lync Server パートナーとのフェデレーションを定義するために必要となるドメインネームシステム (DNS) レコードは、他の組織のドメインの自動 DNS 検出を許可するかどうかを決定します。 Sipfederationtls を発行する場合 \_ 。 \_プロトコル. *\<SIP domain name\>* SRV レコード。他の SIP フェデレーションドメインは、フェデレーションを "検出" することができます。 Lync server コントロールパネルで [ドメインとブロックされたドメインを許可する] の設定を使用するか、Lync Server 管理シェルと **Get**、 **Set**、 **New**、 **Remove-csalloweddomain** および **-get-csblockeddomain** PowerShell コマンドレットを使用して、許可または禁止ドメイン構成を設定することによって、どのフェデレーションドメインが自分と通信できるかを制御できます。 これらの設定の構成方法および PowerShell コマンドレットの使用の詳細については、このトピックの最後にある**関連トピック**を参照してください。

DNS レコードの概要の表には、開いている、つまり検出可能なフェデレーションに必要なエントリが示されています。 フェデレーション検出を実装しない場合は、sipfederationtls を構成しないことを決定でき \_ ます。 \_プロトコル. *\<SIP domain name\>* レコード.

<div>


> [!IMPORTANT]
> _Sipfederationtls を使用する必要がある特定のシナリオがあります。 <EM> &lt; SIP ドメイン名 &gt; </EM> SRV レコードですが、検出可能なフェデレーションを使用したくありません。 このようなインスタンスの1つとして、ユーザーのモビリティを展開した場所があります。 モビリティープッシュ通知クリアリングハウス (PNCH) は特別な種類のフェデレーションで、lync 2010 モバイルクライアントまたは lync 2013 モバイルクライアント2010を使用して、Lync モバイルクライアントまたは Windows Phone を使用している Apple iPhone または iPad の Microsoft Lync Mobile クライアントに使用されます。 _Sipfederationtls。 _tcp。 <EM> &lt; SIP ドメイン名 &gt; </EM> SRV レコードは、モビリティおよびプッシュ通知の場合に使用されます。 この問題を軽減して、発見性を制御するには、[ <STRONG>パートナードメインの検出を有効</STRONG> にする] の設定をクリアして、検出をオフにします。



</div>

展開用に拡張メッセージとプレゼンスプロトコル (XMPP) を構成するには、外部 DNS サーバーに2つのドメインネームシステム (DNS) レコードを作成します。これにより、エッジサーバーまたはエッジプールのアクセスエッジサービスに対するレコードが解決されます。

パブリックインスタントメッセージング接続用にドメインネームシステム (DNS) を構成すると、外部ユーザーをサポートする構成がパブリック IM 接続をサポートすることがわかります。 エッジサーバーまたはエッジプールを既に構成している場合は、パブリック IM 接続をサポートするために必要な DNS レコードを用意する必要があります。

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>DNS の概要-パブリックインスタントメッセージング接続を含む SIP フェデレーション


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
<td><p>_sipfederationtls _sipfederationtls._tcp</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>他の潜在的フェデレーションパートナーへのフェデレーションの自動 DNS 検出に必要なアクセスエッジサービスの外部インターフェイス (以前のリリースでは拡張フェデレーションと呼ばれます) と呼ばれる、"許可された SIP ドメイン" と呼ばれるものです。Lync が有効なユーザーを持つすべての SIP ドメインについて必要に応じて繰り返します。</p>



> [!IMPORTANT]
> この SRV レコードは、モビリティおよび Push Notification Clearing House (PNCH) で必要です。 複数の SIP ドメインがある場合は、Lync Mobile クライアントを持つ各ドメインの SRV レコードを作成して発行します。 展開でサポートされている各 SIP ドメインに対して明示的な SRV レコードが存在しない場合、プッシュ通知サービスと Apple プッシュ通知サービスが期待どおりに動作しないことがあります。

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a>DNS の概要-拡張可能なメッセージングとプレゼンスプロトコル (XMPP)


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
<td><p>_xmpp-server._tcp</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>アクセスエッジサービスまたはエッジプール上の XMPP プロキシの外部インターフェイス。必要に応じて、Lync が有効になっているすべての内部 SIP ドメインについて、グローバルポリシー、ユーザーが配置されているサイトポリシー、Lync が有効なユーザーに適用されているユーザーポリシーを使用して、外部アクセスポリシーの構成を通じて、外部アクセスポリシーの構成を通じて実行できます。 許可されている XMPP ドメインは、XMPP フェデレーションパートナーポリシーでも構成する必要があります。 詳細については、 <strong>「</strong> 関連項目」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com (例)</p></td>
<td><p>XMPP プロキシをホストしているエッジサーバーまたはエッジプールのアクセスエッジサービスの IP アドレス</p></td>
<td><p>XMPP プロキシサービスをホストするアクセスエッジサービスまたはエッジプールを指します。 通常、作成する SRV レコードはこのホスト (A または AAAA) レコードを指し示します。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での XMPP フェデレーションのセットアップ](lync-server-2013-setting-up-xmpp-federation.md)  
[Lync Server 2013 でのプッシュ通知の構成](lync-server-2013-configuring-for-push-notifications.md)  
[Lync Server 2013 でのフェデレーションパートナーの検出を有効または無効にする](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Lync Server 2013 での外部ユーザーアクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)  
[Lync Server 2013 の DNS 要件を決定する](lync-server-2013-determine-dns-requirements.md)  


[Lync Server 2013 での組織の SIP フェデレーションドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

