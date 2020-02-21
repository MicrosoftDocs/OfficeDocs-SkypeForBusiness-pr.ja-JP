---
title: 常設チャットのメンバーシップについて
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cc357eff6cdc68c5285eeb915f5534b6f38b871
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="62b03-102">常設チャットのメンバーシップについて</span><span class="sxs-lookup"><span data-stu-id="62b03-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62b03-103">_**トピックの最終更新日:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="62b03-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="62b03-104">常設チャットルームへのユーザーアクセスは、メンバーシップによって管理されます。ユーザーがメッセージを投稿および閲覧できるようにするには、チャットルームのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="62b03-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="62b03-105">チャットルームへの指定された所属を持つ**プレゼンター**のみが、大**会議室への投稿**を使用できます。</span><span class="sxs-lookup"><span data-stu-id="62b03-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="62b03-106">大会議室は、発表者**のみが投稿**でき、全員が閲覧できるチャットルームの一種です。</span><span class="sxs-lookup"><span data-stu-id="62b03-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="62b03-107">また、常設チャットルームは、カテゴリのルールの下で動作します。</span><span class="sxs-lookup"><span data-stu-id="62b03-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="62b03-108">カテゴリの詳細については、このトピックで後述する「 [Lync Server 2013 でのカテゴリ、ルーム、およびアドインの管理](lync-server-2013-managing-categories-rooms-and-add-ins.md)」と「カテゴリのスコープの適用方法」および「ルームのカテゴリの戦略」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62b03-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="62b03-109">常設チャット管理者は、チャットルームのカテゴリを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="62b03-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="62b03-110">チャットルームカテゴリの作成と管理の一環として、常設チャット管理者は、特定のカテゴリのチャットルームのメンバーまたはクリエーターにアクセスできるプリンシパル (Active Directory ドメインサービスグループ、コンテナー、ユーザー) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="62b03-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="62b03-111">Active Directory ドメインサービスと常設チャット</span><span class="sxs-lookup"><span data-stu-id="62b03-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="62b03-112">常設チャットサーバーは、内部の常設チャットユーザーのプールに対して Active Directory に依存します。</span><span class="sxs-lookup"><span data-stu-id="62b03-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="62b03-113">常設チャット (クライアント) をインストールした後、ユーザーおよびユーザーグループのドメインをルームカテゴリに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="62b03-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="62b03-114">その後、ルーム カテゴリのメンバーシップにそれらのユーザーとグループを追加できます。</span><span class="sxs-lookup"><span data-stu-id="62b03-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="62b03-115">常設チャットルームに変更を加える必要があるユーザーには、重複する名前がないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62b03-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="62b03-116">ユーザー名が重複している場合は別の名前に変更し、ユーザーによる変更の実行を許可してください。</span><span class="sxs-lookup"><span data-stu-id="62b03-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="62b03-117">Active Directory で名前が重複していて、そのユーザーの会議室での変更を試行すると、エラーメッセージが表示され、ユーザーは管理者に連絡して解決策を求めることができます。</span><span class="sxs-lookup"><span data-stu-id="62b03-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="62b03-118">カテゴリの範囲指定のしくみ</span><span class="sxs-lookup"><span data-stu-id="62b03-118">How Category Scoping Works</span></span>

<span data-ttu-id="62b03-119">カテゴリは、その**Allowedmembers**プロパティに基づいて、そのカテゴリの常設チャットルームのメンバーシップリストのメンバーになることができるすべてのユーザーとグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="62b03-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="62b03-120">たとえば、カテゴリの**Allowedmembers**を contoso.com に設定すると、 *contoso*の任意のグループまたはユーザーをそのカテゴリのチャットルームにメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="62b03-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="62b03-121">カテゴリの **AllowedMembers** を "営業\*\*" に設定した場合は、その配布リスト内のグループとユーザーのみを、カテゴリ内のチャット ルームにメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="62b03-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="62b03-122">同様に、**Creators** プロパティを使用すると、カテゴリ内にチャット ルームを作成できるユーザーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="62b03-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="62b03-123">チャット ルームが作成されると、**AllowedMembers** グループのユーザーを、ルームで進行中の管理操作 (メンバーシップの変更や承認など) の**管理者**として指定できます。</span><span class="sxs-lookup"><span data-stu-id="62b03-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="62b03-124">カテゴリの **AllowedMembers** と **Creators** を定義すると、次の利点が得られます。</span><span class="sxs-lookup"><span data-stu-id="62b03-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="62b03-p107">カテゴリ内のすべてのチャット ルームがカテゴリ レベルの制限のセットにバインドされます。これにより、業務ニーズとアクセス ポリシーに基づいてチャット ルームを分離できます。</span><span class="sxs-lookup"><span data-stu-id="62b03-p107">All chat rooms in this category are bound by the restrictions set at the category level. You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="62b03-p108">**Creators** の一覧に含まれるユーザーが、カテゴリ内に新しいチャット ルームを作成できます。チャット ルームを作成できる組織内の担当者の数が制限されているシステムを実装する場合は、この制御を使用して要件を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="62b03-p108">A user who is in the **Creators** list can create new chat rooms in that category. If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="62b03-129">ルーム カテゴリの戦略</span><span class="sxs-lookup"><span data-stu-id="62b03-129">Room Category Strategies</span></span>

<span data-ttu-id="62b03-130">カテゴリの**Allowedmembers**には、このカテゴリの常設チャットルームを使用するすべてのユーザーが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="62b03-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="62b03-131">業務データを保護し、適切なレベルのアクセスを確保するための要件に応じて、ルームの検索およびルームへの参加が可能なユーザーを指定する 1 つ以上のカテゴリの定義が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="62b03-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="62b03-132">ルームの作成を特定のユーザー グループ (中央のヘルプデスク、またはフルタイム勤務の従業員のみ) にのみ許可する場合は、要件を満たすカテゴリの **Creators** を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="62b03-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="62b03-p110">また、カテゴリを使用して倫理的境界を作成することもできます。倫理的境界を使用すると、組織内における利害の対立を避けることができます。たとえば、管理者は、トレーダー専用のカテゴリやアナリスト専用のカテゴリにチャット ルームを作成できます。</span><span class="sxs-lookup"><span data-stu-id="62b03-p110">Categories can also be used to create ethical walls. Ethical walls prevent any conflict of interest in an organization. For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62b03-136">Lync Server 2013 の常設チャットサーバーでは、フェデレーションユーザーへのアクセスはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="62b03-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="62b03-137">以前のバージョンの常設チャットサーバーのフェデレーションユーザーからチャットがある場合、それらは移行されます。</span><span class="sxs-lookup"><span data-stu-id="62b03-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="62b03-138">フェデレーション ユーザーは、無効なプリンシパルとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="62b03-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="62b03-139">ユーザー グループへのメンバーの絞り込み</span><span class="sxs-lookup"><span data-stu-id="62b03-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="62b03-140">カテゴリにドメインを追加する場合は、そのドメインにグループ オブジェクトが含まれているユーザー グループをカテゴリ内のルームのメンバーとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="62b03-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="62b03-141">カテゴリの**Allowedmembers**および**クリエーター**を定義するために、ドメインや組織単位などの Active Directory コンテナーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="62b03-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="62b03-142">**AllowedMembers** または **Creators** の一覧には任意のドメインのオブジェクトを追加できます。</span><span class="sxs-lookup"><span data-stu-id="62b03-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="62b03-143">カテゴリ内のルームに追加できるのは、**AllowedMembers** または **Creators** の一覧に含まれるオブジェクトのみです。</span><span class="sxs-lookup"><span data-stu-id="62b03-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

