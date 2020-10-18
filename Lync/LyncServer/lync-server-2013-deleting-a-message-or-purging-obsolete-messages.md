---
title: 'Lync Server 2013: メッセージの削除または廃止メッセージの削除'
description: 'Lync Server 2013: メッセージの削除または廃止メッセージの削除。'
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
ms.openlocfilehash: 928e34d2ab52b02155568c7da96e4ac1d8154b7a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575823"
---
# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a><span data-ttu-id="e02e2-103">Lync Server 2013 でのメッセージの削除または廃止されたメッセージの削除</span><span class="sxs-lookup"><span data-stu-id="e02e2-103">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e02e2-104">_**トピックの最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="e02e2-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="e02e2-105">常設チャット管理者は、常設チャットルームからメッセージを削除できます (必要に応じて別のメッセージに置き換えることもできます)。</span><span class="sxs-lookup"><span data-stu-id="e02e2-105">A Persistent Chat administrator can delete a message from a Persistent Chat room (and, optionally, can replace it with another message).</span></span> <span data-ttu-id="e02e2-106">管理者は、継続的なメンテナンスの一環として、古いメッセージを削除して、データベースの拡大を最小限にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e02e2-106">Administrators can also purge obsolete messages as part of ongoing maintenance, to minimize growth of the database.</span></span> <span data-ttu-id="e02e2-107">たとえば、次の Windows PowerShell コマンドは、ユーザー kenmyer@litwareinc.com によって投稿された ITChatRoom チャットルームからのすべてのメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="e02e2-107">For example, this Windows PowerShell command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@litwareinc.com:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="e02e2-108">次の使用例は、削除されたメッセージをすべて、メッセージが使用できなくなったことを示すメモに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e02e2-108">And this example replaces any removed messages with the note that the message is no longer available:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

<span data-ttu-id="e02e2-109">詳細については、 [test-cspersistentchatmessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e02e2-109">For more information, see the help topic for the [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

