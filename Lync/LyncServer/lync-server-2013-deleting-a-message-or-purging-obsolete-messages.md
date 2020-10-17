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
ms.openlocfilehash: db44ca77d217c1b7bc0bc4d05c56cb9b6ff99ea4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525454"
---
# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a>Lync Server 2013 でのメッセージの削除または廃止されたメッセージの削除

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-02-05_

常設チャット管理者は、常設チャットルームからメッセージを削除できます (必要に応じて別のメッセージに置き換えることもできます)。 管理者は、継続的なメンテナンスの一環として、古いメッセージを削除して、データベースの拡大を最小限にすることもできます。 たとえば、次の Windows PowerShell コマンドは、ユーザー kenmyer@litwareinc.com によって投稿された ITChatRoom チャットルームからのすべてのメッセージを削除します。

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

次の使用例は、削除されたメッセージをすべて、メッセージが使用できなくなったことを示すメモに置き換えます。

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

詳細については、 [test-cspersistentchatmessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) コマンドレットのヘルプトピックを参照してください。

</div>

<span> </span>

</div>

</div>

</div>

