---
title: 'Lync Server 2013: ユーザーおよびユーザーグループのドメインをルームカテゴリに追加する'
description: 'Lync Server 2013: ユーザーおよびユーザーグループのドメインをルームカテゴリに追加します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding domains of users and user groups to the room category
ms:assetid: ee03f2cf-1c84-41c4-b524-d0729be33b8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215884(v=OCS.15)
ms:contentKeyID: 48706013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 196a795547d5caa6dfd1732c3d6b4630ef79438a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573523"
---
# <a name="adding-domains-of-users-and-user-groups-to-the-room-category-in-lync-server-2013"></a>Lync Server 2013 でユーザーおよびユーザーグループのドメインをルームカテゴリに追加する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-07_

より大規模なユーザーグループをチャットルームに追加するには、「展開」のドキュメントの「 [Configure categories In Lync Server 2013](lync-server-2013-configure-categories.md) 」および「 [Manage categories](manage-categories.md) 」を参照してください。 たとえば、次のコマンドは、active Directory の NorthAmericaUsers OU のすべてのユーザーを NorthAmerica チャットルームに追加します。

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=litwareinc,DC=com"}

このコマンドは、Finance 配布グループのすべてのメンバーを同じチャットルームに追加します。

    Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.litwareinc.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=litwareinc,DC=com"}

</div>

<span> </span>

</div>

</div>

</div>

