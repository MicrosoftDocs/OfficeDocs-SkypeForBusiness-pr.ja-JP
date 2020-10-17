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
# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a><span data-ttu-id="d98e9-102">Lync Server 2013 でのメッセージの削除または廃止されたメッセージの削除</span><span class="sxs-lookup"><span data-stu-id="d98e9-102">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d98e9-103">_**トピックの最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="d98e9-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="d98e9-104">常設チャット管理者は、常設チャットルームからメッセージを削除できます (必要に応じて別のメッセージに置き換えることもできます)。</span><span class="sxs-lookup"><span data-stu-id="d98e9-104">A Persistent Chat administrator can delete a message from a Persistent Chat room (and, optionally, can replace it with another message).</span></span> <span data-ttu-id="d98e9-105">管理者は、継続的なメンテナンスの一環として、古いメッセージを削除して、データベースの拡大を最小限にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d98e9-105">Administrators can also purge obsolete messages as part of ongoing maintenance, to minimize growth of the database.</span></span> <span data-ttu-id="d98e9-106">たとえば、次の Windows PowerShell コマンドは、ユーザー kenmyer@litwareinc.com によって投稿された ITChatRoom チャットルームからのすべてのメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="d98e9-106">For example, this Windows PowerShell command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@litwareinc.com:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="d98e9-107">次の使用例は、削除されたメッセージをすべて、メッセージが使用できなくなったことを示すメモに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d98e9-107">And this example replaces any removed messages with the note that the message is no longer available:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

<span data-ttu-id="d98e9-108">詳細については、 [test-cspersistentchatmessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d98e9-108">For more information, see the help topic for the [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

