---
title: 常設チャットサーバーのベストプラクティス
description: 常設チャットサーバーのベストプラクティス。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c575c0afa0366e88748eadfcf4c04fccb20b375
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571263"
---
# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="b5d45-103">常設チャットサーバーのベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="b5d45-103">Persistent Chat Server best practices</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5d45-104">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="b5d45-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="b5d45-105">カテゴリおよび常設チャットルームを作成し、スコープとメンバーシップを設計する際には、以下のヒントを参考にして計画を立てることができます。</span><span class="sxs-lookup"><span data-stu-id="b5d45-105">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="b5d45-106">企業が倫理的な壁を必要としない場合は、カテゴリツリーの範囲を狭くしないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="b5d45-106">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span></span> <span data-ttu-id="b5d45-107">すべてのユーザーを1つのカテゴリのスコープに配置し、そのカテゴリのすべてのチャットルームを作成します。</span><span class="sxs-lookup"><span data-stu-id="b5d45-107">Put all your users in the scope of one category, and create all chat rooms in that category.</span></span> <span data-ttu-id="b5d45-108">その後、メンバーシップ一覧のみを使用して、各チャットルームへのアクセスを許可または制限します。</span><span class="sxs-lookup"><span data-stu-id="b5d45-108">Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="b5d45-109">ほとんどの場合、新しいトピックについてのディスカッションをいつでも開始できるように、ユーザーが新しいチャットルームを作成できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5d45-109">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span></span> <span data-ttu-id="b5d45-110">これを行うには、 **クリエーター** リストを **allowedmembers** リストと同じにします。</span><span class="sxs-lookup"><span data-stu-id="b5d45-110">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span></span> <span data-ttu-id="b5d45-111">ただし、中央のサポートチームまたは特定のユーザーのみにルームの作成を許可する場合は、[作成者 **] リストを** 適切なサブセットとして設定します。</span><span class="sxs-lookup"><span data-stu-id="b5d45-111">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="b5d45-112">各チャットルームに、組織との適合場所を示す完全な名前と説明の概要を指定します。</span><span class="sxs-lookup"><span data-stu-id="b5d45-112">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span></span> <span data-ttu-id="b5d45-113">ユーザーがチャットルームを使用するときにカテゴリ名を表示することはできないため、ユーザーがチャットルームに対して意図したディスカッションフォーラムを決定するのに役立つように、カテゴリ名を利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b5d45-113">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="b5d45-114">特定の命名規則またはその他のアクセス制御や検証を実装する場合は、カスタムルーム作成ワークフローが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="b5d45-114">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="b5d45-115">常設チャットの構成を使用すると、 **RoomManagementUrl** を、ホストするものにカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="b5d45-115">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="b5d45-116">たとえば、ユーザーが Lync クライアントで [ **ルームの作成** ] をクリックしたときに、カスタムソリューションにリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="b5d45-116">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="b5d45-117">チャットルームの機能を向上させるさまざまなアドインを作成します。これにより、他のビジネスデータをチャットルームに取り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="b5d45-117">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span></span> <span data-ttu-id="b5d45-118">管理者は、システムで許可するアドインを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5d45-118">Administrators must register the add-ins that they want to allow in the system.</span></span> <span data-ttu-id="b5d45-119">チャットルームマネージャーおよび作成者は、それぞれの会議室に関連する、許可されたアドインの一覧から選択できます。</span><span class="sxs-lookup"><span data-stu-id="b5d45-119">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b5d45-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5d45-120">See Also</span></span>


[<span data-ttu-id="b5d45-121">Lync Server 2013 でのカテゴリ、ルーム、およびアドインの管理</span><span class="sxs-lookup"><span data-stu-id="b5d45-121">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

