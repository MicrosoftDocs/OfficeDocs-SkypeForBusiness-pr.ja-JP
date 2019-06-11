---
title: 'Lync Server 2013: 常設チャット サーバー ポリシーを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58e71cd92182fc9f68d272ba23079677983b399
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>Lync Server 2013 で常設チャット サーバー ポリシーを有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-06_

Lync Server 2013 コントロールパネルでは、**常設チャット**グループの**常設チャットのポリシー**ページを使用して、既定のグローバルポリシーの構成と1つ以上のユーザーレベルでポリシーを管理できます。展開用の追加のユーザーとサイトポリシー。 ユーザーが、ポリシーによって常設チャットサーバーを有効にしている場合は、常設チャットサーバー環境が Lync 2013 クライアントに表示されます。

<div>


> [!NOTE]  
> トポロジでは、常設チャットサーバーのサイトポリシーは、ユーザーのプールごと、またはユーザーごとのサイトに適用されます。



</div>

グローバルポリシーは、常設チャットサーバーの展開時に自動的に作成され、構成はできますが、削除はできません。 グローバル ポリシーはすべてのユーザーに適用されるため、ユーザーごとに設定する必要はありません。

グローバルポリシーと共に、常設チャットサーバーのユーザーを有効にする、複数のサイトとユーザーのポリシーを作成して構成することができます。 プールとサイトの常設チャットサーバーポリシーは、そのサイトのユーザーに対してのみ、グローバル常設チャットサーバーポリシーを上書きします。 ユーザーポリシーは、ユーザーポリシーが割り当てられているユーザーのグローバル、プール、サイトの各ポリシーを上書きします。

<div>


> [!NOTE]  
> 常設チャットサーバーを構成して使用するには、最初にトポロジビルダーを使用して、トポロジに常設チャットサーバーサポートを追加してから、トポロジを発行する必要があります。 詳細については、展開ドキュメントの「 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - [Lync Server 2013 で常設チャットのグローバル ポリシーを構成する](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Lync Server 2013 で常設チャットのサイト ポリシーを作成する](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Lync Server 2013 で常設チャット用のユーザー ポリシーを作成する](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Lync Server 2013 で常設チャット ポリシーをユーザーまたはユーザー グループに適用する](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

