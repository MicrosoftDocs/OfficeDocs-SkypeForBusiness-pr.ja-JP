---
title: "Microsoft チーム サイド バイ サイド Skype for Business で有効にします。"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Skype for Business や Microsoft チーム サイドバイ サイド インストールを使ってのガイドです。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 7943765ec33e01f6237f74d5f8b171b267948961
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="enable-microsoft-teams-side-by-side-with-skype-for-business"></a><span data-ttu-id="2925c-103">Microsoft チーム サイド バイ サイド Skype for Business で有効にします。</span><span class="sxs-lookup"><span data-stu-id="2925c-103">Enable Microsoft Teams side-by-side with Skype for Business</span></span> 
=============================================================

<span data-ttu-id="2925c-104">組織での Skype for Business Online の既存の環境では、Microsoft チームの最近使用したファイルの概要は営業案件を単独、通信とコラボレーション ソリューション、ヒント目盛課題としてチームの潜在的なを評価するには2 つのソリューション環境にどのように、共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="2925c-104">For organizations with existing deployments of Skype for Business Online, the recent introduction of Microsoft Teams presents an opportunity to evaluate the potential of Teams as a sole, communications and collaboration solution, and a challenge to tip the scale between the two solutions and how they can coexist in your environment.</span></span>

<span data-ttu-id="2925c-105">チームでは、現在、ビジネスの要件を満たすことができます、1 つの通信や共同作業のソリューション、組織のチームを採用することを開始できます。</span><span class="sxs-lookup"><span data-stu-id="2925c-105">If Teams can meet your business requirements today, you can start adopting Teams to become your single communications and collaboration solution for your organization.</span></span>

<span data-ttu-id="2925c-p101">チームは、対象のすべてのテナントでは、既定で有効になります。このため、ユーザーの期待に進んでをチーム サイド バイ サイド Skype for Business を使ってを管理する方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2925c-p101">Teams is enabled by default, on all eligible tenants. Therefore, you need to decide on how to manage Teams side-by-side with Skype for Business, and continue to meet user expectations.</span></span>

<span data-ttu-id="2925c-p102">一般に、2 つの主要なサイド バイ サイドの顧客の利用があります。ものがあります。</span><span class="sxs-lookup"><span data-stu-id="2925c-p102">In general, there are two major side-by-side customer journeys. They are:</span></span>

-   <span data-ttu-id="2925c-110">**オプション 1:**非管理対象のサイドバイ サイド インストール顧客歩します。</span><span class="sxs-lookup"><span data-stu-id="2925c-110">**Option 1:** Unmanaged side-by-side customer journey.</span></span>

    <span data-ttu-id="2925c-111">IT が実際にコントロールの横に並べて発生、およびユーザー下せる優先アプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="2925c-111">IT does not actively control the side-by-side experience, and users are empowered to make the choice of preferred app.</span></span>

