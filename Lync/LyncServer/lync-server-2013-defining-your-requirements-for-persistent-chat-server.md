---
title: 'Lync Server 2013: 組織における常設チャット サーバーに対する要件の定義'
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
ms.openlocfilehash: a0e7482ab85b72168e990eaa97b2f79cb3665532
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="c7088-102">Lync Server 2013 での、組織における常設チャット サーバーに対する要件の定義</span><span class="sxs-lookup"><span data-stu-id="c7088-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7088-103">_**最終更新日:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="c7088-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="c7088-104">組織に常設チャットサーバーを展開する前に、展開を最適化するために、次の主な質問について考慮することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c7088-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="c7088-105">常設チャットサーバーに対してどのユーザー (ユーザープロファイル) を有効にしますか?</span><span class="sxs-lookup"><span data-stu-id="c7088-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="c7088-106">常設チャットサーバーは、グローバル、サイト、プール、またはユーザーレベルで設定できるポリシーによって有効にされます。</span><span class="sxs-lookup"><span data-stu-id="c7088-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="c7088-107">常設チャットサーバーでは、どのくらいのユーザー (スケール) を有効にする必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="c7088-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="c7088-108">常設チャットサーバーでは、15万のプロビジョニングされたユーザー (ポリシーによって有効) と、常設チャットサーバーを使用する最大8万同時ユーザーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c7088-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="c7088-109">1つの常設チャットサーバーでは、2万で接続されているユーザーをサポートできます。また、1つの常設チャットサーバープールには、合計8万の同時接続ユーザーに対して最大4つのアクティブなサーバーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c7088-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="c7088-110">グループチャットサーバの以前のバージョンから移行しているか、または永続的なチャットサーバを初めて導入していますか?</span><span class="sxs-lookup"><span data-stu-id="c7088-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="c7088-111">コンプライアンス要件はありますか?</span><span class="sxs-lookup"><span data-stu-id="c7088-111">Are there compliance requirements?</span></span> <span data-ttu-id="c7088-112">常設チャットサーバーはコンプライアンスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c7088-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="c7088-113">コンプライアンスサービスは、前のグループチャットサーバーの展開で個別のコンピューターを使用するための要件とは対照的に、常設チャットサーバーのフロントエンドサーバーに対して同一に実行されます。</span><span class="sxs-lookup"><span data-stu-id="c7088-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="c7088-114">コンプライアンスはオプションであり、選択した場合、コンプライアンスのデータとイベントを保存するように構成する必要があるコンプライアンスデータベースが必要です。</span><span class="sxs-lookup"><span data-stu-id="c7088-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="c7088-115">また、コンプライアンスデータベースからデータを取得したり、別の形式 (XML ファイルや Exchange でホストされているアーカイブなど) に変換したりするようにアダプターを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c7088-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="c7088-116">スコープ、論理的境界、およびアクセスをどのように制御しますか。</span><span class="sxs-lookup"><span data-stu-id="c7088-116">How do you want to control scopes, ethical boundaries, and access?</span></span> <span data-ttu-id="c7088-117">**カテゴリ**を定義して、これらの境界を分離したり、これらの各カテゴリで作成されたルームに参加できるユーザーを選択したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c7088-117">You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="c7088-118">ルームを作成できるユーザーをどのように制御しますか。</span><span class="sxs-lookup"><span data-stu-id="c7088-118">How do you want to control who can create rooms?</span></span> <span data-ttu-id="c7088-119">自分のカテゴリ (会議室を作成できるユーザー) に応じて、**作成者**を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c7088-119">You can configure **Creators**, appropriate to your categories, who can create rooms.</span></span> <span data-ttu-id="c7088-120">作成者は、カテゴリによって構成されている**allowedmembers/DeniedMembers**の範囲に従って、他のメンバーを**チャットルーム管理者**として割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c7088-120">Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="c7088-121">ルームをどのように作成しますか。</span><span class="sxs-lookup"><span data-stu-id="c7088-121">How do you want to create rooms?</span></span> <span data-ttu-id="c7088-122">常設チャットサーバーは、部屋の作成と管理のための web ベースの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="c7088-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="c7088-123">これは Lync 2013 クライアントから起動できます。</span><span class="sxs-lookup"><span data-stu-id="c7088-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="c7088-124">ビジネス要件とワークフローを実装するカスタムソリューション (常設 Chat Server ソフトウェア開発キット (SDK) を使用) を定義し、ユーザーをカスタムソリューションに導くために常設チャットサーバーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c7088-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="c7088-125">どのような種類のアドインをプロビジョニングしますか。</span><span class="sxs-lookup"><span data-stu-id="c7088-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="c7088-126">[アドイン] は、会議室に関連するコンテキストを提供するために、Lync 2013 クライアントの [機能拡張] ウィンドウを活用して、ルーム内の操作**を強化し**ます。</span><span class="sxs-lookup"><span data-stu-id="c7088-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="c7088-127">最も役立つと考えられる汎用的なアドイン (自社の Web サイト、社内のコラボレーション ドキュメントなど) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c7088-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="c7088-128">チャット ルーム マネージャーは、必要に応じて登録済みのアドインのいずれかを選択し、ルームに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c7088-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="c7088-129">どのような種類の高可用性要件と障害復旧要件がありますか。</span><span class="sxs-lookup"><span data-stu-id="c7088-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="c7088-130">常設チャットサーバーは、sql Server のミラーリングと SQL Server のクラスタリングをサポートしており、高可用性を実現しており、SQL Server のログ配布によって、障害回復用の sql Server log 送料を備えた、最大8つのサーバーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c7088-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="c7088-131">規制要件はありますか?</span><span class="sxs-lookup"><span data-stu-id="c7088-131">Are there regulatory requirements?</span></span> <span data-ttu-id="c7088-132">お客様の会社が、国内にデータを保存する必要がある国/地域の場合、複数の常設チャットサーバープールを各地域に展開することが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="c7088-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="c7088-133">ルーム、カテゴリ、またはアドインがプールをまたぐことはありません。これは、1つの常設チャットサーバープールにのみ所属します。</span><span class="sxs-lookup"><span data-stu-id="c7088-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="c7088-134">常設チャットサーバープールごとに、一連のカテゴリ、アドイン、会議室を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="c7088-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="c7088-135">ユーザーは、カテゴリの設計方法に応じて、カテゴリのメンバースコープまたはルームのメンバーシップスコープを使用して、1つ以上のプール内のルームにアクセスできるように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="c7088-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c7088-136">複数の常設チャットサーバープールを用意しても、スケールが向上しません (すべての常設チャットサーバープールに同時に接続できるユーザーは8万のみです)。</span><span class="sxs-lookup"><span data-stu-id="c7088-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="c7088-137">複数の常設チャットサーバープールをサポートする主な理由は、規制に関する懸念事項をサポートすることです。</span><span class="sxs-lookup"><span data-stu-id="c7088-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

