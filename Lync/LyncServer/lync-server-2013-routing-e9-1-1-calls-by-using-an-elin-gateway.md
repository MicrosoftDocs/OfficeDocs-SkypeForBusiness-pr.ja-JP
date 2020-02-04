---
title: 'Lync Server 2013: ELIN ゲートウェイを使用した E9-1-1 通話のルーティング'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97c921a0b31438103ba74dcc64925e5b2069a8e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>Lync Server 2013 での ELIN ゲートウェイを使用した E9-1-1 通話のルーティング

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-05_

統合コミュニケーション オープン相互運用性プログラムの一部のパートナーは、認定 E9-1-1 サービス プロバイダーへの SIP トランク接続の代替として機能する、緊急位置識別番号 (ELIN) 対応の認定ゲートウェイを提供しています。 ELIN ゲートウェイは、公衆交換電話網 (PSTN) ベースの E9-1-1 サービスへの ISDN 接続または Centralized Automatic Message Accounting (CAMA) 接続をサポートします。 ELIN ゲートウェイとそのドキュメントへのリンクを提供するパートナーの詳細に[http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425)ついては、を参照してください。

E9 サービスプロバイダへの SIP トランク接続と同様、ELIN ゲートウェイでも、呼び出し元の最も適したパブリック安全応答ポイント (PSAP) に緊急通話をルーティングする手段が提供されていますが、これらのゲートウェイは、場所識別子として ELIN を使います。 組織の緊急対応の場所 (ERL) ごとに ELINs を定義します (詳細については、「 [Lync Server 2013 で ELIN ゲートウェイの場所を管理](lync-server-2013-managing-locations-for-elin-gateways.md)する」を参照してください)。

緊急通話に ELIN ゲートウェイを使用する場合、SIP トランク接続に使用するのと同じ Lync Server E9 1-1 インフラストラクチャを使用します。 つまり、場所情報サービスデータベースによって Lync Server クライアントへの場所が提供され、場所のポリシーによって機能が有効になり、ルーティングが定義されます。 ただし、ELIN gateway では、場所情報サービスデータベースに ELINs を追加して、PSTN キャリアが自動位置情報認識 (ALI) データベースにアップロードする必要があります。

Lync クライアントが位置情報サービスから場所を取得すると、場所に ELIN が含まれます。 緊急通話時には、ELIN ゲートウェイに送信される場所に ELIN が含まれています。 ELIN ゲートウェイは通話を緊急通話と見なすと、発信者の番号を ELIN に置き換えます。 その後、ELIN を発信番号として、通話を PSTN にルーティングします。 PSTN E9-1-1 プロバイダーは、主要道路住所案内 (MSAG) データベースのコンパニオン データベースである ALI データベースで ELIN を検索します。 PSTN が ALI 検索に基づいて最適な PSAP に通話を送信すると、PSAP は ALI 検索に基づいて発信者の場所に最初の対応員を送ります。 発信番号は、コールバック用に事前定義された時間だけ ELIN ゲートウェイ上にキャッシュされます。 コールバック時に、PSAP が ELIN ゲートウェイに到達すると、ELIN が発信者の Direct Inward Dialing (DID) 番号に置き換えられます。

ELIN ゲートウェイがサポートするのは、組織のネットワーク内からの緊急通話だけです。 ネットワーク外からの緊急通話はサポートされません。

<div>


> [!NOTE]  
> 緊急通話に SIP トランク接続を使用する方法について詳しくは、「 <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Lync Server 2013 で sip トランクを使用して E9 通話を転送</A>する」をご覧ください。



</div>

次の図は、ELIN gateway を使用しているときに、緊急通話が Lync Server から PSAP にルーティングされる方法を示しています。

**ELIN ゲートウェイを使用した E9-1-1 通話のルーティング**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  場所、発信者のコールバック番号、(オプション) 通知 URL と会議のコールバック番号を含む SIP 招待は、Lync Server にルーティングされます。

2.  Lync Server は緊急電話番号と一致し、(該当する場所のポリシーで定義されている**PSTN 使用量**の値に基づく) 通話を仲介サーバーにルーティングし、そこから ELIN ゲートウェイに転送します。

3.  ELIN ゲートウェイは、ISDN または CAMA トランク経由で PSTN に通話をルーティングします。

4.  PSTN は通話を緊急通話と見なし、ネットワーク内で選択された E9-1-1 ルーターに通話をルーティングします。E9-1-1 ルーターは、ALI データベースで発信者の番号を検索して地理的な場所を取得します。E9-1-1 ルーターは、ALI データベースから取得した場所情報に基づいて最適な PSAP に通話を送信します。 

5.  通知の場所のポリシーを構成している場合は、1つ以上の組織のセキュリティ責任者に、Lync 緊急通報に関する特別な通知のインスタントメッセージが送信されます。 このメッセージはセキュリティ担当者の画面に必ずポップアップ表示され、そこには発信者の名前、電話番号、時刻、および場所も含まれているので、セキュリティ担当者はインスタント メッセージまたは音声によってその緊急通話発信者に迅速に応答できます。

6.  通話が途切れた場合、PSAP は ELIN を使用して発信者に直接連絡します。ELIN ゲートウェイは、ELIN を発信者の DID に置き換えます。

</div>

<span> </span>

</div>

</div>

</div>

