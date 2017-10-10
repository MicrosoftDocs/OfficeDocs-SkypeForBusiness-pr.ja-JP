---
title: "Skype for Business と共存する Microsoft Teams を有効にする"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "共存する Skype for Business と Microsoft Teams の使用に関するガイダンス"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 760fa47db7965e0c2a74b01ae25f1d23d37d3180
ms.sourcegitcommit: 2592b268977460d0d483a75d741b1ce9fa8da908
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2017
---
<a name="enable-microsoft-teams-side-by-side-with-skype-for-business"></a><span data-ttu-id="374a3-103">Skype for Business と共存する Microsoft Teams を有効にする</span><span class="sxs-lookup"><span data-stu-id="374a3-103">Enable Microsoft Teams side-by-side with Skype for Business</span></span> 
=============================================================

<span data-ttu-id="374a3-104">既に Skype for Business Online が展開されている組織にとって、最近発表された Microsoft Teams は単独の通信/コラボレーション ソリューションとしての Teams の潜在力を評価する機会を提供するものです。同時に、組織は 2 つのソリューションのどちらを重視するか、環境においてそれらをどのように共存できるか、ということについて難しい判断をすることになります。</span><span class="sxs-lookup"><span data-stu-id="374a3-104">For organizations with existing deployments of Skype for Business Online, the recent introduction of Microsoft Teams presents an opportunity to evaluate the potential of Teams as a sole, communications and collaboration solution, and a challenge to tip the scale between the two solutions and how they can coexist in your environment.</span></span>

<span data-ttu-id="374a3-105">Teams が現在のビジネス要件を満たす場合は、組織における単一の通信/コラボレーション ソリューションとして Teams の導入を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="374a3-105">If Teams can meet your business requirements today, you can start adopting Teams to become your single communications and collaboration solution for your organization.</span></span>

<span data-ttu-id="374a3-106">既定では、Teams は資格あるすべてのテナントで有効になります。</span><span class="sxs-lookup"><span data-stu-id="374a3-106">Teams is enabled by default, on all eligible tenants.</span></span> <span data-ttu-id="374a3-107">したがって、Skype for Business と共存する形で Teams を管理する方法を決定し、ユーザーの期待に応える取り組みを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="374a3-107">Therefore, you need to decide on how to manage Teams side-by-side with Skype for Business, and continue to meet user expectations.</span></span>

<span data-ttu-id="374a3-108">通常、共存の環境ではカスタマーによる 2 つの導入方法があります。</span><span class="sxs-lookup"><span data-stu-id="374a3-108">In general, there are two major side-by-side customer journeys.</span></span> <span data-ttu-id="374a3-109">導入方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="374a3-109">They are:</span></span>

-   <span data-ttu-id="374a3-110">**オプション 1:** 管理下にない共存での導入</span><span class="sxs-lookup"><span data-stu-id="374a3-110">**Option 1:** Unmanaged side-by-side customer journey.</span></span>

    <span data-ttu-id="374a3-111">IT は共存のエクスペリエンスを積極的に制御しないため、ユーザーは好みのアプリを選択できます。</span><span class="sxs-lookup"><span data-stu-id="374a3-111">IT does not actively control the side-by-side experience, and users are empowered to make the choice of preferred app.</span></span>

-   <span data-ttu-id="374a3-112">**オプション 2:** 管理下にある共存での導入</span><span class="sxs-lookup"><span data-stu-id="374a3-112">**Option 2:** Managed side-by-side customer journey.</span></span>

    <span data-ttu-id="374a3-113">IT は、ユーザーに対して Team を段階的に紹介することで共存のエクスペリエンスを制御します。最初に Teams でのプライベート チャット、次に会議のエクスペリエンス、最後に通話のエクスペリエンスというように段階的に新しいチャットベースのコラボレーション ワークスペースを導入します。</span><span class="sxs-lookup"><span data-stu-id="374a3-113">IT controls the side-by-side experience, taking users through a journey of gradually introducing Teams to first introduce a new chat-based collaboration workspace with private chat, then meeting experiences, and finally the calling experiences in Teams.</span></span>

![](media/guidance_SkypeforBusiness_image1.png)

<a name="side-by-side-benefits-and-considerations"></a><span data-ttu-id="374a3-114">共存の利点と考慮事項</span><span class="sxs-lookup"><span data-stu-id="374a3-114">Side-by-side benefits and considerations</span></span>
----------------------------------------

