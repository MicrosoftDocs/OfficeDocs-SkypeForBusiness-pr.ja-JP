---
title: 'Lync Server 2013: エッジ サーバーの障害復旧'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d19e5a606c3217ad7653fd4c3c885a97aafdb5ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013 でのエッジ サーバーの障害復旧

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-03-12_

他のサーバーの役割と同様に、エッジサーバーの高可用性を実現する最良の方法は、各サイトのプールに複数のエッジサーバーを展開することです。 1つのエッジサーバーがダウンした場合、プール内の他のサーバーは、引き続きエッジサービスを提供します。

障害回復手順を有効にするには、個別のサイトに別のエッジサーバープールを展開する必要があります。 フロントエンドプールの場合と同様に、エッジプールを明示的にペアリングする必要はありませんが、エッジプールの1つが停止した場合でも、複数のエッジプールを使って実行できるかどうかが示されます。 以下のセクションでは、エッジサーバーのさまざまな機能のディザスタリカバリの詳細について説明します。

<div>

## <a name="remote-access"></a>リモートアクセス

複数のサイトがあり、それぞれにエッジサーバーのプールがあり、1つのエッジプールが失敗した場合、リモートアクセスサービスは管理者の操作がなくても機能し続けます。 異なるサイトでエッジプールを作成する場合、同じ FQDN を使用することはできません。 各エッジプールには、固有の Fqdn (内部および外部) が必要です。 エッジプールでは、フロントエンドサーバーとの通信にリバースプロキシの公開ルールは使用されません。 自動フェールオーバーは、クライアントがリモートアクセスの DNS サービスレコードを再照会したときに、リモートユーザーが別のサイトのエッジサーバーにルーティングされたときに発生します。 クライアントは、DNS SRV レコードの優先度に従って各外部エッジ FQDN を試します。

<div>


> [!NOTE]  
> フェールオーバーがスムーズに動作するためには、すべてのプールのフロントエンドサーバーがすべてのエッジサーバーと通信できるように、ファイアウォールが有効になっていることを確認します。



</div>

</div>

<div>

## <a name="federation"></a>フェデレーション

Lync Server を実行している他の組織とのフェデレーション関係の場合、Geo DNS GTM のような解決策がある限り、受信フェデレーション要求は引き続き機能します。 フェデレーションフェールオーバーは、SRV レコードの優先順位によるフェールオーバーを提供しないことを理解しておくことが重要です。 前に説明した解決策は、受信フェデレーションの障害回復機能を提供するのに役立ちます。

送信フェデレーションは、常に組織内の公開されたエッジプールまたはエッジサーバーによって設定されます。 このエッジプールがダウンしている場合は、トポロジビルダーを使用して、送信フェデレーションルートを変更し、まだ実行中のエッジプールを使用する必要があります。 詳細については、「lync server server[フェデレーションで使用されるエッジプールを Lync server 2013 でフェールオーバー](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)する」を参照してください。

</div>

<div>

## <a name="xmpp-federation"></a>XMPP フェデレーション

XMPP フェデレーションの場合、xmpp フェデレーションゲートウェイとして指定されているエッジプールが停止すると、送信トラフィックと受信トラフィックの両方が失敗します。 XMPP フェデレーションを再度有効にするには、別のエッジプールを使用するように XMPP フェデレーションを変更する必要があります。 詳細については、「 [Lync Server 2013 で XMPP フェデレーションに使用されているエッジプールの障害](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)を確認する」を参照してください。

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>エッジプールは失敗したが、フロントエンドプールがまだ実行されている

エッジプールがサイトで失敗しても、そのサイトのフロントエンドプールがまだ実行されている場合は、最初のエッジプールが停止している間に別のサイトで異なるエッジプールを使用するように、フロントエンドプールを変更する必要があります。 詳細については、「 [Lync Server 2013 でフロントエンドプールに関連付けられているエッジプールを変更する](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

