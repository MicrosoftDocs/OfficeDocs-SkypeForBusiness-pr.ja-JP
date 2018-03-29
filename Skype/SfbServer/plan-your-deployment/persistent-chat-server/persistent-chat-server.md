---
title: Skype for Business Server 2015 の常設チャット サーバーの計画
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: '概要: ビジネス サーバー 2015 に Skype での永続的なチャット サーバーを計画する方法については、このトピックを読みます。'
ms.openlocfilehash: 0380b5ebb43e198160faa3e7f10b1563b4def80f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="9b6c1-103">Skype for Business Server 2015 の常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="9b6c1-103">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9b6c1-104">**の概要:**ビジネス サーバー 2015 に Skype での永続的なチャット サーバーを計画する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-104">**Summary:** Read this topic to learn how to plan for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9b6c1-105">永続的なチャット サーバーは、組織内の複数のユーザーをできるようにするオプションのロールは、時間の経過と共に永続化するチャット ルームの会話に参加します。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-105">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="9b6c1-106">ユーザーは、チャット セッション中にリアルタイムで通信できますが、各セッションの内容 (テキスト、リンク、およびファイルを含む) は永続的であるため、任意の時点でセッションのすべての内容を表示および検索できます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-106">Although users can communicate in real time during a chat session, the content of each session--including text, links, and files--is persistent, which means users can view and search all content of the session at any time.</span></span>
  
<span data-ttu-id="9b6c1-107">によって、組織内のコミュニケーションを向上させるには、永続的なチャット サーバーができます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-107">Persistent Chat Server can help improve communication within your organization by:</span></span>
  
- <span data-ttu-id="9b6c1-108">組織全体で情報の認識と参加を拡大する</span><span class="sxs-lookup"><span data-stu-id="9b6c1-108">Broadening information awareness and participation throughout the organization</span></span>
    
- <span data-ttu-id="9b6c1-109">効率的な情報共有を実現する</span><span class="sxs-lookup"><span data-stu-id="9b6c1-109">Enabling efficient information sharing</span></span> 
    
- <span data-ttu-id="9b6c1-110">地理的に分散し、部門を越えたチームを含め、チーム間のコミュニケーションの向上</span><span class="sxs-lookup"><span data-stu-id="9b6c1-110">Improving communication between teams, including geographically dispersed and cross-functional teams</span></span>
    
- <span data-ttu-id="9b6c1-111">情報過多を緩和する</span><span class="sxs-lookup"><span data-stu-id="9b6c1-111">Reducing information overload</span></span>
    
- <span data-ttu-id="9b6c1-112">オプションで常設チャット コンプライアンス サービスを展開することで、法令上の規制に従う</span><span class="sxs-lookup"><span data-stu-id="9b6c1-112">Following compliance regulations by optionally deploying the Persistent Chat Compliance service</span></span>
    
## <a name="persistent-chat-server-high-level-architecture"></a><span data-ttu-id="9b6c1-113">常設チャット サーバーの高度なアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9b6c1-113">Persistent Chat Server high-level architecture</span></span>

<span data-ttu-id="9b6c1-114">次の図では、永続的なチャット サーバーのアーキテクチャの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-114">The following diagram shows a high-level view of the Persistent Chat Server architecture.</span></span> 
  