<span data-ttu-id="374a3-115">それぞれの移行では、組織の概要に基づいて正しい移行パスを決定するために利点と考慮事項を評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="374a3-115">Each journey has benefits and considerations to evaluate when determining the right path forward based on your organization's profile.</span></span> <span data-ttu-id="374a3-116">次の表に、共存の環境におけるカスタマーによる移行について、非管理下と管理下の比較を示します。</span><span class="sxs-lookup"><span data-stu-id="374a3-116">The table below provides the comparisons between managed and unmanaged side-by-side customer journeys.</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="374a3-117">移行パス</span><span class="sxs-lookup"><span data-stu-id="374a3-117">Migration Paths</span></span></th>
<th align="left"><span data-ttu-id="374a3-118">管理下にない共存</span><span class="sxs-lookup"><span data-stu-id="374a3-118">Unmanaged Side-by-Side</span></span></th>
<th align="left"><span data-ttu-id="374a3-119">管理下にある共存</span><span class="sxs-lookup"><span data-stu-id="374a3-119">Managed Side-by-Side</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="374a3-120"><strong>組織概要</strong></span><span class="sxs-lookup"><span data-stu-id="374a3-120"><strong>Organization profile</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="374a3-121">通常、専用の IT リソースのない小規模の組織</span><span class="sxs-lookup"><span data-stu-id="374a3-121">Typically, smaller organizations with no dedicated IT resources</span></span></li>
<li><span data-ttu-id="374a3-122">IT は作業に適したツールの選択をユーザーの裁量にゆだねる</span><span class="sxs-lookup"><span data-stu-id="374a3-122">IT allows user discretion in selecting right tools for their work</span></span></li>
<li><span data-ttu-id="374a3-123">主な Skype for Business の使用法は IM/P と会議</span><span class="sxs-lookup"><span data-stu-id="374a3-123">Primary Skype for Business usage is IM/P and meetings</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="374a3-124">通常、中規模から大規模の組織</span><span class="sxs-lookup"><span data-stu-id="374a3-124">Typically, mid-size to larger organizations</span></span></li>
<li><span data-ttu-id="374a3-125">IT が新しいツールのロールアウトをより積極的に制御することを希望している</span><span class="sxs-lookup"><span data-stu-id="374a3-125">IT wants to control roll out of new tools more rigorously</span></span></li>
<li><span data-ttu-id="374a3-126">Skype for Business の導入を深める</span><span class="sxs-lookup"><span data-stu-id="374a3-126">Deeper adoption of Skype for Business today</span></span></li>
<li><span data-ttu-id="374a3-127">ネットワークとインフラストラクチャの複雑性の増加</span><span class="sxs-lookup"><span data-stu-id="374a3-127">Increased complexity in network and infrastructure</span></span></li>
<li><span data-ttu-id="374a3-128">複数の場所</span><span class="sxs-lookup"><span data-stu-id="374a3-128">Multiple locations</span></span></p>
<li><span data-ttu-id="374a3-129">独自の UC 機能を持つ単一アプリの選択</span><span class="sxs-lookup"><span data-stu-id="374a3-129">Preference for single app with unique UC capabilities</span></span></li></ul></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="374a3-130"><strong>利点</strong></span><span class="sxs-lookup"><span data-stu-id="374a3-130"><strong>Benefits</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="374a3-131">Skype for Business で利用できない Teams の機能を活用する</span><span class="sxs-lookup"><span data-stu-id="374a3-131">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="374a3-132">Office 365 内で機能強化された最新のワークプレース</span><span class="sxs-lookup"><span data-stu-id="374a3-132">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="374a3-133">ユーザーの柔軟性の向上</span><span class="sxs-lookup"><span data-stu-id="374a3-133">Increased user flexibility</span></span></li>
<li><span data-ttu-id="374a3-134">すべての機能を一度に有効化できる</span><span class="sxs-lookup"><span data-stu-id="374a3-134">Enable all capabilities at once</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="374a3-135">Skype for Business で利用できない Teams の機能を活用する</span><span class="sxs-lookup"><span data-stu-id="374a3-135">Leverage capabilities in Teams that are not available in Skype for Business</span></span></li>
<li><span data-ttu-id="374a3-136">Office 365 内で機能強化された最新のワークプレース</span><span class="sxs-lookup"><span data-stu-id="374a3-136">Enhanced modern workplace within Office 365</span></span></li>
<li><span data-ttu-id="374a3-137">ユーザーの生産性への影響を最小限に抑える</span><span class="sxs-lookup"><span data-stu-id="374a3-137">Minimize user productivity impact</span></span></li>
<li><span data-ttu-id="374a3-138">機能の重複を削減する</span><span class="sxs-lookup"><span data-stu-id="374a3-138">Reduce capability overlap</span></span></li>
<li><span data-ttu-id="374a3-139">UC シナリオにおける最適なツール選択</span><span class="sxs-lookup"><span data-stu-id="374a3-139">Streamline tool choice for UC scenarios</span></span></li>
<li><span data-ttu-id="374a3-140">組織で必要に応じて機能を有効化できるように IT およびビジネスを強化する</span><span class="sxs-lookup"><span data-stu-id="374a3-140">Empower IT and business to enable capabilities as appropriate in organization</span></span></li>
<li><span data-ttu-id="374a3-141">ユーザーのために変更のペースを制御する</span><span class="sxs-lookup"><span data-stu-id="374a3-141">Control the pace of change for users</span></span></li></ul></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="374a3-142"><strong>考慮事項</strong></span><span class="sxs-lookup"><span data-stu-id="374a3-142"><strong>Considerations</strong></span></span></td>
<td align="left"><ul>
<li><span data-ttu-id="374a3-143">同様の重複する機能を持つ複数のアプリ</span><span class="sxs-lookup"><span data-stu-id="374a3-143">Multiple apps with similar, overlapping capabilities</span></span></li>
<li><span data-ttu-id="374a3-144">サポート コールの増加、存在感のない IT、生産性への影響の増大といった問題につながるユーザーの困惑を引き起こす可能性の増加</span><span class="sxs-lookup"><span data-stu-id="374a3-144">Increased potential for user confusion which can lead to increased support calls, shadow IT, impacted productivity</span></span></li>
<li><span data-ttu-id="374a3-145">ネットワーク計画および監視では 2 つのサービスの使用を考慮する必要がある</span><span class="sxs-lookup"><span data-stu-id="374a3-145">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="374a3-146">即座に行う必要のある変更管理の取り組み (啓発、トレーニング、サポート) の増大</span><span class="sxs-lookup"><span data-stu-id="374a3-146">Increased and immediate change management efforts required: awareness, training, and support</span></span></li>
<li><span data-ttu-id="374a3-147">ユーザーがアプリ間の相互運用に関する制限に直面する可能性</span><span class="sxs-lookup"><span data-stu-id="374a3-147">Users may experience interoperability limitations between apps</span></span></li>
</ul></td>
<td align="left"><ul><li><span data-ttu-id="374a3-148">IT がライセンスからユーザー エクスペリエンスまで細かい制御を行うため、計画と実装において追加のサイクルが必要になる</span><span class="sxs-lookup"><span data-stu-id="374a3-148">IT has granular control, from licensing to user experiences, requiring additional cycles of planning and implementation</span></span></li>
<li><span data-ttu-id="374a3-149">Teams の選択機能を無効にするために必要なユーザーの指導とアクション</span><span class="sxs-lookup"><span data-stu-id="374a3-149">User education and action required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="374a3-150">Teams の選択機能を無効にするために必要な変更管理の取り組み</span><span class="sxs-lookup"><span data-stu-id="374a3-150">Change management efforts required to disable select capabilities in Teams</span></span></li>
<li><span data-ttu-id="374a3-151">ネットワーク計画および監視では 2 つのサービスの使用を考慮する必要がある</span><span class="sxs-lookup"><span data-stu-id="374a3-151">Network planning and monitoring must take usage of two services into consideration</span></span></li>
<li><span data-ttu-id="374a3-152">ユーザーがアプリ間の相互運用に関する制限に直面する可能性</span><span class="sxs-lookup"><span data-stu-id="374a3-152">Users may experience interoperability limitations between apps</span></span></li></ul></td>
</tr>
</tbody>
</table>


