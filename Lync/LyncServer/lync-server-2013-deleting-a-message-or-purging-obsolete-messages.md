---
title: 'Lync Server 2013: メッセージの削除または廃止メッセージの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a message or purging obsolete messages
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215874(v=OCS.15)
ms:contentKeyID: 48706000
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8040d52690628b6085727d6a1fdac9288b94d5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a>Lync Server 2013 でのメッセージの削除または廃止メッセージの削除

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-05_

常設チャット管理者は、常設チャットルームからのメッセージを削除できます (必要に応じて、別のメッセージに置き換えることができます)。 管理者は、継続的なメンテナンスの一部として古いメッセージを削除することで、データベースの増加を最小限に抑えることができます。 たとえば、次の Windows PowerShell コマンドは、ユーザー kenmyer@litwareinc.com によって投稿されたすべてのメッセージを ITChatRoom チャットルームから削除します。

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

この例では、削除されたすべてのメッセージを、メッセージが利用できなくなったというメモに置き換えます。

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

詳細については、 [CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage)コマンドレットのヘルプトピックを参照してください。

</div>

<span> </span>

</div>

</div>

</div>

