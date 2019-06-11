---
title: 拡張メッセージングとプレゼンスプロトコル (XMPP) フェデレーションの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2f4e1d8f9b7f164dd9e83f556dcc57809619278
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013 での拡張メッセージングとプレゼンスプロトコル (XMPP) フェデレーションの計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

以前のバージョンの Lync Server と Office Communications Server では、拡張されたメッセージング機能とプレゼンスプロトコル (XMPP) ゲートウェイが提供されており、これを個別のサーバーの役割として展開して、XMPP の展開とのフェデレーションを可能にすることができました。 Microsoft Lync Server 2013 では、XMPP 機能を機能として展開できます。 XMPP 機能は、Edge サーバー上で実行される XMPP プロキシと、フロントエンドサーバー上で実行される XMPP ゲートウェイの2つの部分でインストールされます。

XMPP の展開と構成については、「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」を対象としています。ファイアウォールでのポートとプロトコルのルールの定義、証明書の構成、DNS の追加などを行って、組織での xmpp のサポートを計画します。記録. このセクションの次のトピックでは、展開用の XMPP フェデレーションを正常に計画するために必要な情報についてまとめます。

<div>


> [!IMPORTANT]
> Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [証明書の概要-Lync Server 2013 での拡張可能なメッセージングとプレゼンスプロトコル (XMPP) フェデレーション](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [ポート概要-Lync Server 2013 での拡張可能なメッセージングとプレゼンスプロトコル (XMPP) フェデレーション](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [DNS の概要-Lync Server 2013 での拡張可能なメッセージングとプレゼンスプロトコル (XMPP) フェデレーション](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 XMPP フェデレーションのセットアップ](lync-server-2013-setting-up-xmpp-federation.md)  
[Lync Server 2013 での XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))  
[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))  
[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

