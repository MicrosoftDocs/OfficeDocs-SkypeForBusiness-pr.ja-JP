---
title: 'Lync Server 2013: 1 つのカテゴリから別のカテゴリへのチャットルームの移動'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bde33220c13b5a484f66131ce6090d57d3b9bae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>Lync Server 2013 での1つのカテゴリから別のカテゴリへのチャットルームの移動

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

チャットルームの作成後は、常設チャットルームのカテゴリを変更しないことをお勧めします。 ただし、チャット ルーム マネージャーが別のカテゴリの**作成者**特権を持っている場合、ルームを別のカテゴリに移動できます。 ルームは削除されるのではなく、再作成されます。 データベース内での関連付けの変更です。

チャット ルームのカテゴリの変更は、できるだけ行わないようにする必要があります。カテゴリはチャット ルームの許可されるメンバーシップを決定するので、チャット ルームを別のカテゴリに移動すると、新しいカテゴリでサポートされなくなったシステム アクセス制御リスト (SACL) は削除されます。たとえば、移動前のルームのメンバーが、新しいカテゴリに移動することにより **AllowedMember** ではなくなると、ルームのメンバーシップが変更されて、そのユーザーはルームから削除されます。

Windows PowerShell コマンドラインインターフェイスを使用してチャットルームを移動する方法の詳細については、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成する](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)」の「room Management」を参照してください。

チャットルームの構成の詳細については、「展開」のドキュメントの「 [Configure 室 In Lync Server 2013](lync-server-2013-configure-rooms.md) 」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

