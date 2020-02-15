---
title: 'Lync Server 2013: カテゴリ、ルーム、およびアドインの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing categories, rooms, and add-ins
ms:assetid: a9807031-7369-4a51-9369-6f09bec24141
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412799(v=OCS.15)
ms:contentKeyID: 48185100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c1fcd4422ca855e7247c57d07887b9df20ea695
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-categories-rooms-and-add-ins-in-lync-server-2013"></a><span data-ttu-id="672fd-102">Lync Server 2013 でのカテゴリ、ルーム、およびアドインの管理</span><span class="sxs-lookup"><span data-stu-id="672fd-102">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="672fd-103">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="672fd-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="672fd-104">Lync Server 2013 コントロールパネル、または Windows PowerShell コマンドレットを使用すると、常設チャット管理者は**常設チャット**ページを使用してカテゴリとアドインを作成できます。常設チャットルームを管理するために、管理者は Windows PowerShell コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="672fd-104">In Lync Server 2013 Control Panel, or by using Windows PowerShell cmdlets, Persistent Chat Administrators can use the **Persistent Chat** page to create categories and add-ins. For managing Persistent Chat rooms, Administrators can use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="672fd-105">別の方法として、常設チャット管理者も SIP を有効にしている場合は、Lync クライアントを使用して、チャットルームを作成して管理するための web ページを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="672fd-105">Alternatively, if the Persistent Chat administrator is also SIP-enabled, they can use the Lync client to launch a web page to create and manage chat rooms.</span></span>

<span data-ttu-id="672fd-106">以下のトピックでは、カテゴリおよびチャット ルームを作成して使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="672fd-106">The following topics describe how to create and work with categories and chat rooms.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="672fd-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="672fd-107">In This Section</span></span>

  - [<span data-ttu-id="672fd-108">Lync Server 2013 での新しいカテゴリの作成または編集</span><span class="sxs-lookup"><span data-stu-id="672fd-108">Creating or editing a new category in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-category.md)

  - [<span data-ttu-id="672fd-109">Lync Server 2013 での新しい会議室の作成または編集</span><span class="sxs-lookup"><span data-stu-id="672fd-109">Creating or editing a new room in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-room.md)

  - [<span data-ttu-id="672fd-110">Lync Server 2013 でのルーム用の新しいアドインの作成</span><span class="sxs-lookup"><span data-stu-id="672fd-110">Creating new add-ins for rooms in Lync Server 2013</span></span>](lync-server-2013-creating-new-add-ins-for-rooms.md)

  - [<span data-ttu-id="672fd-111">Lync Server 2013 の大会議室のチャットルームでメッセージを投稿できるユーザーの設定</span><span class="sxs-lookup"><span data-stu-id="672fd-111">Setting who can post messages in an auditorium chat room in Lync Server 2013</span></span>](lync-server-2013-setting-who-can-post-messages-in-an-auditorium-chat-room.md)

  - [<span data-ttu-id="672fd-112">Lync Server 2013 でのチャットルームの無効化または有効化</span><span class="sxs-lookup"><span data-stu-id="672fd-112">Disabling or enabling a chat room in Lync Server 2013</span></span>](lync-server-2013-disabling-or-enabling-a-chat-room.md)

  - [<span data-ttu-id="672fd-113">Lync Server 2013 での1つのカテゴリから別のカテゴリへのチャットルームの移動</span><span class="sxs-lookup"><span data-stu-id="672fd-113">Moving a chat room from one category to another in Lync Server 2013</span></span>](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)

  - [<span data-ttu-id="672fd-114">Lync Server 2013 でのチャットルームまたはカテゴリの削除</span><span class="sxs-lookup"><span data-stu-id="672fd-114">Deleting a chat room or category in Lync Server 2013</span></span>](lync-server-2013-deleting-a-chat-room-or-category.md)

  - [<span data-ttu-id="672fd-115">Lync Server 2013 でのメッセージの削除または廃止されたメッセージの削除</span><span class="sxs-lookup"><span data-stu-id="672fd-115">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>](lync-server-2013-deleting-a-message-or-purging-obsolete-messages.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

