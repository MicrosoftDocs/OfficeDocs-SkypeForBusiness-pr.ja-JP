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
description: ハイブリッド シナリオでの Skype for Businessテレメトリ ツールを使用してオンプレミスの実装を監視する方法の概要。
ms.openlocfilehash: 7b6076224280446b7fc52c505fe5fc3ab8d41be4
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856356"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="9f710-103">通話データ コネクタの計画</span><span class="sxs-lookup"><span data-stu-id="9f710-103">Plan Call Data Connector</span></span>

## <a name="overview"></a><span data-ttu-id="9f710-104">概要</span><span class="sxs-lookup"><span data-stu-id="9f710-104">Overview</span></span>

<span data-ttu-id="9f710-105">このトピックでは、通話データ コネクタを実装するための利点、計画の考慮事項、およびSkype for Business Serverについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9f710-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="9f710-106">通話データ コネクタの構成の詳細については、「Configure Call Data [Connector」を参照してください](configure-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="9f710-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>


<span data-ttu-id="9f710-107">通話データ コネクタは、すべてのユーザーの通話品質を監視するために、さまざまなオンプレミスツールとオンライン ツールを使用する必要がなくなったため、ハイブリッド環境での通話監視を大幅に簡素化します。</span><span class="sxs-lookup"><span data-stu-id="9f710-107">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="9f710-108">ユーザーがオンプレミスまたはオンラインの場合は、組織全体の通話品質をオンラインで表示できます。</span><span class="sxs-lookup"><span data-stu-id="9f710-108">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="9f710-109">通話データ コネクタを使用すると、1 つのツールセットを使用して次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9f710-109">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="9f710-110">ユーザー エクスペリエンスをオンライン、Microsoft Teams、Skype for Business全体で監視Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="9f710-110">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="9f710-111">ネットワーク全体の問題を表示およびトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="9f710-111">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="9f710-112">Call Analytics にヘルプデスクと管理者の役割を割り当て、ヘルプデスクの作業者が自分の責任領域を表示およびトラブルシューティングできます。</span><span class="sxs-lookup"><span data-stu-id="9f710-112">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="9f710-113">次の図に示すように、Skype for Business Server は通話データをクラウド サービスにプッシュして、Skype for Business Online Call Analytics (CA) ツールと通話品質ダッシュボード (CQD) ツールを活用できます。</span><span class="sxs-lookup"><span data-stu-id="9f710-113">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![SfB クラウド ボイスメール](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="9f710-115">サーバーは、QoE (QoE) データと通話詳細記録 (CDR) データの両方をオンライン サービスにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="9f710-115">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="9f710-116">Call Analytics および CQD ツールを使用すると、次のように、通話の品質を監視し、Microsoft TeamsおよびSkype for Businessの接続の問題をトラブルシューティングできます。</span><span class="sxs-lookup"><span data-stu-id="9f710-116">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="9f710-117">Call Analytics は、特定の呼び出しに関する品質の問題に焦点を当てします。</span><span class="sxs-lookup"><span data-stu-id="9f710-117">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="9f710-118">このページには、1 つのアカウント内の各ユーザーの通話と会議に関するSkype for Business表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f710-118">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="9f710-119">Call Analytics を使用すると、ヘルプデスクのオペレーターにアクセス許可を割り当て、その後、管理者センターの残りの部分にアクセスせずに通話を監視Skype for Businessできます。</span><span class="sxs-lookup"><span data-stu-id="9f710-119">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="9f710-120">品質ダッシュボードの呼び出しは、組織全体のネットワークパフォーマンスと問題に焦点を当て、</span><span class="sxs-lookup"><span data-stu-id="9f710-120">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="9f710-121">Skype for Business管理者およびネットワーク エンジニアは、このツールを使用してネットワークパフォーマンスのトラブルシューティングと最適化を行います。</span><span class="sxs-lookup"><span data-stu-id="9f710-121">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="9f710-122">詳細については、「Call [Analytics and Call Quality Dashboard」を参照してください](/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="9f710-122">For more information, see [Call Analytics and Call Quality Dashboard](/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="9f710-123">もちろん、一部の通話品質データをオンプレミスに保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f710-123">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="9f710-124">たとえば、カスタマイズされたレポートとワークフローでサード パーティ製のソリューションを使用している場合などです。</span><span class="sxs-lookup"><span data-stu-id="9f710-124">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="9f710-125">データ コネクタの呼び出しでは、次の図に示すように、データのコピーをオンプレミス サーバーに保持しながら、オンライン サービスへのデータの送信を構成できます。</span><span class="sxs-lookup"><span data-stu-id="9f710-125">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![SfB クラウド ボイスメール](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a><span data-ttu-id="9f710-127">要件</span><span class="sxs-lookup"><span data-stu-id="9f710-127">Requirements</span></span>

<span data-ttu-id="9f710-128">次の要件では、サポートされているトポロジSkype for Business Server既に展開済みである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f710-128">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="9f710-129">サポートされているトポロジおよびサポートされているトポロジSkype for Business Server詳細については、「トポロジの基本[」を参照してください](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="9f710-129">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md).</span></span> <span data-ttu-id="9f710-130">通話データ コネクタを構成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f710-130">To configure Call Data Connector, you must:</span></span>

- <span data-ttu-id="9f710-131">ハイブリッド接続を有効にする。</span><span class="sxs-lookup"><span data-stu-id="9f710-131">Enable Hybrid connectivity.</span></span> <span data-ttu-id="9f710-132">既に展開済Skype for Business Serverデータ コネクタの呼び出しを有効にする場合は、オンプレミス環境とオンライン環境の間にハイブリッド接続がセットアップされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f710-132">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="9f710-133">これは、分割ドメイン構成と呼ばれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9f710-133">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="9f710-134">詳細については、「Skype for Business Server と Microsoft 365 または Office 365 のハイブリッド接続を計画する」および[「Skype for Business Server](plan-hybrid-connectivity.md)と Microsoft 365 または Office 365 のハイブリッド接続を構成する」[を参照してください](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="9f710-134">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="9f710-135">組織の組織Microsoft 365またはOffice 365認証し、次の役割が有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="9f710-135">Authenticate to your Microsoft 365 or Office 365 organization and ensure that you have the following roles enabled:</span></span>

  - <span data-ttu-id="9f710-136">Skype for Business Server管理者</span><span class="sxs-lookup"><span data-stu-id="9f710-136">Skype for Business Server Administrator</span></span>
  - <span data-ttu-id="9f710-137">Microsoft 365またはOffice 365管理者</span><span class="sxs-lookup"><span data-stu-id="9f710-137">Microsoft 365 or Office 365 Global Administrator</span></span>

- <span data-ttu-id="9f710-138">まだ有効にしていない場合は、「通話品質ダッシュボードを有効にして使用する」の説明に従って、[通話品質ダッシュボード] をオンMicrosoft Teams[オンラインSkype for Businessします](/microsoftteams/turning-on-and-using-call-quality-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="9f710-138">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>

- <span data-ttu-id="9f710-139">ローカルの LCSCdr データベースと QoEMetrics データベースを使用して、監視のフロントエンド プールを有効にする。</span><span class="sxs-lookup"><span data-stu-id="9f710-139">Enable the front end pool for Monitoring, with local LCSCdr and QoEMetrics databases.</span></span> <span data-ttu-id="9f710-140">この場合、データ コネクタの呼び出しには、使用する指標データが含まれておりかねない。</span><span class="sxs-lookup"><span data-stu-id="9f710-140">Without this, Call Data Connector won't have metrics data to work with.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f710-141">フロントエンド プールで監視が有効になっていない場合、データ コネクタの呼び出しは機能しません。</span><span class="sxs-lookup"><span data-stu-id="9f710-141">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

- <span data-ttu-id="9f710-142">サーバー間 [認証が適切に構成されています](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="9f710-142">Properly configured [server-to-server authentication](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md).</span></span> 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="9f710-143">オンプレミスおよびオンライン通話品質ダッシュボード (CQD) レポートの比較</span><span class="sxs-lookup"><span data-stu-id="9f710-143">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="9f710-144">機能レポート</span><span class="sxs-lookup"><span data-stu-id="9f710-144">Feature reports</span></span> | <span data-ttu-id="9f710-145">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9f710-145">Skype for Business Online</span></span> | <span data-ttu-id="9f710-146">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9f710-146">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="9f710-147">アプリケーション共有メトリック</span><span class="sxs-lookup"><span data-stu-id="9f710-147">Application sharing metric</span></span> |<span data-ttu-id="9f710-148">はい</span><span class="sxs-lookup"><span data-stu-id="9f710-148">Yes</span></span> | <span data-ttu-id="9f710-149">制限付き</span><span class="sxs-lookup"><span data-stu-id="9f710-149">Limited</span></span> |
| <span data-ttu-id="9f710-150">顧客の構築情報</span><span class="sxs-lookup"><span data-stu-id="9f710-150">Customer building information</span></span>| <span data-ttu-id="9f710-151">はい</span><span class="sxs-lookup"><span data-stu-id="9f710-151">Yes</span></span> | <span data-ttu-id="9f710-152">はい</span><span class="sxs-lookup"><span data-stu-id="9f710-152">Yes</span></span> |
| <span data-ttu-id="9f710-153">ドリルダウン分析</span><span class="sxs-lookup"><span data-stu-id="9f710-153">Drill-down analytics</span></span> | <span data-ttu-id="9f710-154">はい</span><span class="sxs-lookup"><span data-stu-id="9f710-154">Yes</span></span> | <span data-ttu-id="9f710-155">不要</span><span class="sxs-lookup"><span data-stu-id="9f710-155">No</span></span> |
| <span data-ttu-id="9f710-156">メディアの信頼性の指標</span><span class="sxs-lookup"><span data-stu-id="9f710-156">Media reliability metrics</span></span> | <span data-ttu-id="9f710-157">はい</span><span class="sxs-lookup"><span data-stu-id="9f710-157">Yes</span></span> | <span data-ttu-id="9f710-158">制限付き</span><span class="sxs-lookup"><span data-stu-id="9f710-158">Limited</span></span> |
| <span data-ttu-id="9f710-159">アウトオブザボックス レポート</span><span class="sxs-lookup"><span data-stu-id="9f710-159">Out-of-the-box reports</span></span> | <span data-ttu-id="9f710-160">はい</span><span class="sxs-lookup"><span data-stu-id="9f710-160">Yes</span></span> | <span data-ttu-id="9f710-161">はい</span><span class="sxs-lookup"><span data-stu-id="9f710-161">Yes</span></span> |
| <span data-ttu-id="9f710-162">概要レポート</span><span class="sxs-lookup"><span data-stu-id="9f710-162">Overview reports</span></span> | <span data-ttu-id="9f710-163">はい</span><span class="sxs-lookup"><span data-stu-id="9f710-163">Yes</span></span> | <span data-ttu-id="9f710-164">不要</span><span class="sxs-lookup"><span data-stu-id="9f710-164">No</span></span> |
| <span data-ttu-id="9f710-165">ユーザーごとのレポート</span><span class="sxs-lookup"><span data-stu-id="9f710-165">Per user reports</span></span> | <span data-ttu-id="9f710-166">はい</span><span class="sxs-lookup"><span data-stu-id="9f710-166">Yes</span></span> | <span data-ttu-id="9f710-167">はい</span><span class="sxs-lookup"><span data-stu-id="9f710-167">Yes</span></span> |
| <span data-ttu-id="9f710-168">レポート セットのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="9f710-168">Report set customization</span></span> <br> <span data-ttu-id="9f710-169">(レポートの追加、削除、変更)</span><span class="sxs-lookup"><span data-stu-id="9f710-169">(add, delete, modify reports)</span></span> | <span data-ttu-id="9f710-170">はい</span><span class="sxs-lookup"><span data-stu-id="9f710-170">Yes</span></span> | <span data-ttu-id="9f710-171">はい</span><span class="sxs-lookup"><span data-stu-id="9f710-171">Yes</span></span> |
| <span data-ttu-id="9f710-172">ビデオベースの画面共有の指標</span><span class="sxs-lookup"><span data-stu-id="9f710-172">Video-based screen sharing metrics</span></span> | <span data-ttu-id="9f710-173">はい</span><span class="sxs-lookup"><span data-stu-id="9f710-173">Yes</span></span> | <span data-ttu-id="9f710-174">不要</span><span class="sxs-lookup"><span data-stu-id="9f710-174">No</span></span> |
| <span data-ttu-id="9f710-175">プログラムによるアクセス用のデータ API</span><span class="sxs-lookup"><span data-stu-id="9f710-175">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="9f710-176">CQD</span><span class="sxs-lookup"><span data-stu-id="9f710-176">to CQD</span></span> | <span data-ttu-id="9f710-177">不要</span><span class="sxs-lookup"><span data-stu-id="9f710-177">No</span></span> | <span data-ttu-id="9f710-178">はい</span><span class="sxs-lookup"><span data-stu-id="9f710-178">Yes</span></span> |
||||