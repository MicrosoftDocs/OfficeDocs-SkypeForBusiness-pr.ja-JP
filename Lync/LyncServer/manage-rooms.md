---
title: 会議室の管理
description: 会議室を管理する。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be093e14a68639fdde73b58936e1b2f5cf4424cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544593"
---
# <a name="manage-rooms"></a><span data-ttu-id="b6677-103">会議室の管理</span><span class="sxs-lookup"><span data-stu-id="b6677-103">Manage rooms</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6677-104">_**トピックの最終更新日:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b6677-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b6677-105">新しい常設チャットサーバールームを作成するには</span><span class="sxs-lookup"><span data-stu-id="b6677-105">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b6677-106">次のいずれかが当てはまる場合、-PersistentChatPoolFqdn は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b6677-106">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="b6677-107">常設チャットサーバープールは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="b6677-107">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="b6677-108">カテゴリにプール FQDN を提供する。</span><span class="sxs-lookup"><span data-stu-id="b6677-108">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="b6677-109">ルームの追加にプール FQDN を提供する。</span><span class="sxs-lookup"><span data-stu-id="b6677-109">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="b6677-110">既存の常設チャットサーバールームに変更を加えるには</span><span class="sxs-lookup"><span data-stu-id="b6677-110">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="b6677-111">Windows PowerShell: メンバー、マネージャー、プレゼンターは同時に設定できます。</span><span class="sxs-lookup"><span data-stu-id="b6677-111">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="b6677-112">これらはすべて、ホスト カテゴリの AllowedMembers から DeniedMembers を除いたもののサブセットである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6677-112">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="b6677-113">type=normal であるルームは発表者を含むことはできません。</span><span class="sxs-lookup"><span data-stu-id="b6677-113">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="b6677-114">ルームの作成、取得、設定、クリア、または削除</span><span class="sxs-lookup"><span data-stu-id="b6677-114">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="b6677-115">新しいルームを作成するには</span><span class="sxs-lookup"><span data-stu-id="b6677-115">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="b6677-116">ルームを設定するには</span><span class="sxs-lookup"><span data-stu-id="b6677-116">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="b6677-117">ルームを取得するには</span><span class="sxs-lookup"><span data-stu-id="b6677-117">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="b6677-118">または</span><span class="sxs-lookup"><span data-stu-id="b6677-118">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="b6677-119">–filter は名前と説明のみをサポートし、名前/説明がキーワード文字列と一致するルームを検索するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b6677-119">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="b6677-120">PoolFqdn は、指定された常設チャットサーバープール内で検索します。</span><span class="sxs-lookup"><span data-stu-id="b6677-120">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="b6677-121">ルームをクリアし、ルームからメッセージをクリアするには</span><span class="sxs-lookup"><span data-stu-id="b6677-121">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="b6677-122">または</span><span class="sxs-lookup"><span data-stu-id="b6677-122">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="b6677-123">ルームを削除するには</span><span class="sxs-lookup"><span data-stu-id="b6677-123">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="b6677-124">または</span><span class="sxs-lookup"><span data-stu-id="b6677-124">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

