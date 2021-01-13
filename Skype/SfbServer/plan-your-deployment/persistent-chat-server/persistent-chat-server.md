---
title: Skype for Business Server 2015 での常設チャット サーバーの計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: '概要: このトピックでは、Skype for Business Server 2015 で常設チャット サーバーを計画する方法について説明します。'
ms.openlocfilehash: 9195c149744b9aab9927f0b2a6e490442cff6573
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813667"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="89c7a-103">Skype for Business Server 2015 での常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="89c7a-103">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="89c7a-104">**概要:** このトピックでは、Skype for Business Server 2015 で常設チャット サーバーを計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="89c7a-104">**Summary:** Read this topic to learn how to plan for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="89c7a-105">常設チャット サーバーはオプションの役割で、組織内の複数のユーザーがチャット ルームの会話に参加し、時間の長い間保持できます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-105">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="89c7a-106">ユーザーはチャット セッション中にリアルタイムで通信することができますが、各セッションのコンテンツ (テキスト、リンク、ファイルなど) は永続的であり、ユーザーはセッションのすべてのコンテンツをいつでも表示および検索できます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-106">Although users can communicate in real time during a chat session, the content of each session--including text, links, and files--is persistent, which means users can view and search all content of the session at any time.</span></span>
  
<span data-ttu-id="89c7a-107">常設チャット サーバーは、次の方法で組織内の通信を改善するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-107">Persistent Chat Server can help improve communication within your organization by:</span></span>
  
- <span data-ttu-id="89c7a-108">組織全体で情報の認識と参加を拡大する</span><span class="sxs-lookup"><span data-stu-id="89c7a-108">Broadening information awareness and participation throughout the organization</span></span>
    
- <span data-ttu-id="89c7a-109">効率的な情報共有の有効化</span><span class="sxs-lookup"><span data-stu-id="89c7a-109">Enabling efficient information sharing</span></span> 
    
- <span data-ttu-id="89c7a-110">地理的に分散したチームと機能的なチームを含む、チーム間のコミュニケーションの改善</span><span class="sxs-lookup"><span data-stu-id="89c7a-110">Improving communication between teams, including geographically dispersed and cross-functional teams</span></span>
    
- <span data-ttu-id="89c7a-111">情報の過負荷を軽減する</span><span class="sxs-lookup"><span data-stu-id="89c7a-111">Reducing information overload</span></span>
    
- <span data-ttu-id="89c7a-112">オプションで常設チャット コンプライアンス サービスを展開してコンプライアンス規制に従う</span><span class="sxs-lookup"><span data-stu-id="89c7a-112">Following compliance regulations by optionally deploying the Persistent Chat Compliance service</span></span>

> [!NOTE] 
> <span data-ttu-id="89c7a-113">常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="89c7a-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="89c7a-114">Teams でも同じ機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="89c7a-115">詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="89c7a-115">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="89c7a-116">常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
    
## <a name="persistent-chat-server-high-level-architecture"></a><span data-ttu-id="89c7a-117">常設チャット サーバーのアーキテクチャの高レベル</span><span class="sxs-lookup"><span data-stu-id="89c7a-117">Persistent Chat Server high-level architecture</span></span>

<span data-ttu-id="89c7a-118">次の図は、常設チャット サーバー アーキテクチャの大きなビューを示しています。</span><span class="sxs-lookup"><span data-stu-id="89c7a-118">The following diagram shows a high-level view of the Persistent Chat Server architecture.</span></span> 
  
