---
title: 'Lync Server 2013: チャット ルームまたはカテゴリの削除'
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
ms.openlocfilehash: 74cf41679a21612e67c4a793c09ae3484377ef6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a><span data-ttu-id="38254-102">Lync Server 2013 でのチャット ルームまたはカテゴリの削除</span><span class="sxs-lookup"><span data-stu-id="38254-102">Deleting a chat room or category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38254-103">_**最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="38254-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="38254-104">常設チャットルームを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="38254-104">Persistent Chat rooms can be deleted.</span></span> <span data-ttu-id="38254-105">使用されなくなったチャットルームがある場合は、無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="38254-105">If you have a chat room that is no longer being used, you can disable it.</span></span> <span data-ttu-id="38254-106">詳細については、「 [Lync Server 2013 でチャットルームを無効または有効にする](lync-server-2013-disabling-or-enabling-a-chat-room.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38254-106">For details, see [Disabling or enabling a chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span></span>

<span data-ttu-id="38254-107">常設チャット管理者は、Windows PowerShell コマンドレット**CsPersistentChatRoom**を使って、チャットルームを検索して、定期的にチャットルームを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="38254-107">A Persistent Chat administrator can query for disabled chat rooms, and can periodically purge and permanently delete the chat rooms, by using the Windows PowerShell cmdlet, **Remove-CsPersistentChatRoom**.</span></span>

<span data-ttu-id="38254-108">分類項目を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="38254-108">Categories can be deleted.</span></span> <span data-ttu-id="38254-109">ただし、分類項目を削除するには、まずその下にあるすべてのチャットルームを削除するか、チャットルームを新しいカテゴリに移動して、削除する空のカテゴリを残しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="38254-109">However, to delete a category, you must first either delete all chat rooms under it or move the chat rooms to a new category, leaving an empty category for deletion.</span></span> <span data-ttu-id="38254-110">常設チャットサーバーでは、チャットルームを含むカテゴリを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="38254-110">Persistent Chat Server does not allow you to delete a category that contains chat rooms.</span></span> <span data-ttu-id="38254-111">詳細については、「 [Lync Server 2013 で1つのカテゴリのチャットルームを別のカテゴリに移動する](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38254-111">For details, see [Moving a chat room from one category to another in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span></span>

<span data-ttu-id="38254-112">Windows PowerShell コマンドラインインターフェイスを使用して空のカテゴリを削除する方法の詳細については、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)する」の「会議室の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38254-112">For details about deleting empty categories by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="38254-113">チャットルームとカテゴリの詳細については、展開ドキュメントの「lync [server 2013 で会議室を構成](lync-server-2013-configure-rooms.md)する」および「 [lync server 2013 でカテゴリを構成する](lync-server-2013-configure-categories.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38254-113">For details about chat rooms and categories, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) and [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

