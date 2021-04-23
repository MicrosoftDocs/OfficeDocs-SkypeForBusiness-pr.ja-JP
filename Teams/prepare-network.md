---
title: Teams 用に組織のネットワークを準備する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: ネットワーク要件、ネットワーク最適化、帯域幅要件など、Microsoft Teams 用に組織のネットワークを準備する方法について説明します。
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 0bde5b2fac365369fea385a325cbd1d0d05cca07
ms.sourcegitcommit: 8750f98d59e74e3835d762d510fb0e038c8f17eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899088"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="c7845-103">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="c7845-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="c7845-104">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="c7845-104">Network requirements</span></span>

<span data-ttu-id="c7845-105">既に[ネットワークを Microsoft 365 または Office 365 用に最適化](/Office365/Enterprise/assessing-network-connectivity)している場合は、Microsoft Teams の準備ができている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7845-105">If you've already [optimized your network for Microsoft 365 or Office 365](/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="c7845-106">いずれの場合でも、特に **リモート ワーカー** をサポートする最初の Microsoft 365 または Office 365 ワークロードとして Teams を迅速に展開する場合は、Teams の展開を開始する前に次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c7845-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="c7845-107">(Microsoft 365 または Office 365 に接続できるように) すべての場所にインターネット アクセスがありますか?</span><span class="sxs-lookup"><span data-stu-id="c7845-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="c7845-108">少なくとも、通常の Web トラフィックに加えて、すべての場所で、Teams のメディア用に以下を開いていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c7845-108">At a minimum, in addition to normal web traffic, make sure you've opened the following, for all locations, for media in Teams:</span></span>

    |  |  |
    |---------|---------|
    |<span data-ttu-id="c7845-109">ポート</span><span class="sxs-lookup"><span data-stu-id="c7845-109">Ports</span></span>     |<span data-ttu-id="c7845-110">UDP ポート <strong>3478</strong> から <strong>3481</strong></span><span class="sxs-lookup"><span data-stu-id="c7845-110">UDP ports <strong>3478</strong> through <strong>3481</strong></span></span>        |
    |[<span data-ttu-id="c7845-111">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c7845-111">IP addresses</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<span data-ttu-id="c7845-112"><strong>13.107.64.0/18</strong>、<strong>52.112.0.0/14</strong>、および <strong>52.120.0.0/14</strong></span><span class="sxs-lookup"><span data-stu-id="c7845-112"><strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>, and <strong>52.120.0.0/14</strong></span></span>         |

    > [!IMPORTANT]
    > <span data-ttu-id="c7845-113">オンプレミスまたはオンラインのいずれかで Skype for Business と連携する必要がある場合は、追加の DNS レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7845-113">If you need to federate with Skype for Business, either on-premises or online, you will need to configure an additional DNS record.</span></span>
    >
    >|<span data-ttu-id="c7845-114">DNS レコード</span><span class="sxs-lookup"><span data-stu-id="c7845-114">DNS record</span></span>  |<span data-ttu-id="c7845-115">サービス</span><span class="sxs-lookup"><span data-stu-id="c7845-115">Service</span></span>  |<span data-ttu-id="c7845-116">Protocol</span><span class="sxs-lookup"><span data-stu-id="c7845-116">Protocol</span></span>  |<span data-ttu-id="c7845-117">Priority</span><span class="sxs-lookup"><span data-stu-id="c7845-117">Priority</span></span>  |<span data-ttu-id="c7845-118">Weight</span><span class="sxs-lookup"><span data-stu-id="c7845-118">Weight</span></span>  |<span data-ttu-id="c7845-119">Port</span><span class="sxs-lookup"><span data-stu-id="c7845-119">Port</span></span>  |<span data-ttu-id="c7845-120">Target</span><span class="sxs-lookup"><span data-stu-id="c7845-120">Target</span></span>  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|<span data-ttu-id="c7845-121">SRV</span><span class="sxs-lookup"><span data-stu-id="c7845-121">SRV</span></span>     |<span data-ttu-id="c7845-122">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="c7845-122">sipfederationtls</span></span>     |<span data-ttu-id="c7845-123">TCP</span><span class="sxs-lookup"><span data-stu-id="c7845-123">TCP</span></span>     |<span data-ttu-id="c7845-124">100</span><span class="sxs-lookup"><span data-stu-id="c7845-124">100</span></span>     |<span data-ttu-id="c7845-125">1</span><span class="sxs-lookup"><span data-stu-id="c7845-125">1</span></span>     |<span data-ttu-id="c7845-126">5061</span><span class="sxs-lookup"><span data-stu-id="c7845-126">5061</span></span>     |<span data-ttu-id="c7845-127">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c7845-127">sipfed.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="c7845-128">Microsoft 365 または Office 365 の検証済みドメイン (たとえば、contoso.com) はありますか?</span><span class="sxs-lookup"><span data-stu-id="c7845-128">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="c7845-129">組織が Microsoft 365 または Office 365 を展開していない場合は、「[概要](/microsoft-365/admin/admin-overview/get-started-with-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7845-129">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="c7845-130">組織が Microsoft 365 または Office 365 の検証済みドメインを追加または構成していない場合は、「[ドメインに関する FAQ](/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7845-130">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="c7845-131">組織は Exchange Online と SharePoint Online を展開していますか?</span><span class="sxs-lookup"><span data-stu-id="c7845-131">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="c7845-132">組織で Exchange Online が導入されていない場合は、「[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c7845-132">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="c7845-133">組織で SharePoint Online が導入されていない場合は、「[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c7845-133">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="c7845-134">これらのネットワーク要件を満たしていることを確認したら、[Teams を展開する](./deploy-overview.md)準備ができている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7845-134">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](./deploy-overview.md).</span></span> <span data-ttu-id="c7845-135">大規模な多国籍企業の場合、またはネットワークに制限があることがわかっている場合は、Teams 用にネットワークを評価し最適化する方法をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="c7845-135">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7845-136">**教育機関の場合**: 組織が教育機関であり、学生情報システム (SIS) を使用している場合は、Teams を展開する前に [学校データ同期を展開](/schooldatasync/)します。</span><span class="sxs-lookup"><span data-stu-id="c7845-136">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="c7845-137">**オンプレミスの Skypefor Business Server の実行**: 組織でオンプレミスの Skype for Business Server (または Lync Server) を実行している場合、オンプレミスのディレクトリと Microsoft 365 または Office 365 を同期するよう [Azure AD Connect を構成](/skypeforbusiness/hybrid/configure-azure-ad-connect)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7845-137">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="c7845-138">ベスト プラクティス: CQD と通話分析を使用してネットワークを監視する</span><span class="sxs-lookup"><span data-stu-id="c7845-138">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="c7845-139">[通話品質ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md) を使用して、Teams 内の通話と会議の品質に関する分析情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="c7845-139">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="c7845-140">CQD は、品質、信頼性、およびユーザー エクスペリエンスを注意深く監視して、ネットワークを最適化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c7845-140">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="c7845-141">CQD は、全体的なパターンが明らかになる可能性のある組織全体の集約テレメトリを調べます。これにより、問題を特定し、修復を計画できます。</span><span class="sxs-lookup"><span data-stu-id="c7845-141">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="c7845-142">さらに、CQD は、全体的な品質、信頼性、およびユーザー エクスペリエンスに関する分析情報を提供する豊富なメトリックス レポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c7845-142">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="c7845-143">[通話分析](set-up-call-analytics.md)を使用して、個々のユーザーの通話と会議の問題を調査します。</span><span class="sxs-lookup"><span data-stu-id="c7845-143">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="c7845-144">ネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="c7845-144">Network optimization</span></span>

<span data-ttu-id="c7845-145">特に、中小企業で、Microsoft 365 または Office 365 を既に展開している場合などは、次のタスクはオプションであり、Teams の展開に必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c7845-145">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="c7845-146">ネットワークに制限があることがわかっている場合など、ネットワークと Teams のパフォーマンスを最適化するのに、このガイダンスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="c7845-146">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="c7845-147">次の場合は、追加のネットワーク最適化を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7845-147">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="c7845-148">Teams の実行速度が遅い (帯域幅が不足している可能性があります)</span><span class="sxs-lookup"><span data-stu-id="c7845-148">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="c7845-149">通話が途切れ続ける (ファイアウォールまたはプロキシ ブロッカーが原因である可能性があります)</span><span class="sxs-lookup"><span data-stu-id="c7845-149">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="c7845-150">通話が静的で途切れている、または音声がロボットのように聞こえる (ジッターまたはパケット損失の可能性があります)</span><span class="sxs-lookup"><span data-stu-id="c7845-150">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="c7845-151">ネットワーク障害を特定して修正するためのガイダンスを含む、ネットワーク最適化の詳細については、「[Microsoft 365 および Office 365 ネットワーク接続の原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="c7845-151">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="c7845-152">ネットワークの最適化タスク</span><span class="sxs-lookup"><span data-stu-id="c7845-152">Network optimization task</span></span></th>
<th><span data-ttu-id="c7845-153">詳細</span><span class="sxs-lookup"><span data-stu-id="c7845-153">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c7845-154">ネットワーク プランナー</span><span class="sxs-lookup"><span data-stu-id="c7845-154">Network planner</span></span></td>
<td><p><span data-ttu-id="c7845-155">組織の物理的な場所全体の帯域幅の計算やネットワーク要件など、ネットワークの評価については、<a href="https://admin.teams.microsoft.com">Teams 管理センター</a>の <a href="/microsoftteams/network-planner">ネットワーク プランナー</a> ツールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c7845-155">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="c7845-156">ネットワークの詳細と Teams の使用状況を提示すると、Network Planner は、組織の物理的な場所で Teams とクラウドの音声を展開するためのネットワーク要件を計算します。</span><span class="sxs-lookup"><span data-stu-id="c7845-156">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="c7845-157">シナリオの例については、「<a href="/microsoftteams/tutorial-network-planner-example">ネットワーク プランナーの使用 - シナリオの例</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7845-157">For an example scenario, see <a href="/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c7845-158">Teams のアドバイザー</span><span class="sxs-lookup"><span data-stu-id="c7845-158">Advisor for Teams</span></span></td>
<td><span data-ttu-id="c7845-159"><a href="/microsoftteams/use-advisor-teams-roll-out">Teams のアドバイザー</a>は、<a href="https://admin.teams.microsoft.com">Teams 管理センター</a>の一部です。</span><span class="sxs-lookup"><span data-stu-id="c7845-159"><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="c7845-160">Microsoft 365 または Office 365 の環境を評価し、Teams を正常に展開する前に更新または変更する必要がある最も一般的な構成を特定します。</span><span class="sxs-lookup"><span data-stu-id="c7845-160">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c7845-161">外部の名前解決</span><span class="sxs-lookup"><span data-stu-id="c7845-161">External Name Resolution</span></span></td>
<td><span data-ttu-id="c7845-162">Teams クライアントを実行するすべてのコンピュータが外部 DNS クエリを解決して、Microsoft 365 または Office 365 によって提供されるサービスを検出できること、およびファイアウォールが接続を妨げていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c7845-162">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="c7845-163">ファイアウォールのポートの構成については、「<a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 および Office 365 の URL と IP 範囲</a>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c7845-163">For information about configuring firewall ports, go to <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c7845-164">セッションの永続性を維持する</span><span class="sxs-lookup"><span data-stu-id="c7845-164">Maintain session persistence</span></span></td>
<td><span data-ttu-id="c7845-165">ファイアウォールが、UDP のマップされたネットワーク アドレス変換 (NAT) アドレスまたはポートを変更しないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c7845-165">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="c7845-166">NAT プール サイズの検証</span><span class="sxs-lookup"><span data-stu-id="c7845-166">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="c7845-167">ユーザー接続に必要なネットワーク アドレス変換 (NAT) プール サイズを検証します。</span><span class="sxs-lookup"><span data-stu-id="c7845-167">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="c7845-168">複数のユーザーまたはデバイスが<a href="/office365/enterprise/nat-support-with-office-365">ネットワーク アドレス変換 (NAT) またはポート アドレス変換 (PAT)</a> を使用して Microsoft 365 または Office 365 にアクセスする場合は、パブリック ルーティングに対応している各 IP アドレスの背後にあるデバイスが、サポートされる数値を超過していないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7845-168">When multiple users and devices access Microsoft 365 or Office 365 using <a href="/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="c7845-169">適切なパブリック IP アドレスを NAT プールに割り当ててポート枯渇を回避します。</span><span class="sxs-lookup"><span data-stu-id="c7845-169">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="c7845-170">ポート枯渇は、内部ユーザーとデバイスが Microsoft 365 または Office 365 サービスに接続できない原因になります。</span><span class="sxs-lookup"><span data-stu-id="c7845-170">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c7845-171">Microsoft データ センターへのルーティング</span><span class="sxs-lookup"><span data-stu-id="c7845-171">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="c7845-172"><a href="/office365/enterprise/client-connectivity">Microsoft データ センターへの最も効率的なルーティングを実装します</a>。</span><span class="sxs-lookup"><span data-stu-id="c7845-172"><a href="/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="c7845-173">ローカルまたは地域の出力ポイントを使用して、Microsoft ネットワークにできるだけ効率的に接続できる場所を特定します。</span><span class="sxs-lookup"><span data-stu-id="c7845-173">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c7845-174">侵入検知/防御のガイダンス</span><span class="sxs-lookup"><span data-stu-id="c7845-174">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="c7845-175">送信接続の追加のセキュリティ レイヤーとして環境に<a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">侵入検知</a>/防御システム (IDS/IPS) が配備されている場合は、すべての Microsoft 365 または Office 365 の URL を許可していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c7845-175">If your environment has an <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c7845-176">スプリット トンネル VPN の構成</span><span class="sxs-lookup"><span data-stu-id="c7845-176">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="c7845-177">一般に<a href="/windows/security/identity-protection/vpn/vpn-routing">スプリット トンネル VPN</a> と呼ばれる、仮想プライベート ネットワーク (VPN) をバイパスする Teams トラフィックの代替パスを提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7845-177">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="c7845-178">スプリット トンネリングとは、Microsoft 365 または Office 365 のトラフィックが VPN を通過せず、代わりに Microsoft 365 または Office 365 に直接送信されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="c7845-178">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="c7845-179">VPN をバイパスすると、Teams の品質にプラスの影響があり、VPN デバイスと組織のネットワークからの負荷が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="c7845-179">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="c7845-180">スプリット トンネル VPN を実装するには、VPN ベンダーにご相談ください。</span><span class="sxs-lookup"><span data-stu-id="c7845-180">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="c7845-181">VPN をバイパスすることをお勧めするその他の理由:</span><span class="sxs-lookup"><span data-stu-id="c7845-181">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="c7845-182">VPN は通常、リアルタイム メディアをサポートするように設計または構成されていません。</span><span class="sxs-lookup"><span data-stu-id="c7845-182">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="c7845-183">一部の VPN は、UDP (Teams に必要) をサポートしていない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c7845-183">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="c7845-184">また VPN は、既に暗号化されているメディア トラフィックの上に、暗号化の追加レイヤーを導入することもあります。</span><span class="sxs-lookup"><span data-stu-id="c7845-184">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="c7845-185">VPN デバイスを介したヘアピン型トラフィックが原因で、Teams への接続が効率的ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7845-185">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c7845-186">QoS の実装</span><span class="sxs-lookup"><span data-stu-id="c7845-186">Implement QoS</span></span></td>
<td><span data-ttu-id="c7845-187"><a href="/microsoftteams/qos-in-teams">サービスの品質 (QoS) を使用</a>して、パケットの優先度設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c7845-187"><a href="/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="c7845-188">これにより、Teams の通話品質が向上し、通話品質の監視とトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c7845-188">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="c7845-189">QoS は、管理対象ネットワークのすべてのセグメントで実装される必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7845-189">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="c7845-190">ネットワークに帯域幅が適切にプロビジョニングされているときでも、QoS は、予期しないネットワーク イベントが発生した場合のリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="c7845-190">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="c7845-191">QoS では、音声トラフィックが優先されるため、想定外のイベントが発生しても品質に悪影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="c7845-191">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c7845-192">Wi-Fi を最適化する</span><span class="sxs-lookup"><span data-stu-id="c7845-192">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="c7845-193">VPN と同様に、Wi-Fi ネットワークは必ずしもリアルタイム メディアをサポートするように設計または構成されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c7845-193">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="c7845-194">Teams をサポートするために Wi-Fi ネットワークのための計画を立てたり、最適化を行うことは、高品質の展開を実現するための重要な考慮事項です。</span><span class="sxs-lookup"><span data-stu-id="c7845-194">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="c7845-195">計画では、次の要因を考慮します。</span><span class="sxs-lookup"><span data-stu-id="c7845-195">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="c7845-196">Wi-Fi ネットワーク上でメディア トラフィックが適切に優先されるように QoS または Wi-Fi マルチメディア (WMM) を実装します。</span><span class="sxs-lookup"><span data-stu-id="c7845-196">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="c7845-197">W-Fi バンドとアクセス ポイントの配置を計画し最適化します。</span><span class="sxs-lookup"><span data-stu-id="c7845-197">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="c7845-198">アクセス ポイントの配置に応じて、2.4 GHz 帯で十分なエクスペリエンスが提供される可能性がありますが、アクセス ポイントは、多くの場合にその帯域で動作するその他のコンシューマー デバイスによって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="c7845-198">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="c7845-199">5 GHz 帯は、その密度により、リアルタイム メディアにより適していますが、十分なカバレッジを得るためにより多くのアクセス ポイントを必要とします。</span><span class="sxs-lookup"><span data-stu-id="c7845-199">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="c7845-200">エンドポイントも、その帯をサポートしており、それらの帯を利用できるように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7845-200">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="c7845-201">デュアル バンドの Wi-Fi ネットワークを使用している場合は、バンド ステアリングの実装を検討してください。</span><span class="sxs-lookup"><span data-stu-id="c7845-201">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="c7845-202"><em>バンド ステアリング</em>は Wi-Fi ベンダーによって実装された技術で、デュアル バンド クライアントが 5 GHz 帯を使用するように仕向けます。</span><span class="sxs-lookup"><span data-stu-id="c7845-202"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="c7845-203">同じチャネルのアクセス ポイントがお互いに近すぎる場合、信号のオーバーラップや意図しない競合が発生して、ユーザーのエクスペリエンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c7845-203">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="c7845-204">お互いに隣り合っているアクセス ポイントが、オーバーラップしていないチャネル上にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7845-204">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="c7845-205">各無線ベンダーは、その無線ソリューションを展開する場合の推奨事項をそれぞれ持っています。</span><span class="sxs-lookup"><span data-stu-id="c7845-205">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="c7845-206">具体的なガイダンスについては、Wi-Fi ベンダーにご相談ください。</span><span class="sxs-lookup"><span data-stu-id="c7845-206">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="c7845-207">帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="c7845-207">Bandwidth requirements</span></span>

<span data-ttu-id="c7845-208">Teams は、ネットワークの状態に関係なく、最高のオーディオ、ビデオ、およびコンテンツ共有エクスペリエンスを提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c7845-208">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="c7845-209">とはいえ、帯域幅が不十分な場合、Teams はビデオ品質よりもオーディオ品質を優先します。</span><span class="sxs-lookup"><span data-stu-id="c7845-209">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="c7845-210">帯域幅が制限されて *いない* 場合、Teams は、最大 1080p のビデオ解像度、最大 30fps のビデオと 15fps のコンテンツ、およびハイファイ オーディオなど、メディア品質を最適化します。</span><span class="sxs-lookup"><span data-stu-id="c7845-210">Where bandwidth *isn't* limited, Teams optimizes media quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span> 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a><span data-ttu-id="c7845-211">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c7845-211">Related Topics</span></span>

[<span data-ttu-id="c7845-212">Microsoft 365 および Office 365 ネットワーク接続の原則</span><span class="sxs-lookup"><span data-stu-id="c7845-212">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="c7845-213">世界のエンドポイント: Skype for Business Online および Teams </span><span class="sxs-lookup"><span data-stu-id="c7845-213">Worldwide endpoints: Skype for Business Online and Teams</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="c7845-214">Teams 向けのプロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="c7845-214">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="c7845-215">Teams 内のメディア: 会議がシンプルな理由</span><span class="sxs-lookup"><span data-stu-id="c7845-215">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="c7845-216">Teams 内のメディア: メディア フローを深く掘り下げる</span><span class="sxs-lookup"><span data-stu-id="c7845-216">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="c7845-217">Teams での ID モデルと認証</span><span class="sxs-lookup"><span data-stu-id="c7845-217">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="c7845-218">Teams の展開方法</span><span class="sxs-lookup"><span data-stu-id="c7845-218">How to roll out Teams</span></span>](./deploy-overview.md)

[<span data-ttu-id="c7845-219">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c7845-219">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
