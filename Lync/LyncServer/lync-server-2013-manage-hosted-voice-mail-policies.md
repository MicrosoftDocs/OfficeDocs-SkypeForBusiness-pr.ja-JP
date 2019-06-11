---
title: 'Lync Server 2013: ホスト ボイス メール ポリシーの管理'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage hosted voice mail policies
ms:assetid: 50ff22e3-9c8b-4a33-a72f-d149892acf53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398332(v=OCS.15)
ms:contentKeyID: 48184139
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f0db0d2c4e1e8258fb5d9a212084823d1e25f7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="aa0a9-102">Lync Server 2013 でのホスト ボイス メール ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="aa0a9-102">Manage hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa0a9-103">_**最終更新日:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="aa0a9-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="aa0a9-104">ホストされた*ボイスメールポリシー*は、ホストされた Exchange サービス上にあるメールボックスを持つユーザーの呼び出しをルーティングする場所について、Lync Server 2013 Exum ルーティングアプリケーションに情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="aa0a9-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa0a9-105">通常は、1つのホストされたボイスメールポリシーのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="aa0a9-105">Typically, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="aa0a9-106">多くの場合、すべてのニーズに合わせてグローバルポリシーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="aa0a9-106">In many cases, you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="aa0a9-107">サイトのスコープを使用してポリシーを作成すると、指定したサイトに所属するすべてのユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="aa0a9-107">If you create a policy with site scope, it is assigned automatically to all users homed at the specified site.</span></span> <span data-ttu-id="aa0a9-108">ユーザーごとのスコープを持つポリシーを作成する場合は、ユーザー、グループ、連絡先オブジェクトに明示的に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa0a9-108">If you create a policy with per-user scope, you must explicitly assign it to users, groups, and contact objects.</span></span> <span data-ttu-id="aa0a9-109">複数のホストされたボイスメールポリシーを展開することもできますが、その場合は、ポリシーをユーザーごとに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa0a9-109">It is possible to deploy multiple hosted voice mail policies, but in that case the policies must be assigned on a per-user basis.</span></span>



</div>

<span data-ttu-id="aa0a9-110">ホストされたボイスメールポリシーの計画の詳細については、計画ドキュメントの「 [Lync Server 2013 のホスト型ボイスメールポリシー](lync-server-2013-hosted-voice-mail-policies.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa0a9-110">For details about planning hosted voice mail policies, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="aa0a9-111">このセクション中</span><span class="sxs-lookup"><span data-stu-id="aa0a9-111">In This Section</span></span>

  - [<span data-ttu-id="aa0a9-112">Lync Server 2013 でグローバルにホストされるボイスメールのポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="aa0a9-112">Modify the global hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-modify-the-global-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="aa0a9-113">Lync Server 2013 でサイトレベルでホストされるボイスメールのポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="aa0a9-113">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-site-level-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="aa0a9-114">Lync Server 2013 でユーザーごとにホストされるボイスメールのポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="aa0a9-114">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-per-user-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="aa0a9-115">Lync Server 2013 でユーザーごとにホストされるボイスメールのポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="aa0a9-115">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