<a name="unmanaged-side-by-side-customer-journey"></a><span data-ttu-id="374a3-153">管理下にない共存での移行</span><span class="sxs-lookup"><span data-stu-id="374a3-153">Unmanaged side-by-side customer journey</span></span>
---------------------------------------


![](media/guidance_SkypeforBusiness_image4.png)

<span data-ttu-id="374a3-154">管理下にない共存での移行では、Teams はコラボレーション ソリューション (チャットベースのワークスペース、チャネル、アプリ、その他の Office 365 ワークロードとの統合など) として導入されます。この場合、デスクトップ コンピューター (PC または Mac) やモバイル デバイスでのクライアント ソフトウェアや Web クライアントを使用することになります。</span><span class="sxs-lookup"><span data-stu-id="374a3-154">In an unmanaged side-by-side customer journey, Teams is introduced as a collaboration solution (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.) that involves client software and web client on desktop computers (PC or Mac) and mobile devices.</span></span>


<span data-ttu-id="374a3-155">既定では、Teams にはプライベートのチャットと通話、予約済み会議など、Skype for Business と重複する機能も存在します。</span><span class="sxs-lookup"><span data-stu-id="374a3-155">By default, Teams also presents overlapping capabilities with Skype for Business, these include private chat and calling, and scheduled meetings.</span></span> <span data-ttu-id="374a3-156">これは、Teams が組織に完全な通信/コラボレーション ソリューションを提供するということであると同時に、Skype for Business にも同様な機能が存在することを意味します。</span><span class="sxs-lookup"><span data-stu-id="374a3-156">This means Teams ends up providing complete communications and collaboration for the organization, while at the same time Skype for Business provides similar capabilities.</span></span>

<span data-ttu-id="374a3-157">Teams は Skype for Business Online ユーザーとの相互運用性をサポートするため、ユーザーは Teams を起動するときに好みのチャット アプリや通話アプリを選択できます。</span><span class="sxs-lookup"><span data-stu-id="374a3-157">Teams supports interoperability with Skype for Business Online users, and users will be given an opportunity to choose their preferred chat and calling app when they launch Teams.</span></span> <span data-ttu-id="374a3-158">ユーザーが好みのアプリとして Teams を選択し、別のユーザーが Teams をインストールしておらず Skype for Business を好みのチャット/通話 アプリとして選択した場合でも、Teams に搭載される相互運用性を介してお互いにチャットや通話を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="374a3-158">If one user picks Teams as the preferred app, and another user hasn’t installed Teams or picked Skype for Business as the preferred chat and calling app, they can continue to chat and call each other through the interop capabilities that are part of Teams.</span></span>

<span data-ttu-id="374a3-159">Microsoft は相互運用のエクスペリエンスを継続的に向上させています。</span><span class="sxs-lookup"><span data-stu-id="374a3-159">Microsoft is continuously improving the interop experiences.</span></span> <span data-ttu-id="374a3-160">初期の段階では、相互運用のエクスペリエンスがユーザーの期待に応えていないケースが存在した可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="374a3-160">In the beginning, there may be some cases whereby the interop experiences are not meeting user expectations.</span></span> <span data-ttu-id="374a3-161">ユーザーは現在でも Skype for Business を利用できるため、Skype for Business に切り替えて Teams によって提供されていない機能を補完することができます。</span><span class="sxs-lookup"><span data-stu-id="374a3-161">Since Skype for Business is still available to users, they can switch to Skype for Business for the capabilities that currently cannot be served by Teams.</span></span>

<span data-ttu-id="374a3-162">重複するもう 1 つの機能に Teams の予約済み会議があります。この機能では、ユーザーは Teams 会議または Skype for Business 会議のいずれかを予約できます。</span><span class="sxs-lookup"><span data-stu-id="374a3-162">Scheduled meetings in Teams is another overlapping capability that lets users schedule Teams meetings, or Skype for Business meetings.</span></span> <span data-ttu-id="374a3-163">これらのソリューションにはそれぞれの利点がありますが、Teams の会議エクスペリエンスがビジネス要件に適合するもので、Skype for Business 会議の機能を超えるようになると、ユーザーは自然と Teams 会議に移行することが予測されます。</span><span class="sxs-lookup"><span data-stu-id="374a3-163">Each has its own advantages, and over time, when Teams meeting experience meets business requirements or surpasses the functionalities of Skype for Business meetings, we expect users to naturally switch to Teams meetings.</span></span>

