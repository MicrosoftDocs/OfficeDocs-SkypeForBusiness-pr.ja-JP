---
title: 通話データコネクタを計画する |通話品質ダッシュボードのハイブリッド分析の監視
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Skype for Business Online テレメトリツールを使用した、ハイブリッドシナリオでのオンプレミスの実装の監視の概要。
ms.openlocfilehash: 3300ad17b109ac069c4f7382f610dd0214b30197
ms.sourcegitcommit: 1f84b0edc4e418259b9f6392370e2cc4dc70df82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2019
ms.locfileid: "37328429"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="7b0bf-103">通話データコネクタを計画する</span><span class="sxs-lookup"><span data-stu-id="7b0bf-103">Plan Call Data Connector</span></span>

## <a name="overview"></a><span data-ttu-id="7b0bf-104">概要</span><span class="sxs-lookup"><span data-stu-id="7b0bf-104">Overview</span></span>

<span data-ttu-id="7b0bf-105">このトピックでは、Skype for Business Server Call Data Connector を実装する場合の利点、計画に関する考慮事項、および要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="7b0bf-106">通話データコネクタの構成の詳細については、「 [Configure Call Data connector](configure-call-data-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>


<span data-ttu-id="7b0bf-107">通話データコネクタを使用すると、ユーザーの通話品質をすべて監視するためにオンプレミスとオンラインツールの異なるセットを使用する必要がなくなるため、ハイブリッド環境での通話監視が大幅に簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-107">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="7b0bf-108">ユーザーがオンプレミスまたはオンラインに所属しているかどうかにかかわらず、組織全体の通話品質をオンラインで表示するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-108">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="7b0bf-109">Call Data Connector を使用すると、1つのツールセットを使用して次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-109">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="7b0bf-110">Microsoft Teams、Skype for Business Online、Skype for Business Server でのユーザーの作業状況を監視します。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-110">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="7b0bf-111">ネットワーク全体の問題を表示し、トラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-111">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="7b0bf-112">ヘルプデスクおよび管理者の役割を呼び出し分析に割り当てて、ヘルプデスクの作業者が自分の責任範囲を表示およびトラブルシューティングできるようにします。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-112">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="7b0bf-113">通話データコネクタを使用すると、Skype for business Server は、次の図に示すように、Skype for Business Online Call Analytics (CA) と通話品質ダッシュボード (CQD) ツールを利用できるように、クラウドサービスに呼び出しデータをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-113">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![SfB クラウドボイスメール](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="7b0bf-115">サーバーは、QoE (Quality of Experience) データと通話詳細記録 (CDR) データの両方をオンラインサービスにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-115">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="7b0bf-116">Call Analytics and CQD tools を使用すると、次のように、通話の品質を監視し、Microsoft Teams および Skype for Business サービスとの接続の問題のトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-116">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="7b0bf-117">通話分析は、特定の通話の品質の問題に焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-117">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="7b0bf-118">ここには、Skype for Business アカウントの各ユーザーの通話と会議に関する詳細な情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-118">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="7b0bf-119">通話分析を使用すると、ヘルプデスクオペレーターにアクセス許可を割り当てることができます。これにより、他の Skype for Business 管理センターにアクセスすることなく、通話を監視することができます。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-119">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="7b0bf-120">通話品質ダッシュボードは、組織全体のネットワークパフォーマンスと問題に重点を置いています。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-120">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="7b0bf-121">Skype for Business 管理者とネットワークエンジニアは、このツールを使用して、ネットワークパフォーマンスのトラブルシューティングと最適化を行います。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-121">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="7b0bf-122">詳細については、「[通話分析と通話品質ダッシュボード](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-122">For more information, see [Call Analytics and Call Quality Dashboard](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="7b0bf-123">もちろん、一部の通話品質データをオンプレミスで保持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-123">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="7b0bf-124">これは、たとえば、カスタマイズされたレポートとワークフローを使用してサードパーティ製のソリューションを使用している場合などに該当します。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-124">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="7b0bf-125">Call Data Connector を使用すると、次の図に示すように、オンプレミスサーバーにデータのコピーを保持しながら、オンラインサービスへのデータ送信を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-125">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![SfB クラウドボイスメール](../../sfbserver2019/media/call-data-connector-plan-2.png)

## <a name="requirements"></a><span data-ttu-id="7b0bf-127">要件</span><span class="sxs-lookup"><span data-stu-id="7b0bf-127">Requirements</span></span>

<span data-ttu-id="7b0bf-128">次の要件は、サポートされているトポロジで Skype for Business Server を既に展開していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-128">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="7b0bf-129">Skype for Business Server およびサポートされているトポロジの展開の詳細については、「[トポロジの基本](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-129">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics).</span></span> <span data-ttu-id="7b0bf-130">通話データコネクタを構成するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-130">To configure Call Data Connector, you must:</span></span>

- <span data-ttu-id="7b0bf-131">ハイブリッド接続を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-131">Enable Hybrid connectivity.</span></span> <span data-ttu-id="7b0bf-132">Skype for Business Server を既に展開している場合に、通話データコネクタを有効にするには、オンプレミスの環境とオンライン環境の間でハイブリッド接続が設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-132">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="7b0bf-133">これは、分割ドメイン構成と呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-133">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="7b0bf-134">詳細については、「skype for business [server と office 365 の間のハイブリッド接続を計画](plan-hybrid-connectivity.md)する」および「 [Skype for Business server と office 365 の間のハイブリッド接続を構成する](configure-hybrid-connectivity.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-134">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="7b0bf-135">Office 365 テナントに対して認証を行い、次の役割が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-135">Authenticate to your Office 365 tenant and ensure that you have the following roles enabled:</span></span>

  - <span data-ttu-id="7b0bf-136">Skype for Business Server 管理者</span><span class="sxs-lookup"><span data-stu-id="7b0bf-136">Skype for Business Server Administrator</span></span>
  - <span data-ttu-id="7b0bf-137">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="7b0bf-137">Office 365 Global Administrator</span></span>

- <span data-ttu-id="7b0bf-138">まだ行っていない場合は、 [Microsoft Teams および Skype For Business Online の通話品質ダッシュボードの有効化と使用](/microsoftteams/turning-on-and-using-call-quality-dashboard)に関する説明に従って、通話品質ダッシュボードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-138">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>

- <span data-ttu-id="7b0bf-139">ローカルの LCSCdr および QoEMetrics データベースを使用して、監視用のフロントエンドプールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-139">Enable the front end pool for Monitoring, with local LCSCdr and QoEMetrics databases.</span></span> <span data-ttu-id="7b0bf-140">この操作を行わないと、呼び出しデータコネクタは、使用する指標データを持っていません。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-140">Without this, Call Data Connector won't have metrics data to work with.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b0bf-141">フロントエンドプールで監視が有効になっていない場合、Call Data Connector は機能しません。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-141">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

- <span data-ttu-id="7b0bf-142">[サーバー間認証](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications)が正しく構成されている。</span><span class="sxs-lookup"><span data-stu-id="7b0bf-142">Properly configured [server-to-server authentication](https://docs.microsoft.com/skypeforbusiness/manage/authentication/server-to-server-and-partner-applications).</span></span> 

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="7b0bf-143">オンプレミスとオンライン通話品質ダッシュボード (CQD) レポートの比較</span><span class="sxs-lookup"><span data-stu-id="7b0bf-143">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="7b0bf-144">機能レポート</span><span class="sxs-lookup"><span data-stu-id="7b0bf-144">Feature reports</span></span> | <span data-ttu-id="7b0bf-145">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7b0bf-145">Skype for Business Online</span></span> | <span data-ttu-id="7b0bf-146">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7b0bf-146">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="7b0bf-147">アプリケーション共有メトリック</span><span class="sxs-lookup"><span data-stu-id="7b0bf-147">Application sharing metric</span></span> |<span data-ttu-id="7b0bf-148">はい</span><span class="sxs-lookup"><span data-stu-id="7b0bf-148">Yes</span></span> | <span data-ttu-id="7b0bf-149">いう</span><span class="sxs-lookup"><span data-stu-id="7b0bf-149">Limited</span></span> |
| <span data-ttu-id="7b0bf-150">顧客の建物情報</span><span class="sxs-lookup"><span data-stu-id="7b0bf-150">Customer building information</span></span>| <span data-ttu-id="7b0bf-151">はい</span><span class="sxs-lookup"><span data-stu-id="7b0bf-151">Yes</span></span> | <span data-ttu-id="7b0bf-152">はい</span><span class="sxs-lookup"><span data-stu-id="7b0bf-152">Yes</span></span> |
| <span data-ttu-id="7b0bf-153">ドリルダウン分析</span><span class="sxs-lookup"><span data-stu-id="7b0bf-153">Drill-down analytics</span></span> | <span data-ttu-id="7b0bf-154">はい</span><span class="sxs-lookup"><span data-stu-id="7b0bf-154">Yes</span></span> | <span data-ttu-id="7b0bf-155">いいえ</span><span class="sxs-lookup"><span data-stu-id="7b0bf-155">No</span></span> |
| <span data-ttu-id="7b0bf-156">メディアの信頼性の指標</span><span class="sxs-lookup"><span data-stu-id="7b0bf-156">Media reliability metrics</span></span> | <span data-ttu-id="7b0bf-157">はい</span><span class="sxs-lookup"><span data-stu-id="7b0bf-157">Yes</span></span> | <span data-ttu-id="7b0bf-158">いう</span><span class="sxs-lookup"><span data-stu-id="7b0bf-158">Limited</span></span> |
| <span data-ttu-id="7b0bf-159">すぐに使えるレポート</span><span class="sxs-lookup"><span data-stu-id="7b0bf-159">Out-of-the-box reports</span></span> | <span data-ttu-id="7b0bf-160">はい</span><span class="sxs-lookup"><span data-stu-id="7b0bf-160">Yes</span></span> | <span data-ttu-id="7b0bf-161">はい</span><span class="sxs-lookup"><span data-stu-id="7b0bf-161">Yes</span></span> |
| <span data-ttu-id="7b0bf-162">概要レポート</span><span class="sxs-lookup"><span data-stu-id="7b0bf-162">Overview reports</span></span> | <span data-ttu-id="7b0bf-163">はい</span><span class="sxs-lookup"><span data-stu-id="7b0bf-163">Yes</span></span> | <span data-ttu-id="7b0bf-164">いいえ</span><span class="sxs-lookup"><span data-stu-id="7b0bf-164">No</span></span> |
| <span data-ttu-id="7b0bf-165">ユーザーごとのレポート</span><span class="sxs-lookup"><span data-stu-id="7b0bf-165">Per user reports</span></span> | <span data-ttu-id="7b0bf-166">はい</span><span class="sxs-lookup"><span data-stu-id="7b0bf-166">Yes</span></span> | <span data-ttu-id="7b0bf-167">はい</span><span class="sxs-lookup"><span data-stu-id="7b0bf-167">Yes</span></span> |
| <span data-ttu-id="7b0bf-168">レポートセットのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="7b0bf-168">Report set customization</span></span> <br> <span data-ttu-id="7b0bf-169">(レポートの追加、削除、変更)</span><span class="sxs-lookup"><span data-stu-id="7b0bf-169">(add, delete, modify reports)</span></span> | <span data-ttu-id="7b0bf-170">はい</span><span class="sxs-lookup"><span data-stu-id="7b0bf-170">Yes</span></span> | <span data-ttu-id="7b0bf-171">はい</span><span class="sxs-lookup"><span data-stu-id="7b0bf-171">Yes</span></span> |
| <span data-ttu-id="7b0bf-172">ビデオベースの画面共有指標</span><span class="sxs-lookup"><span data-stu-id="7b0bf-172">Video-based screen sharing metrics</span></span> | <span data-ttu-id="7b0bf-173">はい</span><span class="sxs-lookup"><span data-stu-id="7b0bf-173">Yes</span></span> | <span data-ttu-id="7b0bf-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="7b0bf-174">No</span></span> |
| <span data-ttu-id="7b0bf-175">プログラムによるアクセス用のデータ Api</span><span class="sxs-lookup"><span data-stu-id="7b0bf-175">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="7b0bf-176">CQD</span><span class="sxs-lookup"><span data-stu-id="7b0bf-176">to CQD</span></span> | <span data-ttu-id="7b0bf-177">いいえ</span><span class="sxs-lookup"><span data-stu-id="7b0bf-177">No</span></span> | <span data-ttu-id="7b0bf-178">はい</span><span class="sxs-lookup"><span data-stu-id="7b0bf-178">Yes</span></span> |
||||
