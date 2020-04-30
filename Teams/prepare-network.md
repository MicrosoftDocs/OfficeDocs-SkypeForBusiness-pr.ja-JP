---
title: Teams 用に組織のネットワークを準備する
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: f06599b7e3ed06a26715de30d59dd25a61c0f197
ms.sourcegitcommit: 929c050c038a64216e38b0a67569a8f18ad4baf2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "43945571"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="c466e-103">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="c466e-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="c466e-104">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="c466e-104">Network requirements</span></span>

<span data-ttu-id="c466e-105">[Office 365 用にネットワークの最適化](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)を既に行っている場合は、Microsoft Teams の準備ができている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c466e-105">If you've already [optimized your network for Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="c466e-106">いずれの場合も、**リモートワーカー**をサポートするために、最初の Office 365 ワークロードとして teams をすばやくロールアウトする場合は、チームのロールアウトを開始する前に次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c466e-106">In any case - and especially if you're rolling out Teams quickly as your first Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="c466e-107">すべての場所でインターネットにアクセスできますか (Office 365 に接続できるようにします)。</span><span class="sxs-lookup"><span data-stu-id="c466e-107">Do all your locations have internet access (so they can connect to Office 365)?</span></span> <span data-ttu-id="c466e-108">少なくとも、通常の web トラフィックに加えて、Teams のメディアについては、すべての場所で次のように開いていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c466e-108">At a minimum, in addition to normal web traffic, make sure you've opened the following, for all locations, for media in Teams:</span></span>

    |  |  |
    |---------|---------|
    |<span data-ttu-id="c466e-109">ポート</span><span class="sxs-lookup"><span data-stu-id="c466e-109">Ports</span></span>     |<span data-ttu-id="c466e-110">UDP ポート<strong>3478</strong> ~ <strong>3481</strong></span><span class="sxs-lookup"><span data-stu-id="c466e-110">UDP ports <strong>3478</strong> through <strong>3481</strong></span></span>        |
    |[<span data-ttu-id="c466e-111">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="c466e-111">IP addresses</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<span data-ttu-id="c466e-112"><strong>13.107.64.0/18</strong>、 <strong>52.112.0.0/14</strong>、 <strong>52.120.0.0/14</strong></span><span class="sxs-lookup"><span data-stu-id="c466e-112"><strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>, and <strong>52.120.0.0/14</strong></span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="c466e-113">オンプレミスまたはオンラインのいずれかで、Skype for Business とフェデレーションを行う必要がある場合は、追加の DNS レコードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c466e-113">If you need to federate with Skype for Business, either on-premises or online, you will need to configure some additional DNS records.</span></span>
>
>|<span data-ttu-id="c466e-114">CNAME レコード/ホスト名</span><span class="sxs-lookup"><span data-stu-id="c466e-114">CNAME Records / Host name</span></span>  |<span data-ttu-id="c466e-115">消滅</span><span class="sxs-lookup"><span data-stu-id="c466e-115">TTL</span></span>  |<span data-ttu-id="c466e-116">ポイント先のアドレスまたは値</span><span class="sxs-lookup"><span data-stu-id="c466e-116">Points to address or value</span></span>  |
>|---------|---------|---------|
>|<span data-ttu-id="c466e-117">フェデレーション</span><span class="sxs-lookup"><span data-stu-id="c466e-117">sip</span></span>     |    <span data-ttu-id="c466e-118">3600</span><span class="sxs-lookup"><span data-stu-id="c466e-118">3600</span></span>     |    <span data-ttu-id="c466e-119">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c466e-119">sipdir.online.lync.com</span></span>     |
>|<span data-ttu-id="c466e-120">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c466e-120">lyncdiscover</span></span>     |   <span data-ttu-id="c466e-121">3600</span><span class="sxs-lookup"><span data-stu-id="c466e-121">3600</span></span>      |    <span data-ttu-id="c466e-122">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c466e-122">webdir.online.lync.com</span></span>     |
>


    
2.  <span data-ttu-id="c466e-123">Office 365 の確認済みドメイン (たとえば、contoso.com) があるか。</span><span class="sxs-lookup"><span data-stu-id="c466e-123">Do you have a verified domain for Office 365 (for example, contoso.com)?</span></span>
    
      - <span data-ttu-id="c466e-124">組織が Office 365 を展開していない場合は、「一般[法人向け office 365](https://docs.microsoft.com/office365/admin/admin-overview/get-started-with-office-365)の概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c466e-124">If your organization hasn't rolled out Office 365, see [Getting Started with Office 365 for business](https://docs.microsoft.com/office365/admin/admin-overview/get-started-with-office-365).</span></span>
      - <span data-ttu-id="c466e-125">組織で Office 365 の確認済みドメインを追加または構成していない場合は、「 [office 365 ドメインを確認](https://docs.microsoft.com/office365/admin/setup/domains-faq)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c466e-125">If your organization hasn't added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://docs.microsoft.com/office365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="c466e-126">組織が Exchange Online と SharePoint Online を展開していますか?</span><span class="sxs-lookup"><span data-stu-id="c466e-126">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
      - <span data-ttu-id="c466e-127">組織に Exchange Online がインストールされていない場合は、「 [exchange と Microsoft Teams の相互作用](exchange-teams-interact.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c466e-127">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
      - <span data-ttu-id="c466e-128">組織に SharePoint Online がインストールされていない場合は、「 [Sharepoint online と OneDrive For business が Microsoft Teams とどのように連携するかについ](sharepoint-onedrive-interact.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c466e-128">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="c466e-129">これらのネットワーク要件を満たしていることを確認したら、チームを[ロールアウト](How-to-roll-out-teams.md)することができます。</span><span class="sxs-lookup"><span data-stu-id="c466e-129">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="c466e-130">大企業向けの企業の場合、またはネットワークの制限事項があることがわかっている場合は、「チームのネットワークを評価して最適化する方法」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c466e-130">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c466e-131">**教育機関向けの**場合: 組織が教育機関であり、学生情報システム (SIS) を使用している場合は、チームをロールアウトする前に[School Data Sync を展開](https://docs.microsoft.com/schooldatasync/)してください。</span><span class="sxs-lookup"><span data-stu-id="c466e-131">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="c466e-132">**オンプレミスの skype For Business server を実行**している場合: 組織がオンプレミスの Skype For business server (または Lync server) を実行している場合、オンプレミスのディレクトリを Office 365 と同期するように[Azure AD Connect を構成](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c466e-132">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="c466e-133">ベストプラクティス: CQD と通話分析を使用してネットワークを監視する</span><span class="sxs-lookup"><span data-stu-id="c466e-133">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="c466e-134">[通話品質ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md)を使用して、Teams での通話と会議の品質を把握します。</span><span class="sxs-lookup"><span data-stu-id="c466e-134">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="c466e-135">CQD は、品質、信頼性、ユーザーエクスペリエンスを常に把握して、ネットワークを最適化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c466e-135">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="c466e-136">CQD は、全体的なパターンが明らかになる組織全体の集計テレメトリを確認します。これにより、問題を特定し、修復を計画することができます。</span><span class="sxs-lookup"><span data-stu-id="c466e-136">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="c466e-137">さらに、CQD には、品質、信頼性、ユーザーエクスペリエンス全体を把握するための、豊富な指標レポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c466e-137">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="c466e-138">個々のユーザーの通話と会議の問題を調査するには、[通話分析](set-up-call-analytics.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c466e-138">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="c466e-139">ネットワーク最適化</span><span class="sxs-lookup"><span data-stu-id="c466e-139">Network optimization</span></span>

<span data-ttu-id="c466e-140">次のタスクはオプションであり、チームをロールアウトする場合は必須ではありません。特に、小規模なビジネスで、Office 365 を既に展開している場合は、その必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c466e-140">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Office 365.</span></span> <span data-ttu-id="c466e-141">このガイダンスを使用して、ネットワークとチームのパフォーマンスを最適化します。また、ネットワークの制限事項があることがわかっている場合に使います。</span><span class="sxs-lookup"><span data-stu-id="c466e-141">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="c466e-142">次のような場合には、追加のネットワーク最適化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c466e-142">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="c466e-143">チームの実行速度が遅い (帯域幅が十分でない可能性がある)</span><span class="sxs-lookup"><span data-stu-id="c466e-143">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="c466e-144">通話が切断される (ファイアウォールまたはプロキシブロックが原因である可能性があります)</span><span class="sxs-lookup"><span data-stu-id="c466e-144">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="c466e-145">通話には静的と途切れがあります。また、ロボットなどのボイスサウンド (ジッタまたはパケットロスの可能性があります)</span><span class="sxs-lookup"><span data-stu-id="c466e-145">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="c466e-146">ネットワークの障害を特定して修正するためのガイダンスなど、ネットワークの最適化の詳細については、「 [Office 365 のネットワーク接続の原則](https://aka.ms/pnc)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c466e-146">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Office 365 Network Connectivity Principles](https://aka.ms/pnc).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="c466e-147"><strong>ネットワーク最適化タスク</strong></span><span class="sxs-lookup"><span data-stu-id="c466e-147"><strong>Network optimization task</strong></span></span></th>
<th><span data-ttu-id="c466e-148"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="c466e-148"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c466e-149">ネットワークプランナー</span><span class="sxs-lookup"><span data-stu-id="c466e-149">Network planner</span></span></td>
<td><p><span data-ttu-id="c466e-150">組織の物理的な場所での帯域幅の計算やネットワーク要件など、ネットワークの評価について詳しくは、「 <a href="https://docs.microsoft.com/microsoftteams/network-planner">Network Planner</a> <a href="https://admin.teams.microsoft.com">ツール」をご覧ください。</a></span><span class="sxs-lookup"><span data-stu-id="c466e-150">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="https://docs.microsoft.com/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="c466e-151">ネットワークの詳細とチームの利用状況を入力すると、ネットワーク Planner によって、組織の物理的な場所でチームとクラウドボイスを展開するためのネットワーク要件が計算されます。</span><span class="sxs-lookup"><span data-stu-id="c466e-151">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="c466e-152">シナリオの例については、「<a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">ネットワークプランナーの使用例のシナリオ</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c466e-152">For an example scenario, see <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c466e-153">チーム向けのアドバイザー</span><span class="sxs-lookup"><span data-stu-id="c466e-153">Advisor for Teams</span></span></td>
<td><span data-ttu-id="c466e-154"><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">チームのアドバイザー</a>は<a href="https://admin.teams.microsoft.com">teams 管理センター</a>の一部です。</span><span class="sxs-lookup"><span data-stu-id="c466e-154"><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="c466e-155">Office 365 環境を評価し、Teams を正常に展開する前に更新または変更する必要がある最も一般的な構成を特定します。</span><span class="sxs-lookup"><span data-stu-id="c466e-155">It assesses your Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c466e-156">外部の名前解決</span><span class="sxs-lookup"><span data-stu-id="c466e-156">External Name Resolution</span></span></td>
<td><span data-ttu-id="c466e-157">Teams クライアントを実行しているすべてのコンピューターで、Office 365 によって提供されるサービスを検出し、ファイアウォールによってアクセスが拒否されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c466e-157">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="c466e-158">ファイアウォールのポートを構成する方法については、「 <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Office 365 の URL と IP 範囲</a>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c466e-158">For information about configuring firewall ports, go to <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c466e-159">検証 (NAT) プールサイズ</span><span class="sxs-lookup"><span data-stu-id="c466e-159">Validate (NAT) pool size</span></span></td>
<td><span data-ttu-id="c466e-160">ユーザー接続に必要なネットワークアドレス変換 (NAT) プールサイズを確認します。</span><span class="sxs-lookup"><span data-stu-id="c466e-160">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="c466e-161">複数のユーザーやデバイスが<a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">ネットワークアドレス変換 (NAT) またはポートアドレス変換 (PAT)</a>を使って Office 365 にアクセスする場合、各パブリックルーティング可能な IP アドレスの背後に隠れているデバイスが、サポートされている番号を超えないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c466e-161">When multiple users and devices access Office 365 using <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="c466e-162">ポートの枯渇を防ぐため、適切なパブリック IP アドレスが NAT プールに割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c466e-162">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="c466e-163">ポートの枯渇は、社内ユーザーと、Office 365 サービスに接続できないデバイスに寄与します。</span><span class="sxs-lookup"><span data-stu-id="c466e-163">Port exhaustion will contribute to internal users and devices being unable to connect to the Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c466e-164">Microsoft データセンターへのルーティング</span><span class="sxs-lookup"><span data-stu-id="c466e-164">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="c466e-165"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Microsoft データセンターへの最も効率的なルーティングを実装</a>します。</span><span class="sxs-lookup"><span data-stu-id="c466e-165"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="c466e-166">ローカルまたは地域の出口ポイントを使用して、可能な限り効率的に Microsoft ネットワークに接続できる場所を特定します。</span><span class="sxs-lookup"><span data-stu-id="c466e-166">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c466e-167">侵入検知と予防のガイダンス</span><span class="sxs-lookup"><span data-stu-id="c466e-167">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="c466e-168">お客様の環境に、送信接続用のセキュリティレイヤーを追加するために展開された<a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">侵入検出</a>または防止システム (IDS/IPS) が展開されている場合は、すべての Office 365 url をホワイトリストしてください。</span><span class="sxs-lookup"><span data-stu-id="c466e-168">If your environment has an <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to whitelist all Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c466e-169">分割トンネル VPN を構成する</span><span class="sxs-lookup"><span data-stu-id="c466e-169">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="c466e-170">一般に[分割トンネル VPN](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing)と呼ばれる仮想プライベートネットワーク (VPN) をバイパスするチームトラフィックの代替パスを指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c466e-170">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as [split-tunnel VPN](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing).</span></span> <span data-ttu-id="c466e-171">[トンネリングの分割とは、Office 365 のトラフィックが VPN 経由ではなく、直接 Office 365 に移動することを意味します。</span><span class="sxs-lookup"><span data-stu-id="c466e-171">Split tunneling means that traffic for Office 365 doesn't go through the VPN but instead goes directly to Office 365.</span></span> <span data-ttu-id="c466e-172">VPN をバイパスすると、チームの品質にプラスの影響があり、VPN デバイスと組織のネットワークの負荷が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="c466e-172">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="c466e-173">分離トンネル VPN を実装するには、VPN ベンダーと共同作業を行います。</span><span class="sxs-lookup"><span data-stu-id="c466e-173">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="c466e-174">VPN のバイパスが推奨されるその他の理由:</span><span class="sxs-lookup"><span data-stu-id="c466e-174">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="c466e-175">通常、Vpn は、リアルタイムメディアをサポートするように設計されていないか、構成されていません。</span><span class="sxs-lookup"><span data-stu-id="c466e-175">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="c466e-176">一部の Vpn は、UDP をサポートしていない場合もあります (Teams に必要)。</span><span class="sxs-lookup"><span data-stu-id="c466e-176">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="c466e-177">Vpn は、既に暗号化されているメディアトラフィックの上に、暗号化の追加レイヤーを導入することもあります。</span><span class="sxs-lookup"><span data-stu-id="c466e-177">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="c466e-178">VPN デバイス経由でのヘアピンによるトラフィックにより、Teams への接続は効率的でない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c466e-178">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c466e-179">QoS の実装</span><span class="sxs-lookup"><span data-stu-id="c466e-179">Implement QoS</span></span></td>
<td><span data-ttu-id="c466e-180"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">QoS (Quality Of Service) を使っ</a>てパケットの優先順位を設定します。</span><span class="sxs-lookup"><span data-stu-id="c466e-180"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="c466e-181">これにより、チームの通話品質が向上し、通話品質の監視とトラブルシューティングが容易になります。</span><span class="sxs-lookup"><span data-stu-id="c466e-181">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="c466e-182">QoS は、管理されたネットワークのすべてのセグメントに実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c466e-182">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="c466e-183">ネットワークが帯域幅用に適切にプロビジョニングされている場合でも、予期しないネットワークイベントが発生した場合は、QoS によってリスクを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="c466e-183">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="c466e-184">QoS では、このような予期しないイベントが品質に悪影響を与えないように、ボイストラフィックの優先順位が付けられます。</span><span class="sxs-lookup"><span data-stu-id="c466e-184">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c466e-185">WiFi の最適化</span><span class="sxs-lookup"><span data-stu-id="c466e-185">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="c466e-186">VPN と同じように、WiFi ネットワークは、リアルタイムメディアをサポートするように設計されていないこともあります。</span><span class="sxs-lookup"><span data-stu-id="c466e-186">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="c466e-187">チームをサポートするための WiFi ネットワークを計画または最適化することは、高品質な展開を行うための重要な考慮事項です。</span><span class="sxs-lookup"><span data-stu-id="c466e-187">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="c466e-188">次のような要素を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="c466e-188">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="c466e-189">QoS または WiFi マルチメディア (WMM) を実装して、WiFi ネットワーク経由でメディアトラフィックの優先順位が適切に付けられるようにします。</span><span class="sxs-lookup"><span data-stu-id="c466e-189">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="c466e-190">WiFi バンドおよびアクセスポイントの配置を計画して最適化します。</span><span class="sxs-lookup"><span data-stu-id="c466e-190">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="c466e-191">アクセス ポイントの配置に応じて、2.4 GHz 帯で十分なエクスペリエンスが提供される可能性がありますが、アクセス ポイントは、多くの場合にその帯域で動作するその他のコンシューマー デバイスによって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="c466e-191">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="c466e-192">5 GHz の範囲は、高密度な範囲に基づくリアルタイムのメディアに適していますが、十分な範囲を確保するには、さらに多くのアクセスポイントが必要です。</span><span class="sxs-lookup"><span data-stu-id="c466e-192">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="c466e-193">エンドポイントも、その帯をサポートしており、それらの帯を利用できるように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c466e-193">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="c466e-194">デュアルバンド WiFi ネットワークを使用している場合は、バンドステアリングの実装を検討してください。</span><span class="sxs-lookup"><span data-stu-id="c466e-194">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="c466e-195"><em>バンドステアリング</em>は、5 GHz のクライアントを使用するようにデュアルバンドクライアントに影響を与えるために、WiFi ベンダーによって実装された手法です。</span><span class="sxs-lookup"><span data-stu-id="c466e-195"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="c466e-196">同じチャネルのアクセスポイントが近すぎる場合は、信号の重複が発生し、意図せず競合する可能性があり、その結果、ユーザーにとって悪い操作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c466e-196">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="c466e-197">互いに隣接するアクセスポイントが重なっていないチャネル上にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c466e-197">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="c466e-198">各無線ベンダーは、その無線ソリューションを展開する場合の推奨事項をそれぞれ持っています。</span><span class="sxs-lookup"><span data-stu-id="c466e-198">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="c466e-199">具体的なガイダンスについては、WiFi ベンダーにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="c466e-199">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="c466e-200">帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="c466e-200">Bandwidth requirements</span></span>

<span data-ttu-id="c466e-201">Teams は、ネットワークの状況に関係なく、最適なオーディオ、ビデオ、およびコンテンツ共有のエクスペリエンスを提供するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="c466e-201">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="c466e-202">ただし、帯域幅が十分でない場合、チームはビデオ品質よりも音質の高い音質を優先します。</span><span class="sxs-lookup"><span data-stu-id="c466e-202">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="c466e-203">帯域幅が制限されて*いない*場合、チームは、最大1080p のビデオ解像度、ビデオ用および 15 fps 用の最大30fps、および高品質のオーディオを含むメディアの品質を最適化します。</span><span class="sxs-lookup"><span data-stu-id="c466e-203">Where bandwidth *isn't* limited, Teams optimizes media quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span> 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a><span data-ttu-id="c466e-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="c466e-204">Related Topics</span></span>

[<span data-ttu-id="c466e-205">Office 365 のネットワーク接続の原則</span><span class="sxs-lookup"><span data-stu-id="c466e-205">Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="c466e-206">ワールドワイドエンドポイント: Skype for Business Online と Teams</span><span class="sxs-lookup"><span data-stu-id="c466e-206">Worldwide endpoints: Skype for Business Online and Teams</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="c466e-207">Teams のプロキシサーバー</span><span class="sxs-lookup"><span data-stu-id="c466e-207">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="c466e-208">Teams のメディア: 会議が簡単である理由</span><span class="sxs-lookup"><span data-stu-id="c466e-208">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="c466e-209">Teams のメディア: メディアフローの詳細</span><span class="sxs-lookup"><span data-stu-id="c466e-209">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="c466e-210">Teams での ID モデルと認証</span><span class="sxs-lookup"><span data-stu-id="c466e-210">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="c466e-211">Teams の展開方法</span><span class="sxs-lookup"><span data-stu-id="c466e-211">How to roll out Teams</span></span>](How-to-roll-out-teams.md)

