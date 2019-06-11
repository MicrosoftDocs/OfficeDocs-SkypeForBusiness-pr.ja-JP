---
title: 常設チャット サーバーのベスト プラクティス
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ac9419485212df8ecf0a11841a6eaee4c752640
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="9c5cf-102">常設チャット サーバーのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="9c5cf-102">Persistent Chat Server best practices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c5cf-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="9c5cf-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="9c5cf-104">カテゴリと常設チャットルームを作成して、スコープとメンバーシップを設計する際には、次のヒントを参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="9c5cf-104">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="9c5cf-105">会社が倫理的な壁を必要としない場合は、カテゴリツリーの範囲を狭くしないでください。</span><span class="sxs-lookup"><span data-stu-id="9c5cf-105">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span></span> <span data-ttu-id="9c5cf-106">すべてのユーザーを1つのカテゴリの範囲に入れ、そのカテゴリのすべてのチャットルームを作成します。</span><span class="sxs-lookup"><span data-stu-id="9c5cf-106">Put all your users in the scope of one category, and create all chat rooms in that category.</span></span> <span data-ttu-id="9c5cf-107">その後、メンバーシップリストを使用して、各チャットルームへのアクセスを許可または制限します。</span><span class="sxs-lookup"><span data-stu-id="9c5cf-107">Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="9c5cf-108">ほとんどの場合、新しいトピックに関するディスカッションをいつでも開始できるように、ユーザーが新しいチャットルームを作成できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c5cf-108">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span></span> <span data-ttu-id="9c5cf-109">これを行うには\*\*\*\* 、作成者リストを**allowedmembers**リストと同じにします。</span><span class="sxs-lookup"><span data-stu-id="9c5cf-109">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span></span> <span data-ttu-id="9c5cf-110">ただし、中央のサポートチームまたは特定のユーザーにのみ会議室の作成を許可する場合は\*\*\*\* 、適切なサブセットとして作成者の一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="9c5cf-110">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="9c5cf-111">各チャットルームには、組織に適した場所を示す完全な名前と説明の概要を指定します。</span><span class="sxs-lookup"><span data-stu-id="9c5cf-111">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span></span> <span data-ttu-id="9c5cf-112">ユーザーは、チャットルームを使用するときにカテゴリ名を見ることができないため、ユーザーがチャットルームの目的のディスカッションフォーラムを特定するのに役立つように、カテゴリ名を利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="9c5cf-112">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="9c5cf-113">特定の命名規則やその他のアクセス制御や検証を実装する場合は、カスタムの会議室の作成ワークフローが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="9c5cf-113">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="9c5cf-114">常設チャットの構成では、ホストしているものに**RoomManagementUrl**をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="9c5cf-114">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="9c5cf-115">たとえば、ユーザーが Lync クライアントで [**会議室の作成**] をクリックすると、ユーザーはカスタムソリューションにリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="9c5cf-115">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="9c5cf-116">他のビジネスデータをチャットルームに表示して、チャットルームの操作性を向上させるためのさまざまなアドインを作成します。</span><span class="sxs-lookup"><span data-stu-id="9c5cf-116">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span></span> <span data-ttu-id="9c5cf-117">管理者は、システムに許可するアドインを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c5cf-117">Administrators must register the add-ins that they want to allow in the system.</span></span> <span data-ttu-id="9c5cf-118">チャットルームマネージャーと作成者は、それぞれの会議室に最も関連性の高いアドインの一覧から選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="9c5cf-118">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="9c5cf-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c5cf-119">See Also</span></span>


[<span data-ttu-id="9c5cf-120">Lync Server 2013 でのカテゴリ、ルーム、およびアドインの管理</span><span class="sxs-lookup"><span data-stu-id="9c5cf-120">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

