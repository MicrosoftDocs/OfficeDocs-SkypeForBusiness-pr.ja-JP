---
title: 'Lync Server 2013: 常設チャットサーバーの要件の定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd327ea7840a1f630e9fafbcefcffa21a1d095cd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="1bfc5-102">Lync Server 2013 での組織の常設チャットサーバーの要件の定義</span><span class="sxs-lookup"><span data-stu-id="1bfc5-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bfc5-103">_**トピックの最終更新日:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="1bfc5-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="1bfc5-104">組織のために常設チャットサーバーを展開する前に、展開を最適化するために次の重要な質問を検討することが重要です。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="1bfc5-105">常設チャットサーバーでは、誰 (user profile) を有効にする必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="1bfc5-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="1bfc5-106">常設チャットサーバーは、グローバル、サイト、プール、またはユーザーレベルで設定できるポリシーによって有効にされます。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="1bfc5-107">常設チャットサーバーに対して有効にするユーザーの数 (スケール)</span><span class="sxs-lookup"><span data-stu-id="1bfc5-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="1bfc5-108">常設チャットサーバーは、15万でプロビジョニングされたユーザーをサポートします (ポリシーで有効)。また、常設チャットサーバーを使用して、最大で8万の同時ユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="1bfc5-109">1つの常設チャットサーバーは2万に接続されたユーザーをサポートでき、1つの常設チャットサーバープールでは、合計で8万の同時接続ユーザーに対して最大4つのアクティブサーバーを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="1bfc5-110">グループチャットサーバーの以前のバージョンから移行しているか、または初めて常設チャットサーバーを展開していますか。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="1bfc5-111">コンプライアンス要件はありますか。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-111">Are there compliance requirements?</span></span> <span data-ttu-id="1bfc5-112">常設チャットサーバーはコンプライアンスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="1bfc5-113">以前のグループチャットサーバーの展開では、別のコンピューターの要件とは異なり、コンプライアンスサービスは、常設チャットサーバーのフロントエンドサーバーに併置されて実行されます。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="1bfc5-114">コンプライアンスはオプションであり、選択した場合、コンプライアンスのデータとイベントを格納するために構成する必要があるコンプライアンスデータベースを必要とします。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="1bfc5-115">また、コンプライアンスデータベースからデータを取得し、別の形式 (XML ファイルや Exchange ホスト型アーカイブなど) に変換するように、アダプターを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="1bfc5-p104">スコープ、論理的境界、およびアクセスをどのように制御しますか。これらの境界を分離する**カテゴリ**を定義し、各カテゴリに作成されたルームを利用できるユーザーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-p104">How do you want to control scopes, ethical boundaries, and access? You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="1bfc5-p105">ルームを作成できるユーザーをどのように制御しますか。各カテゴリに応じて、ルームを作成できる**作成者**を構成できます。作成者は、カテゴリで構成されている **AllowedMembers/DeniedMembers** のスコープに従って、ルームの継続的な管理 (メンバーの追加または削除) のために、他のメンバーを**チャット ルーム マネージャー**として割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-p105">How do you want to control who can create rooms? You can configure **Creators**, appropriate to your categories, who can create rooms. Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="1bfc5-121">ルームをどのように作成しますか。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-121">How do you want to create rooms?</span></span> <span data-ttu-id="1bfc5-122">常設チャットサーバーは、ルームの作成と管理のための web ベースの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="1bfc5-123">これは、Lync 2013 クライアントから起動できます。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="1bfc5-124">ビジネス要件とワークフローを実装するカスタムソリューション (常設チャットサーバーソフトウェア開発キット (SDK) を使用) を定義し、ユーザーをカスタムソリューションにダイレクトするように常設チャットサーバーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="1bfc5-125">どのような種類のアドインをプロビジョニングしますか。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="1bfc5-126">**アドイン**は、Lync 2013 クライアントの機能拡張ウィンドウを活用して、会議室に関連するコンテキストを提供することで、ルーム内での作業を強化します。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="1bfc5-127">最も役立つと考えられる汎用的なアドイン (自社の Web サイト、社内のコラボレーション ドキュメントなど) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="1bfc5-128">チャット ルーム マネージャーは、必要に応じて登録済みのアドインのいずれかを選択し、ルームに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="1bfc5-129">どのような種類の高可用性要件と障害復旧要件がありますか。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="1bfc5-130">常設チャットサーバーは、高可用性を実現するための SQL Server ミラーリングと SQL Server クラスタリングをサポートし、障害復旧用の SQL Server ログ配布を備えた拡張プールで最大8台のサーバー (アクティブおよび4台のスタンバイ) をサポートします。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="1bfc5-131">法的な要件はありますか。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-131">Are there regulatory requirements?</span></span> <span data-ttu-id="1bfc5-132">企業がデータを国内内に保持する必要がある国/地域の場合は、複数の常設チャットサーバープールを各地域に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="1bfc5-133">ルーム、カテゴリ、またはアドインが複数のプールにまたがることはありません。これは、1つの常設チャットサーバープールにのみ属します。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="1bfc5-134">各常設チャットサーバープールのカテゴリ、アドイン、およびルームのセットを管理できます。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="1bfc5-135">カテゴリ AllowedMembers スコープまたはルームのメンバーシップスコープを使用して、カテゴリの設計方法に応じて、1つまたは複数のプール内のルームにアクセスできるようにユーザーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1bfc5-136">複数の常設チャットサーバープールを使用しても、より大きなスケールを得ることはできません (すべての常設チャットサーバープールで同時に8万に接続されたユーザーは1人だけです)。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="1bfc5-137">複数の常設チャットサーバープールをサポートする主な理由は、規制に関する懸念事項です。</span><span class="sxs-lookup"><span data-stu-id="1bfc5-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

