---
title: 'Lync Server 2013: 新しいルームの作成または編集'
description: 'Lync Server 2013: 新しいルームを作成または編集しています。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d822eb05993f77c57200e29364f0a6a68509450b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562983"
---
# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>Lync Server 2013 での新しい会議室の作成または編集

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-03-19_

常設チャットルームの構成は、通常、ユーザーによって処理されます。通常、常設チャット管理者はチャットルームの構成や管理は行いません。 ルームを管理するための Windows PowerShell コマンドレットは、 **CsPersistentChatAdministrator** 管理者のみが利用できます。

特定のカテゴリの作成 **者である** ユーザーは、Lync クライアントを使用して会議室を作成および管理できます。 特定のチャット ルームのマネージャーとして指定されているユーザーは、ルームのプロパティまたはメンバーシップの編集など、チャット ルームの継続的な管理を実行することもできます。

<div>


> [!TIP]  
> 常設チャット管理者は、作成者にすることもできます。また、クリエーターに課される制限の対象にすることもありません。



</div>

必要に応じて、常設チャット管理者は、Windows PowerShell コマンドレットを使用する代わりに、ユーザーインターフェイスを使用してチャットルームを作成および管理できます。 これを行うには、常設チャットサーバーの管理者を SIP で有効にしてから、Lync クライアントを使用してチャットルームを作成して管理します。

ユーザーに対してカスタムの会議室管理ワークフローを作成する場合は、常設チャットサーバー構成の **RoomManagementUrl** プロパティを設定して、ユーザーを Lync クライアントからカスタムソリューションにリダイレクトすることができます。

Windows PowerShell コマンドラインインターフェイスを使用したチャットルームの構成の詳細については、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)する」の「Room Management」を参照してください。

チャットルームの構成の詳細については、「展開」のドキュメントの「 [Configure 室 In Lync Server 2013](lync-server-2013-configure-rooms.md) 」を参照してください。

<div>


> [!NOTE]  
> 常設チャットサーバーを使用すると、ユーザーは特定のサイトのチャットルームを作成して管理できます。 ただし、ユーザーは同じトポロジ内の他のサイトでチャットルームを作成または管理することはできません。 組織内のすべてのサイトについて、チャットルームの作成者とマネージャーを必ず指定してください。



</div>

<div>


> [!NOTE]  
> Lync Server 存続可能 Branch アプライアンスに所属しているユーザーは、新しいチャットルームを作成したり、既存のルームのルームカードを表示したりすることはできません。



</div>

</div>

<span> </span>

</div>

</div>

</div>

