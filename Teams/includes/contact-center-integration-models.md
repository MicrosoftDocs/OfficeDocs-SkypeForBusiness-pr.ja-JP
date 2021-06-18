## <a name="integration-models-for-solution-providers"></a><span data-ttu-id="4b515-101">ソリューション プロバイダーの統合モデル</span><span class="sxs-lookup"><span data-stu-id="4b515-101">Integration models for solution providers</span></span>

<a name="steps"></a>

<span data-ttu-id="4b515-102">連絡先センター ソリューション プロバイダーとして、接続されている連絡先センター ソリューションを Teams に統合するために選択できる 3 つのモデルがあります。</span><span class="sxs-lookup"><span data-stu-id="4b515-102">As a contact center solution provider, there are three models to choose from to integrate your connected contact center solution into Teams:</span></span>

- <span data-ttu-id="4b515-103">認定された SBC と直接ルーティングを使用して、連絡先センター ソリューションを Teams に接続する場合は、「Connect モデル」を [参照してください](?tabs=connect#steps)。</span><span class="sxs-lookup"><span data-stu-id="4b515-103">If you want to use certified SBCs and Direct Routing to connect a contact center solution to Teams, see the [Connect model](?tabs=connect#steps).</span></span>

- <span data-ttu-id="4b515-104">Azure ボットと Microsoft Graph Communication API を使用して、ソリューション プロバイダーが Teams アプリを作成できる場合は、モデルの拡張に関するページ [を参照してください](?tabs=extend#steps)。</span><span class="sxs-lookup"><span data-stu-id="4b515-104">If you want to use Azure bots and the Microsoft Graph Communication APIs to enable solution providers to create Teams apps, see the [Extend model](?tabs=extend#steps).</span></span>

- <span data-ttu-id="4b515-105">ソリューション プロバイダーがアプリでネイティブ Teams エクスペリエンスを組み込む SDK を使用する場合は [、Power モデル を参照してください](?tabs=power#steps)。</span><span class="sxs-lookup"><span data-stu-id="4b515-105">If you want to use an SDK that enables solution providers to imbed native Teams experiences in their App, see the [Power model](?tabs=power#steps).</span></span> <span data-ttu-id="4b515-106">2021 年の終わりに向けて、SDK が使用可能な場合は、Power ソリューションが可能になります。</span><span class="sxs-lookup"><span data-stu-id="4b515-106">Power solutions will be possible when the SDK is available, towards the end of 2021.</span></span>

### <a name="the-connect-model"></a>[<span data-ttu-id="4b515-107">**Connect モデル**</span><span class="sxs-lookup"><span data-stu-id="4b515-107">**The Connect model**</span></span>](#tab/connect)

<span data-ttu-id="4b515-108">Connect モデルでは、Microsoft 認定の SBC とダイレクト ルーティングを使用して、連絡先センター ソリューションを Teams 電話システム インフラストラクチャに接続し、ルーティング、構成、およびシステムの洞察を強化します。</span><span class="sxs-lookup"><span data-stu-id="4b515-108">The Connect model uses Microsoft certified SBCs and Direct Routing to connect contact center solutions to Teams phone system infrastructure, enabling enhanced routing, configuration, and system insights.</span></span>

<span data-ttu-id="4b515-109">エージェントは、自動化された仮想アシスタントとスキルベースのルーティング キューを設定して、情報を収集し、顧客を主題の専門家と結び付けできます。</span><span class="sxs-lookup"><span data-stu-id="4b515-109">Agents can set up automated virtual assistants and skill-based routing queues to gather information and connect customers with subject matter experts.</span></span>

<span data-ttu-id="4b515-110">**主要な機能**</span><span class="sxs-lookup"><span data-stu-id="4b515-110">**Feature highlights:**</span></span>

<span data-ttu-id="4b515-111">これらの機能は、この統合モデルの機能の包括的な一覧ではサポートされませんが、主な領域は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4b515-111">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="4b515-112">Office CCaaS クライアントから Microsoft テナントに接続するエージェントの 365 認証</span><span class="sxs-lookup"><span data-stu-id="4b515-112">Office 365 authN for agents to connect to their Microsoft tenant from their integrated CCaaS client</span></span> 

  - <span data-ttu-id="4b515-113">Teams でエージェントを使用できる時間を確認する</span><span class="sxs-lookup"><span data-stu-id="4b515-113">See when agents are available with Teams</span></span>

  - <span data-ttu-id="4b515-114">Teams での転送とグループ通話のサポート</span><span class="sxs-lookup"><span data-stu-id="4b515-114">Transfers and group call support with Teams</span></span> 

  - <span data-ttu-id="4b515-115">Teams との統合のための Teams Graph API とクラウド通信 API</span><span class="sxs-lookup"><span data-stu-id="4b515-115">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="4b515-116">ソリューション プロバイダーの SBC で複数の顧客をサポートするマルチテナント SIP トランキング。</span><span class="sxs-lookup"><span data-stu-id="4b515-116">Multi-tenant SIP trunking to support several customers on solution provider’s SBC.</span></span>  

  - <span data-ttu-id="4b515-117">Microsoft 認定セッション ボーダー コントローラー [ <span class="underline">(SBC) を使用する</span>ソリューション プロバイダー](../direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="4b515-117">Solution providers to use [<span class="underline">Microsoft certified session border controller (SBC)</span>](../direct-routing-border-controllers.md)</span></span>


### <a name="the-extend-model"></a>[<span data-ttu-id="4b515-118">**拡張モデル**</span><span class="sxs-lookup"><span data-stu-id="4b515-118">**The Extend model**</span></span>](#tab/extend)

<span data-ttu-id="4b515-119">拡張モデルは、Teams クライアント プラットフォーム[、Teams Graph API、](/graph/api/resources/teams-api-overview?view=graph-rest-1.0)および Microsoft Graph の Cloud Communications API を使用して Teams クライアント[](/microsoftteams/platform/overview)[と統合されます](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)。</span><span class="sxs-lookup"><span data-stu-id="4b515-119">The Extend model integrates with the Teams client using the [Teams client platform](/microsoftteams/platform/overview), [Teams Graph APIs](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) and [Cloud Communications API in Microsoft Graph](/graph/api/resources/communications-api-overview?view=graph-rest-1.0).</span></span> <span data-ttu-id="4b515-120">拡張モデルでは、すべての連絡先センター通話と通話制御エクスペリエンスに Teams 電話システムも使用され、連絡先センター ソリューション プロバイダーは、Microsoft 365 と共にテレフォニーキャリアとして機能します。</span><span class="sxs-lookup"><span data-stu-id="4b515-120">The Extend model also uses the Teams phone system for all contact center calls and call control experiences, and the contact center solution provider acts as a telephony carrier alongside Microsoft 365.</span></span>

<span data-ttu-id="4b515-121">エージェントは、Teams を使用して内部コラボレーションと外部通信を行い、エンゲージメントを開始する前に複数のシステムのデータを関連付ける動的なコンテキスト ノートを利用し、コストの高いコンテキスト切り替えを回避できます。</span><span class="sxs-lookup"><span data-stu-id="4b515-121">Agents can use Teams for internal collaboration and external communication and can benefit from dynamic, contextual notes correlating data from multiple systems prior to starting an engagement and then avoid costly context switching.</span></span>

<span data-ttu-id="4b515-122">組織では、個人に向けてワークフローや高度なルーティング構成を設計し、システムとやり取りの品質を測定できます。</span><span class="sxs-lookup"><span data-stu-id="4b515-122">Organizations can design workflows and advanced routing configurations down to the individual and measure the quality of their system and interactions.</span></span>

<span data-ttu-id="4b515-123">**主要な機能**</span><span class="sxs-lookup"><span data-stu-id="4b515-123">**Feature highlights:**</span></span>

<span data-ttu-id="4b515-124">これらの機能は、この統合モデルの機能の包括的な一覧ではサポートされませんが、主な領域は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4b515-124">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="4b515-125">Teams との統合のための Teams Graph API とクラウド通信 API</span><span class="sxs-lookup"><span data-stu-id="4b515-125">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="4b515-126">エージェント エクスペリエンス用の Teams ベースのアプリ</span><span class="sxs-lookup"><span data-stu-id="4b515-126">Teams-based app for agent experiences</span></span> 

  - <span data-ttu-id="4b515-127">エージェントのプライマリ通話エンドポイントとしての Teams</span><span class="sxs-lookup"><span data-stu-id="4b515-127">Teams as the primary calling endpoint for the agents</span></span> 

  - <span data-ttu-id="4b515-128">すべての通話コントロールを対象とした Teams クライアントの呼び出し</span><span class="sxs-lookup"><span data-stu-id="4b515-128">Teams client calling for all the call controls</span></span>

  - <span data-ttu-id="4b515-129">Teams Web とモバイル クライアントの両方のエージェント エクスペリエンス アプリ</span><span class="sxs-lookup"><span data-stu-id="4b515-129">Agent experience app for both Teams web and mobile client</span></span>

  - <span data-ttu-id="4b515-130">Teams の CCaaS アプリ内のエージェントの分析、ワークフロー管理、ロールベースのエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="4b515-130">Analytics, workflow management, role-based experiences for agents in the CCaaS app in Teams</span></span>

  - <span data-ttu-id="4b515-131">Teams クライアントと統合されたチャットと共同作業操作</span><span class="sxs-lookup"><span data-stu-id="4b515-131">Chat and collaboration experiences integrated with Teams clients</span></span> 

  - <span data-ttu-id="4b515-132">すべてのアプリでの Teams クライアント操作のパフォーマンスと品質の維持</span><span class="sxs-lookup"><span data-stu-id="4b515-132">Preserve performance and quality of Teams client experiences in all apps</span></span>  

### <a name="the-power-model"></a>[<span data-ttu-id="4b515-133">**Power モデル**</span><span class="sxs-lookup"><span data-stu-id="4b515-133">**The Power model**</span></span>](#tab/power)

<span data-ttu-id="4b515-134">Power モデルを使用すると、ソリューション プロバイダーは、Teams 呼び出しインフラストラクチャとクライアント プラットフォームを使用してネイティブの Azure ベースの音声アプリケーションを作成し、顧客とエージェントの共同作業を行う最新のインテリジェントなソリューションを提供できます。</span><span class="sxs-lookup"><span data-stu-id="4b515-134">The Power model enables solution providers to create native Azure-based voice applications using the Teams calling infrastructure and client platform to deliver modern, intelligent solutions for collaborative customer and agent connection.</span></span> <span data-ttu-id="4b515-135">Power モデルの目的は、1 つのアプリで 1 画面のコンタクト センター エクスペリエンスを提供する方法です。</span><span class="sxs-lookup"><span data-stu-id="4b515-135">The goal of the Power model is to provide a one-app, one-screen contact center experience.</span></span>

<span data-ttu-id="4b515-136">**主要な機能**</span><span class="sxs-lookup"><span data-stu-id="4b515-136">**Feature highlights:**</span></span>

<span data-ttu-id="4b515-137">これらの機能は、この統合モデルの機能の包括的な一覧ではサポートされませんが、主な領域は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4b515-137">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="4b515-138">正式なエージェントでは、Teams SDK を介してオムニチャネル通信がネイティブで有効になります</span><span class="sxs-lookup"><span data-stu-id="4b515-138">Formal agent experiences natively enabled for omni-channel communication via Teams SDK</span></span> 

  - <span data-ttu-id="4b515-139">Teams コラボレーション サービスを使用してエージェントの共同作業と顧客とのやり取りを行う</span><span class="sxs-lookup"><span data-stu-id="4b515-139">Use Teams collaboration services for agent collaboration and customer interactions</span></span>  

  - <span data-ttu-id="4b515-140">クラウド サービスの迅速なプロビジョニング、どこからでも展開</span><span class="sxs-lookup"><span data-stu-id="4b515-140">Rapid provisioning of cloud services, deploy anywhere</span></span> 

  - <span data-ttu-id="4b515-141">Teams での会話中に、直接会話を制御し、対話することができます</span><span class="sxs-lookup"><span data-stu-id="4b515-141">Direct conversation control and interaction with users during Teams conversations</span></span> 

>[!NOTE]
> <span data-ttu-id="4b515-142">Power モデルは 2021 年末に提供される予定です。</span><span class="sxs-lookup"><span data-stu-id="4b515-142">The Power model will be available towards the end of 2021.</span></span>
