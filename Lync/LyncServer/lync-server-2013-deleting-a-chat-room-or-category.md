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

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a><span data-ttu-id="2acad-102">Lync Server 2013 でのチャットルームまたはカテゴリの削除</span><span class="sxs-lookup"><span data-stu-id="2acad-102">Deleting a chat room or category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2acad-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2acad-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2acad-104">常設チャットルームを削除できます。</span><span class="sxs-lookup"><span data-stu-id="2acad-104">Persistent Chat rooms can be deleted.</span></span> <span data-ttu-id="2acad-105">使用しなくなったチャット ルームは、無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2acad-105">If you have a chat room that is no longer being used, you can disable it.</span></span> <span data-ttu-id="2acad-106">詳細について[は、「Lync Server 2013 でチャットルームの無効化または有効化](lync-server-2013-disabling-or-enabling-a-chat-room.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2acad-106">For details, see [Disabling or enabling a chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span></span>

<span data-ttu-id="2acad-107">常設チャット管理者は、Windows PowerShell コマンドレットを使用して、無効にされたチャットルームに対してクエリを実行し、チャットルームを定期的に削除して完全に削除することができます。 **clear-cspersistentchatroom**を使用します。</span><span class="sxs-lookup"><span data-stu-id="2acad-107">A Persistent Chat administrator can query for disabled chat rooms, and can periodically purge and permanently delete the chat rooms, by using the Windows PowerShell cmdlet, **Remove-CsPersistentChatRoom**.</span></span>

<span data-ttu-id="2acad-108">カテゴリは削除できます。</span><span class="sxs-lookup"><span data-stu-id="2acad-108">Categories can be deleted.</span></span> <span data-ttu-id="2acad-109">ただし、カテゴリを削除するには、まずその下にあるすべてのチャットルームを削除するか、または新しいカテゴリにチャットルームを移動して、削除のために空のカテゴリを残す必要があります。</span><span class="sxs-lookup"><span data-stu-id="2acad-109">However, to delete a category, you must first either delete all chat rooms under it or move the chat rooms to a new category, leaving an empty category for deletion.</span></span> <span data-ttu-id="2acad-110">常設チャットサーバーでは、チャットルームを含むカテゴリを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="2acad-110">Persistent Chat Server does not allow you to delete a category that contains chat rooms.</span></span> <span data-ttu-id="2acad-111">詳細については、「 [Lync Server 2013 の1つのカテゴリから別のカテゴリへのチャットルームの移動](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2acad-111">For details, see [Moving a chat room from one category to another in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span></span>

<span data-ttu-id="2acad-112">Windows PowerShell コマンドラインインターフェイスを使用して空のカテゴリを削除する方法の詳細については、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成する](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)」の「Room Management」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2acad-112">For details about deleting empty categories by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="2acad-113">チャットルームおよびカテゴリの詳細については、「展開」のドキュメントの「 [configure 部屋 In lync server 2013](lync-server-2013-configure-rooms.md) 」および「 [Configure Categories in lync server 2013](lync-server-2013-configure-categories.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2acad-113">For details about chat rooms and categories, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) and [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

