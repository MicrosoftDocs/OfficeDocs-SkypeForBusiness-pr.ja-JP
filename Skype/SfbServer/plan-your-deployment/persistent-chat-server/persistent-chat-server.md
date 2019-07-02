---
title: Skype for Business Server 2015 の常設チャット サーバーの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: '概要: Skype for Business Server 2015 で常設チャットサーバーを計画する方法については、このトピックを参照してください。'
ms.openlocfilehash: 3e485f938d2bd48dad5f1b9f0baa96d7f3f537d0
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418281"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="04785-103">Skype for Business Server 2015 の常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="04785-103">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="04785-104">**概要:** このトピックでは、Skype for Business Server 2015 で常設チャットサーバーを計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="04785-104">**Summary:** Read this topic to learn how to plan for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="04785-105">常設チャットサーバーは、組織内の複数のユーザーが、時間を経て持続するチャットルームの会話に参加できるようにする、オプションの役割です。</span><span class="sxs-lookup"><span data-stu-id="04785-105">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="04785-106">ユーザーは、チャット セッション中にリアルタイムで通信できますが、各セッションの内容 (テキスト、リンク、およびファイルを含む) は永続的であるため、任意の時点でセッションのすべての内容を表示および検索できます。</span><span class="sxs-lookup"><span data-stu-id="04785-106">Although users can communicate in real time during a chat session, the content of each session--including text, links, and files--is persistent, which means users can view and search all content of the session at any time.</span></span>
  
<span data-ttu-id="04785-107">常設チャットサーバーは、組織内のコミュニケーションを向上させるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="04785-107">Persistent Chat Server can help improve communication within your organization by:</span></span>
  
- <span data-ttu-id="04785-108">組織全体で情報の認識と参加を拡大する</span><span class="sxs-lookup"><span data-stu-id="04785-108">Broadening information awareness and participation throughout the organization</span></span>
    
- <span data-ttu-id="04785-109">効率的な情報共有を実現する</span><span class="sxs-lookup"><span data-stu-id="04785-109">Enabling efficient information sharing</span></span> 
    
- <span data-ttu-id="04785-110">地理的に分散されたチームや職能上の枠を越えたチームを含めて、チーム間でのコミュニケーションを深める</span><span class="sxs-lookup"><span data-stu-id="04785-110">Improving communication between teams, including geographically dispersed and cross-functional teams</span></span>
    
- <span data-ttu-id="04785-111">情報過多を緩和する</span><span class="sxs-lookup"><span data-stu-id="04785-111">Reducing information overload</span></span>
    
- <span data-ttu-id="04785-112">オプションで常設チャット コンプライアンス サービスを展開することで、法令上の規制に従う</span><span class="sxs-lookup"><span data-stu-id="04785-112">Following compliance regulations by optionally deploying the Persistent Chat Compliance service</span></span>

> [!NOTE] 
> <span data-ttu-id="04785-113">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="04785-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="04785-114">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="04785-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="04785-115">詳細については、「 [Microsoft Teams のアップグレードの](/microsoftteams/upgrade-start-here)概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04785-115">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="04785-116">常設チャットを使用する必要がある場合は、この機能が必要なユーザーをチームに移行するか、Skype for Business Server 2015 を使い続けるかのいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="04785-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
    
## <a name="persistent-chat-server-high-level-architecture"></a><span data-ttu-id="04785-117">常設チャット サーバーの高度なアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="04785-117">Persistent Chat Server high-level architecture</span></span>

<span data-ttu-id="04785-118">次の図は、常設チャットサーバーアーキテクチャの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="04785-118">The following diagram shows a high-level view of the Persistent Chat Server architecture.</span></span> 
  
