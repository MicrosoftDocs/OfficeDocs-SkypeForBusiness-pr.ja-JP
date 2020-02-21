---
title: 'Lync Server 2013: 応答グループエージェントグループの作成'
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
ms.openlocfilehash: 0c413da0d5ca1af063bb1be937a118f1056f39da
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a>応答グループエージェントグループの作成 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-12_

エージェントグループを作成するときは、グループに割り当てられているエージェントを選択し、ルーティング方法や、エージェントがグループに対して送受信できるかどうかなど、追加のグループ設定を指定します。

グループにサインインまたは拒否する必要があるエージェント (Lync Server のサインイン時またはログアウト時とは異なる) は、*正式なエージェント*と呼ばれます。 正式なエージェントは、グループにルーティングされる通話を受信する前に、グループにサインインする必要があります。 これは、パートタイム ベースでグループから通話に応答するエージェントには便利な方法です。 正式なエージェント Lync 2013 のメニュー項目をクリックして、Windows Internet Explorer の Internet browser を開き、web ページコンソールを表示することによって、グループにサインインおよびサインアウトします。

グループにサインインしていない、またはグループ外にいるエージェントは、*非公式なエージェント*と呼ばれます。 非公式のエージェントは、Lync Server にサインインするときにグループに自動的にサインインします。グループからサインアウトすることはできません。

<div>


> [!NOTE]  
> 社内ユーザーのみがエージェントであることができます。エージェントが社内からオンラインに移動した場合、応答グループ呼び出しはそのエージェントに送られません。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

[Lync Server 2013 でエージェントグループを作成または変更する](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

