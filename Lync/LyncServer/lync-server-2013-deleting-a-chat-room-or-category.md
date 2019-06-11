---
title: 'Lync Server 2013: チャット ルームまたはカテゴリの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f64b89abd0b3266d2be52e300458ceabf3f9b915
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>Lync Server 2013 でのチャット ルームまたはカテゴリの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

常設チャットルームを削除することができます。 使用されなくなったチャットルームがある場合は、無効にすることができます。 詳細については、「 [Lync Server 2013 でチャットルームを無効または有効にする](lync-server-2013-disabling-or-enabling-a-chat-room.md)」を参照してください。

常設チャット管理者は、Windows PowerShell コマンドレット**CsPersistentChatRoom**を使って、チャットルームを検索して、定期的にチャットルームを削除することができます。

分類項目を削除することができます。 ただし、分類項目を削除するには、まずその下にあるすべてのチャットルームを削除するか、チャットルームを新しいカテゴリに移動して、削除する空のカテゴリを残しておく必要があります。 常設チャットサーバーでは、チャットルームを含むカテゴリを削除することはできません。 詳細については、「 [Lync Server 2013 で1つのカテゴリのチャットルームを別のカテゴリに移動する](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)」を参照してください。

Windows PowerShell コマンドラインインターフェイスを使用して空のカテゴリを削除する方法の詳細については、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)する」の「会議室の管理」を参照してください。

チャットルームとカテゴリの詳細については、展開ドキュメントの「lync [server 2013 で会議室を構成](lync-server-2013-configure-rooms.md)する」および「 [lync server 2013 でカテゴリを構成する](lync-server-2013-configure-categories.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

