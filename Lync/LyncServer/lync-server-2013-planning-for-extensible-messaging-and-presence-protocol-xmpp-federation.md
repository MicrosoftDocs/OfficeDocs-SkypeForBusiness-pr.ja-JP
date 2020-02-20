---
title: 拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) フェデレーションの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8421c8fc7568aae9c7e7cedc0cad9ea0c503140
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Lync Server 2013 での拡張メッセージングおよびプレゼンスプロトコル (XMPP) フェデレーションの計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

以前のバージョンの Lync Server および Office Communications Server では、XMPP 展開とのフェデレーションを可能にするために、個別のサーバーの役割として展開できる拡張メッセージングおよびプレゼンスプロトコル (XMPP) ゲートウェイが提供されていました。 Microsoft Lync Server 2013 では、XMPP 機能を機能として展開できます。 XMPP 機能は、2つの部分で構成されています。これは、エッジサーバーと、フロントエンドサーバー上で実行される XMPP ゲートウェイ上で実行される xmpp プロキシです。

XMPP の展開と構成については、「 [Lync Server 2013 での外部ユーザーアクセスの展開](lync-server-2013-deploying-external-user-access.md)」に記載されています。ファイアウォールでポートとプロトコルルールを定義し、証明書を構成し、DNS レコードを追加することによって、組織での xmpp のサポートを計画します。 このセクションの以下のトピックでは、展開に対して XMPP フェデレーションを正常に計画するために必要な情報をまとめています。

<div>


> [!IMPORTANT]
> Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [証明書の概要-Lync Server 2013 での拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) フェデレーション](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Lync Server 2013 でのポートの概要-拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) フェデレーション](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Lync Server 2013 での DNS の概要-拡張可能なメッセージングおよびプレゼンスプロトコル (XMPP) フェデレーション](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での XMPP フェデレーションのセットアップ](lync-server-2013-setting-up-xmpp-federation.md)  
[Lync Server 2013 での XMPP フェデレーションユーザーアクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[Lync Server 2013 での XMPP フェデレーションパートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))  
[Get-CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))  
[-CsXmppGatewayConfiguration の取得](https://technet.microsoft.com/library/JJ204869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

