---
title: 'Lync Server 2013: 1 つのカテゴリから他のカテゴリへのチャット ルームの移動'
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
ms.openlocfilehash: 72f9774e53321ff6fe667b3b8c8dcfe0e78bcdaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>Lync Server 2013 での 1 つのカテゴリから他のカテゴリへのチャット ルームの移動

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

チャットルームの作成後は、常設チャットルームのカテゴリを変更しないことをお勧めします。 ただし、チャットルームマネージャーが別のカテゴリで**Creator**権限を持っている場合は、そのカテゴリから別のカテゴリにルームを移動することができます。 会議室は削除されず、再び作成されることはありません。 データベース内の関連付けの変更です。

チャットルームのカテゴリを変更することはめったにありません。 カテゴリはチャット ルームの許可されるメンバーシップを決定するので、チャット ルームを別のカテゴリに移動すると、新しいカテゴリでサポートされなくなったシステム アクセス制御リスト (SACL) は削除されます。 たとえば、ユーザーが会議室のメンバーであり、新しいカテゴリの**Allowedmember**ではなくなった場合、会議室のメンバーシップが変更され、ユーザーはルームから削除されます。

Windows PowerShell コマンドラインインターフェイスを使用してチャットルームを移動する方法について詳しくは、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)する」の「会議室の管理」をご覧ください。

チャットルームの設定の詳細については、展開ドキュメントの「 [Lync Server 2013 で会議室を構成](lync-server-2013-configure-rooms.md)する」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

