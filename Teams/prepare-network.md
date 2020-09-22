---
title: Teams 用に組織のネットワークを準備する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: ネットワーク要件、ネットワークの最適化、帯域幅の要件など、組織の Microsoft Teams 用ネットワークの準備について説明します。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 8c67d7f7006720849f4e14ecf7b22e65cdfa9d2f
ms.sourcegitcommit: fb4edc26c566228d74c10cb51a063b5fdc7e11a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177559"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="af892-103">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="af892-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="af892-104">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="af892-104">Network requirements</span></span>

<span data-ttu-id="af892-105">[Microsoft 365 または Office 365 用にネットワーク](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)を既に最適化している場合は、microsoft Teams の準備ができている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="af892-105">If you've already [optimized your network for Microsoft 365 or Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="af892-106">いずれにしても、特に、 **リモートワーカー** をサポートするために teams を最初の Microsoft 365 または Office 365 のワークロードとしてすばやくロールアウトする場合は、チームのロールアウトを開始する前に次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="af892-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="af892-107">すべての場所でインターネットにアクセスできますか (Microsoft 365 または Office 365 に接続できるようにします)。</span><span class="sxs-lookup"><span data-stu-id="af892-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="af892-108">少なくとも、通常の web トラフィックに加えて、Teams のメディアについては、すべての場所で次のように開いていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="af892-108">At a minimum, in addition to normal web traffic, make sure you've opened the following, for all locations, for media in Teams:</span></span>

    |  |  |
    |---------|---------|
    |<span data-ttu-id="af892-109">ポート</span><span class="sxs-lookup"><span data-stu-id="af892-109">Ports</span></span>     |<span data-ttu-id="af892-110">UDP ポート <strong>3478</strong> ~ <strong>3481</strong></span><span class="sxs-lookup"><span data-stu-id="af892-110">UDP ports <strong>3478</strong> through <strong>3481</strong></span></span>        |
    |[<span data-ttu-id="af892-111">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="af892-111">IP addresses</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<span data-ttu-id="af892-112"><strong>13.107.64.0/18</strong>、 <strong>52.112.0.0/14</strong>、 <strong>52.120.0.0/14</strong></span><span class="sxs-lookup"><span data-stu-id="af892-112"><strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>, and <strong>52.120.0.0/14</strong></span></span>         |

    > [!IMPORTANT]
    > <span data-ttu-id="af892-113">オンプレミスまたはオンラインのいずれかで、Skype for Business とフェデレーションを行う必要がある場合は、追加の DNS レコードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af892-113">If you need to federate with Skype for Business, either on-premises or online, you will need to configure some additional DNS records.</span></span>
    >
    >|<span data-ttu-id="af892-114">CNAME レコード/ホスト名</span><span class="sxs-lookup"><span data-stu-id="af892-114">CNAME Records / Host name</span></span>  |<span data-ttu-id="af892-115">消滅</span><span class="sxs-lookup"><span data-stu-id="af892-115">TTL</span></span>  |<span data-ttu-id="af892-116">ポイント先のアドレスまたは値</span><span class="sxs-lookup"><span data-stu-id="af892-116">Points to address or value</span></span>  |
    >|---------|---------|---------|
    >|<span data-ttu-id="af892-117">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="af892-117">sip</span></span>     |    <span data-ttu-id="af892-118">3600</span><span class="sxs-lookup"><span data-stu-id="af892-118">3600</span></span>     |    <span data-ttu-id="af892-119">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="af892-119">sipdir.online.lync.com</span></span>     |
    >|<span data-ttu-id="af892-120">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="af892-120">lyncdiscover</span></span>     |   <span data-ttu-id="af892-121">3600</span><span class="sxs-lookup"><span data-stu-id="af892-121">3600</span></span>      |    <span data-ttu-id="af892-122">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="af892-122">webdir.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="af892-123">Microsoft 365 または Office 365 (たとえば、contoso.com) の確認済みドメインがありますか?</span><span class="sxs-lookup"><span data-stu-id="af892-123">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="af892-124">組織が Microsoft 365 または Office 365 を展開していない場合は、「使用を [開始](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af892-124">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="af892-125">組織で、Microsoft 365 または Office 365 の確認済みドメインを追加または構成していない場合は、ドメインに関する [FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af892-125">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="af892-126">組織が Exchange Online と SharePoint Online を展開していますか?</span><span class="sxs-lookup"><span data-stu-id="af892-126">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="af892-127">組織に Exchange Online がインストールされていない場合は、「 [exchange と Microsoft Teams の相互作用](exchange-teams-interact.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af892-127">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="af892-128">組織に SharePoint Online がインストールされていない場合は、「 [Sharepoint online と OneDrive For business が Microsoft Teams とどのように連携するかについ](sharepoint-onedrive-interact.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af892-128">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="af892-129">これらのネットワーク要件を満たしていることを確認したら、チームを [ロールアウト](How-to-roll-out-teams.md)することができます。</span><span class="sxs-lookup"><span data-stu-id="af892-129">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="af892-130">大企業向けの企業の場合、またはネットワークの制限事項があることがわかっている場合は、「チームのネットワークを評価して最適化する方法」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="af892-130">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af892-131">**教育機関向けの**場合: 組織が教育機関であり、学生情報システム (SIS) を使用している場合は、チームをロールアウトする前に [School Data Sync を展開](https://docs.microsoft.com/schooldatasync/) してください。</span><span class="sxs-lookup"><span data-stu-id="af892-131">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="af892-132">**オンプレミスの skype For Business server を実行**している場合: 組織がオンプレミスの Skype For business server (または Lync server) を実行している場合、オンプレミスのディレクトリを Microsoft 365 または Office 365 と同期するように [Azure AD Connect を構成](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af892-132">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="af892-133">ベストプラクティス: CQD と通話分析を使用してネットワークを監視する</span><span class="sxs-lookup"><span data-stu-id="af892-133">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="af892-134">[通話品質ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md)を使用して、Teams での通話と会議の品質を把握します。</span><span class="sxs-lookup"><span data-stu-id="af892-134">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="af892-135">CQD は、品質、信頼性、ユーザーエクスペリエンスを常に把握して、ネットワークを最適化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="af892-135">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="af892-136">CQD は、全体的なパターンが明らかになる組織全体の集計テレメトリを確認します。これにより、問題を特定し、修復を計画することができます。</span><span class="sxs-lookup"><span data-stu-id="af892-136">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="af892-137">さらに、CQD には、品質、信頼性、ユーザーエクスペリエンス全体を把握するための、豊富な指標レポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="af892-137">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="af892-138">個々のユーザーの通話と会議の問題を調査するには、 [通話分析](set-up-call-analytics.md) を使用します。</span><span class="sxs-lookup"><span data-stu-id="af892-138">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="af892-139">ネットワーク最適化</span><span class="sxs-lookup"><span data-stu-id="af892-139">Network optimization</span></span>

<span data-ttu-id="af892-140">次のタスクはオプションであり、チームをロールアウトする場合は必須ではありません。特に、small business で、Microsoft 365 または Office 365 を既に展開している場合には、これらは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="af892-140">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="af892-141">このガイダンスを使用して、ネットワークとチームのパフォーマンスを最適化します。また、ネットワークの制限事項があることがわかっている場合に使います。</span><span class="sxs-lookup"><span data-stu-id="af892-141">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="af892-142">次のような場合には、追加のネットワーク最適化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="af892-142">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="af892-143">チームの実行速度が遅い (帯域幅が十分でない可能性がある)</span><span class="sxs-lookup"><span data-stu-id="af892-143">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="af892-144">通話が切断される (ファイアウォールまたはプロキシブロックが原因である可能性があります)</span><span class="sxs-lookup"><span data-stu-id="af892-144">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="af892-145">通話には静的と途切れがあります。また、ロボットなどのボイスサウンド (ジッタまたはパケットロスの可能性があります)</span><span class="sxs-lookup"><span data-stu-id="af892-145">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="af892-146">ネットワークの障害を特定して修正するためのガイダンスなど、ネットワークの最適化の詳細については、「 [Microsoft 365 と Office 365 のネットワーク接続の原則](https://aka.ms/pnc)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af892-146">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](https://aka.ms/pnc).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="af892-147"><strong>ネットワーク最適化タスク</strong></span><span class="sxs-lookup"><span data-stu-id="af892-147"><strong>Network optimization task</strong></span></span></th>
<th><span data-ttu-id="af892-148"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="af892-148"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="af892-149">ネットワークプランナー</span><span class="sxs-lookup"><span data-stu-id="af892-149">Network planner</span></span></td>
<td><p><span data-ttu-id="af892-150">組織の物理的な場所での帯域幅の計算やネットワーク要件など、ネットワークの評価について詳しくは、「 <a href="https://docs.microsoft.com/microsoftteams/network-planner">Network Planner</a> <a href="https://admin.teams.microsoft.com">ツール」をご覧ください。</a></span><span class="sxs-lookup"><span data-stu-id="af892-150">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="https://docs.microsoft.com/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="af892-151">ネットワークの詳細と Teams の使用状況を提示すると、Network Planner は、組織の物理的な場所で Teams とクラウドの音声を展開するためのネットワーク要件を計算します。</span><span class="sxs-lookup"><span data-stu-id="af892-151">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="af892-152">シナリオの例については、「 <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">ネットワークプランナーの使用例のシナリオ</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af892-152">For an example scenario, see <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="af892-153">チーム向けのアドバイザー</span><span class="sxs-lookup"><span data-stu-id="af892-153">Advisor for Teams</span></span></td>
<td><span data-ttu-id="af892-154"><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">チームのアドバイザー</a> は <a href="https://admin.teams.microsoft.com">teams 管理センター</a>の一部です。</span><span class="sxs-lookup"><span data-stu-id="af892-154"><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="af892-155">Microsoft 365 または Office 365 の環境を評価し、Teams を正常に展開する前に更新または変更する必要がある最も一般的な構成を特定します。</span><span class="sxs-lookup"><span data-stu-id="af892-155">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="af892-156">外部の名前解決</span><span class="sxs-lookup"><span data-stu-id="af892-156">External Name Resolution</span></span></td>
<td><span data-ttu-id="af892-157">Teams クライアントを実行しているすべてのコンピューターが外部 DNS クエリを解決して、Microsoft 365 または Office 365 によって提供されるサービスを検出し、ファイアウォールによってアクセスが禁止されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="af892-157">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="af892-158">ファイアウォールポートの構成の詳細については、「 <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 および Office 365 の url と IP 範囲</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af892-158">For information about configuring firewall ports, go to <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="af892-159">セッションの永続性を維持する</span><span class="sxs-lookup"><span data-stu-id="af892-159">Maintain session persistence</span></span></td>
<td><span data-ttu-id="af892-160">ファイアウォールによって、UDP の対応付けられたネットワークアドレス変換 (NAT) アドレスまたはポートが変更されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="af892-160">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="af892-161">NAT プールサイズを検証する</span><span class="sxs-lookup"><span data-stu-id="af892-161">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="af892-162">ユーザー接続に必要なネットワークアドレス変換 (NAT) プールサイズを確認します。</span><span class="sxs-lookup"><span data-stu-id="af892-162">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="af892-163">複数のユーザーやデバイスが、 <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">ネットワークアドレス変換 (NAT) またはポートアドレス変換 (PAT)</a>を使用して Microsoft 365 または Office 365 にアクセスする場合、各パブリックルーティング可能な IP アドレスの背後に隠れているデバイスがサポートされている番号を超えないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="af892-163">When multiple users and devices access Microsoft 365 or Office 365 using <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="af892-164">ポートの枯渇を防ぐため、適切なパブリック IP アドレスが NAT プールに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="af892-164">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="af892-165">ポートの枯渇は、内部ユーザーと、Microsoft 365 または Office 365 サービスに接続できないデバイスに影響します。</span><span class="sxs-lookup"><span data-stu-id="af892-165">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="af892-166">Microsoft データセンターへのルーティング</span><span class="sxs-lookup"><span data-stu-id="af892-166">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="af892-167"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Microsoft データセンターへの最も効率的なルーティングを実装</a>します。</span><span class="sxs-lookup"><span data-stu-id="af892-167"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="af892-168">ローカルまたは地域の出口ポイントを使用して、可能な限り効率的に Microsoft ネットワークに接続できる場所を特定します。</span><span class="sxs-lookup"><span data-stu-id="af892-168">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="af892-169">侵入検知と予防のガイダンス</span><span class="sxs-lookup"><span data-stu-id="af892-169">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="af892-170">使用している環境に、送信接続のセキュリティレイヤーを追加するために展開された <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">侵入検知</a> または防止システム (IDS/IPS) が展開されている場合は、必ず Microsoft 365 または Office 365 の url をすべて許可してください。</span><span class="sxs-lookup"><span data-stu-id="af892-170">If your environment has an <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="af892-171">分割トンネル VPN を構成する</span><span class="sxs-lookup"><span data-stu-id="af892-171">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="af892-172">一般に <a href="https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing">分割トンネル VPN</a>と呼ばれる仮想プライベートネットワーク (VPN) をバイパスするチームトラフィックの代替パスを指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af892-172">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="af892-173">[トンネリングの分割とは、Microsoft 365 または Office 365 のトラフィックが VPN 経由ではなく、直接 Microsoft 365 または Office 365 に移行することを意味します。</span><span class="sxs-lookup"><span data-stu-id="af892-173">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="af892-174">VPN をバイパスすると、チームの品質にプラスの影響があり、VPN デバイスと組織のネットワークの負荷が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="af892-174">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="af892-175">分離トンネル VPN を実装するには、VPN ベンダーと共同作業を行います。</span><span class="sxs-lookup"><span data-stu-id="af892-175">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="af892-176">VPN のバイパスが推奨されるその他の理由:</span><span class="sxs-lookup"><span data-stu-id="af892-176">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="af892-177">通常、Vpn は、リアルタイムメディアをサポートするように設計されていないか、構成されていません。</span><span class="sxs-lookup"><span data-stu-id="af892-177">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="af892-178">一部の Vpn は、UDP をサポートしていない場合もあります (Teams に必要)。</span><span class="sxs-lookup"><span data-stu-id="af892-178">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="af892-179">Vpn は、既に暗号化されているメディアトラフィックの上に、暗号化の追加レイヤーを導入することもあります。</span><span class="sxs-lookup"><span data-stu-id="af892-179">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="af892-180">VPN デバイス経由でのヘアピンによるトラフィックにより、Teams への接続は効率的でない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="af892-180">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="af892-181">QoS の実装</span><span class="sxs-lookup"><span data-stu-id="af892-181">Implement QoS</span></span></td>
<td><span data-ttu-id="af892-182"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">QoS (Quality Of Service) を使っ</a> てパケットの優先順位を設定します。</span><span class="sxs-lookup"><span data-stu-id="af892-182"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="af892-183">これにより、チームの通話品質が向上し、通話品質の監視とトラブルシューティングが容易になります。</span><span class="sxs-lookup"><span data-stu-id="af892-183">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="af892-184">QoS は、管理されたネットワークのすべてのセグメントに実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af892-184">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="af892-185">ネットワークが帯域幅用に適切にプロビジョニングされている場合でも、予期しないネットワークイベントが発生した場合は、QoS によってリスクを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="af892-185">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="af892-186">QoS では、このような予期しないイベントが品質に悪影響を与えないように、ボイストラフィックの優先順位が付けられます。</span><span class="sxs-lookup"><span data-stu-id="af892-186">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="af892-187">WiFi の最適化</span><span class="sxs-lookup"><span data-stu-id="af892-187">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="af892-188">VPN と同じように、WiFi ネットワークは、リアルタイムメディアをサポートするように設計されていないこともあります。</span><span class="sxs-lookup"><span data-stu-id="af892-188">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="af892-189">チームをサポートするための WiFi ネットワークを計画または最適化することは、高品質な展開を行うための重要な考慮事項です。</span><span class="sxs-lookup"><span data-stu-id="af892-189">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="af892-190">次のような要素を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="af892-190">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="af892-191">QoS または WiFi マルチメディア (WMM) を実装して、WiFi ネットワーク経由でメディアトラフィックの優先順位が適切に付けられるようにします。</span><span class="sxs-lookup"><span data-stu-id="af892-191">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="af892-192">WiFi バンドおよびアクセスポイントの配置を計画して最適化します。</span><span class="sxs-lookup"><span data-stu-id="af892-192">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="af892-193">アクセス ポイントの配置に応じて、2.4 GHz 帯で十分なエクスペリエンスが提供される可能性がありますが、アクセス ポイントは、多くの場合にその帯域で動作するその他のコンシューマー デバイスによって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="af892-193">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="af892-194">5 GHz の範囲は、高密度な範囲に基づくリアルタイムのメディアに適していますが、十分な範囲を確保するには、さらに多くのアクセスポイントが必要です。</span><span class="sxs-lookup"><span data-stu-id="af892-194">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="af892-195">エンドポイントも、その帯をサポートしており、それらの帯を利用できるように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="af892-195">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="af892-196">デュアルバンド WiFi ネットワークを使用している場合は、バンドステアリングの実装を検討してください。</span><span class="sxs-lookup"><span data-stu-id="af892-196">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="af892-197"><em>バンドステアリング</em> は、5 GHz のクライアントを使用するようにデュアルバンドクライアントに影響を与えるために、WiFi ベンダーによって実装された手法です。</span><span class="sxs-lookup"><span data-stu-id="af892-197"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="af892-198">同じチャネルのアクセスポイントが近すぎる場合は、信号の重複が発生し、意図せず競合する可能性があり、その結果、ユーザーにとって悪い操作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="af892-198">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="af892-199">互いに隣接するアクセスポイントが重なっていないチャネル上にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="af892-199">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="af892-200">各無線ベンダーは、その無線ソリューションを展開する場合の推奨事項をそれぞれ持っています。</span><span class="sxs-lookup"><span data-stu-id="af892-200">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="af892-201">具体的なガイダンスについては、WiFi ベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="af892-201">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="af892-202">帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="af892-202">Bandwidth requirements</span></span>

<span data-ttu-id="af892-203">Teams は、ネットワークの状況に関係なく、最適なオーディオ、ビデオ、およびコンテンツ共有のエクスペリエンスを提供するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="af892-203">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="af892-204">ただし、帯域幅が十分でない場合、チームはビデオ品質よりも音質の高い音質を優先します。</span><span class="sxs-lookup"><span data-stu-id="af892-204">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="af892-205">帯域幅が制限されて *いない* 場合、チームは、最大1080p のビデオ解像度、ビデオ用および 15 fps 用の最大30fps、および高品質のオーディオを含むメディアの品質を最適化します。</span><span class="sxs-lookup"><span data-stu-id="af892-205">Where bandwidth *isn't* limited, Teams optimizes media quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span> 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a><span data-ttu-id="af892-206">関連項目</span><span class="sxs-lookup"><span data-stu-id="af892-206">Related Topics</span></span>

[<span data-ttu-id="af892-207">Microsoft 365 および Office 365 のネットワーク接続の原則</span><span class="sxs-lookup"><span data-stu-id="af892-207">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="af892-208">ワールドワイドエンドポイント: Skype for Business Online と Teams</span><span class="sxs-lookup"><span data-stu-id="af892-208">Worldwide endpoints: Skype for Business Online and Teams</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="af892-209">Teams のプロキシサーバー</span><span class="sxs-lookup"><span data-stu-id="af892-209">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="af892-210">Teams のメディア: 会議が簡単である理由</span><span class="sxs-lookup"><span data-stu-id="af892-210">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="af892-211">Teams のメディア: メディアフローの詳細</span><span class="sxs-lookup"><span data-stu-id="af892-211">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="af892-212">Teams での ID モデルと認証</span><span class="sxs-lookup"><span data-stu-id="af892-212">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="af892-213">Teams の展開方法</span><span class="sxs-lookup"><span data-stu-id="af892-213">How to roll out Teams</span></span>](How-to-roll-out-teams.md)

[<span data-ttu-id="af892-214">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="af892-214">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
