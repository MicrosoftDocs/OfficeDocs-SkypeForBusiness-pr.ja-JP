---
title: 'Lync Server 2013: ホストボイスメールポリシーの管理'
description: 'Lync Server 2013: ホストボイスメールポリシーを管理します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage hosted voice mail policies
ms:assetid: 50ff22e3-9c8b-4a33-a72f-d149892acf53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398332(v=OCS.15)
ms:contentKeyID: 48184139
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcb5e98884d37540d5e75cc8cb6b1b419e4e75e6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556763"
---
# <a name="manage-hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="42405-103">Lync Server 2013 でホストボイスメールポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="42405-103">Manage hosted voice mail policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42405-104">_**トピックの最終更新日:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="42405-104">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="42405-105">*ホストボイスメールポリシー*は、ホストされた Exchange サービスにメールボックスがあるユーザーの呼び出しをルーティングする場所について、Lync Server 2013 Exum ルーティングアプリケーションに情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="42405-105">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="42405-p101">通常、必要なのは 1 つのホスト ボイス メール ポリシーのみです。 多くの場合、すべてのニーズが満たされるようにグローバル ポリシーを変更することができます。 サイト スコープでポリシーを作成すると、そのポリシーは、指定のサイトに存在するすべてのユーザーに自動的に割り当てられます。 ユーザー単位のスコープでポリシーを作成する場合は、そのポリシーをユーザー、グループ、および連絡先オブジェクトに明示的に割り当てる必要があります。 複数のホスト ボイス メール ポリシーを展開できますが、その場合は、ポリシーをユーザーごとに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="42405-p101">Typically, only one hosted voice mail policy is required. In many cases, you can modify the global policy to meet all your needs. If you create a policy with site scope, it is assigned automatically to all users homed at the specified site. If you create a policy with per-user scope, you must explicitly assign it to users, groups, and contact objects. It is possible to deploy multiple hosted voice mail policies, but in that case the policies must be assigned on a per-user basis.</span></span>



</div>

<span data-ttu-id="42405-111">ホストボイスメールポリシーの計画の詳細については、「計画」のドキュメントの「 [hosted voice mail policies In Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42405-111">For details about planning hosted voice mail policies, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="42405-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="42405-112">In This Section</span></span>

  - [<span data-ttu-id="42405-113">Lync Server 2013 でのグローバルホストボイスメールポリシーの変更</span><span class="sxs-lookup"><span data-stu-id="42405-113">Modify the global hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-modify-the-global-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="42405-114">Lync Server 2013 でサイトレベルのホストボイスメールポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="42405-114">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-site-level-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="42405-115">Lync Server 2013 でユーザーごとのホストボイスメールポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="42405-115">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-per-user-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="42405-116">Lync Server 2013 でユーザーごとにホストされるボイスメールポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="42405-116">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

