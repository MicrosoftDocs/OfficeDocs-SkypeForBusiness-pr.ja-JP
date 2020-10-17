---
title: 'Lync Server 2013: ELIN ゲートウェイを使用した E9-1-1 通話のルーティング'
description: 'Lync Server 2013: ELIN ゲートウェイを使用した E9-1-1 通話のルーティング。'
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
ms.openlocfilehash: f9ddbdbbdf10f9eecbffecaaf8416718bbdcf224
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545103"
---
# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>Lync Server 2013 の ELIN ゲートウェイを使用した E9-1-1 通話のルーティング

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-05_

統合コミュニケーション相互運用プログラムの一部のパートナーは、正規の E9-1-1 サービス プロバイダーへの SIP トランク接続の代替としての機能を果たすことができる、緊急位置識別番号 (ELIN) 対応の正規のゲートウェイを提供しています。 ELIN ゲートウェイは、公衆交換電話網 (PSTN) ベースの E9-1-1 サービスへの ISDN 接続 または Centralized Automatic Message Accounting (CAMA) 接続をサポートします。 ELIN ゲートウェイとそのドキュメントへのリンクを提供するパートナーの詳細については、「」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425) 。

E9-1-1 サービスプロバイダーへの SIP トランク接続と同様に、ELIN ゲートウェイも、発信者が最も適切な公共の安全応答ポイント (PSAP) に緊急通話をルーティングする手段を提供します。ただし、これらのゲートウェイは、場所の識別子として ELIN を使用します。 組織内の各緊急対応の場所 (ERL) に ELINs を定義します (詳細については、「 [Lync Server 2013 で ELIN ゲートウェイの場所を管理](lync-server-2013-managing-locations-for-elin-gateways.md)する」を参照してください)。

緊急電話で ELIN ゲートウェイを使用する場合は、SIP トランク接続に使用するのと同じ Lync Server E9-1-1 インフラストラクチャを使用します。 つまり、場所情報サービスデータベースによって Lync Server クライアントへの場所が提供され、場所のポリシーによって機能が有効になり、ルーティングが定義されます。 ただし、ELIN ゲートウェイを使用する場合は、場所情報サービスデータベースに ELINs を追加し、それを PSTN キャリアが自動場所識別 (ALI) データベースにアップロードする必要があります。

Lync クライアントが場所情報サービスから場所を取得すると、その場所には ELIN が含まれます。 緊急通話時、ELIN ゲートウェイに送信される場所に ELIN が含まれています。 ELIN ゲートウェイが通話を緊急通話と認識すると、発信者の番号を ELIN に置き換えます。 そして、ELIN を発信番号として、通話が PSTN にルーティングされます。 PSTN E9-1-1 プロバイダーでは、主要道路住所案内 (MSAG) データベースのコンパニオン データベースである ALI データベース内で ELIN を検索します。 ALI 検索に基づいて最適な PSAP に通話が送られ、ALI 検索に基づいて発信者の場所に最初の対応員が送られます。 発信番号は、コールバック用に、事前に定義された時間だけ、ELIN ゲートウェイ上にキャッシュされます。 コールバック時には、PSAP が ELIN ゲートウェイにアクセスすると、そこで ELIN が発信者の Direct Inward Dialing (DID) 番号に置き換えられます。

ELIN ゲートウェイは、組織のネットワーク内からの緊急通話のみをサポートします。 ネットワーク外からの緊急通話はサポートしません。

<div>


> [!NOTE]  
> 緊急通話での SIP トランク接続の使用の詳細については、「 <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by Using Lync Server 2013</A>」を参照してください。



</div>

次の図は、ELIN ゲートウェイを使用する場合に、Lync Server から PSAP への緊急通話のルーティング方法を示しています。

**ELIN ゲートウェイを使用する場合の E9-1-1 通話のルーティング**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  場所、発信者のコールバック番号、および (オプションで) 通知 URL と会議のコールバック番号を含む SIP INVITE が Lync Server にルーティングされます。

2.  Lync Server は、緊急電話番号と一致し、(該当する場所のポリシーで定義されている **PSTN 使用法** の値に基づいて) 仲介サーバーに通話をルーティングし、そこから ELIN ゲートウェイに転送します。

3.  ELIN ゲートウェイは、ISDN または CAMA トランク経由で PSTN に通話をルーティングします。

4.  PSTN は通話を緊急通話と見なし、ネットワーク内で選択された E9-1-1 ルーターに通話をルーティングします。E9-1-1 ルーターは、ALI データベースで発信者の番号を検索して地理的な場所を取得します。E9-1-1 ルーターは、ALI データベースから取得した場所情報に基づいて最適な PSAP に通話を送信します。

5.  通知の場所のポリシーを構成した場合は、1つまたは複数の組織のセキュリティ担当者に対して、特別な Lync 緊急通知インスタントメッセージが送信されます。 このメッセージはセキュリティ担当者の画面に必ずポップアップ表示され、そこには発信者の名前、電話番号、時刻、および場所も含まれているので、セキュリティ担当者はインスタント メッセージまたは音声によってその緊急通話発信者に迅速に応答できます。

6.  通話が途中で終了した場合、PSAP は ELIN を使用して発信者に直接連絡します。ELIN ゲートウェイは、ELIN を発信者の DID に置き換えます。

</div>

<span> </span>

</div>

</div>

</div>

