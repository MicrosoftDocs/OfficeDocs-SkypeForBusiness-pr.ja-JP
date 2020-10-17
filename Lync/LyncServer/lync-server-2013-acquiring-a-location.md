---
title: 'Lync Server 2013: 場所の取得'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e5b3a6f9e781efbc3c8b7672ad28f1753490e17
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529744"
---
# <a name="acquiring-a-location-in-lync-server-2013"></a>Lync Server 2013 での場所の取得

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-06_

Lync Server 2013 E9-1-1 展開では、内部接続された Lync または Lync Phone Edition クライアントはそれぞれ、自分の場所を実際に取得します。 SIP 登録の後、クライアントは、furnishes について認識しているすべてのネットワーク接続情報を、レプリケートされた SQL Server データベースによってサポートされている web サービスである場所情報サービスへの場所要求に格納します。 各中央サイトプールには、場所情報サービスがあります。これは、ネットワーク情報を使用して、一致する場所についてのレコードを照会します。 一致するものがある場合、Location Information service はクライアントに場所を返します。 一致しない場合は、場所を手動で入力するようにユーザーに求められることがあります (場所のポリシー設定によって異なります)。 場所データは、プレゼンス情報のデータ形式の場所オブジェクト (PIDF-LO) と呼ばれる、インターネット技術標準化委員会 (IETF) の標準化された XML 形式でクライアントに転送されます。

Lync Server クライアントには、緊急電話の一部として PIDF-LO のデータが含まれており、E9-1-1 サービスプロバイダーがこのデータを使用して適切な PSAP を決定し、適切な ESQK を使用してその PSAP に通話をルーティングします。これにより、PSAP ディスパッチャーは発信者の場所を取得できます

次の図は、Lync Server クライアントが場所を取得する方法を示しています (サードパーティクライアントの MAC アドレスベースの場所の方法を除く)。

![クライアントが場所の図を取得する方法](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "クライアントが場所の図を取得する方法")

クライアントが場所情報を取得するには、次の手順を実行する必要があります。

1.  管理者は、場所情報サービスデータベースを network ワイヤマップ (さまざまな種類のネットワークアドレスを対応する緊急応答の場所 (erls) にマップするテーブル) に設定します。

2.  SIP トランクの E9-1-1 サービス プロバイダーを使用する場合、その E9-1-1 サービス プロバイダーが維持する主要道路住所案内 (MSAG) データベースに対して、管理者は ERL の公的アドレス部分を確認します。ELIN ゲートウェイを使用する場合、管理者は、PSTN キャリアが自動ロケーション識別 (ALI) データベースに ELIN をアップロードすることを確認します。

3.  登録中、またはネットワークの変更が発生するたびに、内部接続のクライアントは、検出されたクライアントのネットワークアドレスを含む場所要求を場所情報サービスに送信します。

4.  場所情報サービスは、発行されたレコードに対して1つの場所を照会し、一致するものが見つかった場合は、ERL を PIDF-LO 形式でクライアントに返します。

</div>

<span> </span>

</div>

</div>

</div>