![常設チャット サーバーのアーキテクチャの概要](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
<span data-ttu-id="9b6c1-116">常設チャットは、常設チャット サービスだけでなく、バックエンド SQL データベース コンポーネントも提供するフロントエンド サーバーの役割から構成されています。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-116">Persistent Chat consists of a front-end server role that provides the Persistent Chat services as well as a back-end SQL database component.</span></span> <span data-ttu-id="9b6c1-117">フロントエンドとバックエンド両方のコンポーネントは、専用の常設チャット プールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-117">Both front-end and back-end components are included in a dedicated Persistent Chat pool.</span></span> <span data-ttu-id="9b6c1-118">永続的なチャット サーバーをホストする各コンピューターには、ビジネス サーバー 2015 トポロジの場合、既存の Skype へのアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-118">Each computer that hosts Persistent Chat Server must have access to an existing Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="9b6c1-119">この図では、Skype にメッセージのルーティング用ビジネス サーバー プール a に依存している 1 つの永続的なチャット サーバー プール (A) があります。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-119">In this diagram, there is one Persistent Chat Server pool (A), which is dependent on Skype for Business Server Pool A for routing messages to it.</span></span>
  
<span data-ttu-id="9b6c1-120">それぞれ 4 つまでアクティブな永続的なチャット サーバーのサポートを 80 K の同時ユーザーを持つ、1 つまたは複数の永続的なチャット サーバー プールを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-120">You can deploy one or more Persistent Chat Server pools, each with up to four active Persistent Chat Servers supporting up to 80K concurrent users.</span></span>
  
<span data-ttu-id="9b6c1-121">ビジネス サーバー 2015 の Skype は、登録と、拡張可能なチャットの通信に SIP プロトコル (XCCOS) チャットのセッション開始プロトコル (SIP) を使用して永続的なチャット サービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-121">Skype for Business Server 2015 communicates with the Persistent Chat service using the Session Initiation Protocol (SIP) for registration and the Extensible Chat Communication Over SIP protocol (XCCOS) for chat.</span></span> 
  
## <a name="persistent-chat-services"></a><span data-ttu-id="9b6c1-122">常設チャット サービス</span><span class="sxs-lookup"><span data-stu-id="9b6c1-122">Persistent Chat services</span></span>

<span data-ttu-id="9b6c1-123">次の図では、永続的なチャット サーバーのフロント エンド サービスとバックエンドのデータベース コンポーネントを使用してこれらのサービスが通信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-123">The following diagram shows the Persistent Chat Server front-end services, and how these services communicate with the back-end database components.</span></span> <span data-ttu-id="9b6c1-124">フロントエンド コンポーネントには常設チャット サービスとコンプライアンス サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-124">The front-end components include the Persistent Chat services and the Compliance service.</span></span> <span data-ttu-id="9b6c1-125">バックエンド コンポーネントには常設チャット ストアと常設チャット コンプライアンス ストアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-125">The back-end components include the Persistent Chat store and the Persistent Chat compliance store.</span></span>
  
![常設チャット サーバーのサービスの概要](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a><span data-ttu-id="9b6c1-127">チャット サービス</span><span class="sxs-lookup"><span data-stu-id="9b6c1-127">Chat service</span></span>

<span data-ttu-id="9b6c1-128">チャット サービスはチャネル サービスとも呼ばれ、常設チャット サーバーに対応するコア サービスです。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-128">The Chat service, also called the Channel service, is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="9b6c1-129">チャット サービスには次の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-129">The Chat service provides the following functions:</span></span>
  
- <span data-ttu-id="9b6c1-130">受信メッセージを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-130">Accepts incoming messages</span></span>
    
- <span data-ttu-id="9b6c1-131">登録し、永続的なチャット ルーム内のオンラインの参加者を一覧表示</span><span class="sxs-lookup"><span data-stu-id="9b6c1-131">Registers and lists online participants within a Persistent Chat room</span></span>
    
- <span data-ttu-id="9b6c1-132">他のチャネルのサブスクライバーにメッセージを再送します。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-132">Retransmits messages to other channel subscribers</span></span>
    
- <span data-ttu-id="9b6c1-133">チャネル管理、チャット ルームへの招待、検索、および新しいコンテンツ通知のロジックを実装します。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-133">Implements logic for channel management, chat room invitations, search and new content notifications</span></span>
    
<span data-ttu-id="9b6c1-134">常設チャット サービスは、常設チャット ストアを使用して、チャット ルームのコンテンツおよびその他のシステム メタデータ (承認規則など) を格納し、この情報にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-134">The Persistent Chat service stores and accesses chat room content and other system metadata (authorization rules and so on) by using the Persistent Chat store.</span></span> <span data-ttu-id="9b6c1-135">このサービスには、常設チャット ファイル ストアでチャット ルームにアップロードされたファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-135">The service stores files that are uploaded into chat rooms in the Persistent Chat file store.</span></span>
  
### <a name="compliance-service"></a><span data-ttu-id="9b6c1-136">コンプライアンス サービス</span><span class="sxs-lookup"><span data-stu-id="9b6c1-136">Compliance service</span></span>

<span data-ttu-id="9b6c1-137">常設チャットのアクティビティのアーカイブを求める規制が組織に存在する場合、オプションの常設チャット コンプライアンス サービスを展開できます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-137">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="9b6c1-138">コンプライアンス サービスは、ルームへの参加やルームからの退出など、チャット コンテンツとイベントの常設チャット コンプライアンス ファイル ストアへのアーカイブを担当します。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-138">The Compliance service is responsible for archiving chat content and events, such as joining and leaving rooms, to the Persistent Chat Compliance file store.</span></span> <span data-ttu-id="9b6c1-139">各永続的なチャット サーバーを永続的なチャット プール内では、コンプライアンス ・ サービスがインストールされています。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-139">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> 
  
### <a name="web-services"></a><span data-ttu-id="9b6c1-140">Web サービス</span><span class="sxs-lookup"><span data-stu-id="9b6c1-140">Web services</span></span>

<span data-ttu-id="9b6c1-141">ビジネスのフロント エンド サーバーは、Skype で永続的なチャット web サービスを実行します。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-141">The Persistent Chat web services run on the Skype for Business Front End Servers.</span></span> <span data-ttu-id="9b6c1-142">Web サービスはインターネット インフォメーション サービス (IIS) に依存し、Web コンポーネントとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-142">The web services depend on Internet Information Services (IIS), and are implemented as web components:</span></span>
  
- <span data-ttu-id="9b6c1-143">ファイルのアップロード / ダウンロード用の常設チャット Web サービスは、チャット ルームでのファイルの投稿および取得を処理します。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-143">Persistent Chat web services for file upload and download are responsible for posting and retrieving files from chat rooms.</span></span>
    
- <span data-ttu-id="9b6c1-144">チャット ルーム管理用の常設チャット Web サービスは、ユーザーがチャット ルームを管理したり、新しいチャット ルームを作成したりできるようにします。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-144">Persistent Chat web services for chat room management are responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>
    
## <a name="defining-requirements-for-your-organization"></a><span data-ttu-id="9b6c1-145">組織の要件の定義</span><span class="sxs-lookup"><span data-stu-id="9b6c1-145">Defining requirements for your organization</span></span>

<span data-ttu-id="9b6c1-146">永続的なチャット サーバーを展開する場合は、組織のビジネス要件を決定し、トポロジ、インフラストラクチャ、およびビジネス ニーズをサポートするための技術的な要件を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-146">If you decide to deploy Persistent Chat Server, you'll need to determine your organization's business requirements, then define the topology, infrastructure, and technical requirements to support your business needs.</span></span> <span data-ttu-id="9b6c1-147">配置を最適化するには、次の質問に回答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-147">To optimize your deployment, you'll need to answer the following questions:</span></span>
  
- <span data-ttu-id="9b6c1-148">以前のバージョンのグループ チャット サーバー、または永続的なチャット サーバーでは、以前のバージョンから移行する場合、最初に永続的なチャット サーバーを展開していますか。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-148">Are you migrating from a previous version of Group Chat Server, or a previous version of Persistent Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>
    
- <span data-ttu-id="9b6c1-p109">どのユーザーが常設チャット サーバーを使用できますか。常設チャットのポリシーで、グローバル、サイト、プール、またはユーザー レベルでのユーザー アクセスを決定します。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-p109">Who can use Persistent Chat Server? You specify Persistent Chat policies to determine user access at the global, site, or user level.</span></span>
    
- <span data-ttu-id="9b6c1-p110">常設チャット サーバーへのアクセスが必要であるユーザー数はどれくらいですか。常設チャット サーバーは、150,000 人のプロビジョニングされた (ポリシーによって有効化された) ユーザーをサポートし、同時ユーザーの最大数は 80,000 人です。1 台の常設チャット サーバーで 20,000 人の接続ユーザーをサポートできます。また、1 つの常設チャット サーバー プールで最大 4 台のアクティブ サーバーを保持でき、合計 80,000 人の同時接続ユーザーに対応します。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-p110">How many users will require access to Persistent Chat Server? Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users. A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>
    
- <span data-ttu-id="9b6c1-p111">スコープ、論理的境界、およびアクセスをどのように制御しますか。これらの境界を分離するカテゴリを定義し、各カテゴリに作成されたルームを利用できるユーザーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-p111">How do you want to control scopes, ethical boundaries, and access? You can define categories to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>
    
- <span data-ttu-id="9b6c1-156">ルームを作成できるユーザーをどのように制御しますか。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-156">How do you want to control who can create rooms?</span></span> <span data-ttu-id="9b6c1-157">ルームを作成できる作成者を定義できます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-157">You can define creators who can create rooms.</span></span> <span data-ttu-id="9b6c1-158">作成者は、ルームの継続的な管理のために、他のメンバーをチャット ルーム マネージャーとして割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-158">Creators can assign other members as chat room managers for ongoing management of the rooms.</span></span>
    
- <span data-ttu-id="9b6c1-159">ルームをどのように作成しますか。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-159">How do you want to create rooms?</span></span> <span data-ttu-id="9b6c1-160">永続的なチャット サーバーは、web ベースの作成と管理室の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-160">Persistent Chat Server provides a web-based feature for creating and managing rooms.</span></span> <span data-ttu-id="9b6c1-161">これは、クライアントのビジネスの Skype から起動できます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-161">This can be launched from the Skype for Business client.</span></span> <span data-ttu-id="9b6c1-162">ワークフロー、ビジネス要件を実装して、カスタム ソリューションの使用をユーザーに永続的なチャット サーバーを構成する顧客ソリューションを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-162">You can choose to define a customer solution that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>
    
- <span data-ttu-id="9b6c1-163">どのような種類のアドインをプロビジョニングしますか。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-163">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="9b6c1-164">アドインは、Skype for Business クライアントの拡張機能ウィンドウを利用してルームに関連するコンテキストを提供することで、ルーム内のエクスペリエンスを強化します。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-164">Add-ins enhance the in-room experience by leveraging the extensibility pane in the Skype for Business client to provide context that is relevant to the room.</span></span> <span data-ttu-id="9b6c1-165">最も役立つと考えられる汎用的なアドイン (自社の Web サイト、社内のコラボレーション ドキュメントなど) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-165">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="9b6c1-166">チャット ルーム マネージャーは、必要に応じて登録済みのアドインのいずれかを選択し、ルームに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-166">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span> 
    
- <span data-ttu-id="9b6c1-167">どのような種類の高可用性要件と障害復旧要件がありますか。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-167">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="9b6c1-168">永続的なチャット サーバーには、SQL Server のミラーリングと SQL Server の高可用性クラスタ リングがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-168">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability.</span></span> <span data-ttu-id="9b6c1-169">災害復旧では、永続的なチャット サーバーをサポートしている最大 8 台のサーバー (4 つのアクティブと 4 スタンバイ) SQL Server に引き伸ばされたプールでログ配布します。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-169">For disaster recovery, Persistent Chat Server supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping.</span></span> 
    
- <span data-ttu-id="9b6c1-170">規制要件はありますか。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-170">Are there regulatory requirements?</span></span> <span data-ttu-id="9b6c1-171">会社の国または地域のデータが国の内で保持する必要がある場合は、特定の地域に複数の永続的なチャット サーバー プール、各ローカルに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-171">If your company is in a country or region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="9b6c1-172">ルーム、カテゴリ、またはアドインにまたがらないプール--1 つの永続的なチャット サーバー プールに属しています。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-172">A room, category, or add-in does not span pools--it belongs to only one Persistent Chat Server pool.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9b6c1-173">複数の永続的なチャット サーバー プールのことを提供しません (することができますのみ 80,000 の同時接続ユーザー、すべての永続的なチャット サーバー プール間で) 複数のスケールです。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-173">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrent users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="9b6c1-174">複数の永続的なチャット サーバー プールをサポートするための主な理由は、規制上の問題をサポートすることです。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-174">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="9b6c1-175">関連情報</span><span class="sxs-lookup"><span data-stu-id="9b6c1-175">For more information</span></span>

<span data-ttu-id="9b6c1-176">常設チャット サーバーのインストールと構成の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-176">For more information about installing and configuring Persistent Chat Server, see the following topics:</span></span>
  
- <span data-ttu-id="9b6c1-177">永続的なチャット サーバーを展開する方法の詳細については、[ビジネス サーバー 2015 の Skype での永続的なのチャット サーバーの展開](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-177">For details about how to deploy Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 
    
- <span data-ttu-id="9b6c1-178">永続的なチャット サーバーの展開の設定を構成する方法の詳細については、[ビジネス サーバー 2015 の Skype での永続的なのチャット サーバーの管理](../../manage/persistent-chat/persistent-chat.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b6c1-178">For details about how to configure settings on your Persistent Chat Server deployment, see [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
    

