---
title: 'Lync Server 2013: メッセージの削除または廃止メッセージの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a message or purging obsolete messages
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215874(v=OCS.15)
ms:contentKeyID: 48706000
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75e6d383b1c64441f8ff052e390dc141102e8901
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a><span data-ttu-id="4b24e-102">Lync Server 2013 でのメッセージの削除または廃止メッセージの削除</span><span class="sxs-lookup"><span data-stu-id="4b24e-102">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b24e-103">_**最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="4b24e-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="4b24e-104">常設チャット管理者は、常設チャットルームからのメッセージを削除できます (必要に応じて、別のメッセージに置き換えることができます)。</span><span class="sxs-lookup"><span data-stu-id="4b24e-104">A Persistent Chat administrator can delete a message from a Persistent Chat room (and, optionally, can replace it with another message).</span></span> <span data-ttu-id="4b24e-105">管理者は、継続的なメンテナンスの一部として古いメッセージを削除することで、データベースの増加を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="4b24e-105">Administrators can also purge obsolete messages as part of ongoing maintenance, to minimize growth of the database.</span></span> <span data-ttu-id="4b24e-106">たとえば、次の Windows PowerShell コマンドは、ユーザー kenmyer@litwareinc.com によって投稿されたすべてのメッセージを ITChatRoom チャットルームから削除します。</span><span class="sxs-lookup"><span data-stu-id="4b24e-106">For example, this Windows PowerShell command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@litwareinc.com:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="4b24e-107">この例では、削除されたすべてのメッセージを、メッセージが利用できなくなったというメモに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4b24e-107">And this example replaces any removed messages with the note that the message is no longer available:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

<span data-ttu-id="4b24e-108">詳細については、 [CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b24e-108">For more information, see the help topic for the [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

