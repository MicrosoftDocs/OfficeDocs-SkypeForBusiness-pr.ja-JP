---
title: 'Lync Server 2013: 常設チャットサーバーでのユーザーの役割'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7d01b15c035b3f14a0f2d6dba92719d7f885437
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="3eb72-102">Lync Server 2013 の常設チャットサーバーでのユーザーの役割</span><span class="sxs-lookup"><span data-stu-id="3eb72-102">User roles in Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3eb72-103">_**トピックの最終更新日:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="3eb72-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="3eb72-104">常設チャットサーバーは、許可/拒否メンバーの概念を提供します。これは、常設チャットカテゴリに適用され、特定のカテゴリのルームにアクセスできるユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="3eb72-104">Persistent Chat Server provides the concept of Allowed/Denied members, which applies to Persistent Chat categories and controls who can access rooms in a particular category.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3eb72-105">カテゴリ内の許可/拒否メンバーは、常設チャットルームに適用される<STRONG>メンバー</STRONG>役割とは異なります。</span><span class="sxs-lookup"><span data-stu-id="3eb72-105">Allowed/Denied members in a Category is not the same as a <STRONG>Member</STRONG> role, which applies to a Persistent Chat room.</span></span><BR><span data-ttu-id="3eb72-p101">検索では、検索を実行しているユーザーが許可/拒否されるメンバー リストにある、開いているチャット ルーム、閉じているチャット ルーム、および非公開のチャット ルームがすべて表示されます。検索を行うユーザーが非公開のルームのメンバーではない場合は、非公開のルームは表示されません。ユーザーは、自分がすでにメンバーであるルームか、メンバーシップを要求することができるルームのみを検索できます。</span><span class="sxs-lookup"><span data-stu-id="3eb72-p101">Searches display all open and closed chat rooms for which the user performing the search is in the Allowed/Denied member list. Secret rooms are not displayed unless the user who performs the search is a member of the secret room. The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span>



</div>

<span data-ttu-id="3eb72-p102">許可されたメンバー/拒否されたメンバーの概念が必要となる主な根拠は、倫理的な壁です。たとえば、銀行および金融機関では、一般的に、ポリシーおよび指針の実装中は、トレーダーとアナリストが連絡することを防ぐ、倫理的な境界を設定します。この要件に対処する目的で、管理者はカテゴリを作成できます。1 つのカテゴリではトレーダーにより作成、使用されるルームを用意し、別のカテゴリではアナリストにより作成、使用されるルームを用意できます。この制約をシステムに組み込むことで、親カテゴリで禁止されている場合は、ルームのメンバーとしてユーザーを追加することが禁止されます。</span><span class="sxs-lookup"><span data-stu-id="3eb72-p102">The primary rationale for the concept of Allowed/Denied Members is ethical walls. For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions. To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts. With this constraint is designed into the system prohibits adding a user as a member of the room if the parent category prevents it.</span></span>

