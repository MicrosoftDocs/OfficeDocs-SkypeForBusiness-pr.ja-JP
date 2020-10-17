---
title: 常設チャットサーバーのベストプラクティス
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fceea7401a6d5442738a0cc64e9a2bafbfd83827
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500144"
---
# <a name="persistent-chat-server-best-practices"></a>常設チャットサーバーのベストプラクティス

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-06_

カテゴリおよび常設チャットルームを作成し、スコープとメンバーシップを設計する際には、以下のヒントを参考にして計画を立てることができます。

  - 企業が倫理的な壁を必要としない場合は、カテゴリツリーの範囲を狭くしないようにしてください。 すべてのユーザーを1つのカテゴリのスコープに配置し、そのカテゴリのすべてのチャットルームを作成します。 その後、メンバーシップ一覧のみを使用して、各チャットルームへのアクセスを許可または制限します。

  - ほとんどの場合、新しいトピックについてのディスカッションをいつでも開始できるように、ユーザーが新しいチャットルームを作成できるようにする必要があります。 これを行うには、 **クリエーター** リストを **allowedmembers** リストと同じにします。 ただし、中央のサポートチームまたは特定のユーザーのみにルームの作成を許可する場合は、[作成者 **] リストを** 適切なサブセットとして設定します。

  - 各チャットルームに、組織との適合場所を示す完全な名前と説明の概要を指定します。 ユーザーがチャットルームを使用するときにカテゴリ名を表示することはできないため、ユーザーがチャットルームに対して意図したディスカッションフォーラムを決定するのに役立つように、カテゴリ名を利用することはできません。

  - 特定の命名規則またはその他のアクセス制御や検証を実装する場合は、カスタムルーム作成ワークフローが必要になることがあります。 常設チャットの構成を使用すると、 **RoomManagementUrl** を、ホストするものにカスタマイズできます。 たとえば、ユーザーが Lync クライアントで [ **ルームの作成** ] をクリックしたときに、カスタムソリューションにリダイレクトすることができます。

  - チャットルームの機能を向上させるさまざまなアドインを作成します。これにより、他のビジネスデータをチャットルームに取り込むことができます。 管理者は、システムで許可するアドインを登録する必要があります。 チャットルームマネージャーおよび作成者は、それぞれの会議室に関連する、許可されたアドインの一覧から選択できます。

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのカテゴリ、ルーム、およびアドインの管理](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

