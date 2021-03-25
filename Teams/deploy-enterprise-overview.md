---
title: Microsoft Teams エンタープライズ展開の概要
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Microsoft Teams のエンタープライズ機能を展開する方法を学びます。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd3e60fafecd3cf025187935a9dc28b492c39d1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121415"
---
# <a name="teams-enterprise-deployment-overview"></a><span data-ttu-id="153df-103">Teams エンタープライズ展開の概要</span><span class="sxs-lookup"><span data-stu-id="153df-103">Teams enterprise deployment overview</span></span>

<span data-ttu-id="153df-104">中規模または大規模のビジネスの場合、ユーザーにサービスを展開する方法、Microsoft Teams クライアントをユーザーに展開する方法、ネットワーク設計がユーザーにどのように影響するか、リアルタイム通信の品質などについて考える必要があります。 </span><span class="sxs-lookup"><span data-stu-id="153df-104">If you're a medium or large business, you need to think about how you're going to roll out the service to your users, how you're going to deploy the Microsoft Teams client to them, how your network design could impact the quality of real-time communication, and so on.</span></span> <span data-ttu-id="153df-105">組織内のチームの計画に役立つ記事へのポインターについては、次のセクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="153df-105">Check out the following sections for pointers to articles that'll help you plan for Teams in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="153df-106">まだ行っていない場合は、パイロットから Teams の展開を開始することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="153df-106">If you haven't done so already, we strongly suggest that you begin your Teams deployment with a pilot.</span></span> <span data-ttu-id="153df-107">パイロットにより、計画と最終的な展開の前に、あなたや早期採用者が Teams とその機能に精通することができます。 パイロットを開始する方法の詳細については、「[Microsoft Teams を開始する](get-started-with-teams-quick-start.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="153df-107">A pilot will allow you and a few early adopters to get familiar with Teams and its features before your planning and eventual roll out. For more information about how to start your pilot, check out [Get started with Microsoft Teams](get-started-with-teams-quick-start.md).</span></span>