<span data-ttu-id="3eb72-113">次に、4つのユーザーロール常設チャットサーバーを示します。</span><span class="sxs-lookup"><span data-stu-id="3eb72-113">Following are the four user roles Persistent Chat Server:</span></span>

  - <span data-ttu-id="3eb72-114">**作成者:** チャットルームを作成する権限を持つユーザー。</span><span class="sxs-lookup"><span data-stu-id="3eb72-114">**Creator:** Users who have permissions to create chat rooms.</span></span> <span data-ttu-id="3eb72-115">これらのユーザーは、特定のカテゴリの作成者リストに含まれています。これらのユーザーは、そのカテゴリのチャットルームを作成したり、カテゴリに基づいてメンバーシップを割り当てたり、チャットルームを管理する上司を割り当てたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3eb72-115">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="3eb72-116">チャットルームを作成したユーザーは、ルームの管理者として自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="3eb72-116">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3eb72-p104">作成者であることは、チャット ルームを作成する権限があるということだけです。作成されたチャット サービスで、作成者がさらにメンバーシップ、管理者などを調整できるようになるのは、管理者に自動的に昇格することによります。</span><span class="sxs-lookup"><span data-stu-id="3eb72-p104">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span>

    
    </div>
    
    <span data-ttu-id="3eb72-119">この役割は、組織でチャット ルームの作成を制御する目的で存在します。特に、ポリシーと指針を施行する目的でチャット ルームの作成を集約的に管理する必要があり、その後、組織内のその他のユーザーにチャット ルーム管理を委任する場合です。</span><span class="sxs-lookup"><span data-stu-id="3eb72-119">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>

  - <span data-ttu-id="3eb72-120">**マネージャー:** チャットルームのプロパティを管理するユーザーです。</span><span class="sxs-lookup"><span data-stu-id="3eb72-120">**Manager:** Users who manage properties of a chat room.</span></span> <span data-ttu-id="3eb72-121">チャット ルームの管理者は、メンバー リストの変更 (メンバーの追加と削除) やチャット ルーム管理者リストの変更 (管理者の追加と削除) を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3eb72-121">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="3eb72-122">チャット ルーム管理者は、自分がチャット ルームに参加できるように、(大会議室の) 発表者リストまたはメンバーに自分自身を追加できます。</span><span class="sxs-lookup"><span data-stu-id="3eb72-122">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="3eb72-123">また、チャット ルーム管理者はチャット ルームを無効にできます (システム管理者は、無効にされたチャット ルームを検索して、それらを完全に削除できます)。</span><span class="sxs-lookup"><span data-stu-id="3eb72-123">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="3eb72-124">システム管理者は、チャット ルームのカテゴリ以外、チャット ルームのすべてのプロパティを変更できます。</span><span class="sxs-lookup"><span data-stu-id="3eb72-124">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="3eb72-125">チャットルームが作成された後に、常設チャット管理者のみがカテゴリを変更できます。</span><span class="sxs-lookup"><span data-stu-id="3eb72-125">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3eb72-126">ルーム管理者が、別のカテゴリの作成者でもある場合、カテゴリを、自分がルームを作成する権限があるカテゴリに変更できます。</span><span class="sxs-lookup"><span data-stu-id="3eb72-126">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span>

    
    </div>

  - <span data-ttu-id="3eb72-127">**メンバー:** チャットルームのメンバーであるユーザー。</span><span class="sxs-lookup"><span data-stu-id="3eb72-127">**Member:** Users who are members of a chat room.</span></span> <span data-ttu-id="3eb72-128">メンバーは、ディレクトリ内のチャット ルームを見たり (非公開のチャット ルームでも可能)、チャット ルームを購読したり (未読メッセージ、エゴ フィルター、キーワード フィルターなどのメタデータ オプションを含む)、チャット ルームに参加したりできます (発表者のみがメッセージを投稿できるオーディオリアム チャット ルームでなければ、投稿もできます)。</span><span class="sxs-lookup"><span data-stu-id="3eb72-128">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="3eb72-129">チャット ルームのメンバーではないユーザーは、カテゴリの許可されたメンバー リストに入っていれば、チャット ルームを検索することはできますが、コンテンツにアクセスするにはチャット ルームへの参加を要求する必要があります (システムにはアクセスの要求または承認の機能はありません。</span><span class="sxs-lookup"><span data-stu-id="3eb72-129">Users who aren’t members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="3eb72-130">電子メール、電話、他の手段で外部的に行う必要があります)。</span><span class="sxs-lookup"><span data-stu-id="3eb72-130">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>

  - <span data-ttu-id="3eb72-131">**プレゼンター:** 大会議室に投稿できるユーザー。</span><span class="sxs-lookup"><span data-stu-id="3eb72-131">**Presenter:** Users who can post to an auditorium room.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3eb72-132">常設チャットサーバーを使用すると、ユーザーは特定のサイトのチャットルームを作成して管理できます。</span><span class="sxs-lookup"><span data-stu-id="3eb72-132">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="3eb72-133">ただし、ユーザーは同じトポロジ内の他のサイトでチャットルームを作成または管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="3eb72-133">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="3eb72-134">組織内のすべてのサイトについて、チャットルームの作成者とマネージャーを必ず指定してください。</span><span class="sxs-lookup"><span data-stu-id="3eb72-134">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<span data-ttu-id="3eb72-135">常設チャットサーバーの管理者の役割は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3eb72-135">The following roles are administrator roles for Persistent Chat Server:</span></span>

  - <span data-ttu-id="3eb72-136">**常設チャット管理者 (CsPersistentChatAdministrator):** これは、常設チャットサーバーを管理および管理するための新しい役割ベースのアクセス制御 (RBAC) の役割です。</span><span class="sxs-lookup"><span data-stu-id="3eb72-136">**Persistent Chat Administrator (CsPersistentChatAdministrator):** This is a new Role-Based Access Control (RBAC) role to administer and manage Persistent Chat Server.</span></span> <span data-ttu-id="3eb72-137">CsPersistentChatAdministrator として指定されたユーザーまたはセキュリティグループは、Windows PowerShell コマンドレットをリモートで (つまり、常設チャットサーバー以外のコンピューターから) 使用して、常設チャットサーバーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="3eb72-137">Users or security groups designated as CsPersistentChatAdministrator are able administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="3eb72-138">常設チャットサーバーは、常設チャット管理者が常設チャットサーバーのフロントエンドサーバーの RTC ローカル管理者ローカルグループのメンバーであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3eb72-138">Persistent Chat Server checks that the Persistent Chat Administrator is member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
    <span data-ttu-id="3eb72-139">CsPersistentChatAdministrator の役割では、チャットルームの管理 (メンバーシップ、マネージャー、カテゴリ、会議室のマークを含むすべてのプロパティの変更)、およびチャットルームを作成してアクセスできるユーザーを定義するチャットルームのカテゴリを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="3eb72-139">The CsPersistentChatAdministrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="3eb72-140">また、管理者はチャットルームを無効としてマークし、アクティブでなくなったチャットルームをクリーンアップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3eb72-140">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="3eb72-141">管理者は、作成者または許可されたメンバーの制限の対象にはなりません。</span><span class="sxs-lookup"><span data-stu-id="3eb72-141">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="3eb72-142">管理者は任意の種類のチャットルームを作成し、自分自身をメンバーとして任意のチャットルームに追加できます。</span><span class="sxs-lookup"><span data-stu-id="3eb72-142">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="3eb72-143">管理者は、常設チャットの構成 (プールのプロパティ、グローバル設定、およびコンプライアンス構成) を変更して管理することもできます。また、従来のグループチャットサーバーの展開から Lync Server 2013 の常設チャットへの移行を計画して実装することもできます。Server.</span><span class="sxs-lookup"><span data-stu-id="3eb72-143">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Lync Server 2013 Persistent Chat Server.</span></span>

  - <span data-ttu-id="3eb72-144">**Lync 管理者:** 展開を担当する Lync Server 2013 の全体的なエンタープライズ管理者。</span><span class="sxs-lookup"><span data-stu-id="3eb72-144">**Lync Administrator:** Overall enterprise administrator for Lync Server 2013 responsible for deployment.</span></span>

  - <span data-ttu-id="3eb72-145">**Operations Manager:** ユーザーが日常業務の管理を担当しています。</span><span class="sxs-lookup"><span data-stu-id="3eb72-145">**Operations Manager:** User responsible for managing day-to-day operations.</span></span>

  - <span data-ttu-id="3eb72-146">**サードパーティの開発者およびパートナー:** サードパーティの開発者はシステムを拡張します。特に、グループ会話、コンプライアンスサポートおよびツール、web/モバイルクライアント、Bot 開発のフレームワークに対する倫理的なウォールソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="3eb72-146">**Third-party developers and partners:** Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

