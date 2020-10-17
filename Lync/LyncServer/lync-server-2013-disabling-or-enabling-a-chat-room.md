---
title: 'Lync Server 2013: チャットルームの無効化または有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 088ea4f3441716efdec748222e9aefeca9643a77
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528964"
---
# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="9bb95-102">Lync Server 2013 でのチャットルームの無効化または有効化</span><span class="sxs-lookup"><span data-stu-id="9bb95-102">Disabling or enabling a chat room in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bb95-103">_**トピックの最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="9bb95-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="9bb95-104">常設チャットルームのトピックが関連していない場合は、無効にすることでチャットルームをユーザーが使用できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9bb95-104">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="9bb95-105">チャットルームが無効になると、すべてのメンバーが会議室からすぐに切断されます。</span><span class="sxs-lookup"><span data-stu-id="9bb95-105">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="9bb95-106">チャットルームが無効になると、ユーザーはチャットルームの検索で再参加または検索を行うことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="9bb95-106">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="9bb95-107">常設チャットの管理者は、無効にされたチャットルームを後で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9bb95-107">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="9bb95-108">チャット ルームを無効にすると、メンバーシップ リストとその他の設定が保持されます。</span><span class="sxs-lookup"><span data-stu-id="9bb95-108">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="9bb95-109">会議室を再度有効にする場合は、手動で設定を再作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9bb95-109">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="9bb95-110">チャットルームの履歴が残っている場合 (チャットルームの履歴の永続は、カテゴリ内のすべての会議に適用されるカテゴリのオプションの設定です。既定では、固定されていますが、カテゴリの [ **チャットの有効** ] を false に設定することによって無効にすることができます)、チャットルームが無効にされて</span><span class="sxs-lookup"><span data-stu-id="9bb95-110">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="9bb95-111">ただし、チャットルームが無効の状態のままになるときには、そのコンテンツは検索に表示されません。</span><span class="sxs-lookup"><span data-stu-id="9bb95-111">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="9bb95-112">後でチャットルームを有効にした場合、ユーザーはチャットルームが無効になる前に投稿されたメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="9bb95-112">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="9bb95-113">Windows PowerShell コマンドラインインターフェイスを使用してチャットルームを無効および有効にする方法の詳細については、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成する](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)」の「Room Management」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bb95-113">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="9bb95-114">チャットルームを無効にするには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="9bb95-114">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="9bb95-115">チャットルームを有効にするには、Disabled プロパティを False に設定します。</span><span class="sxs-lookup"><span data-stu-id="9bb95-115">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="9bb95-116">なお、チャットルームは、Lync Server コントロールパネルを使用して有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9bb95-116">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="9bb95-117">チャットルームの構成の詳細については、「展開」のドキュメントの「 [Configure 室 In Lync Server 2013](lync-server-2013-configure-rooms.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bb95-117">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

