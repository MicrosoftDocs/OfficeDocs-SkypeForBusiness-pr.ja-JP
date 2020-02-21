---
title: 'Lync Server 2013: エッジサーバーの障害復旧'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff0c4b685c607850921be6b15b2611e427e5e226
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 でのエッジサーバーの障害復旧

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-03-12_

エッジ サーバーで高可用性を実現する最適な方法は、ほかのサーバーの役割の場合と同様に、各サイト内のプールに複数のエッジ サーバーを展開することです。あるエッジ サーバーがダウンしても、プール内のほかのエッジ サーバーによって引き続きエッジ サービスが提供されます。

障害復旧の手順を有効にするには、サイトごとに個別のエッジ サーバー プールを展開する必要があります。フロントエンド プールの場合に行うような明示的なエッジ プールのペアリングは不要ですが、複数のエッジ プールによって、あるエッジ プール全体がダウンしても可用性を維持できるようにしておく必要があります。以降のセクションでは、エッジ サーバーの各種機能の障害復旧について詳しく説明します。

<div>

## <a name="remote-access"></a>リモート アクセス

複数のサイトがあり、それぞれにエッジサーバーのプールがあり、エッジプール全体で障害が発生すると、リモートアクセスサービスは管理者の操作なしで引き続き機能します。 異なるサイトにエッジプールを作成する場合、同じ FQDN を使用することはできません。 各エッジプールには、固有の Fqdn (内部および外部) を指定する必要があります。 エッジプールは、フロントエンドサーバーとの通信にリバースプロキシ公開ルールを使用しません。 自動フェールオーバーは、クライアントがリモートアクセス DNS サービスレコードを再照会し、リモートユーザーが別のサイトのエッジサーバーにルーティングされるときに発生します。 クライアントは、DNS SRV レコードの優先度に従って各外部エッジ FQDN を試行します。

<div>


> [!NOTE]  
> フェールオーバーを円滑に動作させるには、ファイアウォールがすべてのプールのフロントエンドサーバーをすべてのエッジサーバーと通信できるようにします。



</div>

</div>

<div>

## <a name="federation"></a>フェデレーション

Lync Server を実行している他の組織とのフェデレーション関係については、Geo DNS GTM のようなソリューションがある限り、受信フェデレーション要求は引き続き機能します。 フェデレーションフェールオーバーでは、SRV レコードに優先度の高いフェールオーバーが提供されないことを理解しておくことが重要です。 以前提供したソリューションでは、受信フェデレーションの障害復旧機能を提供するのに役立ちます。

送信フェデレーションのセットアップは、必ず組織内の 1 つの公開エッジ プールまたはエッジ サーバーによって行われます。 このエッジ プールがダウンしている場合は、トポロジ ビルダーによって、動作しているエッジ プールが使用されるように送信フェデレーションのルートを変更する必要があります。 詳細については、「lync server[フェデレーションで使用されるエッジプールのフェールオーバー (Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md) )」を参照してください。

</div>

<div>

## <a name="xmpp-federation"></a>XMPP フェデレーション

XMPP フェデレーションでは、XMPP フェデレーション ゲートウェイとして指定されているエッジ プールがダウンすると、送信トラフィックと受信トラフィックの両方でエラーが発生します。 XMPP フェデレーションを再び機能させるには、別のエッジ プールを使用するように XMPP フェデレーションを変更する必要があります。 詳細については、「 [Lync Server 2013 での XMPP フェデレーションに使用するエッジプールのフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)」を参照してください。

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>エッジ プールで障害が発生してもフロントエンド プールが動作している場合

あるサイトでエッジ プールに障害が発生しても、そのサイトのフロントエンド プールが動作している場合は、障害の発生したエッジ プールがダウンしている間は異なるサイトにある別のエッジ プールを使用するようにフロントエンド プールを変更する必要があります。 詳細については、「 [Lync Server 2013 のフロントエンドプールに関連付けられたエッジプールの変更](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