![常設チャット サーバーのアーキテクチャの概要](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
<span data-ttu-id="04785-120">常設チャットは、常設チャット サービスだけでなく、バックエンド SQL データベース コンポーネントも提供するフロントエンド サーバーの役割から構成されています。</span><span class="sxs-lookup"><span data-stu-id="04785-120">Persistent Chat consists of a front-end server role that provides the Persistent Chat services as well as a back-end SQL database component.</span></span> <span data-ttu-id="04785-121">フロントエンドとバックエンド両方のコンポーネントは、専用の常設チャット プールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="04785-121">Both front-end and back-end components are included in a dedicated Persistent Chat pool.</span></span> <span data-ttu-id="04785-122">常設チャットサーバーをホストする各コンピューターには、既存の Skype for Business Server 2015 トポロジへのアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="04785-122">Each computer that hosts Persistent Chat Server must have access to an existing Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="04785-123">この図では、1つの常設チャットサーバープール (A) があります。これは、Skype for Business Server プール A に依存して、メッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="04785-123">In this diagram, there is one Persistent Chat Server pool (A), which is dependent on Skype for Business Server Pool A for routing messages to it.</span></span>
  
<span data-ttu-id="04785-124">1つまたは複数の常設チャットサーバープールを展開できます。それぞれは、最大4つのアクティブな常設チャットサーバーをサポートしており、80K の同時ユーザーをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="04785-124">You can deploy one or more Persistent Chat Server pools, each with up to four active Persistent Chat Servers supporting up to 80K concurrent users.</span></span>
  
<span data-ttu-id="04785-125">Skype for Business Server 2015 は、セッション開始プロトコル (SIP) を使って登録用の常設チャットサービスと通信し、チャット用の SIP プロトコル (XCCOS) 経由の拡張チャット通信を使用します。</span><span class="sxs-lookup"><span data-stu-id="04785-125">Skype for Business Server 2015 communicates with the Persistent Chat service using the Session Initiation Protocol (SIP) for registration and the Extensible Chat Communication Over SIP protocol (XCCOS) for chat.</span></span> 
  
## <a name="persistent-chat-services"></a><span data-ttu-id="04785-126">常設チャット サービス</span><span class="sxs-lookup"><span data-stu-id="04785-126">Persistent Chat services</span></span>

<span data-ttu-id="04785-127">次の図は、常設チャットサーバーのフロントエンドサービスと、これらのサービスとバックエンドデータベースコンポーネントとの通信方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="04785-127">The following diagram shows the Persistent Chat Server front-end services, and how these services communicate with the back-end database components.</span></span> <span data-ttu-id="04785-128">フロントエンド コンポーネントには常設チャット サービスとコンプライアンス サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="04785-128">The front-end components include the Persistent Chat services and the Compliance service.</span></span> <span data-ttu-id="04785-129">バックエンド コンポーネントには常設チャット ストアと常設チャット コンプライアンス ストアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="04785-129">The back-end components include the Persistent Chat store and the Persistent Chat compliance store.</span></span>
  
![常設チャット サーバーのサービスの概要](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a><span data-ttu-id="04785-131">チャット サービス</span><span class="sxs-lookup"><span data-stu-id="04785-131">Chat service</span></span>

<span data-ttu-id="04785-132">チャット サービスはチャネル サービスとも呼ばれ、常設チャット サーバーに対応するコア サービスです。</span><span class="sxs-lookup"><span data-stu-id="04785-132">The Chat service, also called the Channel service, is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="04785-133">チャット サービスには次の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="04785-133">The Chat service provides the following functions:</span></span>
  
- <span data-ttu-id="04785-134">受信メッセージを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="04785-134">Accepts incoming messages</span></span>
    
- <span data-ttu-id="04785-135">常設チャット ルーム内のオンライン参加者を登録し、参加者の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="04785-135">Registers and lists online participants within a Persistent Chat room</span></span>
    
- <span data-ttu-id="04785-136">メッセージを他のチャネル サブスクライバーに再送信します。</span><span class="sxs-lookup"><span data-stu-id="04785-136">Retransmits messages to other channel subscribers</span></span>
    
- <span data-ttu-id="04785-137">チャネル管理、チャット ルームへの招待、検索、および新しいコンテンツ通知のロジックを実装します。</span><span class="sxs-lookup"><span data-stu-id="04785-137">Implements logic for channel management, chat room invitations, search and new content notifications</span></span>
    
<span data-ttu-id="04785-138">常設チャット サービスは、常設チャット ストアを使用して、チャット ルームのコンテンツおよびその他のシステム メタデータ (承認規則など) を格納し、この情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="04785-138">The Persistent Chat service stores and accesses chat room content and other system metadata (authorization rules and so on) by using the Persistent Chat store.</span></span> <span data-ttu-id="04785-139">このサービスには、常設チャット ファイル ストアでチャット ルームにアップロードされたファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="04785-139">The service stores files that are uploaded into chat rooms in the Persistent Chat file store.</span></span>
  
### <a name="compliance-service"></a><span data-ttu-id="04785-140">コンプライアンス サービス</span><span class="sxs-lookup"><span data-stu-id="04785-140">Compliance service</span></span>

<span data-ttu-id="04785-141">常設チャットのアクティビティのアーカイブを求める規制が組織に存在する場合、オプションの常設チャット コンプライアンス サービスを展開できます。</span><span class="sxs-lookup"><span data-stu-id="04785-141">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="04785-142">コンプライアンス サービスは、ルームへの参加やルームからの退出など、チャット コンテンツとイベントの常設チャット コンプライアンス ファイル ストアへのアーカイブを担当します。</span><span class="sxs-lookup"><span data-stu-id="04785-142">The Compliance service is responsible for archiving chat content and events, such as joining and leaving rooms, to the Persistent Chat Compliance file store.</span></span> <span data-ttu-id="04785-143">コンプライアンスサービスは、常設チャットプールの常設チャットサーバーごとにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="04785-143">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> 
  
### <a name="web-services"></a><span data-ttu-id="04785-144">Web サービス</span><span class="sxs-lookup"><span data-stu-id="04785-144">Web services</span></span>

<span data-ttu-id="04785-145">常設チャット web サービスは、Skype for Business フロントエンドサーバー上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="04785-145">The Persistent Chat web services run on the Skype for Business Front End Servers.</span></span> <span data-ttu-id="04785-146">Web サービスはインターネット インフォメーション サービス (IIS) に依存し、Web コンポーネントとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="04785-146">The web services depend on Internet Information Services (IIS), and are implemented as web components:</span></span>
  
- <span data-ttu-id="04785-147">ファイルのアップロード / ダウンロード用の常設チャット Web サービスは、チャット ルームでのファイルの投稿および取得を処理します。</span><span class="sxs-lookup"><span data-stu-id="04785-147">Persistent Chat web services for file upload and download are responsible for posting and retrieving files from chat rooms.</span></span>
    
- <span data-ttu-id="04785-148">チャット ルーム管理用の常設チャット Web サービスは、ユーザーがチャット ルームを管理したり、新しいチャット ルームを作成したりできるようにします。</span><span class="sxs-lookup"><span data-stu-id="04785-148">Persistent Chat web services for chat room management are responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>
    
## <a name="defining-requirements-for-your-organization"></a><span data-ttu-id="04785-149">組織の要件の定義</span><span class="sxs-lookup"><span data-stu-id="04785-149">Defining requirements for your organization</span></span>

<span data-ttu-id="04785-150">常設チャットサーバーを展開する場合は、組織のビジネス要件を決定してから、ビジネスニーズをサポートするトポロジ、インフラストラクチャ、および技術要件を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04785-150">If you decide to deploy Persistent Chat Server, you'll need to determine your organization's business requirements, then define the topology, infrastructure, and technical requirements to support your business needs.</span></span> <span data-ttu-id="04785-151">展開を最適化するには、次の質問に答える必要があります。</span><span class="sxs-lookup"><span data-stu-id="04785-151">To optimize your deployment, you'll need to answer the following questions:</span></span>
  
- <span data-ttu-id="04785-152">グループチャットサーバの以前のバージョン、または以前のバージョンの常設チャットサーバから移行している場合、または永続的なチャットサーバを初めて導入する場合は、</span><span class="sxs-lookup"><span data-stu-id="04785-152">Are you migrating from a previous version of Group Chat Server, or a previous version of Persistent Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>
    
- <span data-ttu-id="04785-p110">どのユーザーが常設チャット サーバーを使用できますか。常設チャットのポリシーで、グローバル、サイト、プール、またはユーザー レベルでのユーザー アクセスを決定します。</span><span class="sxs-lookup"><span data-stu-id="04785-p110">Who can use Persistent Chat Server? You specify Persistent Chat policies to determine user access at the global, site, or user level.</span></span>
    
- <span data-ttu-id="04785-p111">常設チャット サーバーへのアクセスが必要であるユーザー数はどれくらいですか。常設チャット サーバーは、150,000 人のプロビジョニングされた (ポリシーによって有効化された) ユーザーをサポートし、同時ユーザーの最大数は 80,000 人です。1 台の常設チャット サーバーで 20,000 人の接続ユーザーをサポートできます。また、1 つの常設チャット サーバー プールで最大 4 台のアクティブ サーバーを保持でき、合計 80,000 人の同時接続ユーザーに対応します。</span><span class="sxs-lookup"><span data-stu-id="04785-p111">How many users will require access to Persistent Chat Server? Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users. A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>
    
- <span data-ttu-id="04785-p112">スコープ、論理的境界、およびアクセスをどのように制御しますか。これらの境界を分離するカテゴリを定義し、各カテゴリに作成されたルームを利用できるユーザーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="04785-p112">How do you want to control scopes, ethical boundaries, and access? You can define categories to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>
    
- <span data-ttu-id="04785-160">ルームを作成できるユーザーをどのように制御しますか。</span><span class="sxs-lookup"><span data-stu-id="04785-160">How do you want to control who can create rooms?</span></span> <span data-ttu-id="04785-161">ルームを作成できる作成者を定義できます。</span><span class="sxs-lookup"><span data-stu-id="04785-161">You can define creators who can create rooms.</span></span> <span data-ttu-id="04785-162">作成者は、ルームの継続的な管理のために、他のメンバーをチャット ルーム マネージャーとして割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="04785-162">Creators can assign other members as chat room managers for ongoing management of the rooms.</span></span>
    
- <span data-ttu-id="04785-163">ルームをどのように作成しますか。</span><span class="sxs-lookup"><span data-stu-id="04785-163">How do you want to create rooms?</span></span> <span data-ttu-id="04785-164">常設チャットサーバーは、会議室の作成と管理を行うための web ベースの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="04785-164">Persistent Chat Server provides a web-based feature for creating and managing rooms.</span></span> <span data-ttu-id="04785-165">これは、Skype for Business クライアントから起動できます。</span><span class="sxs-lookup"><span data-stu-id="04785-165">This can be launched from the Skype for Business client.</span></span> <span data-ttu-id="04785-166">ビジネス要件とワークフローを実装する顧客ソリューションを定義し、常設チャットサーバーを構成してユーザーをカスタムソリューションに導くことができます。</span><span class="sxs-lookup"><span data-stu-id="04785-166">You can choose to define a customer solution that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>
    
- <span data-ttu-id="04785-167">どのような種類のアドインをプロビジョニングしますか。</span><span class="sxs-lookup"><span data-stu-id="04785-167">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="04785-168">アドインは、Skype for Business クライアントの拡張機能ウィンドウを利用してルームに関連するコンテキストを提供することで、ルーム内のエクスペリエンスを強化します。</span><span class="sxs-lookup"><span data-stu-id="04785-168">Add-ins enhance the in-room experience by leveraging the extensibility pane in the Skype for Business client to provide context that is relevant to the room.</span></span> <span data-ttu-id="04785-169">最も役立つと考えられる汎用的なアドイン (自社の Web サイト、社内のコラボレーション ドキュメントなど) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="04785-169">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="04785-170">チャット ルーム マネージャーは、必要に応じて登録済みのアドインのいずれかを選択し、ルームに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="04785-170">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span> 
    
- <span data-ttu-id="04785-171">どのような種類の高可用性要件と障害復旧要件がありますか。</span><span class="sxs-lookup"><span data-stu-id="04785-171">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="04785-172">常設チャットサーバーは、SQL Server のミラーリングと SQL Server クラスタリングをサポートし、高可用性を実現します。</span><span class="sxs-lookup"><span data-stu-id="04785-172">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability.</span></span> <span data-ttu-id="04785-173">ディザスターリカバリーの場合、常設チャットサーバーは、SQL Server のログ配布によって、ストレッチプール内の最大8台のサーバー (アクティブと4台のスタンバイ) をサポートします。</span><span class="sxs-lookup"><span data-stu-id="04785-173">For disaster recovery, Persistent Chat Server supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping.</span></span> 
    
- <span data-ttu-id="04785-174">規制要件はありますか?</span><span class="sxs-lookup"><span data-stu-id="04785-174">Are there regulatory requirements?</span></span> <span data-ttu-id="04785-175">会社が国内の国または地域内にあり、その国内にデータを保存する必要がある場合は、複数の常設チャットサーバープールを個々の地域に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04785-175">If your company is in a country or region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="04785-176">会議室、カテゴリ、アドインはプールには影響しません。1つの常設チャットサーバープールのみに所属します。</span><span class="sxs-lookup"><span data-stu-id="04785-176">A room, category, or add-in does not span pools--it belongs to only one Persistent Chat Server pool.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="04785-177">複数の常設チャットサーバープールを用意しても、スケールを拡大することはできません (すべての常設チャットサーバープールで同時に8万を使用できるユーザーは依然としています)。</span><span class="sxs-lookup"><span data-stu-id="04785-177">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrent users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="04785-178">複数の常設チャットサーバープールをサポートする主な理由は、規制に関する懸念事項をサポートすることです。</span><span class="sxs-lookup"><span data-stu-id="04785-178">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="04785-179">関連情報</span><span class="sxs-lookup"><span data-stu-id="04785-179">For more information</span></span>

<span data-ttu-id="04785-180">常設チャット サーバーのインストールと構成の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="04785-180">For more information about installing and configuring Persistent Chat Server, see the following topics:</span></span>
  
- <span data-ttu-id="04785-181">常設チャットサーバーの展開方法の詳細については、「 [Skype For Business server 2015 での常設チャットサーバーの展開](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04785-181">For details about how to deploy Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 
    
- <span data-ttu-id="04785-182">常設チャットサーバーの展開で設定を構成する方法について詳しくは、「 [Skype For Business server 2015 で常設チャットサーバーを管理](../../manage/persistent-chat/persistent-chat.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04785-182">For details about how to configure settings on your Persistent Chat Server deployment, see [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
    

