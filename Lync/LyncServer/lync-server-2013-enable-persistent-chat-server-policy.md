---
title: 'Lync Server 2013: 常設チャットサーバーポリシーの有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bfc0f8ed1160d29eb68fc00172c77b466692327
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>Lync Server 2013 で常設チャットサーバーポリシーを有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-06_

Lync Server 2013 コントロールパネルでは、**常設チャット**グループの [**常設チャットポリシー** ] ページを使用して、グローバル、プール、サイト、またはユーザーレベルでポリシーを管理できます。これには、既定のグローバルポリシーの構成や、展開用の1つまたは複数の追加のユーザーおよびサイトポリシーの作成が含まれます。 ユーザーがポリシーによって常設チャットサーバーに対して有効になっている場合、常設チャットサーバー環境が Lync 2013 クライアントに表示されます。

<div>


> [!NOTE]  
> トポロジでは、常設チャットサーバーのサイトポリシーは、グローバルに、ユーザーのプールごと、またはユーザーのサイトごと、またはユーザーごとに適用されます。



</div>

グローバルポリシーは、常設チャットサーバーを展開するときに自動的に作成されますが、構成することはできますが、削除することはできません。 グローバル ポリシーはすべてのユーザーに適用されるため、ユーザーごとに設定する必要はありません。

グローバルポリシーと共に、常設チャットサーバーに対してユーザーを有効にする複数のサイトおよびユーザーポリシーを作成し、構成することができます。 プールおよびサイト常設チャットサーバーポリシーは、そのサイトのユーザーに対してのみ、グローバル常設チャットサーバーポリシーを上書きします。 ユーザーポリシーは、ユーザーポリシーが割り当てられているユーザーのグローバル、プール、およびサイトポリシーの両方を上書きします。

<div>


> [!NOTE]  
> 常設チャットサーバーを構成して使用するには、まず、トポロジビルダーを使用して、常設チャットサーバーのサポートをトポロジに追加してから、トポロジを公開する必要があります。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</A>」を参照してください。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 で常設チャットのグローバルポリシーを構成する](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Lync Server 2013 で常設チャットのサイトポリシーを作成する](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Lync Server 2013 で常設チャット用のユーザーポリシーを作成する](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Lync Server 2013 で常設チャットポリシーをユーザーまたはユーザーグループに適用する](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

