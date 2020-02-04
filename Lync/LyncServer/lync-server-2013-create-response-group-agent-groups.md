---
title: 'Lync Server 2013: 応答グループのエージェント グループの作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e2a8a41b67818cf1f2aec9ec8daaa46eeff783a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a>Lync Server 2013 での応答グループのエージェント グループの作成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-12_

エージェント グループを作成するときは、そのグループに割り当てるエージェントを選択し、詳細なグループ設定 (ルーティング方法、グループに対するエージェントの権限など) を指定します。

グループからサインアウトする必要があるエージェントは、Lync Server のサインインまたはサインアウトとは異なり、*正式なエージェント*と呼ばれます。 公式エージェントが、グループにルーティングされた着信を受信するには、そのグループにサインインする必要があります。 これは、パートタイム ベースでグループから通話に応答するエージェントには便利な方法です。 正式なエージェントは、Lync 2013 のメニュー項目をクリックして、Windows Internet Explorer のインターネットブラウザーを開き、web ページ本体を表示することによって、グループにサインインおよびサインアウトします。

グループにサインインしていないか、グループからサインアウトしていないエージェントは、"*非公式のエージェント*" と呼ばれます。 非公式のエージェントは、Lync Server へのサインイン時にグループに自動的にサインインされ、グループからサインアウトすることはできません。

<div>


> [!NOTE]  
> エージェントにできるのは社内ユーザーのみです。 エージェントがオンプレミスからオンラインに移行された場合、応答グループの呼び出しはそのエージェントにルーティングされません。



</div>

<div>

## <a name="in-this-section"></a>このセクション中

[Lync Server 2013 でエージェントグループを作成または変更する](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

