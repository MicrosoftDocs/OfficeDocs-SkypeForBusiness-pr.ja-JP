---
title: 'Lync Server 2013: チャット ルームの無効化または有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f89862b4f7e38a637fa183641f8cdc75e0491379
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>Lync Server 2013 でのチャット ルームの無効化または有効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-05_

常設チャットルームのトピックが不要になった場合は、そのチャットルームを無効にしてユーザーが利用できないようにすることができます。 チャット ルームを無効にすると、すべてのメンバーがチャット ルームから即座に切断されます。 チャット ルームを無効にした後、ユーザーは、そのチャット ルームに再び参加することも、チャット ルームを検索することもできません。

無効になったチャットルームは、常設チャット管理者が後で有効にすることができます。 チャットルームを無効にすると、そのメンバーのメンバーシップリストとその他の設定が保持されます。 もう一度会議室を有効にした場合は、手動で設定を再作成する必要はありません。

チャットルームの履歴が残っている場合 (チャットルームの履歴の保存は、カテゴリ内のすべての会議室に適用されるカテゴリのオプションの設定です。既定では、これは永続的ですが、カテゴリの [**チャット履歴を有効**にする] に設定してオフにすることができます。false) チャットルームを無効にすると、コンテンツは保持されます。 ただし、チャット ルームが無効になっている間、コンテンツは検索に表示されません。 チャット ルームを後で有効にすると、ユーザーは、チャット ルームが無効になる前に投稿されたメッセージを検索できます。

Windows PowerShell コマンドラインインターフェイスを使用してチャットルームを無効にして有効にする方法について詳しくは、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)する」の「会議室の管理」をご覧ください。 チャットルームを無効にするには、次のようなコマンドを使用します。

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

チャットルームを有効にするには、Disabled プロパティを False に設定します。

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Lync Server コントロールパネルを使用して、チャットルームを有効または無効にすることはできません。

チャットルームの設定の詳細については、展開ドキュメントの「 [Lync Server 2013 で会議室を構成](lync-server-2013-configure-rooms.md)する」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

