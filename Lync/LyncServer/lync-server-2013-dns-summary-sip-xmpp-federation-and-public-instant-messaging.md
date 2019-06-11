---
title: DNS 概要-SIP、XMPP フェデレーション、パブリックインスタントメッセージ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22b38fdb9e936df8b3fd148022acdbd857cdcfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>DNS 概要-Lync Server 2013 での SIP、XMPP フェデレーション、およびパブリックインスタントメッセージング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2017-03-09_

Office Communications Server または Lync Server パートナーとのフェデレーションを定義するために必要なドメインネームシステム (DNS) レコードは、他のパースペクティブパートナーによるドメインの自動 DNS 検出を許可するかどうかを決定することによって決定されます。 \_Sipfederationtls を発行する場合。\_tcp。 *SIP ドメイン名\> \<* SRV レコードでは、他の SIP フェデレーションドメインでフェデレーションを「検出」できます。 Lync Server のコントロールパネルで [ドメインとブロックされたドメインを許可する] 設定を使用するか、または Lync Server 管理シェル**を使用して [許可] または [禁止ドメイン] 設定を行うか、または** **CsBlockedDomain** PowerShell コマンドレットを取得、**設定**、**新規**、**削除**します。 これらの設定を構成する方法と PowerShell コマンドレットの使用方法の詳細については、このトピックの最後にある**関連トピック**を参照してください。

[DNS records summary] テーブルには、オープン、または検出可能なフェデレーションに必要なエントリが示されています。 フェデレーション検出を実装しない場合は、 \_sipfederationtls を構成しないことを選択できます。\_tcp。 *SIP ドメイン名\>レコード。 \<*

<div>


> [!IMPORTANT]
> _Sipfederationtls を持っている必要がある特定のシナリオがあります。 _tcp <EM>SIP ドメイン名&gt; &lt;</EM>SRV レコードですが、検出可能なフェデレーションは必要ありません。 このようなインスタンスの1つは、ユーザーのモバイル機能を展開した場合です。 モビリティープッシュ通知 (PNCH) は、lync 2010 モバイルクライアントまたは Lync 2013 モバイルクライアントを使用して、Lync 2010 モバイルクライアントまたは Windows Phone を使用している、Apple iPhone または iPad 上の Microsoft Lync モバイルクライアントで使用される特殊な種類のフェデレーションです。 _Sipfederationtls。 _tcp <EM>SIP ドメイン名&gt; &lt;</EM>SRV レコードは、モビリティーとプッシュ通知の場合に使用されます。 この問題を軽減して発見性を制御するには、[<STRONG>パートナードメイン探索を有効</STRONG>にする] 設定をオフにして検出をオフにします。



</div>

展開用の拡張メッセージングとプレゼンスプロトコル (XMPP) を構成するには、外部 DNS サーバーで、エッジサーバーまたはエッジプールのアクセスエッジサービスへのレコードを解決する2つのドメインネームシステム (DNS) レコードを作成します。

パブリックインスタントメッセージング接続用にドメインネームシステム (DNS) を構成すると、外部ユーザーをサポートする構成はパブリック IM 接続をサポートすることになります。 エッジサーバーまたはエッジプールを既に構成している場合は、パブリック IM 接続をサポートするために必要な DNS レコードを用意する必要があります。

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a>DNS 概要-パブリックインスタントメッセージング接続を含む SIP フェデレーション


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
<th>IP アドレス/FQDN ホストレコード</th>
<th>マップ先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>他の潜在的なフェデレーションパートナーとのフェデレーションを自動的に検出するには、アクセスエッジサービスの外部インターフェイスが必要です。また、"許可された SIP ドメイン" と呼ばれます (以前のリリースでは拡張フェデレーションと呼ばれます)。Lync を有効にしたユーザーがいるすべての SIP ドメインで、必要に応じて繰り返す</p>



> [!IMPORTANT]
> この SRV レコードは、モビリティとプッシュ通知のクリアリングハウスで必要です。 SIP ドメインが複数ある場合は、Lync モバイルクライアントを含むドメインごとに SRV レコードを作成して公開します。 展開でサポートされている SIP ドメインごとに、明示的な SRV レコードがない場合、プッシュ通知サービスと Apple プッシュ通知サービスが予期したとおりに動作しないことがあります。

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
<th>IP アドレス/FQDN ホストレコード</th>
<th>マップ先/コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>アクセスエッジサービスまたはエッジプールの XMPP プロキシ外部インターフェイス。グローバルポリシー、ユーザーが配置されているサイトポリシー、またはユーザーポリシーを使用して、外部アクセスポリシーの構成を通じて、すべての内部 SIP ドメインについて必要に応じてこの手順を繰り返します。Lync 対応ユーザー。 許可されている XMPP ドメインは、XMPP フェデレーションパートナーポリシーでも構成する必要があります。 詳細については、 <strong>「</strong>関連項目」を参照してください。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>xmpp.contoso.com (など)</p></td>
<td><p>エッジサーバーまたは XMPP プロキシをホストしているエッジプールのアクセスエッジサービスの IP アドレス</p></td>
<td><p>XMPP プロキシサービスをホストしているアクセスエッジサービスまたはエッジプールへのポイント。 通常、作成した SRV レコードは、このホスト (A または AAAA) レコードをポイントします。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 XMPP フェデレーションのセットアップ](lync-server-2013-setting-up-xmpp-federation.md)  
[Lync Server 2013 でプッシュ通知を構成する](lync-server-2013-configuring-for-push-notifications.md)  
[Lync Server 2013 でのフェデレーション パートナーの検出の有効化または無効化](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[Lync Server 2013 の外部ユーザー アクセスのシナリオ](lync-server-2013-scenarios-for-external-user-access.md)  
[Lync Server 2013 の DNS の要件を確認する](lync-server-2013-determine-dns-requirements.md)  


[Lync Server 2013 での組織の SIP フェデレーション ドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

