---
title: 'Lync Server 2013: 1 つのカテゴリから他のカテゴリへのチャット ルームの移動'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c61d20ff1de7437054df36af224293dcdcb61d54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="bc270-102">Lync Server 2013 での 1 つのカテゴリから他のカテゴリへのチャット ルームの移動</span><span class="sxs-lookup"><span data-stu-id="bc270-102">Moving a chat room from one category to another in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc270-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bc270-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bc270-104">チャットルームの作成後は、常設チャットルームのカテゴリを変更しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bc270-104">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="bc270-105">ただし、チャットルームマネージャーが別のカテゴリで**Creator**権限を持っている場合は、そのカテゴリから別のカテゴリにルームを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="bc270-105">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="bc270-106">会議室は削除されず、再び作成されることはありません。</span><span class="sxs-lookup"><span data-stu-id="bc270-106">The room is not deleted and recreated.</span></span> <span data-ttu-id="bc270-107">データベース内の関連付けの変更です。</span><span class="sxs-lookup"><span data-stu-id="bc270-107">It is a change of association within the database.</span></span>

<span data-ttu-id="bc270-108">チャットルームのカテゴリを変更することはめったにありません。</span><span class="sxs-lookup"><span data-stu-id="bc270-108">Changing a chat room category should be done rarely.</span></span> <span data-ttu-id="bc270-109">カテゴリはチャット ルームの許可されるメンバーシップを決定するので、チャット ルームを別のカテゴリに移動すると、新しいカテゴリでサポートされなくなったシステム アクセス制御リスト (SACL) は削除されます。</span><span class="sxs-lookup"><span data-stu-id="bc270-109">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="bc270-110">たとえば、ユーザーが会議室のメンバーであり、新しいカテゴリの**Allowedmember**ではなくなった場合、会議室のメンバーシップが変更され、ユーザーはルームから削除されます。</span><span class="sxs-lookup"><span data-stu-id="bc270-110">For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="bc270-111">Windows PowerShell コマンドラインインターフェイスを使用してチャットルームを移動する方法について詳しくは、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)する」の「会議室の管理」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bc270-111">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="bc270-112">チャットルームの設定の詳細については、展開ドキュメントの「 [Lync Server 2013 で会議室を構成](lync-server-2013-configure-rooms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc270-112">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

