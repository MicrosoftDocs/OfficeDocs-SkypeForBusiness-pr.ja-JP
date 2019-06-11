---
title: 'Lync Server 2013: 場所の取得'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb123cf2f38d935bc0cc641c67e6d0ff1d54e4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a>Lync Server 2013 での場所の取得

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-06_

Lync Server 2013 E9 の展開では、内部接続された Lync または Lync Phone Edition クライアントはそれぞれ、自分の場所をアクティブに取得しています。 SIP 登録後、クライアントは、furnishes について知っているすべてのネットワーク接続情報を、レプリケートされた SQL Server データベースによってサポートされている web サービスである位置情報サービスへの場所要求で認識します。 各セントラルサイトプールには、位置情報サービスがあります。これにより、ネットワーク情報を使用して、一致する場所についてレコードを照会します。 一致する場合は、位置情報サービスによってクライアントに位置情報が返されます。 一致していない場合、場所を手動で入力するように求めるメッセージが表示されることがあります (場所のポリシーの設定によって異なります)。 場所データは、プレゼンス情報データ形式の場所オブジェクト (PIDF) と呼ばれるインターネットエンジニアリングタスクフォース (IETF) の標準化された XML 形式でクライアントに送信されます。

Lync Server クライアントには、緊急通話の一部として PIDF データが含まれており、このデータは E9 サービスプロバイダーによって、適切な PSAP を特定し、その PSAP に呼び出しをルーティングするために、正しい ESQK と共に使用されます。これにより、PSAP ディスパッチャーは、発信者の場所。

次の図は、Lync Server クライアントで場所を取得する方法を示しています (サードパーティのクライアント MAC アドレスベースの場所のメソッドを除く)。

![クライアントが位置情報ダイアグラムを取得する方法](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "クライアントが位置情報ダイアグラムを取得する方法")

クライアントが場所情報を取得するには、次の手順を実行する必要があります。

1.  管理者は、場所情報サービスデータベースに network wiremap (さまざまな種類のネットワークアドレスを対応する緊急対応の場所 (ERLs) にマップするテーブル) を設定します。

2.  SIP トランクの E9-1-1 サービス プロバイダーを使用する場合、その E9-1-1 サービス プロバイダーが維持する主要道路住所案内 (MSAG) データベースに対して、管理者は ERL の公的アドレス部分を確認します。ELIN ゲートウェイを使用する場合、管理者は、PSTN キャリアが自動ロケーション識別 (ALI) データベースに ELIN をアップロードすることを確認します。

3.  登録中、またはネットワークの変更が発生するたびに、内部接続クライアントは、クライアントの検出されたネットワークアドレスを含む位置情報要求を、位置情報サービスに送信します。

4.  位置情報サービスは、発行されたレコードに対して場所を照会します。一致するものが見つかった場合は、ERL を PIDF 形式でクライアントに返します。

</div>

<span> </span>

</div>

</div>

</div>