<span data-ttu-id="153df-108">以下のセクションを読み、組織での Teams の展開を開始する準備ができたら、「[企業で Microsoft Teams を設定する](deploy-enterprise-setup.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="153df-108">After you've read the sections below and are ready to start deploying Teams in your organization, see [Set up Microsoft Teams in your enterprise](deploy-enterprise-setup.md).</span></span>

## <a name="architecture"></a><span data-ttu-id="153df-109">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="153df-109">Architecture</span></span>

<span data-ttu-id="153df-110">Teams は Microsoft 365 に緊密に統合されており、チャット、ファイル共有、会議、テレフォニー、ビデオ ストリーミングなどを強化するために多くの機能を使用しています。</span><span class="sxs-lookup"><span data-stu-id="153df-110">Teams is tightly integrated into Microsoft 365 and uses many features to power chat, file sharing, meetings, telephony, video streaming, and more.</span></span> <span data-ttu-id="153df-111">Teams を展開する前に、[Microsoft Teams IT アーキテクチャとテレフォニー ソリューション ポスター](teams-architecture-solutions-posters.md)を確認して、Teams が Microsoft 365 の他の部分とどのように連携して、ユーザーに完全なコラボレーション エクスペリエンスを提供するかを理解してください。</span><span class="sxs-lookup"><span data-stu-id="153df-111">Before you roll out Teams, check out [Microsoft Teams IT architecture and telephony solutions posters](teams-architecture-solutions-posters.md) to get familiar with how Teams works with the rest of Microsoft 365 to create a complete collaboration experience for your users.</span></span>

## <a name="workloads"></a><span data-ttu-id="153df-112">ワークロード</span><span class="sxs-lookup"><span data-stu-id="153df-112">Workloads</span></span>

<span data-ttu-id="153df-113">Teams には、互いに独立して展開できる次の 3 つのワークロードがあります: **チャット、チーム、チャネル**; **ミーティングと会議**; および **電話システムと PSTN (公衆交換電話網) 接続** です。</span><span class="sxs-lookup"><span data-stu-id="153df-113">Teams has three workloads that can be deployed independently of each other: **chat, teams, and channels**; **meetings and conferencing**; and **Phone System and PSTN (public switched telephone network) connectivity**.</span></span> <span data-ttu-id="153df-114">各ワークロードには、そのワークロードに関する情報を簡単に見つけられるように、ドキュメントに独自のセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="153df-114">Each workload has its own section in our documentation to make it easier to find information about that workload.</span></span> <span data-ttu-id="153df-115">これには、展開計画についての情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="153df-115">This includes deployment planning information.</span></span>

<span data-ttu-id="153df-116">展開するワークロードの展開計画情報を確認するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="153df-116">To see deployment planning information for the workload you want to deploy, see the following articles:</span></span>

- [<span data-ttu-id="153df-117">チームとチャネルについて理解する</span><span class="sxs-lookup"><span data-stu-id="153df-117">Chat, teams, and channels</span></span>](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [<span data-ttu-id="153df-118">ミーティングと会議</span><span class="sxs-lookup"><span data-stu-id="153df-118">Meetings and conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="153df-119">音声 - 電話システムと PSTN 接続</span><span class="sxs-lookup"><span data-stu-id="153df-119">Phone System and PSTN connectivity</span></span>](cloud-voice-landing-page.md)

## <a name="network-planner"></a><span data-ttu-id="153df-120">ネットワーク プランナー</span><span class="sxs-lookup"><span data-stu-id="153df-120">Network planner</span></span>

<span data-ttu-id="153df-121">Teams のネットワーク計画は、多数のユーザー、複雑なネットワーク、またはその両方がある場合に非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="153df-121">Network planning for Teams is extremely important when you have large numbers of users, complex networks, or both.</span></span> <span data-ttu-id="153df-122">Teams は、音声通話とビデオ会議をサポートしています。どちらもリアルタイム通信に依存して、ユーザーに可能な限り最高のエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="153df-122">Teams supports voice calling and video conferencing, both of which rely on real-time communications to provide the best experience possible for users.</span></span> <span data-ttu-id="153df-123">ネットワークは、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="153df-123">Networks must:</span></span>

- <span data-ttu-id="153df-124">同時音声通話、ビデオ会議、会議、画面共有などの数に対応するのに十分な帯域幅容量があること。</span><span class="sxs-lookup"><span data-stu-id="153df-124">Have sufficient bandwidth capacity to accommodate the number of concurrent voice calls, video conferences, meetings, screen sharing, and so on.</span></span>
- <span data-ttu-id="153df-125">リアルタイム通信プロトコルをサポートするネットワーク ハードウェアを用意済みであること。</span><span class="sxs-lookup"><span data-stu-id="153df-125">Have network hardware that supports real-time communication protocols.</span></span>
- <span data-ttu-id="153df-126">ネットワーク上のデバイス、Microsoft 365 サービス、および外部ユーザー間で必要なネットワーク ポートを許可済みであること。</span><span class="sxs-lookup"><span data-stu-id="153df-126">Allow the required network ports between devices on your networks, Microsoft 365 services, and external users.</span></span>

<span data-ttu-id="153df-127">Teams ネットワークの要件を理解するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="153df-127">See the following articles to help you understand Teams network requirements:</span></span>

- [<span data-ttu-id="153df-128">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="153df-128">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)
- [<span data-ttu-id="153df-129">Teams または Skype for Business Online 向けのプロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="153df-129">Proxy servers for Teams or Skype for Business Online</span></span>](proxy-servers-for-skype-for-business-online.md)

<span data-ttu-id="153df-130">計画を支援するために、Teams にはネットワーク プランナーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="153df-130">To help you with your planning, Teams includes the Network planner.</span></span> <span data-ttu-id="153df-131">ネットワーク プランナーは、ユーザーの数と種類、組織にあるサイトの数、ネットワーク リンクの帯域幅容量などについて質問します。</span><span class="sxs-lookup"><span data-stu-id="153df-131">The Network planner asks you questions about the number and types of users you have, how many sites your organization has, the bandwidth capacity of your network links, and more.</span></span> <span data-ttu-id="153df-132">この情報を使用して、ネットワーク プランナーは、各アクティビティの帯域幅要件と推奨事項を示すレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="153df-132">Using this information, the Network planner creates a report that shows the bandwidth requirements for each activity, along with the recommendations.</span></span>

 > [!div class="nextstepaction"]
> [<span data-ttu-id="153df-133">ネットワーク プランナーに移動する</span><span class="sxs-lookup"><span data-stu-id="153df-133">Go to Network planner</span></span>](https://admin.teams.microsoft.com/networkplanner/organization)

<span data-ttu-id="153df-134">(ネットワーク プランナーを開くには、[Microsoft 365 グローバル管理者](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles)である必要があります。)</span><span class="sxs-lookup"><span data-stu-id="153df-134">(You must be a [Microsoft 365 global admin](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) to open the Network planner.)</span></span>

<span data-ttu-id="153df-135">ネットワーク プランナーの動作の詳細については、「[Microsoft Teams で ネットワーク プランナー を使用する](network-planner.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="153df-135">For details about how the Network planner works, see [Use the Network planner for Microsoft Teams](network-planner.md).</span></span>

<span data-ttu-id="153df-136">ネットワーク プランナーがネットワークを計画する方法の例を確認するには、「[ネットワーク プランナーの使用 - 例のシナリオ](tutorial-network-planner-example.yml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="153df-136">To see an example of how Network planner can plan your network, see [Using Network Planner - example scenario](tutorial-network-planner-example.yml).</span></span>

## <a name="teams-advisor"></a><span data-ttu-id="153df-137">Teams アドバイザー</span><span class="sxs-lookup"><span data-stu-id="153df-137">Teams advisor</span></span>

<span data-ttu-id="153df-138">Teams アドバイザーは、チーム、チャネル、ファイル共有、および Planner を統合して、組織の展開プロジェクトを作成する Teams 内のソリューションです。</span><span class="sxs-lookup"><span data-stu-id="153df-138">The Teams advisor is a solution within Teams that brings together teams, channels, file sharing, and Planner, to create a deployment project for your organization.</span></span> <span data-ttu-id="153df-139">Teams Advisor は、選択したワークロード (チャット、チーム、チャネルなど) に固有のプロジェクト計画を作成します。これには、展開中に実行する必要のある推奨タスクが含まれます。</span><span class="sxs-lookup"><span data-stu-id="153df-139">Teams advisor creates project plan, specific to the workload you select (such as chat, teams, and channels), that includes the recommended tasks you should perform during your deployment.</span></span> <span data-ttu-id="153df-140">各タスクには、プロセスをガイドするための指示、提案、および関連記事へのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="153df-140">Each task contains instructions, suggestions, and links to relevant articles, to guide you through the process.</span></span> <span data-ttu-id="153df-141">1 人以上の個人にタスクを簡単に割り当て、各タスクの開始日と終了日を指定できます。</span><span class="sxs-lookup"><span data-stu-id="153df-141">You can easily assign tasks to one or more individuals, and specify start and end dates for each task.</span></span>

> [!TIP]
> <span data-ttu-id="153df-142">Microsoft Learn の [Teams Advisor モジュールを使用してロールアウトを完了する](/learn/modules/m365-teams-rollout-using-advisor/)ことにより、Teams Advisor を使用して Teams の展開を計画する方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="153df-142">See how you can use Teams advisor to help you plan your Teams deployment by completing the [Roll out using the Teams advisor](/learn/modules/m365-teams-rollout-using-advisor/) module on Microsoft Learn.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="153df-143">Teams アドバイザーに移動する</span><span class="sxs-lookup"><span data-stu-id="153df-143">Go to Teams advisor</span></span>](https://admin.teams.microsoft.com/teams-deployment)

<span data-ttu-id="153df-144">(Teams アドバイザーを開くには、[Microsoft 365 グローバル管理者](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles)である必要があります。)</span><span class="sxs-lookup"><span data-stu-id="153df-144">(You must be a [Microsoft 365 global admin](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) to open the Teams advisor.)</span></span>

<span data-ttu-id="153df-145">Teams アドバイザーの機能の詳細については、「[Teams のアドバイザーを使用して、Microsoft Teams の展開を支援する](use-advisor-teams-roll-out.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="153df-145">For details about how the Teams advisor works, see [Use Advisor for Teams to help you roll out Microsoft Teams](use-advisor-teams-roll-out.md).</span></span>

## <a name="lifecycle-and-governance-planning"></a><span data-ttu-id="153df-146">ライフサイクルとガバナンスの計画</span><span class="sxs-lookup"><span data-stu-id="153df-146">Lifecycle and governance planning</span></span>

<span data-ttu-id="153df-147">Teams の展開を計画するときは、組織内のチーム、チャネル、ファイルなどのライフサイクルを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="153df-147">As you plan your Teams deployment, you need to consider the lifecycle of teams, channels, files, and so on, in your organization.</span></span> <span data-ttu-id="153df-148">また、どのような種類の情報がそれらに格納されるかについても考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="153df-148">You should also think about what types of information will be stored in them.</span></span> <span data-ttu-id="153df-149">Teams は、特定のプロジェクトや部門用に作成することも、組織全体の中心的なリソースとして使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="153df-149">Teams may be created for a specific project, for a department, or they might be used as a central resource for the entire organization.</span></span> <span data-ttu-id="153df-150">これらの用途にはそれぞれ異なる要件があり、次のような質問が発生します。</span><span class="sxs-lookup"><span data-stu-id="153df-150">Each of these uses have different requirements, which drive questions like the following:</span></span>

- <span data-ttu-id="153df-151">チームはどのくらいアクティブな状態のままですか?</span><span class="sxs-lookup"><span data-stu-id="153df-151">How long will the teams remain active?</span></span>
- <span data-ttu-id="153df-152">チームとそのチャネルを誰が所有および管理する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="153df-152">Who should own and manage the teams and their channels?</span></span>
- <span data-ttu-id="153df-153">一部のチームに適用する必要があるものの、他のチームには適用しない、特定のコンプライアンス要件がありますか?</span><span class="sxs-lookup"><span data-stu-id="153df-153">Should certain compliance requirements apply to some teams, but not others?</span></span>
- <span data-ttu-id="153df-154">ユーザーが適切なチームを特定するのに役立つ命名ポリシーが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="153df-154">Should there be a naming policy to help users identify the right team?</span></span>

<span data-ttu-id="153df-155">初期展開の一部としてポリシーとガイドラインを作成すると、ユーザーが必要な情報を確実に見つけられるようになります。</span><span class="sxs-lookup"><span data-stu-id="153df-155">Creating policies and guidelines as part of your initial deployment will help ensure that your users can find the information they need.</span></span> <span data-ttu-id="153df-156">ただし、同様に重要なこととして、適切なポリシーは、情報漏えいから組織を保護し、規制要件に準拠し、アーカイブを目的として必要に応じて情報を保持するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="153df-156">Just as importantly, however, appropriate policies will help protect your organization from information leakage, help you conform to regulatory requirements, and help you retain information as needed for archival purposes.</span></span>

<span data-ttu-id="153df-157">Teams のライフサイクル管理とガバナンスの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="153df-157">To learn more about lifecycle management and governance in Teams, see the following:</span></span>

- [<span data-ttu-id="153df-158">Teams でのライフサイクル管理を計画する</span><span class="sxs-lookup"><span data-stu-id="153df-158">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
- [<span data-ttu-id="153df-159">Teams でのガバナンスを計画する</span><span class="sxs-lookup"><span data-stu-id="153df-159">Plan for governance in Teams</span></span>](plan-teams-governance.md)

## <a name="adoption"></a><span data-ttu-id="153df-160">導入</span><span class="sxs-lookup"><span data-stu-id="153df-160">Adoption</span></span>

<span data-ttu-id="153df-161">組織とユーザーが Teams を最大限に活用できるようにするには、導入プログラムが必要です。</span><span class="sxs-lookup"><span data-stu-id="153df-161">To ensure that your organization and your users get the most out of Teams, you need an adoption program.</span></span> <span data-ttu-id="153df-162">効果的な導入プログラムは、次のことができる早期導入者を動員することができます。</span><span class="sxs-lookup"><span data-stu-id="153df-162">An effective adoption program can mobilize early adopters who can:</span></span>

- <span data-ttu-id="153df-163">Teams のメリットを同僚やビジネス リーダーまたはグループ リーダーに明確に伝える。</span><span class="sxs-lookup"><span data-stu-id="153df-163">Articulate the benefits of Teams to their colleagues and to business or group leaders.</span></span>
- <span data-ttu-id="153df-164">Teams がコラボレーションを改善し、相互の接続を容易にする方法を理解している他の人の関心を呼び起こす。</span><span class="sxs-lookup"><span data-stu-id="153df-164">Spark excitement in others who see how Teams improves collaboration and makes it easier to connect with each other.</span></span>
- <span data-ttu-id="153df-165">既存のビジネスプロセスを評価し、Teams をそれらに統合する方法についての推奨事項を作成するのを助ける。</span><span class="sxs-lookup"><span data-stu-id="153df-165">Help evaluate existing business processes and make recommendations for how Teams can be integrated into them.</span></span>
- <span data-ttu-id="153df-166">導入プロセスの改善に役立てるために、成功と困難の両方を展開チームに報告します。</span><span class="sxs-lookup"><span data-stu-id="153df-166">Report back to the deployment team both successes and difficulties to help improve the adoption process.</span></span>

<span data-ttu-id="153df-167">導入プログラムの設定の詳細については、「[Microsoft Teams を導入する](adopt-microsoft-teams-landing-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="153df-167">For details about setting up an adoption program, see [Adopt Microsoft Teams](adopt-microsoft-teams-landing-page.md).</span></span>