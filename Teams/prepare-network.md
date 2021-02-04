---
title: Teams 用に組織のネットワークを準備する
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: ネットワーク要件、ネットワークの最適化、帯域幅要件など、組織のネットワークを Microsoft Teams 用に準備する方法について説明します。
localization_priority: Normal
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
ms.openlocfilehash: 9212c096323eb57754e0a8a47b61649bec42de87
ms.sourcegitcommit: 5c33ca450a3215b9bf3c5da8bb3c9ef1a715a1a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099574"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="372f6-103">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="372f6-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="372f6-104">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="372f6-104">Network requirements</span></span>

<span data-ttu-id="372f6-105">[Microsoft 365 または Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)用にネットワークを既に最適化している場合は、Microsoft Teams の準備が整っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="372f6-105">If you've already [optimized your network for Microsoft 365 or Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="372f6-106">いずれにしても、特に、リモート ワーカーをサポートするために最初の Microsoft 365 または Office 365 ワークロードとしてTeams をすばやく展開する場合は、Teams のロールアウトを開始する前に、次の点を確認してください。</span><span class="sxs-lookup"><span data-stu-id="372f6-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="372f6-107">すべての場所にインターネットアクセス権がありますか (Microsoft 365 または Office 365 に接続できます)。</span><span class="sxs-lookup"><span data-stu-id="372f6-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="372f6-108">少なくとも、通常の Web トラフィックに加えて、Teams のメディアに対して、すべての場所に対して次の情報を開いている必要があります。</span><span class="sxs-lookup"><span data-stu-id="372f6-108">At a minimum, in addition to normal web traffic, make sure you've opened the following, for all locations, for media in Teams:</span></span>

    |  |  |
    |---------|---------|
    |<span data-ttu-id="372f6-109">ポート</span><span class="sxs-lookup"><span data-stu-id="372f6-109">Ports</span></span>     |<span data-ttu-id="372f6-110">UDP ポート <strong>3478</strong> ~ <strong>3481</strong></span><span class="sxs-lookup"><span data-stu-id="372f6-110">UDP ports <strong>3478</strong> through <strong>3481</strong></span></span>        |
    |[<span data-ttu-id="372f6-111">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="372f6-111">IP addresses</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<span data-ttu-id="372f6-112"><strong>13.107.64.0/18、52.112.0.0/14、</strong><strong>および 52.120.0.0/14</strong> <strong></strong></span><span class="sxs-lookup"><span data-stu-id="372f6-112"><strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>, and <strong>52.120.0.0/14</strong></span></span>         |

    > [!IMPORTANT]
    > <span data-ttu-id="372f6-113">Skype for Business (オンプレミスまたはオンライン) とフェデレーションする必要がある場合は、追加の DNS レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="372f6-113">If you need to federate with Skype for Business, either on-premises or online, you will need to configure some additional DNS records.</span></span>
    >
    >|<span data-ttu-id="372f6-114">CNAME レコード/ホスト名</span><span class="sxs-lookup"><span data-stu-id="372f6-114">CNAME Records / Host name</span></span>  |<span data-ttu-id="372f6-115">TTL</span><span class="sxs-lookup"><span data-stu-id="372f6-115">TTL</span></span>  |<span data-ttu-id="372f6-116">ポイント先のアドレスまたは値</span><span class="sxs-lookup"><span data-stu-id="372f6-116">Points to address or value</span></span>  |
    >|---------|---------|---------|
    >|<span data-ttu-id="372f6-117">sip</span><span class="sxs-lookup"><span data-stu-id="372f6-117">sip</span></span>     |    <span data-ttu-id="372f6-118">3600</span><span class="sxs-lookup"><span data-stu-id="372f6-118">3600</span></span>     |    <span data-ttu-id="372f6-119">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="372f6-119">sipdir.online.lync.com</span></span>     |
    >|<span data-ttu-id="372f6-120">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="372f6-120">lyncdiscover</span></span>     |   <span data-ttu-id="372f6-121">3600</span><span class="sxs-lookup"><span data-stu-id="372f6-121">3600</span></span>      |    <span data-ttu-id="372f6-122">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="372f6-122">webdir.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="372f6-123">Microsoft 365 または Office 365 の確認済みドメイン (contoso.com など) がある場合</span><span class="sxs-lookup"><span data-stu-id="372f6-123">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="372f6-124">組織で Microsoft 365 または Office 365 が展開されていない場合は、「使用を開始する」を [参照してください](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365)。</span><span class="sxs-lookup"><span data-stu-id="372f6-124">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="372f6-125">組織で Microsoft 365 または Office 365 の確認済みドメインが追加または構成されていない場合は、ドメインに関する FAQ を [参照してください](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)。</span><span class="sxs-lookup"><span data-stu-id="372f6-125">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="372f6-126">組織で Exchange Online と SharePoint Online を展開していますか?</span><span class="sxs-lookup"><span data-stu-id="372f6-126">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="372f6-127">組織に Exchange Online がインストールされていない場合は、「Exchange と Microsoft Teams のやり取り方法について理解する」を [参照してください](exchange-teams-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="372f6-127">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="372f6-128">組織に SharePoint Online がインストールされていない場合は [、「SharePoint Online](sharepoint-onedrive-interact.md)と OneDrive for Business が Microsoft Teams とやり取りする方法について理解する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="372f6-128">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="372f6-129">これらのネットワーク要件を満たしていることを確認したら、Teams を展開する準備 [が整う可能性があります](How-to-roll-out-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="372f6-129">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="372f6-130">大規模な多国籍企業の場合、またはネットワークに制限がある場合は、Teams 用にネットワークを評価して最適化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="372f6-130">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="372f6-131">**教育機関の場合**: 組織が教育機関で学生情報システム (SIS) を使用している場合は [、Teams](https://docs.microsoft.com/schooldatasync/) を展開する前に School Data Sync を展開します。</span><span class="sxs-lookup"><span data-stu-id="372f6-131">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](https://docs.microsoft.com/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="372f6-132">オンプレミス **の Skype for Business Server** の実行: 組織でオンプレミスの Skype for Business Server (または Lync Server) を実行している場合は、オンプレミス ディレクトリを Microsoft 365 または Office 365 と同期するように Azure AD [Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="372f6-132">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="372f6-133">ベスト プラクティス: CQD と通話分析を使用してネットワークを監視する</span><span class="sxs-lookup"><span data-stu-id="372f6-133">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="372f6-134">通話品質 [ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md) を使用して、Teams での通話と会議の品質に関する洞察を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="372f6-134">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="372f6-135">CQD は、品質、信頼性、ユーザー エクスペリエンスを常に把握することで、ネットワークの最適化に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="372f6-135">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="372f6-136">CQD は、全体的なパターンが明らかになる可能性がある組織全体の集計テレメトリを調えます。これにより、問題を特定し、修復を計画することができます。</span><span class="sxs-lookup"><span data-stu-id="372f6-136">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="372f6-137">さらに、CQD には、全体的な品質、信頼性、ユーザー エクスペリエンスに関する洞察を提供する豊富なメトリック レポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="372f6-137">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="372f6-138">通話分析を使用 [して、個々の](set-up-call-analytics.md) ユーザーの通話や会議の問題を調査します。</span><span class="sxs-lookup"><span data-stu-id="372f6-138">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="372f6-139">ネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="372f6-139">Network optimization</span></span>

<span data-ttu-id="372f6-140">次のタスクはオプションであり、Teams を展開する場合は必須ではありません。特に小規模企業で、Microsoft 365 または Office 365 を展開している場合です。</span><span class="sxs-lookup"><span data-stu-id="372f6-140">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="372f6-141">このガイダンスを使用して、ネットワークと Teams のパフォーマンスを最適化するか、ネットワークに制限がある場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="372f6-141">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="372f6-142">次の場合は、さらにネットワークの最適化を行う必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="372f6-142">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="372f6-143">Teams の実行速度が遅い (帯域幅が不足している可能性がある)</span><span class="sxs-lookup"><span data-stu-id="372f6-143">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="372f6-144">通話がドロップし続ける (ファイアウォールまたはプロキシブロックが原因である可能性がある)</span><span class="sxs-lookup"><span data-stu-id="372f6-144">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="372f6-145">呼び出しが静的で切り取り、または音声がロボットのように聞こえる (ジッターやパケット損失の可能性がある)</span><span class="sxs-lookup"><span data-stu-id="372f6-145">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="372f6-146">ネットワークの最適化の詳細な説明 (ネットワーク障害の特定と修正のガイダンスなど) については [、Microsoft 365 および Office 365 ネットワーク](https://aka.ms/pnc)接続の原則を参照してください。</span><span class="sxs-lookup"><span data-stu-id="372f6-146">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](https://aka.ms/pnc).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="372f6-147"><strong>ネットワーク最適化タスク</strong></span><span class="sxs-lookup"><span data-stu-id="372f6-147"><strong>Network optimization task</strong></span></span></th>
<th><span data-ttu-id="372f6-148"><strong>詳細</strong></span><span class="sxs-lookup"><span data-stu-id="372f6-148"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="372f6-149">ネットワーク プランナー</span><span class="sxs-lookup"><span data-stu-id="372f6-149">Network planner</span></span></td>
<td><p><span data-ttu-id="372f6-150">組織の物理的な場所における帯域幅の計算やネットワーク要件など、ネットワークの評価に関するヘルプについては、Teams 管理センター<a href="https://docs.microsoft.com/microsoftteams/network-planner"></a>のネットワーク プランナー ツールを<a href="https://admin.teams.microsoft.com">参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="372f6-150">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="https://docs.microsoft.com/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="372f6-151">ネットワークの詳細と Teams の使用状況を提示すると、Network Planner は、組織の物理的な場所で Teams とクラウドの音声を展開するためのネットワーク要件を計算します。</span><span class="sxs-lookup"><span data-stu-id="372f6-151">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="372f6-152">シナリオ例については、「ネットワーク プランナーの使用 - シナリオ <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">例」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="372f6-152">For an example scenario, see <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="372f6-153">Teams のアドバイザー</span><span class="sxs-lookup"><span data-stu-id="372f6-153">Advisor for Teams</span></span></td>
<td><span data-ttu-id="372f6-154"><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Teams のアドバイザーは、Teams</a> 管理センター <a href="https://admin.teams.microsoft.com">の一部です</a>。</span><span class="sxs-lookup"><span data-stu-id="372f6-154"><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="372f6-155">Microsoft 365 または Office 365 の環境を評価し、Teams を正常に展開する前に更新または変更する必要がある最も一般的な構成を特定します。</span><span class="sxs-lookup"><span data-stu-id="372f6-155">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="372f6-156">外部の名前解決</span><span class="sxs-lookup"><span data-stu-id="372f6-156">External Name Resolution</span></span></td>
<td><span data-ttu-id="372f6-157">Teams クライアントを実行しているすべてのコンピューターが外部 DNS クエリを解決して、Microsoft 365 または Office 365 によって提供されるサービスを検出し、ファイアウォールがアクセスを妨げているのではないか確認してください。</span><span class="sxs-lookup"><span data-stu-id="372f6-157">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="372f6-158">ファイアウォール ポートの構成については <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">、Microsoft 365 と 365</a>の URL Office IP 範囲を参照してください。</span><span class="sxs-lookup"><span data-stu-id="372f6-158">For information about configuring firewall ports, go to <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="372f6-159">セッションの永続性を維持する</span><span class="sxs-lookup"><span data-stu-id="372f6-159">Maintain session persistence</span></span></td>
<td><span data-ttu-id="372f6-160">ファイアウォールで、UDP のマップされたネットワーク アドレス変換 (NAT) アドレスまたはポートが変更されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="372f6-160">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="372f6-161">NAT プールのサイズを検証する</span><span class="sxs-lookup"><span data-stu-id="372f6-161">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="372f6-162">ユーザー接続に必要なネットワーク アドレス変換 (NAT) プール のサイズを検証します。</span><span class="sxs-lookup"><span data-stu-id="372f6-162">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="372f6-163">複数のユーザーやデバイスがネットワーク アドレス変換 (NAT) またはポート アドレス変換 <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">(PAT)</a>を使用して Microsoft 365 または Office 365 にアクセスする場合は、パブリックにラウト可能な各 IP アドレスの背後に隠れているデバイスがサポートされている数を超えないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="372f6-163">When multiple users and devices access Microsoft 365 or Office 365 using <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="372f6-164">ポートが使い果たされるのを防ぐために、適切なパブリック IP アドレスが NAT プールに割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="372f6-164">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="372f6-165">ポートの使い果たされ、内部ユーザーやデバイスが Microsoft 365 または Office 365 サービスに接続できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="372f6-165">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="372f6-166">Microsoft データ センターへのルーティング</span><span class="sxs-lookup"><span data-stu-id="372f6-166">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="372f6-167"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Microsoft データ センターへの最も効率的なルーティングを実装します</a>。</span><span class="sxs-lookup"><span data-stu-id="372f6-167"><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="372f6-168">ローカルまたは地域の出口ポイントを使用して、可能な限り効率的に Microsoft ネットワークに接続できる場所を特定します。</span><span class="sxs-lookup"><span data-stu-id="372f6-168">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="372f6-169">侵入検出と防止のガイダンス</span><span class="sxs-lookup"><span data-stu-id="372f6-169">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="372f6-170">環境に、送信接続<a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools"></a>用のセキュリティ層の追加のために展開された侵入検出または防止システム (IDS/IPS) がある場合は、すべての Microsoft 365 または Office 365 URL を許可してください。</span><span class="sxs-lookup"><span data-stu-id="372f6-170">If your environment has an <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="372f6-171">分割トンネル VPN を構成する</span><span class="sxs-lookup"><span data-stu-id="372f6-171">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="372f6-172">仮想プライベート ネットワーク (VPN) をバイパスする Teams トラフィックの代替パス (一般に分割トンネル <a href="https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing">VPN) を提供することをお勧めします</a>。</span><span class="sxs-lookup"><span data-stu-id="372f6-172">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="372f6-173">分割トンネリングとは、Microsoft 365 または Office 365 のトラフィックが VPN を経由するのではなく、Microsoft 365 または Office 365 に直接送信されるという意味です。</span><span class="sxs-lookup"><span data-stu-id="372f6-173">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="372f6-174">VPN をバイパスすると、Teams の品質にプラスの影響を与え、VPN デバイスや組織のネットワークからの負荷が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="372f6-174">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="372f6-175">分割トンネル VPN を実装するには、VPN ベンダーとご利用ください。</span><span class="sxs-lookup"><span data-stu-id="372f6-175">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="372f6-176">その他の理由として、VPN をバイパスすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="372f6-176">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="372f6-177">VPN は通常、リアルタイム メディアをサポートするように設計または構成されていません。</span><span class="sxs-lookup"><span data-stu-id="372f6-177">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="372f6-178">一部の VPN は UDP をサポートしていない場合があります (これは Teams に必要です)。</span><span class="sxs-lookup"><span data-stu-id="372f6-178">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="372f6-179">また、VPN は、既に暗号化されているメディア トラフィックの上に、暗号化の層を追加します。</span><span class="sxs-lookup"><span data-stu-id="372f6-179">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="372f6-180">VPN デバイスを介した髪の毛のピン留めトラフィックが原因で、Teams への接続が効率的ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="372f6-180">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="372f6-181">QoS の実装</span><span class="sxs-lookup"><span data-stu-id="372f6-181">Implement QoS</span></span></td>
<td><span data-ttu-id="372f6-182"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">サービスの品質 (QoS) を使用して</a> 、パケットの優先順位付けを構成します。</span><span class="sxs-lookup"><span data-stu-id="372f6-182"><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="372f6-183">これにより、Teams の通話品質が向上し、通話品質を監視およびトラブルシューティングできます。</span><span class="sxs-lookup"><span data-stu-id="372f6-183">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="372f6-184">QoS は、管理対象ネットワークのすべてのセグメントに実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="372f6-184">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="372f6-185">ネットワークが帯域幅に対して十分にプロビジョニングされている場合でも、QoS は、予定のないネットワーク イベントが発生した場合のリスク軽減を提供します。</span><span class="sxs-lookup"><span data-stu-id="372f6-185">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="372f6-186">QoS では、音声トラフィックが優先順位付けされ、これらの不必要なイベントが品質に悪影響を及ぼしません。</span><span class="sxs-lookup"><span data-stu-id="372f6-186">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="372f6-187">WiFi を最適化する</span><span class="sxs-lookup"><span data-stu-id="372f6-187">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="372f6-188">VPN と同様に、WiFi ネットワークは必ずしもリアルタイム メディアをサポートするように設計または構成されているとは限りません。</span><span class="sxs-lookup"><span data-stu-id="372f6-188">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="372f6-189">Teams をサポートするための WiFi ネットワークの計画または最適化は、高品質の展開に関する重要な考慮事項です。</span><span class="sxs-lookup"><span data-stu-id="372f6-189">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="372f6-190">次の要因を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="372f6-190">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="372f6-191">メディア トラフィックが WiFi ネットワークよりも適切に優先順位付けされるのを確認するには、QoS または WiFi マルチメディア (WMM) を実装します。</span><span class="sxs-lookup"><span data-stu-id="372f6-191">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="372f6-192">WiFi バンドとアクセス ポイントの配置を計画して最適化します。</span><span class="sxs-lookup"><span data-stu-id="372f6-192">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="372f6-193">アクセス ポイントの配置に応じて、2.4 GHz 帯で十分なエクスペリエンスが提供される可能性がありますが、アクセス ポイントは、多くの場合にその帯域で動作するその他のコンシューマー デバイスによって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="372f6-193">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="372f6-194">5 GHz の範囲は、密な範囲が原因でリアルタイム メディアに適していますが、十分なカバレッジを得るには、より多くのアクセス ポイントが必要です。</span><span class="sxs-lookup"><span data-stu-id="372f6-194">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="372f6-195">エンドポイントも、その帯をサポートしており、それらの帯を利用できるように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="372f6-195">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="372f6-196">デュアルバンド WiFi ネットワークを使用している場合は、バンド 運営の実装を検討してください。</span><span class="sxs-lookup"><span data-stu-id="372f6-196">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="372f6-197"><em>バンド 運営は</em> 、WiFi ベンダーが 5 GHz の範囲を使用するデュアルバンド クライアントに影響を与える手法です。</span><span class="sxs-lookup"><span data-stu-id="372f6-197"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="372f6-198">同じチャネルのアクセス ポイントが近すぎると、信号の重複が発生し、意図せず競合し、ユーザーのエクスペリエンスが悪い結果になります。</span><span class="sxs-lookup"><span data-stu-id="372f6-198">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="372f6-199">互いに隣り合っているアクセス ポイントが、重複しないチャネル上に表示されます。</span><span class="sxs-lookup"><span data-stu-id="372f6-199">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="372f6-200">各無線ベンダーは、その無線ソリューションを展開する場合の推奨事項をそれぞれ持っています。</span><span class="sxs-lookup"><span data-stu-id="372f6-200">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="372f6-201">具体的なガイダンスについては、WiFi ベンダーに問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="372f6-201">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="372f6-202">帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="372f6-202">Bandwidth requirements</span></span>

<span data-ttu-id="372f6-203">Teams は、ネットワークの状態に関係なく、最高のオーディオ、ビデオ、コンテンツ共有エクスペリエンスを提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="372f6-203">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="372f6-204">つまり、帯域幅が十分でない場合、Teams はオーディオ品質をビデオ品質よりも優先します。</span><span class="sxs-lookup"><span data-stu-id="372f6-204">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="372f6-205">帯域幅が制限されていない場合、Teams は最大 1080p のビデオ解像度、ビデオの場合は最大 30fps、コンテンツの場合は 15fps、忠実度の高いオーディオなど、メディア品質を最適化します。</span><span class="sxs-lookup"><span data-stu-id="372f6-205">Where bandwidth *isn't* limited, Teams optimizes media quality, including up to 1080p video resolution, up to 30fps for video and 15fps for content, and high-fidelity audio.</span></span> 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a><span data-ttu-id="372f6-206">関連項目</span><span class="sxs-lookup"><span data-stu-id="372f6-206">Related Topics</span></span>

[<span data-ttu-id="372f6-207">Microsoft 365 および Office 365 ネットワーク接続の原則</span><span class="sxs-lookup"><span data-stu-id="372f6-207">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="372f6-208">世界中のエンドポイント: Skype for Business Online と Teams</span><span class="sxs-lookup"><span data-stu-id="372f6-208">Worldwide endpoints: Skype for Business Online and Teams</span></span>](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="372f6-209">Teams のプロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="372f6-209">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="372f6-210">Teams のメディア: 会議が単純な理由</span><span class="sxs-lookup"><span data-stu-id="372f6-210">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="372f6-211">Teams のメディア: メディア フローの詳細</span><span class="sxs-lookup"><span data-stu-id="372f6-211">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="372f6-212">Teams での ID モデルと認証</span><span class="sxs-lookup"><span data-stu-id="372f6-212">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="372f6-213">Teams の展開方法</span><span class="sxs-lookup"><span data-stu-id="372f6-213">How to roll out Teams</span></span>](How-to-roll-out-teams.md)

[<span data-ttu-id="372f6-214">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="372f6-214">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
