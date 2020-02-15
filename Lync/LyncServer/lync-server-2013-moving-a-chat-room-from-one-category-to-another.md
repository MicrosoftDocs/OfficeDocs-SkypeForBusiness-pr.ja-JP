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
ms.openlocfilehash: 40077d8092f8b0b78b6e9ce78cd16c6f1e0812f0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="3fc6b-102">Lync Server 2013 での1つのカテゴリから別のカテゴリへのチャットルームの移動</span><span class="sxs-lookup"><span data-stu-id="3fc6b-102">Moving a chat room from one category to another in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fc6b-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3fc6b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3fc6b-104">チャットルームの作成後は、常設チャットルームのカテゴリを変更しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3fc6b-104">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="3fc6b-105">ただし、チャット ルーム マネージャーが別のカテゴリの**作成者**特権を持っている場合、ルームを別のカテゴリに移動できます。</span><span class="sxs-lookup"><span data-stu-id="3fc6b-105">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="3fc6b-106">ルームは削除されるのではなく、再作成されます。</span><span class="sxs-lookup"><span data-stu-id="3fc6b-106">The room is not deleted and recreated.</span></span> <span data-ttu-id="3fc6b-107">データベース内での関連付けの変更です。</span><span class="sxs-lookup"><span data-stu-id="3fc6b-107">It is a change of association within the database.</span></span>

<span data-ttu-id="3fc6b-p102">チャット ルームのカテゴリの変更は、できるだけ行わないようにする必要があります。カテゴリはチャット ルームの許可されるメンバーシップを決定するので、チャット ルームを別のカテゴリに移動すると、新しいカテゴリでサポートされなくなったシステム アクセス制御リスト (SACL) は削除されます。たとえば、移動前のルームのメンバーが、新しいカテゴリに移動することにより **AllowedMember** ではなくなると、ルームのメンバーシップが変更されて、そのユーザーはルームから削除されます。</span><span class="sxs-lookup"><span data-stu-id="3fc6b-p102">Changing a chat room category should be done rarely. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="3fc6b-111">Windows PowerShell コマンドラインインターフェイスを使用してチャットルームを移動する方法の詳細については、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成する](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)」の「room Management」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fc6b-111">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="3fc6b-112">チャットルームの構成の詳細については、「展開」のドキュメントの「 [Configure 室 In Lync Server 2013](lync-server-2013-configure-rooms.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fc6b-112">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