-   <span data-ttu-id="2925c-112">**オプション 2:**顧客のサイドバイ サイド インストール旅を管理します。</span><span class="sxs-lookup"><span data-stu-id="2925c-112">**Option 2:** Managed side-by-side customer journey.</span></span>

    <span data-ttu-id="2925c-113">IT の制御秘密チャット、経験、そしてチーム呼び出しのエクスペリエンスを [会議の新しいチャット ベースのコラボレーション ワークスペースを最初に導入するチームのサイドバイ サイド インストール プログラム、徐々 に導入する際の旅を使用してユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2925c-113">IT controls the side-by-side experience, taking users through a journey of gradually introducing Teams to first introduce a new chat-based collaboration workspace with private chat, then meeting experiences, and finally the calling experiences in Teams.</span></span>

![2 つのサイドバイ サイド インストール顧客利用の図: 管理を管理します。](media/guidance_SkypeforBusiness_image1.png)

<a name="side-by-side-benefits-and-considerations"></a><span data-ttu-id="2925c-115">サイド バイ サイドの主な利点と注意事項</span><span class="sxs-lookup"><span data-stu-id="2925c-115">Side-by-side benefits and considerations</span></span>
----------------------------------------

<span data-ttu-id="2925c-p103">各旅には、主な利点と評価して、転送、組織のプロファイルに基づく右のパスを決定する際の考慮事項があります。次の表は、管理および非管理対象のサイドバイ サイド インストール顧客の利用を比較するを提供します。</span><span class="sxs-lookup"><span data-stu-id="2925c-p103">Each journey has benefits and considerations to evaluate when determining the right path forward based on your organization's profile. The table below provides the comparisons between managed and unmanaged side-by-side customer journeys.</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2925c-118">移行方法</span><span class="sxs-lookup"><span data-stu-id="2925c-118">Migration Paths</span></span></th>
<th align="left"><span data-ttu-id="2925c-119">非管理対象サイド バイ サイド</span><span class="sxs-lookup"><span data-stu-id="2925c-119">Unmanaged Side-by-Side</span></span></th>
<th align="left"><span data-ttu-id="2925c-120">管理されたサイド バイ サイド</span><span class="sxs-lookup"><span data-stu-id="2925c-120">Managed Side-by-Side</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="2925c-121"><strong>組織プロファイル</strong></span><span class="sxs-lookup"><span data-stu-id="2925c-121"><strong>Organization profile</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="2925c-122">通常、IT リソースがない専用小規模組織の場合</span><span class="sxs-lookup"><span data-stu-id="2925c-122">Typically, smaller organizations with no dedicated IT resources</span></span></li>
<li><span data-ttu-id="2925c-123">IT により、ユーザーの任意の作業の適切なツールを選択します。</span><span class="sxs-lookup"><span data-stu-id="2925c-123">IT allows user discretion in selecting right tools for their work</span></span></li>
<li><span data-ttu-id="2925c-124">ビジネスを使用するための主 Skype は、IM/P と会議</span><span class="sxs-lookup"><span data-stu-id="2925c-124">Primary Skype for Business usage is IM/P and meetings</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="2925c-125">大規模な組織に、一般的に、規模</span><span class="sxs-lookup"><span data-stu-id="2925c-125">Typically, mid-size to larger organizations</span></span></li>
<li><span data-ttu-id="2925c-126">コントロールに、必要のロールアウトの新しいツールの厳格なその他</span><span class="sxs-lookup"><span data-stu-id="2925c-126">IT wants to control roll out of new tools more rigorously</span></span></li>
<li><span data-ttu-id="2925c-127">Skype for Business の詳細な導入今日</span><span class="sxs-lookup"><span data-stu-id="2925c-127">Deeper adoption of Skype for Business today</span></span></li>
<li><span data-ttu-id="2925c-128">ネットワークとインフラストラクチャの複雑さの増加</span><span class="sxs-lookup"><span data-stu-id="2925c-128">Increased complexity in network and infrastructure</span></span></li>
<li><span data-ttu-id="2925c-129">複数の場所</span><span class="sxs-lookup"><span data-stu-id="2925c-129">Multiple locations</span></span></p>
<li><span data-ttu-id="2925c-130">UC の固有の機能を 1 つのアプリの基本設定</span><span class="sxs-lookup"><span data-stu-id="2925c-130">Preference for single app with unique UC capabilities</span></span></li></ul></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="2925c-131"><strong>主な利点</strong></span><span class="sxs-lookup"><span data-stu-id="2925c-131"><strong>Benefits</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="2925c-132">Skype for Business では使用できないチームで機能を活用します。</span><span class="sxs-lookup"><span data-stu-id="2925c-132">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="2925c-133">Office 365 で最近ワークプ レースの強化</span><span class="sxs-lookup"><span data-stu-id="2925c-133">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="2925c-134">柔軟性の高いレベルのユーザー</span><span class="sxs-lookup"><span data-stu-id="2925c-134">Increased user flexibility</span></span></li>
<li><span data-ttu-id="2925c-135">一度にすべての機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2925c-135">Enable all capabilities at once</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="2925c-136">Skype for Business では使用できないチームで機能を活用します。</span><span class="sxs-lookup"><span data-stu-id="2925c-136">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="2925c-137">Office 365 で最近ワークプ レースの強化</span><span class="sxs-lookup"><span data-stu-id="2925c-137">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="2925c-138">ユーザーの生産性の向上を最小化します。</span><span class="sxs-lookup"><span data-stu-id="2925c-138">Minimize user productivity impact</span></span></li>
<li><span data-ttu-id="2925c-139">機能の重複を減らす</span><span class="sxs-lookup"><span data-stu-id="2925c-139">Reduce capability overlap</span></span></li>
<li><span data-ttu-id="2925c-140">UC のシナリオを効率化するツールの選択</span><span class="sxs-lookup"><span data-stu-id="2925c-140">Streamline tool choice for UC scenarios</span></span></li>
<li><span data-ttu-id="2925c-141">支援 IT とビジネス組織で適切に機能を有効にするには</span><span class="sxs-lookup"><span data-stu-id="2925c-141">Empower IT and business to enable capabilities as appropriate in organization</span></span></li>
<li><span data-ttu-id="2925c-142">ユーザーの変更の速度を制御します。</span><span class="sxs-lookup"><span data-stu-id="2925c-142">Control the pace of change for users</span></span></li></ul></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="2925c-143"><strong>考慮事項</strong></span><span class="sxs-lookup"><span data-stu-id="2925c-143"><strong>Considerations</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="2925c-144">重なっている、類似した機能を持つ複数のアプリ</span><span class="sxs-lookup"><span data-stu-id="2925c-144">Multiple apps with similar, overlapping capabilities</span></span></li>
<li><span data-ttu-id="2925c-145">ユーザーが混乱これが原因で電話サポートの向上、影 IT、影響を受ける生産性の向上潜在的な</span><span class="sxs-lookup"><span data-stu-id="2925c-145">Increased potential for user confusion which can lead to increased support calls, shadow IT, impacted productivity</span></span></li>
<li><span data-ttu-id="2925c-146">ネットワークの計画およびモニタリングする必要があります考慮 2 つのサービスの使用</span><span class="sxs-lookup"><span data-stu-id="2925c-146">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="2925c-147">必要なが強化されるとすぐに変更管理作業: 在籍情報、トレーニング、およびサポート</span><span class="sxs-lookup"><span data-stu-id="2925c-147">Increased and immediate change management efforts required: awareness, training, and support</span></span></li>
<li><span data-ttu-id="2925c-148">アプリの間の相互運用性の制限事項があります。</span><span class="sxs-lookup"><span data-stu-id="2925c-148">Users may experience interoperability limitations between apps</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="2925c-149">IT からライセンスを計画および実装の他のサイクルを必要とする、ユーザー エクスペリエンスの詳細なコントロールを持つ</span><span class="sxs-lookup"><span data-stu-id="2925c-149">IT has granular control, from licensing to user experiences, requiring additional cycles of planning and implementation</span></span></li>
<li><span data-ttu-id="2925c-150">ユーザーの教育機関向けおよびチームの選択の機能を無効にするに必要なアクション</span><span class="sxs-lookup"><span data-stu-id="2925c-150">User education and action required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="2925c-151">チームの選択の機能を無効にするために必要な管理作業を変更します。</span><span class="sxs-lookup"><span data-stu-id="2925c-151">Change management efforts required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="2925c-152">ネットワークの計画およびモニタリングする必要があります考慮 2 つのサービスの使用</span><span class="sxs-lookup"><span data-stu-id="2925c-152">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="2925c-153">アプリの間の相互運用性の制限事項があります。</span><span class="sxs-lookup"><span data-stu-id="2925c-153">Users may experience interoperability limitations between apps</span></span></li></ul></td>
</tr>
</tbody>
</table>


<a name="unmanaged-side-by-side-customer-journey"></a><span data-ttu-id="2925c-154">非管理対象のサイドバイ サイド インストール顧客歩</span><span class="sxs-lookup"><span data-stu-id="2925c-154">Unmanaged side-by-side customer journey</span></span>
---------------------------------------


![非管理対象のサイドバイ サイド インストール カスタマー ネットワークの図。](media/guidance_SkypeforBusiness_image4.png)

<span data-ttu-id="2925c-156">デスクトップ コンピューター (PC または Mac でのクライアント ソフトウェアと web クライアントに関連する共同作業ソリューション (チャット ベースのワークスペース、チャンネル、アプリ、他の Office 365 ワークロードなどとの統合) として、非管理対象のサイドバイ サイド インストール顧客の旅のチームが導入されました) のモバイル デバイスとします。</span><span class="sxs-lookup"><span data-stu-id="2925c-156">In an unmanaged side-by-side customer journey, Teams is introduced as a collaboration solution (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.) that involves client software and web client on desktop computers (PC or Mac) and mobile devices.</span></span>


<span data-ttu-id="2925c-p104">既定では、チームは、Skype for Business で重複する機能を提供するも、これら秘密チャットなど、通話、会議をスケジュールします。これは、チームが Skype for Business はのような機能が同時に完全なコミュニケーションと、組織のコラボレーションを提供することを意味します。</span><span class="sxs-lookup"><span data-stu-id="2925c-p104">By default, Teams also presents overlapping capabilities with Skype for Business, these include private chat and calling, and scheduled meetings. This means Teams ends up providing complete communications and collaboration for the organization, while at the same time Skype for Business provides similar capabilities.</span></span>

<span data-ttu-id="2925c-p105">チーム for Business Online ユーザーは、Skype での相互運用性をサポートしているし、ユーザーがチームを実行するときに、優先チャットと呼び出しのアプリを選択するには、営業案件を指定します。1 人のユーザーが、好みのアプリとチームを選択し、他のユーザーがチームがインストールされていないや Skype for Business 優先チャットと通話のアプリを選んだ場合は、チャット、チームの一部である相互運用機能を通じて互いに呼び出しを続けることができます。</span><span class="sxs-lookup"><span data-stu-id="2925c-p105">Teams supports interoperability with Skype for Business Online users, and users will be given an opportunity to choose their preferred chat and calling app when they launch Teams. If one user picks Teams as the preferred app, and another user hasn’t installed Teams or picked Skype for Business as the preferred chat and calling app, they can continue to chat and call each other through the interop capabilities that are part of Teams.</span></span>

<span data-ttu-id="2925c-p106">Microsoft の相互運用エクスペリエンスを向上継続的にです。最初は、あなたの相互運用エクスペリエンスでは、ユーザーの期待を満たしていない場合があります。Skype for Business が引き続きユーザーに利用可能なのでは、現在、チームが提供されることはできませんが、機能の Skype for Business に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="2925c-p106">Microsoft is continuously improving the interop experiences. In the beginning, there may be some cases whereby the interop experiences are not meeting user expectations. Since Skype for Business is still available to users, they can switch to Skype for Business for the capabilities that currently cannot be served by Teams.</span></span>

<span data-ttu-id="2925c-p107">チームでスケジュールされた会議は、ユーザーがチーム会議、または [Skype for Business 会議スケジュールを設定できる別の重複する機能です。独自の利点は、チーム会議エクスペリエンスがビジネス要件を満たしているや、Skype for Business 会議の機能を超える場合、時間経過と予想していますユーザーが自然にチーム会議に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="2925c-p107">Scheduled meetings in Teams is another overlapping capability that lets users schedule Teams meetings, or Skype for Business meetings. Each has its own advantages, and over time, when Teams meeting experience meets business requirements or surpasses the functionalities of Skype for Business meetings, we expect users to naturally switch to Teams meetings.</span></span>

<span data-ttu-id="2925c-p108">この非管理対象のサイドバイ サイド インストール カスタマー ネットワークでは、ユーザーからのサポートへの電話の処理の相互運用機能に関する問題が直面するときに、ヘルプデスクのチームを準備します。ユーザーの通知または Skype for Business 会議の場合は、チーム会議を選択して、その逆します。</span><span class="sxs-lookup"><span data-stu-id="2925c-p108">In this unmanaged side-by-side customer journey, prepare your helpdesk team to handle support calls from users when facing issues with interop capabilities. Or advise users when to choose Teams meetings over Skype for Business meetings, and vice versa.</span></span>

<span data-ttu-id="2925c-168">このサイドバイ サイド インストール顧客旅あなたユーザーより多くの非管理対象のサイドバイ サイド インストール操作の内容と、最適なコミュニケーションや共同作業するユーザーが組織で認めオープン、組織に適用される場合があります。要件に合わせてツール。</span><span class="sxs-lookup"><span data-stu-id="2925c-168">This side-by-side customer journey may be applicable to your organization, whereby the users are more receptive to the nature of the unmanaged side-by-side experience, and the organization openly allows the users to pick the best communications and collaboration tools that suit their requirements.</span></span>

<a name="managed-side-by-side-customer-journey"></a><span data-ttu-id="2925c-169">サイド バイ サイド カスタマー ネットワークの管理</span><span class="sxs-lookup"><span data-stu-id="2925c-169">Managed side-by-side customer journey</span></span>
-------------------------------------

![管理のサイドバイ サイド インストール カスタマー ネットワークの図。](media/guidance_SkypeforBusiness_image2.png)

<span data-ttu-id="2925c-171">組織のチームを導入する方法をより細かく制御したいと管理のサイドバイ サイド インストール顧客旅を開始します。</span><span class="sxs-lookup"><span data-stu-id="2925c-171">A managed side-by-side customer journey starts with organization wanting more control over how Teams is introduced.</span></span>

-   <span data-ttu-id="2925c-p109">この旅の**最初のステップ**内モダンなコラボレーション要件 (チャット ベースのワークスペース、チャンネル、アプリ、他の Office 365 ワークロードなどとの統合。) にあるチームの制限パイロットであります。アドホック チャネルの会議とプライベートのチャット チームでも秘密チャット エクスペリエンス チーム会議エクスペリエンスを評価するためにパイロット ユーザーのようなテキストを入力する有効です。この段階では、スケジュールされた会議とチームで非公開の通話機能が無効になります。パイロットの使用を開始する、 [Skype for Business とチームをパイロット](pilot-essentials.md)に移動します。</span><span class="sxs-lookup"><span data-stu-id="2925c-p109">The **first step** of this journey is a limited pilot of Teams scoped to modern collaboration requirements (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.). Ad-hoc channel meetings and private chat in Teams is also enabled to provide a chance for pilot users to evaluate the Teams meetings experience and private chat experiences. Scheduled meetings and private calling capabilities in Teams are disabled at this stage. To get started with a pilot, go to [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>
    
-   <span data-ttu-id="2925c-p110">チームのロールアウトの組織全体で非公開チャットの最新のグループ作業のこの旅の**2 番目の手順**を拡張します。スケジュールされた会議とプライベート呼び出しは、Skype でのビジネス機能の重複部分を小さくために、チームで無効にするのに進みます。</span><span class="sxs-lookup"><span data-stu-id="2925c-p110">The **second step** of this journey is extending the rollout of Teams for modern collaboration with private chat throughout the organization. Scheduled meetings, and private calling continue to be disabled in Teams to reduce the overlap  with with Skype for Business capabilities.</span></span>

    <span data-ttu-id="2925c-178">この時点では、組織全体のチームまたは Skype for Business に優先チャット アプリケーションを設定する必要があるかどうかを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2925c-178">At this stage, you may need to consider whether preferred chat application should be set to Teams or Skype for Business for the entire organization.</span></span>

    - <span data-ttu-id="2925c-179">場合は、チーム内で、組織全体では、他の関係者と通信するときに早期段階の相互運用性の課題を処理するユーザーを準備します。</span><span class="sxs-lookup"><span data-stu-id="2925c-179">If set to Teams, prepare your users to handle early interoperability challenges when communicating with other parties within and across the organization.</span></span>
    
    - <span data-ttu-id="2925c-180">Skype for Business、非公開に設定する [内でチャット チーム、チームのままになりますエンドユーザーすぐに利用できる、チーム内でのチャット機能のプラットフォームの永続的な性質、およびそれらを引き続き使用 Skype for Business 秘密チャット間での Skype for Business のユーザーを組織内で、組織全体でします。</span><span class="sxs-lookup"><span data-stu-id="2925c-180">If set to Skype for Business, private chats within Teams will remain in Teams, and end users can immediately take advantage of the cross-platform persistent nature of chat capabilities within Teams, and they will continue to use Skype for Business for private chats among Skype for Business users, within the organization and across the organization.</span></span>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="2925c-181">注</span><span class="sxs-lookup"><span data-stu-id="2925c-181">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="2925c-p111">現在優先チャット アプリケーションの設定はクライアント レベルでのみ利用できます。ユーザーのトレーニングおよび導入キャンペーンは、意図した組織全体で使う構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2925c-p111">Currently the preferred chat application setting is available only at the client level. User training and adoption campaign will be required to drive the intended organization-wide configuration.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="2925c-p112">管理のサイドバイ サイド インストール カスタマー ネットワークの**3 番目の手順**は、組織はチーム会議の操作と機能が、ビジネス要件を満たしていることにしたときに起動します。プライベートを有効にすると、チーム内のチャンネルの会議、ユーザーにチーム会議と Skype for Business 会議スケジュールを設定するためのオプションが表示されます。このため、時間経過ユーザーが自然に切り替えることチーム会議を継続的な革新をチームで指定された予定です。Skype for Business からチームの使用をステアリングに成功する含めた、トレーニング、サポートとの通信を説明する堅牢な変更管理プログラムの実装に向けて、付加価値チームが作業を開始する方法のガイダンスをクリアすると、ユーザーに提供することチームします。周知キャンペーンをデザインするために、[ユーザーの準備](http://aka.ms/UserReadiness)のリソースを活用できます。</span><span class="sxs-lookup"><span data-stu-id="2925c-p112">The **third step** of the managed side-by-side customer journey starts when the organization decides that Teams meeting experience and capabilities meet their business requirements. By enabling private and channel meetings in Teams, users are presented with options to schedule both Teams meetings and Skype for Business meetings. Therefore, it is expected that over time users will naturally switch to Teams meetings given the continued innovations in Teams. To be successful in steering usage from Skype for Business to Teams, implement a robust change management program inclusive of training, support and communications that explains the value-add that Teams offers to the user, with clear guidance on how to get started with Teams. Leverage our [User Readiness](http://aka.ms/UserReadiness) resources to help design your awareness campaign.</span></span>


<span data-ttu-id="2925c-p113">チーム呼び出しを有効にすると管理のサイドバイ サイド インストール カスタマー ネットワークの**4 番目の手順**を開始します。チームの相互運用性の機能は、シームレス サイドバイ サイド インストールを確認するには、この手順で頻度の高い機能です。理想的には、プライベート通話には、チームの使用を適用するのには、チームは、既定の呼び出し元アプリとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="2925c-p113">The **fourth step** of the managed side-by-side customer journey begins with enabling calling in Teams. Teams interoperability capabilities will feature heavily in this step to ensure a seamless side-by-side experience. Ideally, to enforce the use of Teams for private calling, Teams is set as the default calling app.</span></span> 

<span data-ttu-id="2925c-p114">可能性のある、時間経過は組織全体がチーム通信とコラボレーションの要件を満たすし、 **5 の手順**を実行するだけに依存することができます。チームの新機能を受信するときに表示されたら、 [Office 365 ロードマップ](http://aka.ms/TeamsRoadmap)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2925c-p114">Over time, potentially the whole organization can rely solely on Teams to meet communications and collaboration requirements and take the **fifth step**. To see when new features are coming in Teams, see the [Office 365 Roadmap](http://aka.ms/TeamsRoadmap).</span></span> 

<a name="managing-side-by-side-experience"></a><span data-ttu-id="2925c-194">サイド バイ サイドのエクスペリエンスを管理します。</span><span class="sxs-lookup"><span data-stu-id="2925c-194">Managing side-by-side experience</span></span>
--------------------------------

<span data-ttu-id="2925c-p115">既定では、対象の Office 365 サブスクリプションを持つ組織の場合は、マイクロソフトのチームが有効になります。場合は、組織では、非管理対象のサイドバイ サイド インストール カスタマー ネットワークのプロファイルに適したを強くお勧めとしてを保持するのマイクロソフトのチームの自然の導入を推進します。</span><span class="sxs-lookup"><span data-stu-id="2925c-p115">By default, for organizations with eligible Office 365 subscriptions, Microsoft Teams is enabled. If your organization fits the profile for unmanaged side-by-side customer journey, we highly recommend you keep it as-is to foster organic adoption of Microsoft Teams.</span></span>

<span data-ttu-id="2925c-197">チームでは、(現在 PC のみに適用可能なインストール) 用の IT 管理者特権が必要としないを最新の Web ブラウザー デスクトップ クライアントおよびモバイル クライアントからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2925c-197">Teams is accessible via modern Web browser desktop clients which require no IT administrative privilege (for installation, currently applicable to PC only) and mobile clients.</span></span>

<span data-ttu-id="2925c-p116">ユーザーが試すし、必要に応じている機能を使用できるように、既定では、プライベート チャットと通話、アドホックとスケジュールされた会議の場合は、そのアプリから、チームのすべての機能が有効になります。チームで最初の実行エクスペリエンスでは、ユーザーを選択し、好みのチャット (Microsoft チームまたは Skype for Business) の呼び出し元のアプリケーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2925c-p116">All capabilities in Teams, from private chat and calling, ad-hoc and scheduled meetings, and apps are enabled by default, allowing users to experiment and use the capabilities that suit their needs. A first-run experience in Teams guides users to pick their preferred chat and calling application (Microsoft Teams or Skype for Business).</span></span>

<span data-ttu-id="2925c-200">組織でチームなどの新しいツールの他のコントロールのリリースを要求、次のオプション見なすことができます管理のサイドバイ サイド インストール顧客歩は。</span><span class="sxs-lookup"><span data-stu-id="2925c-200">Should your organization require a more controlled release of new tools such as Teams, the following options can be considered for your managed side-by-side customer journey, they are:</span></span>

-   <span data-ttu-id="2925c-p117">パイロットおよびチームの共同作業のための展開します。[Skype for Business とチームがパイロット](pilot-essentials.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2925c-p117">Pilot and rollout of Teams for collaboration. See [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>

-   <span data-ttu-id="2925c-203">会議のチームの展開</span><span class="sxs-lookup"><span data-stu-id="2925c-203">Rollout of Teams for meetings</span></span>

-   <span data-ttu-id="2925c-204">通話のチームの展開</span><span class="sxs-lookup"><span data-stu-id="2925c-204">Rollout of Teams for calling</span></span>

### <a name="teams-pilot-and-rollout-for-collaboration"></a><span data-ttu-id="2925c-205">チームとのグループ作業の展開</span><span class="sxs-lookup"><span data-stu-id="2925c-205">Teams pilot and rollout for collaboration</span></span>

<span data-ttu-id="2925c-206">重要なは、Microsoft チームは Office 365 グループを強化し、常設チャットと Office 365 との統合中心に構築されました。</span><span class="sxs-lookup"><span data-stu-id="2925c-206">At its core, Microsoft Teams was built around persistent chat and integration with Office 365 by enhancing Office 365 Groups.</span></span>

<span data-ttu-id="2925c-207">既定では、対象の Office 365 サブスクリプション ライセンスを使用して組織内のユーザーがチームの有効なためパイロット グループの外部では、すべてのユーザーのチーム ライセンスを無効にする制限付きのチーム パイロットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2925c-207">Since by default users in your organization with an eligible Office 365 subscription license are enabled for Teams, a limited Teams pilot will involve disabling the Teams license for all users who are outside of the pilot group.</span></span>

<span data-ttu-id="2925c-p118">グループ作業とプライベート チャット ソリューションでは、名前を付けて、チームのリリースを対象とオーバー ラップする Skype for Business での機能が原因でユーザーが混乱を小さくために、Office 365 のテナント レベルで、次の設定を変更できます。これらの Office 365 の設定を変更するには、 [Office 365 の組織で Microsoft チームを設定する](Office-365-set-up.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2925c-p118">To focus the Teams release as a collaboration and private chat solution, and to reduce user confusion due to overlapping capabilities with Skype for Business, you can change the following settings at the Office 365 tenant level. To change these Office 365 settings, see [Set up Microsoft Teams in your Office 365 organization](Office-365-set-up.md).</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2925c-210">セクション</span><span class="sxs-lookup"><span data-stu-id="2925c-210">Section</span></span></th>
<th align="left"><span data-ttu-id="2925c-211">設定</span><span class="sxs-lookup"><span data-stu-id="2925c-211">Setting</span></span></th>
<th align="left"><span data-ttu-id="2925c-212">説明</span><span class="sxs-lookup"><span data-stu-id="2925c-212">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="2925c-213">通話と会議</strong></span><span class="sxs-lookup"><span data-stu-id="2925c-213">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="2925c-214">プライベート会議のスケジュールを設定できるようにする:<strong>オフ</strong></span><span class="sxs-lookup"><span data-stu-id="2925c-214">Allow scheduling for private meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="2925c-215">チャンネルの会議のスケジュールを設定できるようにする:<strong>オフ</strong></span><span class="sxs-lookup"><span data-stu-id="2925c-215">Allow scheduling for channel meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="2925c-216">プライベート通話を許可する:<strong>オフ</strong></span><span class="sxs-lookup"><span data-stu-id="2925c-216">Allow private calling: <strong>Off</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="2925c-217">この設定を無効にすると、ユーザーがプライベート会議のスケジュールができなくなります</span><span class="sxs-lookup"><span data-stu-id="2925c-217">Disabling this setting prevents users from scheduling private meetings</span></span></p><p><span data-ttu-id="2925c-218">この設定を無効にすると、ユーザーがチャンネルの会議のスケジューリングができなくなります</span><span class="sxs-lookup"><span data-stu-id="2925c-218">Disabling this setting prevents users from scheduling channel meetings</span></span></p><p><span data-ttu-id="2925c-219">この設定を無効にすると、ユーザーが (音声とビデオ) からプライベート発信することができなくなります</span><span class="sxs-lookup"><span data-stu-id="2925c-219">Disabling this setting prevents users from making private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="2925c-220">注</span><span class="sxs-lookup"><span data-stu-id="2925c-220">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="2925c-221">必要がありますを無効にする Business および Enterprise の両方のユーザーとゲスト ユーザーに個人的な呼び出す (ゲスト アクセスを組織に該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="2925c-221">You must disable Private Calling to both Business and Enterprise users, and Guest users (if Guest Access is applicable to your organization).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>



<span data-ttu-id="2925c-p119">この設定では、ユーザーを導入できますアドホック チャネル meetup] を使用する会議をチームで作業する方法の音声、ビデオ、および画面を最新のグループ作業機能の一部として共有を有効にします。エンドユーザーとチーム永続的なプラットフォーム間で、非公開チャット機能も便利です。</span><span class="sxs-lookup"><span data-stu-id="2925c-p119">With this configuration, users can be introduced to how meetings work in Teams by advocating the use of ad-hoc channel meetup, enabling the use of voice, video, and screen sharing as part of the modern collaboration experience. End users can also benefit from Teams persistent, cross-platform, private chat capabilities.</span></span>

<span data-ttu-id="2925c-224">組織全体のさまざまな展開ではにより、すべてのユーザーのライセンスをチームのグループ作業とプライベート チャットの成功チーム パイロット実行できます。</span><span class="sxs-lookup"><span data-stu-id="2925c-224">A successful Teams pilot for collaboration and private chat can be followed up with broad rollout throughout the organization by enabling Teams license for all users.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="2925c-225">注</span><span class="sxs-lookup"><span data-stu-id="2925c-225">Note</span></span></p></td>
<td align="left"><span data-ttu-id="2925c-226">試験運用、およびフェーズ 2 秘密チャットが有効な場合は、Skype for Business のユーザーとのチャット チームのユーザーを次の操作をことはできません。</span><span class="sxs-lookup"><span data-stu-id="2925c-226">During the pilot, and in phase two when private chat is enabled, a Teams user chatting with a Skype for Business user will not be able to do the following:</span></span><br><span data-ttu-id="2925c-227">
-チャット セッションからビデオ通話を開始します。</span><span class="sxs-lookup"><span data-stu-id="2925c-227">
- Start video call from a chat session</span></span><br><span data-ttu-id="2925c-228">
-ファイルを転送します。</span><span class="sxs-lookup"><span data-stu-id="2925c-228">
- Transfers files</span></span> <br><span data-ttu-id="2925c-229">
-チャット セッションからマルチパーティの通話を開始します。</span><span class="sxs-lookup"><span data-stu-id="2925c-229">
- Initiate a multiparty call from the chat session</span></span><br><span data-ttu-id="2925c-230">
-ユーザーは、デスクトップ共有セッションを開始することができません。</span><span class="sxs-lookup"><span data-stu-id="2925c-230">
- Users will not be able to start a desktop sharing session</span></span><br>

</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


### <a name="rollout-of-teams-for-meetings"></a><span data-ttu-id="2925c-231">会議のチームの展開</span><span class="sxs-lookup"><span data-stu-id="2925c-231">Rollout of Teams for meetings</span></span>

<span data-ttu-id="2925c-232">ユーザーは、マイクロソフトのチームを使用して共同作業に慣れて作業は、スケジュールされた会議が、組織内で有効にする次の機能と見なされますことができます。</span><span class="sxs-lookup"><span data-stu-id="2925c-232">As users are getting accustomed to collaborating using Microsoft Teams, scheduled meetings can be considered as the next capability to enable in the organization.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="2925c-233">注</span><span class="sxs-lookup"><span data-stu-id="2925c-233">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="2925c-234">スケジュールされた会議の開催者は、自分のメールボックスを Exchange Online の複数のテナント (または Exchange オンライン専用 vNext) が必要です。</span><span class="sxs-lookup"><span data-stu-id="2925c-234">The organizers of scheduled meetings must have their mailboxes in Exchange Online multi-tenant (or Exchange Online Dedicated vNext).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="2925c-235">テナント レベル、チームのスケジュールされた会議を有効にするのには、次の設定を構成でき、設定は、Business および Enterprise ユーザーのみに適用します。</span><span class="sxs-lookup"><span data-stu-id="2925c-235">The following settings can be configured at the tenant level to enable scheduled meetings in Teams, and the settings are applicable to Business and Enterprise users only.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2925c-236">セクション</span><span class="sxs-lookup"><span data-stu-id="2925c-236">Section</span></span></th>
<th align="left"><span data-ttu-id="2925c-237">設定</span><span class="sxs-lookup"><span data-stu-id="2925c-237">Setting</span></span></th>
<th align="left"><span data-ttu-id="2925c-238">説明</span><span class="sxs-lookup"><span data-stu-id="2925c-238">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="2925c-239">通話と会議</strong></span><span class="sxs-lookup"><span data-stu-id="2925c-239">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="2925c-240">プライベート会議のスケジュールを設定できるようにする: <strong>[</strong></span><span class="sxs-lookup"><span data-stu-id="2925c-240">Allow scheduling for private meetings: <strong>On</strong></span></span></p><p><span data-ttu-id="2925c-241">チャンネルの会議のスケジュールを設定できるようにする: <strong>[</strong></span><span class="sxs-lookup"><span data-stu-id="2925c-241">Allow scheduling for channel meetings: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="2925c-242">個人的な会議をスケジュールするユーザーは、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2925c-242">Enabling this setting allows users to schedule private meetings</span></span></p><p><span data-ttu-id="2925c-243">チャンネルの会議をスケジュールするユーザーは、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2925c-243">Enabling this setting allows users to schedule channel meetings</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2925c-p120">スケジュールされた会議チーム デスクトップ クライアントのブラウザーを使って整理することができますや会議を使用して、Microsoft Outlook でアドインの Microsoft チームします。チームでスケジュールされた会議を有効にすると、新しいチーム会議を作成またはチーム会議に既存の Skype for Business 会議を更新するユーザーを教育始めるをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2925c-p120">Scheduled meetings can be organized via the Teams desktop client, a browser, or via Microsoft Outlook using the meeting add-in for Microsoft Teams. Once scheduled meetings in Teams is enabled, we recommend you start educating users to create new Teams meetings or update existing Skype for Business meetings to Teams meetings.</span></span>

### <a name="rollout-of-teams-for-calling"></a><span data-ttu-id="2925c-246">通話のチームの展開</span><span class="sxs-lookup"><span data-stu-id="2925c-246">Rollout of Teams for calling</span></span>

<span data-ttu-id="2925c-p121">プライベート通話は、継続的を作成して、時間経過説得力のある代わりに提供 Skype for Business をチーム機能です。組織では、チームの個人的な通話機能が重要なビジネス要件を満たしていると見なされる、ときに、チームで非公開の呼び出しを有効にするテナント レベルで、次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="2925c-p121">Private calling is the Teams capability that will be continuously developed, and over time provide a compelling replacement to Skype for Business. When your organization considers that Teams private calling capabilities meet key business requirements, the following settings can be configured at the tenant level to enable private calling in Teams.</span></span> 

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2925c-249">セクション</span><span class="sxs-lookup"><span data-stu-id="2925c-249">Section</span></span></th>
<th align="left"><span data-ttu-id="2925c-250">設定</span><span class="sxs-lookup"><span data-stu-id="2925c-250">Setting</span></span></th>
<th align="left"><span data-ttu-id="2925c-251">説明</span><span class="sxs-lookup"><span data-stu-id="2925c-251">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="2925c-252">通話と会議</strong></span><span class="sxs-lookup"><span data-stu-id="2925c-252">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="2925c-253">プライベート通話を許可する: <strong>[</strong></span><span class="sxs-lookup"><span data-stu-id="2925c-253">Allow private calling: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="2925c-254">この設定を有効にすることができます (音声とビデオ) にプライベートの呼び出しを配置するには</span><span class="sxs-lookup"><span data-stu-id="2925c-254">Enabling this setting allows users to place private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="2925c-255">注</span><span class="sxs-lookup"><span data-stu-id="2925c-255">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="2925c-256">[プライベートでチャットを許可]: この設定を有効にするにより、ユーザーは、[プライベートで他のユーザーとチャットします。</span><span class="sxs-lookup"><span data-stu-id="2925c-256">Allow users to chat privately: Enabling this setting allows users to chat with other users privately.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>


<span data-ttu-id="2925c-257">この段階では、すべてのユーザーを優先呼び出しアプリとしてチームを選択するように指示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2925c-257">At this stage, all users must be instructed to choose Teams as the preferred calling app.</span></span>

<span data-ttu-id="2925c-258">プライベート通話の有効化、チームが現在 Skype for Business を提供しているすべての機能を提供し、ユーザーがチームは通信とコラボレーションの要件を満たすために使用を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="2925c-258">With the enablement of private calling, Teams will deliver all capabilities currently provided by Skype for Business, and users can start using Teams to fulfill their communications and collaboration requirements.</span></span>


<table>
<thead>
<tr class="header">
<td align="left"><p><img src="media/pilot_essentials_image2.png" /></p></td>
<td align="left">
<p><span data-ttu-id="2925c-259"><strong>に次の動作:</strong>1 回チームはアップし実行 - サイド バイ Skype for Business、[チームのユーザーの導入を使用してドライブの値](continue-journey.md)を使って、Skype for Business からチームへの旅を続行しながらです。</span><span class="sxs-lookup"><span data-stu-id="2925c-259"><strong>Next Action:</strong> Once Teams is up and running side-by-side with Skype for Business, [Drive Value through user adoption of Teams](continue-journey.md), while continuing your journey from Skype for Business to Teams.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>