![常設チャット サーバーのアーキテクチャの概要](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
<span data-ttu-id="89c7a-120">常設チャットは、常設チャット サービスを提供するフロントエンド サーバーの役割と、データベース コンポーネントのSQL構成されます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-120">Persistent Chat consists of a front-end server role that provides the Persistent Chat services as well as a back-end SQL database component.</span></span> <span data-ttu-id="89c7a-121">フロントエンド コンポーネントとバック エンド コンポーネントの両方が専用の常設チャット プールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="89c7a-121">Both front-end and back-end components are included in a dedicated Persistent Chat pool.</span></span> <span data-ttu-id="89c7a-122">常設チャット サーバーをホストする各コンピューターは、既存の Skype for Business Server 2015 トポロジにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="89c7a-122">Each computer that hosts Persistent Chat Server must have access to an existing Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="89c7a-123">この図には、1 つの常設チャット サーバー プール (A) があります。これは、メッセージをルーティングするために Skype for Business Server プール A に依存しています。</span><span class="sxs-lookup"><span data-stu-id="89c7a-123">In this diagram, there is one Persistent Chat Server pool (A), which is dependent on Skype for Business Server Pool A for routing messages to it.</span></span>
  
<span data-ttu-id="89c7a-124">1 つ以上の常設チャット サーバー プールを展開できます。各プールには、最大 80,000 人の同時ユーザーをサポートする最大 4 つのアクティブな常設チャット サーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="89c7a-124">You can deploy one or more Persistent Chat Server pools, each with up to four active Persistent Chat Servers supporting up to 80K concurrent users.</span></span>
  
<span data-ttu-id="89c7a-125">Skype for Business Server 2015 は、登録にセッション開始プロトコル (SIP) を使用し、チャット用に XCOS (Extensible Chat Communication Over SIP Protocol) を使用して常設チャット サービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="89c7a-125">Skype for Business Server 2015 communicates with the Persistent Chat service using the Session Initiation Protocol (SIP) for registration and the Extensible Chat Communication Over SIP protocol (XCCOS) for chat.</span></span> 
  
## <a name="persistent-chat-services"></a><span data-ttu-id="89c7a-126">常設チャット サービス</span><span class="sxs-lookup"><span data-stu-id="89c7a-126">Persistent Chat services</span></span>

<span data-ttu-id="89c7a-127">次の図は、常設チャット サーバーのフロントエンド サービスと、これらのサービスがバック エンド データベース コンポーネントと通信する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="89c7a-127">The following diagram shows the Persistent Chat Server front-end services, and how these services communicate with the back-end database components.</span></span> <span data-ttu-id="89c7a-128">フロントエンド コンポーネントには、常設チャット サービスとコンプライアンス サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-128">The front-end components include the Persistent Chat services and the Compliance service.</span></span> <span data-ttu-id="89c7a-129">バック エンド コンポーネントには、常設チャット ストアと常設チャット コンプライアンス ストアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-129">The back-end components include the Persistent Chat store and the Persistent Chat compliance store.</span></span>
  
![常設チャット サーバーのサービスの概要](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a><span data-ttu-id="89c7a-131">チャット サービス</span><span class="sxs-lookup"><span data-stu-id="89c7a-131">Chat service</span></span>

<span data-ttu-id="89c7a-132">チャット サービス (チャネル サービスとも呼ばれる) は、常設チャット サーバーを担当するコア サービスです。</span><span class="sxs-lookup"><span data-stu-id="89c7a-132">The Chat service, also called the Channel service, is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="89c7a-133">チャット サービスには、次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="89c7a-133">The Chat service provides the following functions:</span></span>
  
- <span data-ttu-id="89c7a-134">受信メッセージを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-134">Accepts incoming messages</span></span>
    
- <span data-ttu-id="89c7a-135">常設チャット ルーム内のオンライン参加者を登録および一覧表示する</span><span class="sxs-lookup"><span data-stu-id="89c7a-135">Registers and lists online participants within a Persistent Chat room</span></span>
    
- <span data-ttu-id="89c7a-136">メッセージを他のチャネル サブスクライバーに再送信します。</span><span class="sxs-lookup"><span data-stu-id="89c7a-136">Retransmits messages to other channel subscribers</span></span>
    
- <span data-ttu-id="89c7a-137">チャネル管理、チャット ルームへの招待、検索、新しいコンテンツ通知のロジックを実装します</span><span class="sxs-lookup"><span data-stu-id="89c7a-137">Implements logic for channel management, chat room invitations, search and new content notifications</span></span>
    
<span data-ttu-id="89c7a-138">常設チャット サービスは、常設チャット ストアを使用して、チャット ルームのコンテンツや他のシステム メタデータ (承認ルールなど) を格納し、アクセスします。</span><span class="sxs-lookup"><span data-stu-id="89c7a-138">The Persistent Chat service stores and accesses chat room content and other system metadata (authorization rules and so on) by using the Persistent Chat store.</span></span> <span data-ttu-id="89c7a-139">このサービスは、常設チャット ファイル ストア内のチャット ルームにアップロードされたファイルを格納します。</span><span class="sxs-lookup"><span data-stu-id="89c7a-139">The service stores files that are uploaded into chat rooms in the Persistent Chat file store.</span></span>
  
### <a name="compliance-service"></a><span data-ttu-id="89c7a-140">コンプライアンス サービス</span><span class="sxs-lookup"><span data-stu-id="89c7a-140">Compliance service</span></span>

<span data-ttu-id="89c7a-141">組織に常設チャットのアクティビティをアーカイブする必要がある規制がある場合は、オプションの常設チャット コンプライアンス サービスを展開できます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-141">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="89c7a-142">コンプライアンス サービスは、チャットのコンテンツとイベント (ルームへの参加やルームの退出など) を常設チャット コンプライアンス ファイル ストアにアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="89c7a-142">The Compliance service is responsible for archiving chat content and events, such as joining and leaving rooms, to the Persistent Chat Compliance file store.</span></span> <span data-ttu-id="89c7a-143">コンプライアンス サービスは、常設チャット プール内の各常設チャット サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-143">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> 
  
### <a name="web-services"></a><span data-ttu-id="89c7a-144">Web サービス</span><span class="sxs-lookup"><span data-stu-id="89c7a-144">Web services</span></span>

<span data-ttu-id="89c7a-145">常設チャット Web サービスは、Skype for Business フロントエンド サーバー上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-145">The Persistent Chat web services run on the Skype for Business Front End Servers.</span></span> <span data-ttu-id="89c7a-146">Web サービスはインターネット インフォメーション サービス (IIS) に依存し、Web コンポーネントとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-146">The web services depend on Internet Information Services (IIS), and are implemented as web components:</span></span>
  
- <span data-ttu-id="89c7a-147">ファイルのアップロードとダウンロードのための常設チャット Web サービスは、チャット ルームでのファイルの投稿と取得を担当します。</span><span class="sxs-lookup"><span data-stu-id="89c7a-147">Persistent Chat web services for file upload and download are responsible for posting and retrieving files from chat rooms.</span></span>
    
- <span data-ttu-id="89c7a-148">チャット ルーム管理用の常設チャット Web サービスは、ユーザーがチャット ルームを管理し、新しいチャット ルームを作成する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="89c7a-148">Persistent Chat web services for chat room management are responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>
    
## <a name="defining-requirements-for-your-organization"></a><span data-ttu-id="89c7a-149">組織の要件の定義</span><span class="sxs-lookup"><span data-stu-id="89c7a-149">Defining requirements for your organization</span></span>

<span data-ttu-id="89c7a-150">常設チャット サーバーを展開する場合は、組織のビジネス要件を決定し、ビジネス ニーズをサポートするトポロジ、インフラストラクチャ、および技術要件を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89c7a-150">If you decide to deploy Persistent Chat Server, you'll need to determine your organization's business requirements, then define the topology, infrastructure, and technical requirements to support your business needs.</span></span> <span data-ttu-id="89c7a-151">展開を最適化するには、次の質問に回答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89c7a-151">To optimize your deployment, you'll need to answer the following questions:</span></span>
  
- <span data-ttu-id="89c7a-152">以前のバージョンのグループ チャット サーバーまたは以前のバージョンの常設チャット サーバーから移行している場合、または常設チャット サーバーを初めて展開する場合</span><span class="sxs-lookup"><span data-stu-id="89c7a-152">Are you migrating from a previous version of Group Chat Server, or a previous version of Persistent Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>
    
- <span data-ttu-id="89c7a-153">常設チャット サーバーを使用できるユーザー</span><span class="sxs-lookup"><span data-stu-id="89c7a-153">Who can use Persistent Chat Server?</span></span> <span data-ttu-id="89c7a-154">常設チャット ポリシーを指定して、グローバル レベル、サイト レベル、またはユーザー レベルでのユーザー アクセスを決定します。</span><span class="sxs-lookup"><span data-stu-id="89c7a-154">You specify Persistent Chat policies to determine user access at the global, site, or user level.</span></span>
    
- <span data-ttu-id="89c7a-155">常設チャット サーバーにアクセスする必要があるユーザーの数</span><span class="sxs-lookup"><span data-stu-id="89c7a-155">How many users will require access to Persistent Chat Server?</span></span> <span data-ttu-id="89c7a-156">常設チャット サーバーは、150,000 人のプロビジョニングされたユーザー (ポリシーで有効) と最大 80,000 人の同時ユーザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="89c7a-156">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users.</span></span> <span data-ttu-id="89c7a-157">1 つの常設チャット サーバーで 20,000 人の接続ユーザーをサポートできます。また、1 つの常設チャット サーバー プールは、合計 80,000 人の同時接続ユーザーに対して最大 4 台のアクティブ サーバーを持つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89c7a-157">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>
    
- <span data-ttu-id="89c7a-158">スコープ、論理的境界、およびアクセスをどのように制御しますか。</span><span class="sxs-lookup"><span data-stu-id="89c7a-158">How do you want to control scopes, ethical boundaries, and access?</span></span> <span data-ttu-id="89c7a-159">これらの境界を分離するカテゴリを定義し、各カテゴリで作成されたルームに入室できるユーザーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-159">You can define categories to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>
    
- <span data-ttu-id="89c7a-160">ルームを作成できるユーザーをどのように制御しますか。</span><span class="sxs-lookup"><span data-stu-id="89c7a-160">How do you want to control who can create rooms?</span></span> <span data-ttu-id="89c7a-161">ルームを作成できる作成者を定義できます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-161">You can define creators who can create rooms.</span></span> <span data-ttu-id="89c7a-162">作成者は、ルームを継続的に管理するために、他のメンバーをチャット ルーム マネージャーとして割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-162">Creators can assign other members as chat room managers for ongoing management of the rooms.</span></span>
    
- <span data-ttu-id="89c7a-163">ルームをどのように作成しますか。</span><span class="sxs-lookup"><span data-stu-id="89c7a-163">How do you want to create rooms?</span></span> <span data-ttu-id="89c7a-164">常設チャット サーバーは、ルームを作成および管理するための Web ベースの機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="89c7a-164">Persistent Chat Server provides a web-based feature for creating and managing rooms.</span></span> <span data-ttu-id="89c7a-165">これは、Skype for Business クライアントから起動できます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-165">This can be launched from the Skype for Business client.</span></span> <span data-ttu-id="89c7a-166">ビジネス要件とワークフローを実装する顧客ソリューションを定義し、ユーザーにカスタム ソリューションを指示する常設チャット サーバーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-166">You can choose to define a customer solution that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>
    
- <span data-ttu-id="89c7a-167">どのような種類のアドインをプロビジョニングしますか。</span><span class="sxs-lookup"><span data-stu-id="89c7a-167">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="89c7a-168">アドインは、Skype for Business クライアントの拡張ウィンドウを利用して、ルームに関連するコンテキストを提供することで、ルーム内のエクスペリエンスを向上します。</span><span class="sxs-lookup"><span data-stu-id="89c7a-168">Add-ins enhance the in-room experience by leveraging the extensibility pane in the Skype for Business client to provide context that is relevant to the room.</span></span> <span data-ttu-id="89c7a-169">最も役立つと考えられる汎用的なアドイン (自社の Web サイト、社内のコラボレーション ドキュメントなど) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-169">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="89c7a-170">チャット ルーム マネージャーは、必要に応じて登録済みのアドインのいずれかを選択し、ルームに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="89c7a-170">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span> 
    
- <span data-ttu-id="89c7a-171">どのような種類の高可用性要件と障害復旧要件がありますか。</span><span class="sxs-lookup"><span data-stu-id="89c7a-171">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="89c7a-172">常設チャット サーバーは、高可用性SQL ServerミラーリングとSQL Serverクラスタリングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="89c7a-172">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability.</span></span> <span data-ttu-id="89c7a-173">障害復旧では、常設チャット サーバーは、ログ配布を使用するストレッチド プールで最大 8 つのサーバー (4 つのアクティブおよび 4 SQL Serverサポートします。</span><span class="sxs-lookup"><span data-stu-id="89c7a-173">For disaster recovery, Persistent Chat Server supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping.</span></span> 
    
- <span data-ttu-id="89c7a-174">規制要件はありますか?</span><span class="sxs-lookup"><span data-stu-id="89c7a-174">Are there regulatory requirements?</span></span> <span data-ttu-id="89c7a-175">企業が、データを国または地域内に保持する必要がある場合は、複数の常設チャット サーバー プールを展開し、各プールを特定の地域に対してローカルに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89c7a-175">If your company is in a country or region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="89c7a-176">ルーム、カテゴリ、またはアドインはプールにまたがるのではなく、1 つの常設チャット サーバー プールにのみ属します。</span><span class="sxs-lookup"><span data-stu-id="89c7a-176">A room, category, or add-in does not span pools--it belongs to only one Persistent Chat Server pool.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="89c7a-177">複数の常設チャット サーバー プールを使用しても、規模は大きくなされません (すべての常設チャット サーバー プールで同時に使用できるユーザー数は 80,000 人に制限されます)。</span><span class="sxs-lookup"><span data-stu-id="89c7a-177">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrent users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="89c7a-178">複数の常設チャット サーバー プールをサポートする主な理由は、規制上の懸念をサポートする理由です。</span><span class="sxs-lookup"><span data-stu-id="89c7a-178">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="89c7a-179">詳細情報</span><span class="sxs-lookup"><span data-stu-id="89c7a-179">For more information</span></span>

<span data-ttu-id="89c7a-180">常設チャット サーバーのインストールと構成の詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89c7a-180">For more information about installing and configuring Persistent Chat Server, see the following topics:</span></span>
  
- <span data-ttu-id="89c7a-181">常設チャット サーバーを展開する方法の詳細については [、「Deploy Persistent Chat Server in Skype for Business Server 2015」](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89c7a-181">For details about how to deploy Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 
    
- <span data-ttu-id="89c7a-182">常設チャット サーバーの展開で設定を構成する方法の詳細については [、「Manage Persistent Chat Server in Skype for Business Server 2015」](../../manage/persistent-chat/persistent-chat.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89c7a-182">For details about how to configure settings on your Persistent Chat Server deployment, see [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
    