<span data-ttu-id="374a3-164">管理下にない共存での移行では、相互運用の機能に関する問題に直面するユーザーからのサポート コールを処理するため、ヘルプデスク チームを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="374a3-164">In this unmanaged side-by-side customer journey, prepare your helpdesk team to handle support calls from users when facing issues with interop capabilities.</span></span> <span data-ttu-id="374a3-165">または、Teams 会議または Skype for Business 会議のどちらを優先すべきかユーザーにアドバイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="374a3-165">Or advise users when to choose Teams meetings over Skype for Business meetings, and vice versa.</span></span>

<span data-ttu-id="374a3-166">共存でのこの移行は組織規模で適用可能であり、ユーザーは管理下にない共存のエクスペリエンスの特質を受け入れる立場にあります。したがって、組織はユーザーの要件に合う最適な通信/コラボレーション ツールを選択することを率直に受け入れることになります。</span><span class="sxs-lookup"><span data-stu-id="374a3-166">This side-by-side customer journey may be applicable to your organization, whereby the users are more receptive to the nature of the unmanaged side-by-side experience, and the organization openly allows the users to pick the best communications and collaboration tools that suit their requirements.</span></span>

<a name="managed-side-by-side-customer-journey"></a><span data-ttu-id="374a3-167">管理下にある共存での移行</span><span class="sxs-lookup"><span data-stu-id="374a3-167">Managed side-by-side customer journey</span></span>
-------------------------------------

![](media/guidance_SkypeforBusiness_image2.png)

<span data-ttu-id="374a3-168">Teams の導入に対する制御を強めたい組織は、管理下にある共存での移行を開始します。</span><span class="sxs-lookup"><span data-stu-id="374a3-168">A managed side-by-side customer journey starts with organization wanting more control over how Teams is introduced.</span></span>

