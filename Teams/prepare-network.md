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
ms.openlocfilehash: db911db3631caebb0e767401f80c36bdac6c9c1b
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420832"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="35bc9-103">Microsoft Teams 用に組織のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="35bc9-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="35bc9-104">ネットワーク要件</span><span class="sxs-lookup"><span data-stu-id="35bc9-104">Network requirements</span></span>

<span data-ttu-id="35bc9-105">既に[ネットワークを Microsoft 365 または Office 365 用に最適化](/Office365/Enterprise/assessing-network-connectivity)している場合は、Microsoft Teams の準備ができている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35bc9-105">If you've already [optimized your network for Microsoft 365 or Office 365](/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="35bc9-106">いずれの場合でも、特に **リモート ワーカー** をサポートする最初の Microsoft 365 または Office 365 ワークロードとして Teams を迅速に展開する場合は、Teams の展開を開始する前に次のことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="35bc9-107">(Microsoft 365 または Office 365 に接続できるように) すべての場所にインターネット アクセスがありますか?</span><span class="sxs-lookup"><span data-stu-id="35bc9-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="35bc9-108">通常の Web トラフィックに加えて、[Office 365 の URL と IP アドレスの範囲](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)に記載されている Teams 用の TCP ポートと IP アドレスを開いていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-108">In addition to normal web traffic, make sure you've opened the TCP ports and IP addresses listed for Teams in [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="35bc9-109">オンプレミスまたはオンラインのいずれかで Skype for Business と連携する必要がある場合は、追加の DNS レコードを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35bc9-109">If you need to federate with Skype for Business, either on-premises or online, you will need to configure an additional DNS record.</span></span>
    >
    >|<span data-ttu-id="35bc9-110">DNS レコード</span><span class="sxs-lookup"><span data-stu-id="35bc9-110">DNS record</span></span>  |<span data-ttu-id="35bc9-111">サービス</span><span class="sxs-lookup"><span data-stu-id="35bc9-111">Service</span></span>  |<span data-ttu-id="35bc9-112">Protocol</span><span class="sxs-lookup"><span data-stu-id="35bc9-112">Protocol</span></span>  |<span data-ttu-id="35bc9-113">Priority</span><span class="sxs-lookup"><span data-stu-id="35bc9-113">Priority</span></span>  |<span data-ttu-id="35bc9-114">Weight</span><span class="sxs-lookup"><span data-stu-id="35bc9-114">Weight</span></span>  |<span data-ttu-id="35bc9-115">Port</span><span class="sxs-lookup"><span data-stu-id="35bc9-115">Port</span></span>  |<span data-ttu-id="35bc9-116">Target</span><span class="sxs-lookup"><span data-stu-id="35bc9-116">Target</span></span>  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|<span data-ttu-id="35bc9-117">SRV</span><span class="sxs-lookup"><span data-stu-id="35bc9-117">SRV</span></span>     |<span data-ttu-id="35bc9-118">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="35bc9-118">sipfederationtls</span></span>     |<span data-ttu-id="35bc9-119">TCP</span><span class="sxs-lookup"><span data-stu-id="35bc9-119">TCP</span></span>     |<span data-ttu-id="35bc9-120">100</span><span class="sxs-lookup"><span data-stu-id="35bc9-120">100</span></span>     |<span data-ttu-id="35bc9-121">1</span><span class="sxs-lookup"><span data-stu-id="35bc9-121">1</span></span>     |<span data-ttu-id="35bc9-122">5061</span><span class="sxs-lookup"><span data-stu-id="35bc9-122">5061</span></span>     |<span data-ttu-id="35bc9-123">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="35bc9-123">sipfed.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="35bc9-124">Microsoft 365 または Office 365 の検証済みドメイン (たとえば、contoso.com) はありますか?</span><span class="sxs-lookup"><span data-stu-id="35bc9-124">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="35bc9-125">組織が Microsoft 365 または Office 365 を展開していない場合は、「[概要](/microsoft-365/admin/admin-overview/get-started-with-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-125">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="35bc9-126">組織が Microsoft 365 または Office 365 の検証済みドメインを追加または構成していない場合は、「[ドメインに関する FAQ](/microsoft-365/admin/setup/domains-faq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-126">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="35bc9-127">組織は Exchange Online と SharePoint Online を展開していますか?</span><span class="sxs-lookup"><span data-stu-id="35bc9-127">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="35bc9-128">組織で Exchange Online が導入されていない場合は、「[Exchange と Microsoft Teams の連携](exchange-teams-interact.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-128">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="35bc9-129">組織で SharePoint Online が導入されていない場合は、「[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-129">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="35bc9-130">これらのネットワーク要件を満たしていることを確認したら、[Teams を展開する](./deploy-overview.md)準備ができている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35bc9-130">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](./deploy-overview.md).</span></span> <span data-ttu-id="35bc9-131">大規模な多国籍企業の場合、またはネットワークに制限があることがわかっている場合は、Teams 用にネットワークを評価し最適化する方法をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-131">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35bc9-132">**教育機関の場合**: 組織が教育機関であり、学生情報システム (SIS) を使用している場合は、Teams を展開する前に [学校データ同期を展開](/schooldatasync/)します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-132">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="35bc9-133">**オンプレミスの Skypefor Business Server の実行**: 組織でオンプレミスの Skype for Business Server (または Lync Server) を実行している場合、オンプレミスのディレクトリと Microsoft 365 または Office 365 を同期するよう [Azure AD Connect を構成](/skypeforbusiness/hybrid/configure-azure-ad-connect)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35bc9-133">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="35bc9-134">ベスト プラクティス: CQD と通話分析を使用してネットワークを監視する</span><span class="sxs-lookup"><span data-stu-id="35bc9-134">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="35bc9-135">[通話品質ダッシュボード (CQD)](turning-on-and-using-call-quality-dashboard.md) を使用して、Teams 内の通話と会議の品質に関する分析情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-135">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="35bc9-136">CQD は、品質、信頼性、およびユーザー エクスペリエンスを注意深く監視して、ネットワークを最適化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="35bc9-136">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="35bc9-137">CQD は、全体的なパターンが明らかになる可能性のある組織全体の集約テレメトリを調べます。これにより、問題を特定し、修復を計画できます。</span><span class="sxs-lookup"><span data-stu-id="35bc9-137">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="35bc9-138">さらに、CQD は、全体的な品質、信頼性、およびユーザー エクスペリエンスに関する分析情報を提供する豊富なメトリックス レポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-138">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="35bc9-139">[通話分析](set-up-call-analytics.md)を使用して、個々のユーザーの通話と会議の問題を調査します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-139">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="35bc9-140">ネットワークの最適化</span><span class="sxs-lookup"><span data-stu-id="35bc9-140">Network optimization</span></span>

<span data-ttu-id="35bc9-141">特に、中小企業で、Microsoft 365 または Office 365 を既に展開している場合などは、次のタスクはオプションであり、Teams の展開に必要ありません。</span><span class="sxs-lookup"><span data-stu-id="35bc9-141">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="35bc9-142">ネットワークに制限があることがわかっている場合など、ネットワークと Teams のパフォーマンスを最適化するのに、このガイダンスを使用してください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-142">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="35bc9-143">次の場合は、追加のネットワーク最適化を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35bc9-143">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="35bc9-144">Teams の実行速度が遅い (帯域幅が不足している可能性があります)</span><span class="sxs-lookup"><span data-stu-id="35bc9-144">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="35bc9-145">通話が途切れ続ける (ファイアウォールまたはプロキシ ブロッカーが原因である可能性があります)</span><span class="sxs-lookup"><span data-stu-id="35bc9-145">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="35bc9-146">通話が静的で途切れている、または音声がロボットのように聞こえる (ジッターまたはパケット損失の可能性があります)</span><span class="sxs-lookup"><span data-stu-id="35bc9-146">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="35bc9-147">ネットワーク障害を特定して修正するためのガイダンスを含む、ネットワーク最適化の詳細については、「[Microsoft 365 および Office 365 ネットワーク接続の原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-147">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="35bc9-148">ネットワークの最適化タスク</span><span class="sxs-lookup"><span data-stu-id="35bc9-148">Network optimization task</span></span></th>
<th><span data-ttu-id="35bc9-149">詳細</span><span class="sxs-lookup"><span data-stu-id="35bc9-149">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="35bc9-150">ネットワーク プランナー</span><span class="sxs-lookup"><span data-stu-id="35bc9-150">Network planner</span></span></td>
<td><p><span data-ttu-id="35bc9-151">組織の物理的な場所全体の帯域幅の計算やネットワーク要件など、ネットワークの評価については、<a href="https://admin.teams.microsoft.com">Teams 管理センター</a>の <a href="/microsoftteams/network-planner">ネットワーク プランナー</a> ツールを確認してください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-151">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="35bc9-152">ネットワークの詳細と Teams の使用状況を提示すると、Network Planner は、組織の物理的な場所で Teams とクラウドの音声を展開するためのネットワーク要件を計算します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-152">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="35bc9-153">シナリオの例については、「<a href="/microsoftteams/tutorial-network-planner-example">ネットワーク プランナーの使用 - シナリオの例</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-153">For an example scenario, see <a href="/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="35bc9-154">Teams のアドバイザー</span><span class="sxs-lookup"><span data-stu-id="35bc9-154">Advisor for Teams</span></span></td>
<td><span data-ttu-id="35bc9-155"><a href="/microsoftteams/use-advisor-teams-roll-out">Teams のアドバイザー</a>は、<a href="https://admin.teams.microsoft.com">Teams 管理センター</a>の一部です。</span><span class="sxs-lookup"><span data-stu-id="35bc9-155"><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="35bc9-156">Microsoft 365 または Office 365 の環境を評価し、Teams を正常に展開する前に更新または変更する必要がある最も一般的な構成を特定します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-156">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="35bc9-157">外部の名前解決</span><span class="sxs-lookup"><span data-stu-id="35bc9-157">External Name Resolution</span></span></td>
<td><span data-ttu-id="35bc9-158">Teams クライアントを実行するすべてのコンピュータが外部 DNS クエリを解決して、Microsoft 365 または Office 365 によって提供されるサービスを検出できること、およびファイアウォールが接続を妨げていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-158">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="35bc9-159">ファイアウォールのポートの構成については、「<a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 および Office 365 の URL と IP 範囲</a>」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-159">For information about configuring firewall ports, go to <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="35bc9-160">セッションの永続性を維持する</span><span class="sxs-lookup"><span data-stu-id="35bc9-160">Maintain session persistence</span></span></td>
<td><span data-ttu-id="35bc9-161">ファイアウォールが、UDP のマップされたネットワーク アドレス変換 (NAT) アドレスまたはポートを変更しないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-161">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="35bc9-162">NAT プール サイズの検証</span><span class="sxs-lookup"><span data-stu-id="35bc9-162">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="35bc9-163">ユーザー接続に必要なネットワーク アドレス変換 (NAT) プール サイズを検証します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-163">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="35bc9-164">複数のユーザーまたはデバイスが<a href="/office365/enterprise/nat-support-with-office-365">ネットワーク アドレス変換 (NAT) またはポート アドレス変換 (PAT)</a> を使用して Microsoft 365 または Office 365 にアクセスする場合は、パブリック ルーティングに対応している各 IP アドレスの背後にあるデバイスが、サポートされる数値を超過していないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35bc9-164">When multiple users and devices access Microsoft 365 or Office 365 using <a href="/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="35bc9-165">適切なパブリック IP アドレスを NAT プールに割り当ててポート枯渇を回避します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-165">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="35bc9-166">ポート枯渇は、内部ユーザーとデバイスが Microsoft 365 または Office 365 サービスに接続できない原因になります。</span><span class="sxs-lookup"><span data-stu-id="35bc9-166">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="35bc9-167">Microsoft データ センターへのルーティング</span><span class="sxs-lookup"><span data-stu-id="35bc9-167">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="35bc9-168"><a href="/office365/enterprise/client-connectivity">Microsoft データ センターへの最も効率的なルーティングを実装します</a>。</span><span class="sxs-lookup"><span data-stu-id="35bc9-168"><a href="/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="35bc9-169">ローカルまたは地域の出力ポイントを使用して、Microsoft ネットワークにできるだけ効率的に接続できる場所を特定します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-169">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="35bc9-170">侵入検知/防御のガイダンス</span><span class="sxs-lookup"><span data-stu-id="35bc9-170">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="35bc9-171">送信接続の追加のセキュリティ レイヤーとして環境に<a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">侵入検知</a>/防御システム (IDS/IPS) が配備されている場合は、すべての Microsoft 365 または Office 365 の URL を許可していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-171">If your environment has an <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="35bc9-172">スプリット トンネル VPN の構成</span><span class="sxs-lookup"><span data-stu-id="35bc9-172">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="35bc9-173">一般に<a href="/windows/security/identity-protection/vpn/vpn-routing">スプリット トンネル VPN</a> と呼ばれる、仮想プライベート ネットワーク (VPN) をバイパスする Teams トラフィックの代替パスを提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35bc9-173">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="35bc9-174">スプリット トンネリングとは、Microsoft 365 または Office 365 のトラフィックが VPN を通過せず、代わりに Microsoft 365 または Office 365 に直接送信されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-174">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="35bc9-175">VPN をバイパスすると、Teams の品質にプラスの影響があり、VPN デバイスと組織のネットワークからの負荷が軽減されます。</span><span class="sxs-lookup"><span data-stu-id="35bc9-175">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="35bc9-176">スプリット トンネル VPN を実装するには、VPN ベンダーにご相談ください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-176">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="35bc9-177">VPN をバイパスすることをお勧めするその他の理由:</span><span class="sxs-lookup"><span data-stu-id="35bc9-177">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="35bc9-178">VPN は通常、リアルタイム メディアをサポートするように設計または構成されていません。</span><span class="sxs-lookup"><span data-stu-id="35bc9-178">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="35bc9-179">一部の VPN は、UDP (Teams に必要) をサポートしていない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="35bc9-179">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="35bc9-180">また VPN は、既に暗号化されているメディア トラフィックの上に、暗号化の追加レイヤーを導入することもあります。</span><span class="sxs-lookup"><span data-stu-id="35bc9-180">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="35bc9-181">VPN デバイスを介したヘアピン型トラフィックが原因で、Teams への接続が効率的ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35bc9-181">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="35bc9-182">QoS の実装</span><span class="sxs-lookup"><span data-stu-id="35bc9-182">Implement QoS</span></span></td>
<td><span data-ttu-id="35bc9-183"><a href="/microsoftteams/qos-in-teams">サービスの品質 (QoS) を使用</a>して、パケットの優先度設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-183"><a href="/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="35bc9-184">これにより、Teams の通話品質が向上し、通話品質の監視とトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="35bc9-184">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="35bc9-185">QoS は、管理対象ネットワークのすべてのセグメントで実装される必要があります。</span><span class="sxs-lookup"><span data-stu-id="35bc9-185">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="35bc9-186">ネットワークに帯域幅が適切にプロビジョニングされているときでも、QoS は、予期しないネットワーク イベントが発生した場合のリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-186">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="35bc9-187">QoS では、音声トラフィックが優先されるため、想定外のイベントが発生しても品質に悪影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="35bc9-187">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="35bc9-188">Wi-Fi を最適化する</span><span class="sxs-lookup"><span data-stu-id="35bc9-188">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="35bc9-189">VPN と同様に、Wi-Fi ネットワークは必ずしもリアルタイム メディアをサポートするように設計または構成されているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="35bc9-189">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="35bc9-190">Teams をサポートするために Wi-Fi ネットワークのための計画を立てたり、最適化を行うことは、高品質の展開を実現するための重要な考慮事項です。</span><span class="sxs-lookup"><span data-stu-id="35bc9-190">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="35bc9-191">計画では、次の要因を考慮します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-191">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="35bc9-192">Wi-Fi ネットワーク上でメディア トラフィックが適切に優先されるように QoS または Wi-Fi マルチメディア (WMM) を実装します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-192">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="35bc9-193">W-Fi バンドとアクセス ポイントの配置を計画し最適化します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-193">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="35bc9-194">アクセス ポイントの配置に応じて、2.4 GHz 帯で十分なエクスペリエンスが提供される可能性がありますが、アクセス ポイントは、多くの場合にその帯域で動作するその他のコンシューマー デバイスによって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="35bc9-194">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="35bc9-195">5 GHz 帯は、その密度により、リアルタイム メディアにより適していますが、十分なカバレッジを得るためにより多くのアクセス ポイントを必要とします。</span><span class="sxs-lookup"><span data-stu-id="35bc9-195">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="35bc9-196">エンドポイントも、その帯をサポートしており、それらの帯を利用できるように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="35bc9-196">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="35bc9-197">デュアル バンドの Wi-Fi ネットワークを使用している場合は、バンド ステアリングの実装を検討してください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-197">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="35bc9-198"><em>バンド ステアリング</em>は Wi-Fi ベンダーによって実装された技術で、デュアル バンド クライアントが 5 GHz 帯を使用するように仕向けます。</span><span class="sxs-lookup"><span data-stu-id="35bc9-198"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="35bc9-199">同じチャネルのアクセス ポイントがお互いに近すぎる場合、信号のオーバーラップや意図しない競合が発生して、ユーザーのエクスペリエンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35bc9-199">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="35bc9-200">お互いに隣り合っているアクセス ポイントが、オーバーラップしていないチャネル上にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-200">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="35bc9-201">各無線ベンダーは、その無線ソリューションを展開する場合の推奨事項をそれぞれ持っています。</span><span class="sxs-lookup"><span data-stu-id="35bc9-201">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="35bc9-202">具体的なガイダンスについては、Wi-Fi ベンダーにご相談ください。</span><span class="sxs-lookup"><span data-stu-id="35bc9-202">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="35bc9-203">帯域幅要件</span><span class="sxs-lookup"><span data-stu-id="35bc9-203">Bandwidth requirements</span></span>

<span data-ttu-id="35bc9-204">Teams は、ネットワークの状態に関係なく、最高のオーディオ、ビデオ、およびコンテンツ共有エクスペリエンスを提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="35bc9-204">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="35bc9-205">とはいえ、帯域幅が不十分な場合、Teams はビデオ品質よりもオーディオ品質を優先します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-205">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="35bc9-206">帯域幅が制限されていない場合、Teams は、ハイファイ オーディオ、最大 1080p のビデオ解像度、最大 30fps (フレーム/秒) のビデオとコンテンツなど、メディア品質を最適化します。</span><span class="sxs-lookup"><span data-stu-id="35bc9-206">Where bandwidth isn't limited, Teams optimizes media quality, including high-fidelity audio, up to 1080p video resolution, and up to 30fps (frames per second) for video and content.</span></span>

<span data-ttu-id="35bc9-207">この表では、Teams がどのように帯域幅を使用するかについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="35bc9-207">This table describes how Teams uses bandwidth.</span></span> <span data-ttu-id="35bc9-208">Teams は常に帯域幅の使用率を控えめにし、1.5 Mbps 以下で HD ビデオ品質を提供できます。</span><span class="sxs-lookup"><span data-stu-id="35bc9-208">Teams is always conservative on bandwidth utilization and can deliver HD video quality in under 1.5Mbps.</span></span> <span data-ttu-id="35bc9-209">各オーディオ/ビデオ通話または会議の実際の帯域幅の消費量は、ビデオレイアウト、ビデオ解像度、1 秒あたりのビデオ フレームなどのいくつかの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="35bc9-209">The actual bandwidth consumption in each audio/video call or meeting will vary based on several factors, such as video layout, video resolution, and video frames per second.</span></span> <span data-ttu-id="35bc9-210">より多くの帯域幅が利用可能になると、最高のエクスペリエンスを提供するために品質と使用率を増加させるようになっています。</span><span class="sxs-lookup"><span data-stu-id="35bc9-210">When more bandwidth is available, quality and usage will increase to deliver the best experience.</span></span>

:::row:::
   :::column span="":::
      <span data-ttu-id="35bc9-211">**モダリティ**</span><span class="sxs-lookup"><span data-stu-id="35bc9-211">**Modality**</span></span>
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="35bc9-212">**帯域幅の要件 (ビットレート KB/秒 上昇/下降)**</span><span class="sxs-lookup"><span data-stu-id="35bc9-212">**Bandwidth requirements (bitrate KB/s up/down)**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="35bc9-213">**Minimum**</span><span class="sxs-lookup"><span data-stu-id="35bc9-213">**Minimum**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="35bc9-214">**推奨**</span><span class="sxs-lookup"><span data-stu-id="35bc9-214">**Recommended**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="35bc9-215">**最高のパフォーマンス**</span><span class="sxs-lookup"><span data-stu-id="35bc9-215">**Best performance**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="35bc9-216">**Audio**</span><span class="sxs-lookup"><span data-stu-id="35bc9-216">**Audio**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="35bc9-217">一対一</span><span class="sxs-lookup"><span data-stu-id="35bc9-217">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-218">10/10</span><span class="sxs-lookup"><span data-stu-id="35bc9-218">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-219">58/58</span><span class="sxs-lookup"><span data-stu-id="35bc9-219">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-220">76/76</span><span class="sxs-lookup"><span data-stu-id="35bc9-220">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="35bc9-221">会議</span><span class="sxs-lookup"><span data-stu-id="35bc9-221">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-222">10/10</span><span class="sxs-lookup"><span data-stu-id="35bc9-222">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-223">58/58</span><span class="sxs-lookup"><span data-stu-id="35bc9-223">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-224">76/76</span><span class="sxs-lookup"><span data-stu-id="35bc9-224">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="35bc9-225">**ビデオ**</span><span class="sxs-lookup"><span data-stu-id="35bc9-225">**Video**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="35bc9-226">一対一</span><span class="sxs-lookup"><span data-stu-id="35bc9-226">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-227">150/150</span><span class="sxs-lookup"><span data-stu-id="35bc9-227">150/150</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-228">1,500/1,500</span><span class="sxs-lookup"><span data-stu-id="35bc9-228">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-229">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="35bc9-229">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="35bc9-230">会議</span><span class="sxs-lookup"><span data-stu-id="35bc9-230">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-231">150/200</span><span class="sxs-lookup"><span data-stu-id="35bc9-231">150/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-232">2,500/4,000</span><span class="sxs-lookup"><span data-stu-id="35bc9-232">2,500/4,000</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-233">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="35bc9-233">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="35bc9-234">**画面共有**</span><span class="sxs-lookup"><span data-stu-id="35bc9-234">**Screen sharing**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="35bc9-235">一対一</span><span class="sxs-lookup"><span data-stu-id="35bc9-235">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-236">200/200</span><span class="sxs-lookup"><span data-stu-id="35bc9-236">200/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-237">1,500/1,500</span><span class="sxs-lookup"><span data-stu-id="35bc9-237">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-238">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="35bc9-238">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="35bc9-239">会議</span><span class="sxs-lookup"><span data-stu-id="35bc9-239">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-240">250/250</span><span class="sxs-lookup"><span data-stu-id="35bc9-240">250/250</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-241">2,500/2,500</span><span class="sxs-lookup"><span data-stu-id="35bc9-241">2,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-242">4,000/4,000</span><span class="sxs-lookup"><span data-stu-id="35bc9-242">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="35bc9-243">**Together モード**</span><span class="sxs-lookup"><span data-stu-id="35bc9-243">**Together Mode**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="35bc9-244">一対一</span><span class="sxs-lookup"><span data-stu-id="35bc9-244">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-245">該当なし</span><span class="sxs-lookup"><span data-stu-id="35bc9-245">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-246">該当なし</span><span class="sxs-lookup"><span data-stu-id="35bc9-246">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-247">該当なし</span><span class="sxs-lookup"><span data-stu-id="35bc9-247">N/A</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="35bc9-248">会議</span><span class="sxs-lookup"><span data-stu-id="35bc9-248">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-249">1,000/1,500</span><span class="sxs-lookup"><span data-stu-id="35bc9-249">1,000/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-250">1,500/2,500</span><span class="sxs-lookup"><span data-stu-id="35bc9-250">1,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="35bc9-251">2,500/4,000</span><span class="sxs-lookup"><span data-stu-id="35bc9-251">2,500/4,000</span></span>
   :::column-end:::
:::row-end:::

<span data-ttu-id="35bc9-252">**最小**、**推奨**、および **最高のパフォーマンス** の帯域幅の要件は、エンドポイントごとの使用状況に基づきます。</span><span class="sxs-lookup"><span data-stu-id="35bc9-252">**Minimum**, **Recommended**, and **Best performance** bandwidth requirements are based on per-endpoint usage.</span></span> <span data-ttu-id="35bc9-253">一般には、コンピューター デバイスやモバイル デバイスなどのユーザーごとに 1 つのエンドポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="35bc9-253">Typically, there's one endpoint per user, such as a computer or mobile device.</span></span> <span data-ttu-id="35bc9-254">ただし、ユーザーがコンピューター *と* モバイル デバイスの *両方* で Teams 会議に参加した場合は、2 つのエンドポイントがそのユーザーに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="35bc9-254">However, if a user joins a Teams meeting on *both* a computer *and* a mobile device, two endpoints are associated with that user.</span></span>

- <span data-ttu-id="35bc9-255">ビデオ通話の **最小** 帯域幅要件は、最大 240p の解像度で、画面共通コンテンツのフレーム レートは Adaptive 1.875 から 7.5fps で、Together モードのギャラリー ビデオは最大 540p 解像度です。</span><span class="sxs-lookup"><span data-stu-id="35bc9-255">**Minimum** Bandwidth requirements for video calls are up to 240p resolution, screen sharing content frame rates adaptive 1.875 to 7.5fps, and Together Mode/Large Gallery video up to 540p resolution.</span></span>  

- <span data-ttu-id="35bc9-256">ビデオ通話の **推奨** 帯域幅要件は、最大 1080p の解像度<sup>\*</sup>で、画面共通コンテンツのフレーム レートは Adaptive 7.5 から 30fps で、Together モードのギャラリー ビデオは最大 1080p 解像度<sup>\*</sup>です。</span><span class="sxs-lookup"><span data-stu-id="35bc9-256">**Recommended** Bandwidth requirements for video calls are up to 1080p resolution<sup>\*</sup>, screen sharing content frame rates adaptive 7.5 to 30fps, and Together Mode/Large Gallery video up to 1080p resolution<sup>\*</sup>.</span></span>  

- <span data-ttu-id="35bc9-257">**最高のパフォーマンス** ガイダンスでは、大規模な出席者の会議向けのハイファイ ビデオ、高損失環境で、かつ画面共有フレーム レートが Adaptive 15 から 30fps の高モーション コンテンツを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="35bc9-257">**Best Performance** Guidance allows higher fidelity video for larger attendee meetings, high loss environments, and higher motion content with screen sharing content frame rates adaptive 15 to 30fps.</span></span>

<span data-ttu-id="35bc9-258"><sup>\*</sup>最大 1080p の画質を想定していても、ネットワーク状態に応じて、ビデオ解像度や品質が適宜最適化されます。</span><span class="sxs-lookup"><span data-stu-id="35bc9-258"><sup>\*</sup>Expect up to 1080p quality but depending on your network conditions, video resolution and quality will be optimized accordingly.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="35bc9-259">関連トピック</span><span class="sxs-lookup"><span data-stu-id="35bc9-259">Related Topics</span></span>

[<span data-ttu-id="35bc9-260">Microsoft 365 および Office 365 ネットワーク接続の原則</span><span class="sxs-lookup"><span data-stu-id="35bc9-260">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="35bc9-261">世界のエンドポイント: Skype for Business Online および Teams </span><span class="sxs-lookup"><span data-stu-id="35bc9-261">Worldwide endpoints: Skype for Business Online and Teams</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="35bc9-262">Teams 向けのプロキシ サーバー</span><span class="sxs-lookup"><span data-stu-id="35bc9-262">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="35bc9-263">Teams 内のメディア: 会議がシンプルな理由</span><span class="sxs-lookup"><span data-stu-id="35bc9-263">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="35bc9-264">Teams 内のメディア: メディア フローを深く掘り下げる</span><span class="sxs-lookup"><span data-stu-id="35bc9-264">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="35bc9-265">Teams での ID モデルと認証</span><span class="sxs-lookup"><span data-stu-id="35bc9-265">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="35bc9-266">Teams の展開方法</span><span class="sxs-lookup"><span data-stu-id="35bc9-266">How to roll out Teams</span></span>](./deploy-overview.md)

[<span data-ttu-id="35bc9-267">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="35bc9-267">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
