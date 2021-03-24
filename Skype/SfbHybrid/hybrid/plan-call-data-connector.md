---
title: 通話データ コネクタの計画|通話品質ダッシュボードの監視ハイブリッド分析
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: ハイブリッド シナリオでの Skype for Business Online テレメトリ ツールの使用によるオンプレミスの実装の監視の概要。
ms.openlocfilehash: f47f0969d102408299678842b18bb503eaf6aea0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110553"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="8ae77-103">通話データ コネクタの計画</span><span class="sxs-lookup"><span data-stu-id="8ae77-103">Plan Call Data Connector</span></span>

## <a name="overview"></a><span data-ttu-id="8ae77-104">概要</span><span class="sxs-lookup"><span data-stu-id="8ae77-104">Overview</span></span>

<span data-ttu-id="8ae77-105">このトピックでは、Skype for Business Server Call Data Connector を実装するための利点、計画上の考慮事項、および要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ae77-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="8ae77-106">通話データ コネクタの構成の詳細については、「Configure Call Data [Connector」を参照してください](configure-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="8ae77-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>


<span data-ttu-id="8ae77-107">通話データ コネクタは、すべてのユーザーの通話品質を監視するために、さまざまなオンプレミスツールとオンライン ツールを使用する必要がなくなったため、ハイブリッド環境での通話監視を大幅に簡素化します。</span><span class="sxs-lookup"><span data-stu-id="8ae77-107">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="8ae77-108">ユーザーがオンプレミスまたはオンラインの場合は、組織全体の通話品質をオンラインで表示できます。</span><span class="sxs-lookup"><span data-stu-id="8ae77-108">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="8ae77-109">通話データ コネクタを使用すると、1 つのツールセットを使用して次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8ae77-109">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="8ae77-110">Microsoft Teams、Skype for Business Online、Skype for Business Server 全体でユーザー エクスペリエンスを監視します。</span><span class="sxs-lookup"><span data-stu-id="8ae77-110">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="8ae77-111">ネットワーク全体の問題を表示およびトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="8ae77-111">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="8ae77-112">Call Analytics にヘルプデスクと管理者の役割を割り当て、ヘルプデスクの作業者が自分の責任領域を表示およびトラブルシューティングできます。</span><span class="sxs-lookup"><span data-stu-id="8ae77-112">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="8ae77-113">次の図に示すように、Skype for Business Server は通話データをクラウド サービスにプッシュして、Skype for Business Online Call Analytics (CA) ツールと通話品質ダッシュボード (CQD) ツールを活用できます。</span><span class="sxs-lookup"><span data-stu-id="8ae77-113">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![SfB クラウドボイスメール](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="8ae77-115">サーバーは、QoE (QoE) データと通話詳細記録 (CDR) データの両方をオンライン サービスにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="8ae77-115">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="8ae77-116">Call Analytics および CQD ツールを使用すると、通話の品質を監視し、Microsoft Teams および Skype for Business サービスの接続の問題を次のようにトラブルシューティングできます。</span><span class="sxs-lookup"><span data-stu-id="8ae77-116">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="8ae77-117">Call Analytics は、特定の呼び出しに関する品質の問題に焦点を当てします。</span><span class="sxs-lookup"><span data-stu-id="8ae77-117">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="8ae77-118">Skype for Business アカウントの各ユーザーの通話と会議に関する詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="8ae77-118">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="8ae77-119">Call Analytics を使用すると、ヘルプデスクのオペレーターにアクセス許可を割り当て、その後、Skype for Business 管理センターの残りの部分にアクセスせずに通話を監視できます。</span><span class="sxs-lookup"><span data-stu-id="8ae77-119">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="8ae77-120">品質ダッシュボードの呼び出しは、組織全体のネットワークパフォーマンスと問題に焦点を当て、</span><span class="sxs-lookup"><span data-stu-id="8ae77-120">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="8ae77-121">Skype for Business 管理者およびネットワーク エンジニアは、このツールを使用してネットワークパフォーマンスのトラブルシューティングと最適化を行います。</span><span class="sxs-lookup"><span data-stu-id="8ae77-121">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="8ae77-122">詳細については、「Call [Analytics and Call Quality Dashboard」を参照してください](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="8ae77-122">For more information, see [Call Analytics and Call Quality Dashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="8ae77-123">もちろん、一部の通話品質データをオンプレミスに保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ae77-123">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="8ae77-124">たとえば、カスタマイズされたレポートとワークフローでサード パーティ製のソリューションを使用している場合などです。</span><span class="sxs-lookup"><span data-stu-id="8ae77-124">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="8ae77-125">データ コネクタの呼び出しでは、次の図に示すように、データのコピーをオンプレミス サーバーに保持しながら、オンライン サービスへのデータの送信を構成できます。</span><span class="sxs-lookup"><span data-stu-id="8ae77-125">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![SfB クラウドボイスメール](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a><span data-ttu-id="8ae77-127">要件</span><span class="sxs-lookup"><span data-stu-id="8ae77-127">Requirements</span></span>

<span data-ttu-id="8ae77-128">次の要件では、サポートされているトポロジに Skype for Business Server が既に展開済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ae77-128">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="8ae77-129">Skype for Business Server およびサポートされるトポロジの展開の詳細については、「トポロジの基本 [」を参照してください](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="8ae77-129">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md).</span></span> <span data-ttu-id="8ae77-130">通話データ コネクタを構成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ae77-130">To configure Call Data Connector, you must:</span></span>

- <span data-ttu-id="8ae77-131">ハイブリッド接続を有効にする。</span><span class="sxs-lookup"><span data-stu-id="8ae77-131">Enable Hybrid connectivity.</span></span> <span data-ttu-id="8ae77-132">Skype for Business Server が既に展開済みで、通話データ コネクタを有効にする場合は、オンプレミス環境とオンライン環境の間にハイブリッド接続がセットアップされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ae77-132">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="8ae77-133">これは、分割ドメイン構成と呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ae77-133">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="8ae77-134">詳細については、「Plan hybrid connectivity between Skype for Business Server and [Microsoft 365 or Office 365」](plan-hybrid-connectivity.md) および「Configure hybrid connectivity between Skype for Business Server and [Microsoft 365 or Office 365」](configure-hybrid-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ae77-134">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="8ae77-135">Microsoft 365 または 365 組織Office認証し、次の役割を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="8ae77-135">Authenticate to your Microsoft 365 or Office 365 organization and ensure that you have the following roles enabled:</span></span>

  - <span data-ttu-id="8ae77-136">Skype for Business Server Administrator</span><span class="sxs-lookup"><span data-stu-id="8ae77-136">Skype for Business Server Administrator</span></span>
  - <span data-ttu-id="8ae77-137">Microsoft 365 または Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="8ae77-137">Microsoft 365 or Office 365 Global Administrator</span></span>

- <span data-ttu-id="8ae77-138">まだ実行していない場合は、「Microsoft Teams および Skype for Business Online の通話品質ダッシュボードを有効にして使用する」の説明に従って、[通話品質ダッシュボード] を [オンにしてください](/microsoftteams/turning-on-and-using-call-quality-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="8ae77-138">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>

- <span data-ttu-id="8ae77-139">ローカルの LCSCdr データベースと QoEMetrics データベースを使用して、監視のフロントエンド プールを有効にする。</span><span class="sxs-lookup"><span data-stu-id="8ae77-139">Enable the front end pool for Monitoring, with local LCSCdr and QoEMetrics databases.</span></span> <span data-ttu-id="8ae77-140">この場合、データ コネクタの呼び出しには、使用する指標データが含まれておりかねない。</span><span class="sxs-lookup"><span data-stu-id="8ae77-140">Without this, Call Data Connector won't have metrics data to work with.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ae77-141">フロントエンド プールで監視が有効になっていない場合、データ コネクタの呼び出しは機能しません。</span><span class="sxs-lookup"><span data-stu-id="8ae77-141">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

- <span data-ttu-id="8ae77-142">サーバー間 [認証が適切に構成されています](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="8ae77-142">Properly configured [server-to-server authentication](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md).</span></span> 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="8ae77-143">オンプレミスおよびオンライン通話品質ダッシュボード (CQD) レポートの比較</span><span class="sxs-lookup"><span data-stu-id="8ae77-143">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="8ae77-144">機能レポート</span><span class="sxs-lookup"><span data-stu-id="8ae77-144">Feature reports</span></span> | <span data-ttu-id="8ae77-145">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8ae77-145">Skype for Business Online</span></span> | <span data-ttu-id="8ae77-146">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8ae77-146">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="8ae77-147">アプリケーション共有メトリック</span><span class="sxs-lookup"><span data-stu-id="8ae77-147">Application sharing metric</span></span> |<span data-ttu-id="8ae77-148">はい</span><span class="sxs-lookup"><span data-stu-id="8ae77-148">Yes</span></span> | <span data-ttu-id="8ae77-149">制限付き</span><span class="sxs-lookup"><span data-stu-id="8ae77-149">Limited</span></span> |
| <span data-ttu-id="8ae77-150">顧客の構築情報</span><span class="sxs-lookup"><span data-stu-id="8ae77-150">Customer building information</span></span>| <span data-ttu-id="8ae77-151">はい</span><span class="sxs-lookup"><span data-stu-id="8ae77-151">Yes</span></span> | <span data-ttu-id="8ae77-152">はい</span><span class="sxs-lookup"><span data-stu-id="8ae77-152">Yes</span></span> |
| <span data-ttu-id="8ae77-153">ドリルダウン分析</span><span class="sxs-lookup"><span data-stu-id="8ae77-153">Drill-down analytics</span></span> | <span data-ttu-id="8ae77-154">はい</span><span class="sxs-lookup"><span data-stu-id="8ae77-154">Yes</span></span> | <span data-ttu-id="8ae77-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="8ae77-155">No</span></span> |
| <span data-ttu-id="8ae77-156">メディアの信頼性の指標</span><span class="sxs-lookup"><span data-stu-id="8ae77-156">Media reliability metrics</span></span> | <span data-ttu-id="8ae77-157">はい</span><span class="sxs-lookup"><span data-stu-id="8ae77-157">Yes</span></span> | <span data-ttu-id="8ae77-158">制限付き</span><span class="sxs-lookup"><span data-stu-id="8ae77-158">Limited</span></span> |
| <span data-ttu-id="8ae77-159">アウトオブザボックス レポート</span><span class="sxs-lookup"><span data-stu-id="8ae77-159">Out-of-the-box reports</span></span> | <span data-ttu-id="8ae77-160">はい</span><span class="sxs-lookup"><span data-stu-id="8ae77-160">Yes</span></span> | <span data-ttu-id="8ae77-161">はい</span><span class="sxs-lookup"><span data-stu-id="8ae77-161">Yes</span></span> |
| <span data-ttu-id="8ae77-162">概要レポート</span><span class="sxs-lookup"><span data-stu-id="8ae77-162">Overview reports</span></span> | <span data-ttu-id="8ae77-163">はい</span><span class="sxs-lookup"><span data-stu-id="8ae77-163">Yes</span></span> | <span data-ttu-id="8ae77-164">いいえ</span><span class="sxs-lookup"><span data-stu-id="8ae77-164">No</span></span> |
| <span data-ttu-id="8ae77-165">ユーザーごとのレポート</span><span class="sxs-lookup"><span data-stu-id="8ae77-165">Per user reports</span></span> | <span data-ttu-id="8ae77-166">はい</span><span class="sxs-lookup"><span data-stu-id="8ae77-166">Yes</span></span> | <span data-ttu-id="8ae77-167">はい</span><span class="sxs-lookup"><span data-stu-id="8ae77-167">Yes</span></span> |
| <span data-ttu-id="8ae77-168">レポート セットのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="8ae77-168">Report set customization</span></span> <br> <span data-ttu-id="8ae77-169">(レポートの追加、削除、変更)</span><span class="sxs-lookup"><span data-stu-id="8ae77-169">(add, delete, modify reports)</span></span> | <span data-ttu-id="8ae77-170">はい</span><span class="sxs-lookup"><span data-stu-id="8ae77-170">Yes</span></span> | <span data-ttu-id="8ae77-171">はい</span><span class="sxs-lookup"><span data-stu-id="8ae77-171">Yes</span></span> |
| <span data-ttu-id="8ae77-172">ビデオベースの画面共有の指標</span><span class="sxs-lookup"><span data-stu-id="8ae77-172">Video-based screen sharing metrics</span></span> | <span data-ttu-id="8ae77-173">はい</span><span class="sxs-lookup"><span data-stu-id="8ae77-173">Yes</span></span> | <span data-ttu-id="8ae77-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="8ae77-174">No</span></span> |
| <span data-ttu-id="8ae77-175">プログラムによるアクセス用のデータ API</span><span class="sxs-lookup"><span data-stu-id="8ae77-175">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="8ae77-176">CQD</span><span class="sxs-lookup"><span data-stu-id="8ae77-176">to CQD</span></span> | <span data-ttu-id="8ae77-177">いいえ</span><span class="sxs-lookup"><span data-stu-id="8ae77-177">No</span></span> | <span data-ttu-id="8ae77-178">はい</span><span class="sxs-lookup"><span data-stu-id="8ae77-178">Yes</span></span> |
||||