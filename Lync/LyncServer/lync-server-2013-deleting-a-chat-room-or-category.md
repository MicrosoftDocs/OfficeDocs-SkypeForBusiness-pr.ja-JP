---
title: 'Lync Server 2013: チャットルームまたはカテゴリの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c4e346d33e44a9365d9cf4924374c2a28b8b908
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>Lync Server 2013 でのチャットルームまたはカテゴリの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

常設チャットルームを削除できます。 使用しなくなったチャット ルームは、無効にすることができます。 詳細について[は、「Lync Server 2013 でチャットルームの無効化または有効化](lync-server-2013-disabling-or-enabling-a-chat-room.md)」を参照してください。

常設チャット管理者は、Windows PowerShell コマンドレットを使用して、無効にされたチャットルームに対してクエリを実行し、チャットルームを定期的に削除して完全に削除することができます。 **clear-cspersistentchatroom**を使用します。

カテゴリは削除できます。 ただし、カテゴリを削除するには、まずその下にあるすべてのチャットルームを削除するか、または新しいカテゴリにチャットルームを移動して、削除のために空のカテゴリを残す必要があります。 常設チャットサーバーでは、チャットルームを含むカテゴリを削除することはできません。 詳細については、「 [Lync Server 2013 の1つのカテゴリから別のカテゴリへのチャットルームの移動](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)」を参照してください。

Windows PowerShell コマンドラインインターフェイスを使用して空のカテゴリを削除する方法の詳細については、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成する](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)」の「Room Management」を参照してください。

チャットルームおよびカテゴリの詳細については、「展開」のドキュメントの「 [configure 部屋 In lync server 2013](lync-server-2013-configure-rooms.md) 」および「 [Configure Categories in lync server 2013](lync-server-2013-configure-categories.md) 」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