-   <span data-ttu-id="374a3-169">この移行の**最初のステップ**では、最新のコラボレーション要件 (チャットベースのワークスペース、チャネル、アプリ、その他の Office 365 ワークロードとの統合など) に範囲を絞った Teams の制限付きパイロットを実施します。</span><span class="sxs-lookup"><span data-stu-id="374a3-169">The **first step** of this journey is a limited pilot of Teams scoped to modern collaboration requirements (chat-based workspace, channels, apps, integration with other Office 365 workloads, etc.).</span></span> <span data-ttu-id="374a3-170">Teams で臨時のチャネル会議やプライベート チャットも有効にして、パイロット ユーザーに Teams 会議とプライベート チャットのエクスペリエンスを評価する機会を与えます。</span><span class="sxs-lookup"><span data-stu-id="374a3-170">Ad-hoc channel meetings and private chat in Teams is also enabled to provide a chance for pilot users to evaluate the Teams meetings experience and private chat experiences.</span></span> <span data-ttu-id="374a3-171">この段階では、Teams の予約済み会議とプライベート通話機能は無効にしておきます。</span><span class="sxs-lookup"><span data-stu-id="374a3-171">Scheduled meetings and private calling capabilities in Teams are disabled at this stage.</span></span> <span data-ttu-id="374a3-172">パイロットを開始するには、「[Pilot Teams with Skype for Business (Skype for Business と共存する Teams のパイロット)](pilot-essentials.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="374a3-172">To get started with a pilot, go to [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>
    
-   <span data-ttu-id="374a3-173">導入の **2 番目のステップ**では、組織全体でプライベート チャットによる最新のコラボレーションに向けて Teams のロールアウトを拡張します。</span><span class="sxs-lookup"><span data-stu-id="374a3-173">The **second step** of this journey is extending the rollout of Teams for modern collaboration with private chat throughout the organization.</span></span> <span data-ttu-id="374a3-174">Skype for Business 機能との重複を回避するため、Teams で予約済み会議とプライベート通話を継続して無効のままにします。</span><span class="sxs-lookup"><span data-stu-id="374a3-174">Scheduled meetings, and private calling continue to be disabled in Teams to reduce the overlap  with with Skype for Business capabilities.</span></span>

    <span data-ttu-id="374a3-175">この段階では、組織全体で優先するチャット アプリケーションを Teams または Skype for Business のいずれかに設定するかを考慮しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="374a3-175">At this stage, you may need to consider whether preferred chat application should be set to Teams or Skype for Business for the entire organization.</span></span>

    - <span data-ttu-id="374a3-176">Teams に設定する場合は、組織内の他の部門や組織全体で通信を行う場合に直面する相互運用の課題に初期の段階で対処できるようユーザーを指導する必要があります。</span><span class="sxs-lookup"><span data-stu-id="374a3-176">If set to Teams, prepare your users to handle early interoperability challenges when communicating with other parties within and across the organization.</span></span>
    
    - <span data-ttu-id="374a3-177">Skype for Business に設定する場合でも、Teams 内でのプライベート チャットは Teams 内で実行されます。エンドユーザーは Teams 内でそのチャット機能が備えるクロスプラットフォームの特長をすぐに活用できます。同時に、ユーザーは組織内または組織全体の Skype for Business ユーザー同士のプライベート チャットにこれまでどおり Skype for Business を使用できます。</span><span class="sxs-lookup"><span data-stu-id="374a3-177">If set to Skype for Business, private chats within Teams will remain in Teams, and end users can immediately take advantage of the cross-platform persistent nature of chat capabilities within Teams, and they will continue to use Skype for Business for private chats among Skype for Business users, within the organization and across the organization.</span></span>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="374a3-178">注意</span><span class="sxs-lookup"><span data-stu-id="374a3-178">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="374a3-179">現時点では、チャット アプリケーションの優先設定はクライアント レベルでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="374a3-179">Currently the preferred chat application setting is available only at the client level.</span></span> <span data-ttu-id="374a3-180">意図した組織全体にわたる構成を促進するためにユーザー トレーニングや導入キャンペーンを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="374a3-180">User training and adoption campaign will be required to drive the intended organization-wide configuration.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="374a3-181">管理下にある共存での移行の **3 番目のステップ**は、組織が Teams の会議エクスペリエンスと機能が組織のビジネス要件に適合すると判断した時点で開始します。</span><span class="sxs-lookup"><span data-stu-id="374a3-181">The **third step** of the managed side-by-side customer journey starts when the organization decides that Teams meeting experience and capabilities meet their business requirements.</span></span> <span data-ttu-id="374a3-182">Teams のプライベート会議とチャネル会議を有効にすると、ユーザーは Teams 会議と Skype for Business 会議の両方を予約することができるオプションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="374a3-182">By enabling private and channel meetings in Teams, users are presented with options to schedule both Teams meetings and Skype for Business meetings.</span></span> <span data-ttu-id="374a3-183">したがって、Teams の継続的な革新性を考慮すれば、時間の経過とともにユーザーは Teams 会議に移行することが予測されます。</span><span class="sxs-lookup"><span data-stu-id="374a3-183">Therefore, it is expected that over time users will naturally switch to Teams meetings given the continued innovations in Teams.</span></span> <span data-ttu-id="374a3-184">Skype for Business から Teams への使用の切り替えを円滑に促すために、Teams を使い始めるに際しての明瞭なガイダンスを利用して Teams がユーザーに提供する付加価値を説明する、トレーニング、サポート、コミュニケーションを含む強力な変更管理プログラムを実施します。</span><span class="sxs-lookup"><span data-stu-id="374a3-184">To be successful in steering usage from Skype for Business to Teams, implement a robust change management program inclusive of training, support and communications that explains the value-add that Teams offers to the user, with clear guidance on how to get started with Teams.</span></span> <span data-ttu-id="374a3-185">啓発キャンペーンの設計に役立つ [User Readiness (ユーザーの準備状況)](http://aka.ms/UserReadiness) リソースをご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="374a3-185">Leverage our [User Readiness](http://aka.ms/UserReadiness) resources to help design your awareness campaign.</span></span>


<span data-ttu-id="374a3-186">管理下にある共存での移行の **4 番目のステップ**では Teams の通話機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="374a3-186">The **fourth step** of the managed side-by-side customer journey begins with enabling calling in Teams.</span></span> <span data-ttu-id="374a3-187">このステップでは、シームレスな共存エクスペリエンスを確実にするために Teams の相互運用機能を重視します。</span><span class="sxs-lookup"><span data-stu-id="374a3-187">Teams interoperability capabilities will feature heavily in this step to ensure a seamless side-by-side experience.</span></span> <span data-ttu-id="374a3-188">プライベート通話に Teams を使用することを推進するには、Teams を既定の通信アプリとして設定することが理想的です。</span><span class="sxs-lookup"><span data-stu-id="374a3-188">Ideally, to enforce the use of Teams for private calling, Teams is set as the default calling app.</span></span> 

<span data-ttu-id="374a3-189">時間の経過とともに、通信およびコラボレーションの要件を満たすために、組織全体で Teams だけに依存するようになり、**5 番目のステップ**に進むことが予測されます。</span><span class="sxs-lookup"><span data-stu-id="374a3-189">Over time, potentially the whole organization can rely solely on Teams to meet communications and collaboration requirements and take the **fifth step**.</span></span> <span data-ttu-id="374a3-190">Teams に新機能が導入される時期については、「[Office 365 Roadmap (Office 365 ロードマップ)](http://aka.ms/TeamsRoadmap)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="374a3-190">To see when new features are coming in Teams, see the [Office 365 Roadmap](http://aka.ms/TeamsRoadmap).</span></span> 

<a name="managing-side-by-side-experience"></a><span data-ttu-id="374a3-191">共存エクスペリエンスの管理</span><span class="sxs-lookup"><span data-stu-id="374a3-191">Managing side-by-side experience</span></span>
--------------------------------

<span data-ttu-id="374a3-192">既定では、資格のある Office 365 サブスクリプションを保有している組織では、Microsoft Teams が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="374a3-192">By default, for organizations with eligible Office 365 subscriptions, Microsoft Teams is enabled.</span></span> <span data-ttu-id="374a3-193">組織が管理下にない共存での移行の条件に適合する場合は、現状を維持して Microsoft Teams の導入を自然な流れで促すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="374a3-193">If your organization fits the profile for unmanaged side-by-side customer journey, we highly recommend you keep it as-is to foster organic adoption of Microsoft Teams.</span></span>

<span data-ttu-id="374a3-194">Teams は、IT 管理権限が不要な最新の Web ブラウザー デスクトップ クライアント (インストール時。現時点では PC にのみ適用可能) やモバイル クライアントからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="374a3-194">Teams is accessible via modern Web browser desktop clients which require no IT administrative privilege (for installation, currently applicable to PC only) and mobile clients.</span></span>

<span data-ttu-id="374a3-195">プライベートなチャットや通話から、臨時会議や予約済み会議、およびアプリまで、Teams のすべての機能は既定で有効になります。そのため、ユーザーはニーズに合わせて機能を試したり使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="374a3-195">All capabilities in Teams, from private chat and calling, ad-hoc and scheduled meetings, and apps are enabled by default, allowing users to experiment and use the capabilities that suit their needs.</span></span> <span data-ttu-id="374a3-196">Teams の初回実行時のエクスペリエンスにより、ユーザーは好みのチャット/通話アプリケーション (Microsoft Teams または Skype for Business) を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="374a3-196">A first-run experience in Teams guides users to pick their preferred chat and calling application (Microsoft Teams or Skype for Business).</span></span>

<span data-ttu-id="374a3-197">Teams などの新しいツールのリリースを組織でより積極的に制御する場合は、管理下の共存での移行について次のオプションを考慮することができます。</span><span class="sxs-lookup"><span data-stu-id="374a3-197">Should your organization require a more controlled release of new tools such as Teams, the following options can be considered for your managed side-by-side customer journey, they are:</span></span>

-   <span data-ttu-id="374a3-198">コラボレーションに向けた Teams のパイロットおよびロールアウト</span><span class="sxs-lookup"><span data-stu-id="374a3-198">Pilot and rollout of Teams for collaboration.</span></span> <span data-ttu-id="374a3-199">「[Pilot Teams with Skype for Business (Skype for Business と共存する Teams のパイロット)](pilot-essentials.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="374a3-199">See [Pilot Teams with Skype for Business](pilot-essentials.md).</span></span>

-   <span data-ttu-id="374a3-200">会議に向けた Teams のロールアウト</span><span class="sxs-lookup"><span data-stu-id="374a3-200">Rollout of Teams for meetings</span></span>

-   <span data-ttu-id="374a3-201">通話に向けた Teams のロールアウト</span><span class="sxs-lookup"><span data-stu-id="374a3-201">Rollout of Teams for calling</span></span>

### <a name="teams-pilot-and-rollout-for-collaboration"></a><span data-ttu-id="374a3-202">コラボレーションに向けた Teams のパイロットとロールアウト</span><span class="sxs-lookup"><span data-stu-id="374a3-202">Teams pilot and rollout for collaboration</span></span>

<span data-ttu-id="374a3-203">Microsoft Teams は、Office 365 グループの機能強化を通して、Office 365 との統合と常設チャットを基礎として構築されています。</span><span class="sxs-lookup"><span data-stu-id="374a3-203">At its core, Microsoft Teams was built around persistent chat and integration with Office 365 by enhancing Office 365 Groups.</span></span>

<span data-ttu-id="374a3-204">既定では、資格のある Office 365 サブスクリプション ライセンスを有する組織内のユーザーは Teams に対して有効になるため、制限付きの Teams パイロットはパイロット グループ外のすべてのユーザーの Teams ライセンスを無効にすることに関係します。</span><span class="sxs-lookup"><span data-stu-id="374a3-204">Since by default users in your organization with an eligible Office 365 subscription license are enabled for Teams, a limited Teams pilot will involve disabling the Teams license for all users who are outside of the pilot group.</span></span>

<span data-ttu-id="374a3-205">コラボレーションとプライベート チャットのソリューションとしての Teams のリリースに焦点をあてて、Skype for Business と機能が重複していることによるユーザーの混乱を軽減するには、Office 365 テナント レベルで次の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="374a3-205">To focus the Teams release as a collaboration and private chat solution, and to reduce user confusion due to overlapping capabilities with Skype for Business, you can change the following settings at the Office 365 tenant level.</span></span> <span data-ttu-id="374a3-206">Office 365 設定を変更するには、「[Office 365 を使用する組織で Microsoft Teams をセットアップする](Office-365-set-up.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="374a3-206">To change these Office 365 settings, see [Set up Microsoft Teams in your Office 365 organization](Office-365-set-up.md).</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="374a3-207">セクション</span><span class="sxs-lookup"><span data-stu-id="374a3-207">Section Heading</span></span></th>
<th align="left"><span data-ttu-id="374a3-208">設定</span><span class="sxs-lookup"><span data-stu-id="374a3-208">Setting</span></span></th>
<th align="left"><span data-ttu-id="374a3-209">説明</span><span class="sxs-lookup"><span data-stu-id="374a3-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="374a3-210">通話と会議</strong></span><span class="sxs-lookup"><span data-stu-id="374a3-210">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="374a3-211">プライベート会議の予約を許可する: <strong>オフ</strong></span><span class="sxs-lookup"><span data-stu-id="374a3-211">Allow scheduling for private meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="374a3-212">チャネル会議の予約を許可する: <strong>オフ</strong></span><span class="sxs-lookup"><span data-stu-id="374a3-212">Allow scheduling for channel meetings: <strong>Off</strong></span></span></p><p><span data-ttu-id="374a3-213">プライベート通話を許可: <strong>オフ</strong></span><span class="sxs-lookup"><span data-stu-id="374a3-213">Allow private calling: <strong>Off</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="374a3-214">この設定を無効にすると、ユーザーはプライベート会議を予約できなくなります。</span><span class="sxs-lookup"><span data-stu-id="374a3-214">Disabling this setting prevents users from scheduling private meetings</span></span></p><p><span data-ttu-id="374a3-215">この設定を無効にすると、ユーザーはチャネル会議を予約できなくなります。</span><span class="sxs-lookup"><span data-stu-id="374a3-215">Disabling this setting prevents users from scheduling channel meetings</span></span></p><p><span data-ttu-id="374a3-216">この設定を無効にすると、ユーザーはプライベート通話 (音声およびビデオ) を行うことができなくなります。</span><span class="sxs-lookup"><span data-stu-id="374a3-216">Disabling this setting prevents users from making private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>


<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="374a3-217">注意</span><span class="sxs-lookup"><span data-stu-id="374a3-217">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="374a3-218">Business ユーザーと Enterprise ユーザーの両方でプライベート通話を無効にする必要があります。組織でゲスト アクセスが適用可能な場合はゲスト ユーザーのプライベート通話も無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="374a3-218">You must disable Private Calling to both Business and Enterprise users, and Guest users (if Guest Access is applicable to your organization).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>



<span data-ttu-id="374a3-219">この構成では、最新のコラボレーション エクスペリエンスの一部として、臨時のチャネル会議の使用を促進し、音声、ビデオ、画面共有の使用を有効にすることで、Teams の会議の仕組みをユーザーに紹介することができます。</span><span class="sxs-lookup"><span data-stu-id="374a3-219">With this configuration, users can be introduced to how meetings work in Teams by advocating the use of ad-hoc channel meetup, enabling the use of voice, video, and screen sharing as part of the modern collaboration experience.</span></span> <span data-ttu-id="374a3-220">エンドユーザーは Teams のクロスプラットフォームの常設プライベート チャット機能も利用できます。</span><span class="sxs-lookup"><span data-stu-id="374a3-220">End users can also benefit from Teams persistent, cross-platform, private chat capabilities.</span></span>

<span data-ttu-id="374a3-221">コラボレーションおよびプライベート チャットに向けた Teams のパイロットが成功したら、その次にすべてのユーザーに対して Teams ライセンスを有効にして組織全体で広範なロールアウトを実施できます。</span><span class="sxs-lookup"><span data-stu-id="374a3-221">A successful Teams pilot for collaboration and private chat can be followed up with broad rollout throughout the organization by enabling Teams license for all users.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="374a3-222">注意</span><span class="sxs-lookup"><span data-stu-id="374a3-222">Note</span></span></p></td>
<td align="left"><span data-ttu-id="374a3-223">パイロットの実施時、およびプライベート チャットが有効な段階 2 では、Skype for Business ユーザーとの Teams ユーザーのチャットで次の操作を行うことができません。</span><span class="sxs-lookup"><span data-stu-id="374a3-223">During the pilot, and in phase two when private chat is enabled, a Teams user chatting with a Skype for Business user will not be able to do the following:</span></span><br><span data-ttu-id="374a3-224">
- チャット セッションからビデオ通話を開始する</span><span class="sxs-lookup"><span data-stu-id="374a3-224">
- Start video call from a chat session</span></span><br><span data-ttu-id="374a3-225">
- ファイルを転送する</span><span class="sxs-lookup"><span data-stu-id="374a3-225">
- Transfers files</span></span> <br><span data-ttu-id="374a3-226">
- チャット セッションから複数パーティ間の通話を開始する</span><span class="sxs-lookup"><span data-stu-id="374a3-226">
- Initiate a multiparty call from the chat session</span></span><br><span data-ttu-id="374a3-227">
- ユーザーはデスクトップ共有セッションを開始できない</span><span class="sxs-lookup"><span data-stu-id="374a3-227">
- Users will not be able to start a desktop sharing session</span></span><br>

</td>
</tr>
</thead>
<tbody>
</tbody>
</table>


### <a name="rollout-of-teams-for-meetings"></a><span data-ttu-id="374a3-228">会議に向けた Teams のロールアウト</span><span class="sxs-lookup"><span data-stu-id="374a3-228">Rollout of Teams for meetings</span></span>

<span data-ttu-id="374a3-229">ユーザーが Microsoft Teams を使用したコラボレーションに慣れてきたら、次に有効にする機能として予約済み会議を検討します。</span><span class="sxs-lookup"><span data-stu-id="374a3-229">As users are getting accustomed to collaborating using Microsoft Teams, scheduled meetings can be considered as the next capability to enable in the organization.</span></span>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="374a3-230">注意</span><span class="sxs-lookup"><span data-stu-id="374a3-230">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="374a3-231">予約済み会議の開催者には、Exchange Online マルチテナント (または Exchange Online 専用 vNext) でのメールボックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="374a3-231">The organizers of scheduled meetings must have their mailboxes in Exchange Online multi-tenant (or Exchange Online Dedicated vNext).</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>

<span data-ttu-id="374a3-232">テナントレベルで次の設定を構成して、Teams で予約済み会議を有効にします。これらの設定は Business および Enterprise ユーザーにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="374a3-232">The following settings can be configured at the tenant level to enable scheduled meetings in Teams, and the settings are applicable to Business and Enterprise users only.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="374a3-233">セクション</span><span class="sxs-lookup"><span data-stu-id="374a3-233">Section Heading</span></span></th>
<th align="left"><span data-ttu-id="374a3-234">設定</span><span class="sxs-lookup"><span data-stu-id="374a3-234">Setting</span></span></th>
<th align="left"><span data-ttu-id="374a3-235">説明</span><span class="sxs-lookup"><span data-stu-id="374a3-235">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="374a3-236">通話と会議</strong></span><span class="sxs-lookup"><span data-stu-id="374a3-236">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="374a3-237">プライベート会議の予約を許可する: <strong>オン</strong></span><span class="sxs-lookup"><span data-stu-id="374a3-237">Allow scheduling for private meetings: <strong>On</strong></span></span></p><p><span data-ttu-id="374a3-238">チャネル会議の予約を許可する: <strong>オン</strong></span><span class="sxs-lookup"><span data-stu-id="374a3-238">Allow scheduling for channel meetings: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="374a3-239">この設定を有効にすると、ユーザーはプライベート会議を予約できようになります。</span><span class="sxs-lookup"><span data-stu-id="374a3-239">Enabling this setting allows users to schedule private meetings</span></span></p><p><span data-ttu-id="374a3-240">この設定を有効にすると、ユーザーはチャネル会議を予約できるようになります。</span><span class="sxs-lookup"><span data-stu-id="374a3-240">Enabling this setting allows users to schedule channel meetings</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="374a3-241">予約済み会議は、Teams デスクトップ クライアントやブラウザー、または Microsoft Teams の会議アドインを使用した Microsoft Outlook で開催できます。</span><span class="sxs-lookup"><span data-stu-id="374a3-241">Scheduled meetings can be organized via the Teams desktop client, a browser, or via Microsoft Outlook using the meeting add-in for Microsoft Teams.</span></span> <span data-ttu-id="374a3-242">Teams で予約済み会議を有効にすると同時に、ユーザーに対して新しい Teams 会議の作成、既存の Skype for Business から Teams 会議への更新についての指導を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="374a3-242">Once scheduled meetings in Teams is enabled, we recommend you start educating users to create new Teams meetings or update existing Skype for Business meetings to Teams meetings.</span></span>

### <a name="rollout-of-teams-for-calling"></a><span data-ttu-id="374a3-243">通話に向けた Teams のロールアウト</span><span class="sxs-lookup"><span data-stu-id="374a3-243">Rollout of Teams for calling</span></span>

<span data-ttu-id="374a3-244">Teams のプライベート通話の機能は、Skype for Business に取って代わる強力な機能として継続して開発されます。</span><span class="sxs-lookup"><span data-stu-id="374a3-244">Private calling is the Teams capability that will be continuously developed, and over time provide a compelling replacement to Skype for Business.</span></span> <span data-ttu-id="374a3-245">Teams のプライベート通話機能が主要なビジネス要件に適合すると組織が判断した場合は、Teams のプライベート通話を有効にするために次の設定をテナントレベルで構成することができます。</span><span class="sxs-lookup"><span data-stu-id="374a3-245">When your organization considers that Teams private calling capabilities meet key business requirements, the following settings can be configured at the tenant level to enable private calling in Teams.</span></span> 

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="374a3-246">セクション</span><span class="sxs-lookup"><span data-stu-id="374a3-246">Section Heading</span></span></th>
<th align="left"><span data-ttu-id="374a3-247">設定</span><span class="sxs-lookup"><span data-stu-id="374a3-247">Setting</span></span></th>
<th align="left"><span data-ttu-id="374a3-248">説明</span><span class="sxs-lookup"><span data-stu-id="374a3-248">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><strong><br><span data-ttu-id="374a3-249">通話と会議</strong></span><span class="sxs-lookup"><span data-stu-id="374a3-249">Calls and meetings</strong></span></span></td>
<td align="left"><p><span data-ttu-id="374a3-250">Allow private calling (プライベート通話を許可): <strong>オン</strong></span><span class="sxs-lookup"><span data-stu-id="374a3-250">Allow private calling: <strong>On</strong></span></span></p></td>
<td align="left"><p><span data-ttu-id="374a3-251">この設定を有効にすると、ユーザーはプライベート通話 (音声およびビデオ) を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="374a3-251">Enabling this setting allows users to place private calls (audio and video)</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="center"><p><img src="media/guidance_SkypeforBusiness_image3.png" /></p>
<p><span data-ttu-id="374a3-252">注意</span><span class="sxs-lookup"><span data-stu-id="374a3-252">Note</span></span></p></td>
<td align="left"><br><br><span data-ttu-id="374a3-253">Allow users to chat privately (ユーザーがプライベートでチャットすることを許可する): この設定を有効にすると、ユーザーは他のユーザーとプライベートでチャットすることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="374a3-253">Allow users to chat privately: Enabling this setting allows users to chat with other users privately.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>


<span data-ttu-id="374a3-254">この段階では、優先する通話アプリとして Teams を選択するようにすべてのユーザーに指導します。</span><span class="sxs-lookup"><span data-stu-id="374a3-254">At this stage, all users must be instructed to choose Teams as the preferred calling app.</span></span>

<span data-ttu-id="374a3-255">プライベート通話を有効にすることで、Skype for Business が提供するすべての機能が Teams で利用可能になり、ユーザーは通信とコラボレーションの要件を完全に満たすソリューションとして Teams の使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="374a3-255">With the enablement of private calling, Teams will deliver all capabilities currently provided by Skype for Business, and users can start using Teams to fulfill their communications and collaboration requirements.</span></span>


<table>
<thead>
<tr class="header">
<td align="left"><p><img src="media/pilot_essentials_image2.png" /></p></td>
<td align="left">
<p><span data-ttu-id="374a3-256"><strong>次のアクション:</strong> Skype for Business と共存する Teams を稼動状態にしたら、[ユーザーによる Teams の導入を介してその価値を創出](continue-journey.md)すると同時に Skype for Business から Teams への移行を継続的に実施します。</span><span class="sxs-lookup"><span data-stu-id="374a3-256"><strong>Next Action:</strong> Once Teams is up and running side-by-side with Skype for Business, [Drive Value through user adoption of Teams](continue-journey.md), while continuing your journey from Skype for Business to Teams.</span></span></td>
</tr>
</thead>
<tbody>
</tbody>
</table>