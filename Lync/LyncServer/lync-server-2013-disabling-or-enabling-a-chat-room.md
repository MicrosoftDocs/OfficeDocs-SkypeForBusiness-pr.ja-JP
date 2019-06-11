---
title: 'Lync Server 2013: チャット ルームの無効化または有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f89862b4f7e38a637fa183641f8cdc75e0491379
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="d686a-102">Lync Server 2013 でのチャット ルームの無効化または有効化</span><span class="sxs-lookup"><span data-stu-id="d686a-102">Disabling or enabling a chat room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d686a-103">_**最終更新日:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="d686a-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="d686a-104">常設チャットルームのトピックが不要になった場合は、そのチャットルームを無効にしてユーザーが利用できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d686a-104">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="d686a-105">チャット ルームを無効にすると、すべてのメンバーがチャット ルームから即座に切断されます。</span><span class="sxs-lookup"><span data-stu-id="d686a-105">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="d686a-106">チャット ルームを無効にした後、ユーザーは、そのチャット ルームに再び参加することも、チャット ルームを検索することもできません。</span><span class="sxs-lookup"><span data-stu-id="d686a-106">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="d686a-107">無効になったチャットルームは、常設チャット管理者が後で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d686a-107">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="d686a-108">チャットルームを無効にすると、そのメンバーのメンバーシップリストとその他の設定が保持されます。</span><span class="sxs-lookup"><span data-stu-id="d686a-108">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="d686a-109">もう一度会議室を有効にした場合は、手動で設定を再作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d686a-109">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="d686a-110">チャットルームの履歴が残っている場合 (チャットルームの履歴の保存は、カテゴリ内のすべての会議室に適用されるカテゴリのオプションの設定です。既定では、これは永続的ですが、カテゴリの [**チャット履歴を有効**にする] に設定してオフにすることができます。false) チャットルームを無効にすると、コンテンツは保持されます。</span><span class="sxs-lookup"><span data-stu-id="d686a-110">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="d686a-111">ただし、チャット ルームが無効になっている間、コンテンツは検索に表示されません。</span><span class="sxs-lookup"><span data-stu-id="d686a-111">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="d686a-112">チャット ルームを後で有効にすると、ユーザーは、チャット ルームが無効になる前に投稿されたメッセージを検索できます。</span><span class="sxs-lookup"><span data-stu-id="d686a-112">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="d686a-113">Windows PowerShell コマンドラインインターフェイスを使用してチャットルームを無効にして有効にする方法について詳しくは、「 [Windows powershell コマンドレットを使用して常設チャットサーバーを構成](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)する」の「会議室の管理」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d686a-113">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="d686a-114">チャットルームを無効にするには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d686a-114">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="d686a-115">チャットルームを有効にするには、Disabled プロパティを False に設定します。</span><span class="sxs-lookup"><span data-stu-id="d686a-115">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="d686a-116">Lync Server コントロールパネルを使用して、チャットルームを有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d686a-116">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="d686a-117">チャットルームの設定の詳細については、展開ドキュメントの「 [Lync Server 2013 で会議室を構成](lync-server-2013-configure-rooms.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d686a-117">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

