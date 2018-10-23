---
title: 呼び出しデータ コネクタを計画します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: ハイブリッド シナリオでは、設置型の実装を監視する遠隔測定ツールのオンライン ビジネスの Skype を使用する場合の概要です。
ms.openlocfilehash: e9039d3865e3baf5740f4f7489b1a7cfec6dea98
ms.sourcegitcommit: 112dc19075f9213207fde9e30bcde5681324b7c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2018
ms.locfileid: "25696213"
---
# <a name="plan-call-data-connector"></a><span data-ttu-id="c3933-103">呼び出しデータ コネクタを計画します。</span><span class="sxs-lookup"><span data-stu-id="c3933-103">Plan Call Data Connector</span></span>

## <a name="overview"></a><span data-ttu-id="c3933-104">概要</span><span class="sxs-lookup"><span data-stu-id="c3933-104">Overview</span></span>
<span data-ttu-id="c3933-105">このトピックでは、利点、計画の考慮事項、および Skype のビジネス サーバーを呼び出してデータ コネクタの実装の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="c3933-105">This topic describes benefits, planning considerations, and requirements for implementing Skype for Business Server Call Data Connector.</span></span> <span data-ttu-id="c3933-106">データの電話コネクタの構成の詳細については、[呼び出しデータ コネクタの構成](configure-call-data-connector.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3933-106">For more information on configuring Call Data Connector, see [Configure Call Data Connector](configure-call-data-connector.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c3933-107">パブリック プレビュー リリースでは、分析機能の呼び出しのダッシュ ボードのみがあります。</span><span class="sxs-lookup"><span data-stu-id="c3933-107">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="c3933-108">呼び出しデータ コネクタは、設置とオンラインのツールの別のセットを使用してすべてのユーザーの通話の音質を監視する必要がないので、ハイブリッド環境での呼び出しの監視を大幅に簡略化します。</span><span class="sxs-lookup"><span data-stu-id="c3933-108">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span> <span data-ttu-id="c3933-109">ホーム設置型またはオンライン ユーザーは、かどうかは組織全体に対してオンライン通話の品質を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="c3933-109">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="c3933-110">呼び出しのデータ コネクタの 1 つのツールセットを使用して次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c3933-110">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="c3933-111">マイクロソフトのチーム、ビジネス オンラインでは、Skype、Skype ビジネス サーバーの間でユーザーの操作性を監視します。</span><span class="sxs-lookup"><span data-stu-id="c3933-111">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>

- <span data-ttu-id="c3933-112">表示し、ネットワーク上の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="c3933-112">View and troubleshoot problems across your network.</span></span>

- <span data-ttu-id="c3933-113">表示し、各自の責任範囲のトラブルシューティングを行うヘルプデスクの従業員を支援することは、分析機能の呼び出しのヘルプデスクや管理者の役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c3933-113">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span> 

<span data-ttu-id="c3933-114">呼び出しのデータ コネクタに、Skype ビジネス サーバーのプッシュ呼び出しデータ クラウド サービスをビジネス オンラインを呼び出す分析 (CA) および呼び出し品質ダッシュ ボード (救難) ツールでは、Skype を活用することができますように次の図に示すように。</span><span class="sxs-lookup"><span data-stu-id="c3933-114">With Call Data Connector, the Skype for Business Server pushes call data to the cloud service so that you can leverage the Skype for Business Online Call Analytics (CA) and Call Quality Dashboard (CQD) tools, as shown in the following diagram:</span></span>

![デバイス クラウドのボイスメール](../../sfbserver2019/media/call-data-connector-plan-1.png)

<span data-ttu-id="c3933-116">サーバーは、オンライン サービスに高品質のエクスペリエンス (QoE) と呼び出しの詳細記録 (CDR) データの両方をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="c3933-116">The server pushes both Quality of Experience (QoE) and Call Detail Recording (CDR) data to the online service.</span></span>

<span data-ttu-id="c3933-117">救難ツール、分析機能の呼び出しを使用すると、通話の品質を監視し、次のようにマイクロソフト チームと Skype のビジネス ・ サービスの接続の問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="c3933-117">The Call Analytics and CQD tools enable you to monitor the quality of calls and troubleshoot connection problems with Microsoft Teams and Skype for Business services as follows:</span></span>

- <span data-ttu-id="c3933-118">特定の通話品質の問題の分析の焦点を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c3933-118">Call Analytics focuses on quality problems with specific calls.</span></span> <span data-ttu-id="c3933-119">ビジネス アカウントは、Skype の呼び出しとの会議の各ユーザーに関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3933-119">It shows detailed information about calls and meetings for each user in a Skype for Business account.</span></span>  <span data-ttu-id="c3933-120">分析機能の呼び出しでは、ビジネス管理センターは、Skype の残りの部分にアクセスすることがなく呼び出しを監視できるよう、ヘルプデスク オペレーターにアクセス許可を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c3933-120">With Call Analytics, you can assign permissions to a helpdesk operator who can then monitor calls without having access to the rest of the Skype for Business Admin center.</span></span>

- <span data-ttu-id="c3933-121">通話品質のダッシュ ボードでは、ネットワークのパフォーマンスに焦点を当てていて、組織全体で発行します。</span><span class="sxs-lookup"><span data-stu-id="c3933-121">Call Quality Dashboard focuses on network performance and issues across an organization.</span></span> <span data-ttu-id="c3933-122">ビジネス管理者およびネットワーク ・ エンジニアの Skype では、このツールを使用のトラブルシューティングを行うし、ネットワーク パフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="c3933-122">Skype for Business administrators and network engineers use this tool to troubleshoot and optimize network performance.</span></span>

<span data-ttu-id="c3933-123">詳細については、[分析機能を呼び出すと品質のダッシュ ボードを呼び出す](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3933-123">For more information, see [Call Analytics and Call Quality Dashboard](https://docs.microsoft.com/en-us/SkypeForBusiness/using-call-quality-in-your-organization/difference-between-call-analytics-and-call-quality-dashboard).</span></span>

<span data-ttu-id="c3933-124">もちろん、施設内にいくつかの呼び出し品質のデータを保持することもできます。</span><span class="sxs-lookup"><span data-stu-id="c3933-124">Of course, you might want to keep some call quality data on premises.</span></span> <span data-ttu-id="c3933-125">これがある場合、たとえば、カスタマイズされたレポートおよびワークフローにより、サード ・ パーティ製ソリューションを使用している場合。</span><span class="sxs-lookup"><span data-stu-id="c3933-125">This might be the case, for example, if you are using a third-party solution with customized reports and workflows.</span></span>  <span data-ttu-id="c3933-126">呼び出しデータ コネクタも維持しながら、データのコピー、オンプレミスのサーバー上で次の図に示すように、オンライン サービスに送信するデータを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c3933-126">Call Data Connector allows you to configure sending data to the online service while also keeping a copy of the data on your on-premises server, as shown in the following diagram:</span></span>

![デバイス クラウドのボイスメール](../../sfbserver2019/media/call-data-connector-plan-2.png)


## <a name="requirements"></a><span data-ttu-id="c3933-128">要件</span><span class="sxs-lookup"><span data-stu-id="c3933-128">Requirements</span></span>

<span data-ttu-id="c3933-129">次の要件では、ビジネス サーバーのトポロジでサポートされている展開の Skype が既にあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c3933-129">The following requirements assume that you already have Skype for Business Server deployed in a supported topology.</span></span>  <span data-ttu-id="c3933-130">Skype をビジネスのサーバーおよびサポートされているトポロジの展開に関する詳細については、[トポロジの基礎](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3933-130">For more information about deploying Skype for Business Server and supported topologies, see [Topology Basics](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/topology-basics/topology-basics).</span></span> <span data-ttu-id="c3933-131">データの電話コネクタを構成するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3933-131">To configure Call Data Connector, you must:</span></span>

- <span data-ttu-id="c3933-132">ハイブリッド接続を有効にします。</span><span class="sxs-lookup"><span data-stu-id="c3933-132">Enable Hybrid connectivity.</span></span> <span data-ttu-id="c3933-133">ビジネス サーバーの展開の Skype があるし、データの電話コネクタを有効にするは、ハイブリッド接続の設置とオンライン環境の設定があることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3933-133">If you already have Skype for Business Server deployed and you want to enable Call Data Connector, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="c3933-134">分割ドメインの構成とも呼びます。</span><span class="sxs-lookup"><span data-stu-id="c3933-134">This is sometimes called a split domain configuration.</span></span> 

   <span data-ttu-id="c3933-135">詳細については、 [Skype ビジネス サーバーと Office 365 の間のハイブリッドの接続を計画](plan-hybrid-connectivity.md)し、 [Skype ビジネス サーバーと Office 365 の間のハイブリッド接続の構成](configure-hybrid-connectivity.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3933-135">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

-  <span data-ttu-id="c3933-136">Office 365 テナントに認証し、次の役割が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3933-136">Authenticate to your Office 365 tenant and ensure that you have the following roles enabled:</span></span>

   - <span data-ttu-id="c3933-137">Skype ビジネス用のサーバーの管理者</span><span class="sxs-lookup"><span data-stu-id="c3933-137">Skype for Business Server Administrator</span></span> 
   - <span data-ttu-id="c3933-138">Office 365 のグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="c3933-138">Office 365 Global Administrator</span></span> 

- <span data-ttu-id="c3933-139">されていない場合は、品質のダッシュ ボードを呼び出すオン[を有効にしてマイクロソフトのチームとビジネス オンラインの Skype の品質ダッシュ ボードの呼び出しを使用する](/microsoftteams/turning-on-and-using-call-quality-dashboard)で説明したようです。</span><span class="sxs-lookup"><span data-stu-id="c3933-139">If you have not already done so, turn on Call Quality Dashboard as described in [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/microsoftteams/turning-on-and-using-call-quality-dashboard).</span></span>
 
- <span data-ttu-id="c3933-140">ローカルの LCSCdr と QoEMetrics データベースの監視では、フロント エンド プールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="c3933-140">Enable the front end pool for Monitoring, with local LCSCdr and QoEMetrics databases.</span></span> <span data-ttu-id="c3933-141">これを呼び出すデータ コネクタは、測定値のデータを使用を必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c3933-141">Without this, Call Data Connector won't have metrics data to work with.</span></span> 
 
> [!IMPORTANT]
> <span data-ttu-id="c3933-142">フロント エンド プールの監視が有効になっていない場合は、呼び出しデータ コネクタは機能しません。</span><span class="sxs-lookup"><span data-stu-id="c3933-142">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="comparison-of-on-premises-and-online-call-quality-dashboard-cqd-reports"></a><span data-ttu-id="c3933-143">設置とオンラインの呼び出し品質ダッシュ ボード (救難) の比較レポートします。</span><span class="sxs-lookup"><span data-stu-id="c3933-143">Comparison of on-premises and online Call Quality Dashboard (CQD) reports</span></span>

| <span data-ttu-id="c3933-144">機能レポート</span><span class="sxs-lookup"><span data-stu-id="c3933-144">Feature reports</span></span> | <span data-ttu-id="c3933-145">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c3933-145">Skype for Business Online</span></span> | <span data-ttu-id="c3933-146">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c3933-146">Skype for Business Server</span></span>   |
|:---------------------------|:---------------------|:---------------------|:------------------|
| <span data-ttu-id="c3933-147">アプリケーション共有の指標</span><span class="sxs-lookup"><span data-stu-id="c3933-147">Application sharing metric</span></span> |<span data-ttu-id="c3933-148">あり</span><span class="sxs-lookup"><span data-stu-id="c3933-148">Yes</span></span> | <span data-ttu-id="c3933-149">制限されます。</span><span class="sxs-lookup"><span data-stu-id="c3933-149">Limited</span></span> |
| <span data-ttu-id="c3933-150">お客様の建物の情報</span><span class="sxs-lookup"><span data-stu-id="c3933-150">Customer building information</span></span>| <span data-ttu-id="c3933-151">あり</span><span class="sxs-lookup"><span data-stu-id="c3933-151">Yes</span></span> | <span data-ttu-id="c3933-152">あり</span><span class="sxs-lookup"><span data-stu-id="c3933-152">Yes</span></span> |
| <span data-ttu-id="c3933-153">ドリル ・ ダウン分析</span><span class="sxs-lookup"><span data-stu-id="c3933-153">Drill-down analytics</span></span> | <span data-ttu-id="c3933-154">あり</span><span class="sxs-lookup"><span data-stu-id="c3933-154">Yes</span></span> | <span data-ttu-id="c3933-155">なし</span><span class="sxs-lookup"><span data-stu-id="c3933-155">No</span></span> |
| <span data-ttu-id="c3933-156">メディアの信頼性の指標</span><span class="sxs-lookup"><span data-stu-id="c3933-156">Media reliability metrics</span></span> | <span data-ttu-id="c3933-157">あり</span><span class="sxs-lookup"><span data-stu-id="c3933-157">Yes</span></span> | <span data-ttu-id="c3933-158">制限されます。</span><span class="sxs-lookup"><span data-stu-id="c3933-158">Limited</span></span> |
| <span data-ttu-id="c3933-159">ボックスのレポート</span><span class="sxs-lookup"><span data-stu-id="c3933-159">Out-of-the-box reports</span></span> | <span data-ttu-id="c3933-160">あり</span><span class="sxs-lookup"><span data-stu-id="c3933-160">Yes</span></span> | <span data-ttu-id="c3933-161">あり</span><span class="sxs-lookup"><span data-stu-id="c3933-161">Yes</span></span> |
| <span data-ttu-id="c3933-162">プロジェクト概要のレポート</span><span class="sxs-lookup"><span data-stu-id="c3933-162">Overview reports</span></span> | <span data-ttu-id="c3933-163">あり</span><span class="sxs-lookup"><span data-stu-id="c3933-163">Yes</span></span> | <span data-ttu-id="c3933-164">なし</span><span class="sxs-lookup"><span data-stu-id="c3933-164">No</span></span> |
| <span data-ttu-id="c3933-165">レポートのユーザーごと</span><span class="sxs-lookup"><span data-stu-id="c3933-165">Per user reports</span></span> | <span data-ttu-id="c3933-166">あり</span><span class="sxs-lookup"><span data-stu-id="c3933-166">Yes</span></span> | <span data-ttu-id="c3933-167">あり</span><span class="sxs-lookup"><span data-stu-id="c3933-167">Yes</span></span> |
| <span data-ttu-id="c3933-168">レポートの設定のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c3933-168">Report set customization</span></span> <br> <span data-ttu-id="c3933-169">(追加、削除、レポートの変更)</span><span class="sxs-lookup"><span data-stu-id="c3933-169">(add, delete, modify reports)</span></span> | <span data-ttu-id="c3933-170">あり</span><span class="sxs-lookup"><span data-stu-id="c3933-170">Yes</span></span> | <span data-ttu-id="c3933-171">あり</span><span class="sxs-lookup"><span data-stu-id="c3933-171">Yes</span></span> |
| <span data-ttu-id="c3933-172">ビデオ ベースの画面の測定値を共有</span><span class="sxs-lookup"><span data-stu-id="c3933-172">Video-based screen sharing metrics</span></span> | <span data-ttu-id="c3933-173">あり</span><span class="sxs-lookup"><span data-stu-id="c3933-173">Yes</span></span> | <span data-ttu-id="c3933-174">なし</span><span class="sxs-lookup"><span data-stu-id="c3933-174">No</span></span> |
| <span data-ttu-id="c3933-175">プログラムによるアクセスのためのデータ Api</span><span class="sxs-lookup"><span data-stu-id="c3933-175">Data APIs for programmatic access</span></span> <br> <span data-ttu-id="c3933-176">救難に</span><span class="sxs-lookup"><span data-stu-id="c3933-176">to CQD</span></span> | <span data-ttu-id="c3933-177">なし</span><span class="sxs-lookup"><span data-stu-id="c3933-177">No</span></span> | <span data-ttu-id="c3933-178">はい</span><span class="sxs-lookup"><span data-stu-id="c3933-178">Yes</span></span> |
||||
