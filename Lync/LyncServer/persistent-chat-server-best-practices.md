---
title: 常設チャット サーバーのベスト プラクティス
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 119bc67622928ec2e60f082e72322e7b0b923c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a>常設チャット サーバーのベスト プラクティス

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-06_

カテゴリと常設チャットルームを作成して、スコープとメンバーシップを設計する際には、次のヒントを参考にしてください。

  - 会社が倫理的な壁を必要としない場合は、カテゴリツリーの範囲を狭くしないでください。 すべてのユーザーを1つのカテゴリの範囲に入れ、そのカテゴリのすべてのチャットルームを作成します。 その後、メンバーシップリストを使用して、各チャットルームへのアクセスを許可または制限します。

  - ほとんどの場合、新しいトピックに関するディスカッションをいつでも開始できるように、ユーザーが新しいチャットルームを作成できるようにする必要があります。 これを行うには **、作成者リストを** **allowedmembers**リストと同じにします。 ただし、中央のサポートチームまたは特定のユーザーにのみ会議室の作成を許可する場合は、適切なサブセットとして作成者**の一覧を**作成します。

  - 各チャットルームには、組織に適した場所を示す完全な名前と説明の概要を指定します。 ユーザーは、チャットルームを使用するときにカテゴリ名を見ることができないため、ユーザーがチャットルームの目的のディスカッションフォーラムを特定するのに役立つように、カテゴリ名を利用することはできません。

  - 特定の命名規則やその他のアクセス制御や検証を実装する場合は、カスタムの会議室の作成ワークフローが必要になることがあります。 常設チャットの構成では、ホストしているものに**RoomManagementUrl**をカスタマイズできます。 たとえば、ユーザーが Lync クライアントで [**会議室の作成**] をクリックすると、ユーザーはカスタムソリューションにリダイレクトすることができます。

  - 他のビジネスデータをチャットルームに表示して、チャットルームの操作性を向上させるためのさまざまなアドインを作成します。 管理者は、システムに許可するアドインを登録する必要があります。 チャットルームマネージャーと作成者は、それぞれの会議室に最も関連性の高いアドインの一覧から選ぶことができます。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのカテゴリ、ルーム、およびアドインの管理](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

