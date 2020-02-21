---
title: 'Lync Server 2013: チャットルームの無効化または有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74c8c5d1bc78f41d4c1a2694e50fb99b869b9247
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>Lync Server 2013 でのチャットルームの無効化または有効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-05_

常設チャットルームのトピックが関連していない場合は、無効にすることでチャットルームをユーザーが使用できないようにすることができます。 チャットルームが無効になると、すべてのメンバーが会議室からすぐに切断されます。 チャットルームが無効になると、ユーザーはチャットルームの検索で再参加または検索を行うことができなくなります。

常設チャットの管理者は、無効にされたチャットルームを後で有効にすることができます。 チャット ルームを無効にすると、メンバーシップ リストとその他の設定が保持されます。 会議室を再度有効にする場合は、手動で設定を再作成する必要はありません。

チャットルームの履歴が残っている場合 (チャットルームの履歴の永続は、カテゴリ内のすべての会議に適用されるカテゴリのオプションの設定です。既定では、固定されていますが、カテゴリの [**チャットの有効**] を false に設定することによって無効にすることができます)、チャットルームが無効にされて ただし、チャットルームが無効の状態のままになるときには、そのコンテンツは検索に表示されません。 後でチャットルームを有効にした場合、ユーザーはチャットルームが無効になる前に投稿されたメッセージを検索できます。

Windows PowerShell コマンドラインインターフェイスを使用してチャットルームを無効および有効にする方法の詳細については、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成する](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)」の「Room Management」を参照してください。 チャットルームを無効にするには、次のようなコマンドを使用します。

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

チャットルームを有効にするには、Disabled プロパティを False に設定します。

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

なお、チャットルームは、Lync Server コントロールパネルを使用して有効または無効にすることはできません。

チャットルームの構成の詳細については、「展開」のドキュメントの「 [Configure 室 In Lync Server 2013](lync-server-2013-configure-rooms.md) 」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

