---
title: Operations Management Suite (OMS) を使用したクラウド コネクタの監視
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: Microsoft Operations Management Suite (OMS) を使用してクラウド コネクタ バージョン 2.1 以降の展開を監視する方法については、このトピックを参照してください。
ms.openlocfilehash: 55685aae01bdcc3c7c979627dbba910bb33203fa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098543"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="492d1-103">Operations Management Suite (OMS) を使用したクラウド コネクタの監視</span><span class="sxs-lookup"><span data-stu-id="492d1-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

> [!Important]
> <span data-ttu-id="492d1-104">Cloud Connector Edition は、Skype for Business Online と共に 2021 年 7 月 31 日に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="492d1-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="492d1-105">組織が Teams にアップグレードしたら、直接ルーティングを使用してオンプレミスのテレフォニー ネットワークを Teams に接続する方法 [について説明します](/MicrosoftTeams/direct-routing-landing-page)。</span><span class="sxs-lookup"><span data-stu-id="492d1-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="492d1-106">Microsoft Operations Management Suite (OMS) を使用してクラウド コネクタ バージョン 2.1 以降の展開を監視する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="492d1-106">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="492d1-107">Microsoft クラウド IT 管理ソリューションである Operations Management Suite (OMS) を使用して、クラウド コネクタ バージョン 2.1 以降の展開を監視できます。</span><span class="sxs-lookup"><span data-stu-id="492d1-107">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="492d1-108">OMS Log Analytics を使用すると、物理マシンや仮想マシンを含むリソースの可用性とパフォーマンスを監視および分析できます。</span><span class="sxs-lookup"><span data-stu-id="492d1-108">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="492d1-109">OMS と Log Analytics の詳細については [、「What is Operations Management Suite (OMS)」を参照してください。](/azure/operations-management-suite/operations-management-suite-overview)</span><span class="sxs-lookup"><span data-stu-id="492d1-109">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="492d1-110">このトピックは、以下のセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="492d1-110">This topic contains the following sections:</span></span>

- <span data-ttu-id="492d1-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="492d1-111">Prerequisites</span></span>

- <span data-ttu-id="492d1-112">OMS を使用するクラウド コネクタの構成</span><span class="sxs-lookup"><span data-stu-id="492d1-112">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="492d1-113">OMS の構成</span><span class="sxs-lookup"><span data-stu-id="492d1-113">Configure OMS</span></span>

- <span data-ttu-id="492d1-114">Log Analytics リポジトリ内のアラートを分析する</span><span class="sxs-lookup"><span data-stu-id="492d1-114">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="492d1-115">推奨される監視セット</span><span class="sxs-lookup"><span data-stu-id="492d1-115">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="492d1-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="492d1-116">Prerequisites</span></span>

<span data-ttu-id="492d1-117">OMS を使用してクラウド コネクタの展開を監視する前に、次の情報が必要になります。</span><span class="sxs-lookup"><span data-stu-id="492d1-117">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="492d1-118">**Azure アカウントと OMS ワークスペース。**</span><span class="sxs-lookup"><span data-stu-id="492d1-118">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="492d1-119">Azure アカウントをまだ持ってない場合は、OMS Log Analytics を使用するアカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="492d1-119">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="492d1-120">Azure アカウントを作成して OMS ワークスペースを設定する方法については [、「Log Analytics](/azure/log-analytics/log-analytics-get-started)ワークスペースの概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="492d1-120">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="492d1-121">**クラウド コネクタ バージョン 2.1 以降**</span><span class="sxs-lookup"><span data-stu-id="492d1-121">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="492d1-122">**クラウド コネクタの監視には、Log Analytics の** 新しいログ検索が必要です。</span><span class="sxs-lookup"><span data-stu-id="492d1-122">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="492d1-123">詳細については [、「Azure Log Analytics ワークスペースを新しいログ検索にアップグレードする」を参照してください](/azure/log-analytics/log-analytics-log-search-upgrade)。</span><span class="sxs-lookup"><span data-stu-id="492d1-123">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="492d1-124">OMS を使用するクラウド コネクタの構成</span><span class="sxs-lookup"><span data-stu-id="492d1-124">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="492d1-125">OMS を使用するには、クラウド コネクタのオンプレミス環境を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="492d1-125">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="492d1-126">これを行うには、OMS ワークスペース ID とキーが必要です。OMS ポータルを使用すると、次のように見つけます。設定 -- 接続ソース \> -- \> Windows サーバー。</span><span class="sxs-lookup"><span data-stu-id="492d1-126">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![クラウド コネクタ OMS のスクリーン ショット](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="492d1-128">OMS を使用するクラウド コネクタの構成方法は、シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="492d1-128">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="492d1-129">**新しいクラウド コネクタ アプライアンス** をインストールする場合、またはアプライアンスを再展開する場合は、Install-CcAppliance を実行する前に、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="492d1-129">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="492d1-130">[ファイルのCloudConnector.ini [Common] セクションで、OMSEnabled パラメーターを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="492d1-130">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="492d1-131">クラウド コネクタが展開またはアップグレードされるごとに、OMS エージェントを VM に自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="492d1-131">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="492d1-132">OMS エージェントがクラウド コネクタの自動更新を存続できるよう、この機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="492d1-132">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="492d1-133">OMS ID とキーを構成するには、-AccountType OMSWorkspace Set-CcCredentialを実行します。</span><span class="sxs-lookup"><span data-stu-id="492d1-133">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="492d1-134">**既存のクラウド コネクタ アプライアンスに OMS エージェント** をインストールする場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="492d1-134">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="492d1-135">[ファイルのCloudConnector.ini [Common] セクションで、OMSEnabled=true を設定します。</span><span class="sxs-lookup"><span data-stu-id="492d1-135">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="492d1-136">Import-CcConfiguration を実行します。</span><span class="sxs-lookup"><span data-stu-id="492d1-136">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="492d1-137">Install-CcOMSAgent を実行します。</span><span class="sxs-lookup"><span data-stu-id="492d1-137">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="492d1-138">OMSWorkspace 資格情報が設定されていない場合は、install-CcOMSAgent を実行するときに資格情報の入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="492d1-138">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="492d1-139">**OMS エージェントが既にインストールされているクラウド コネクタ アプライアンスの OMS ワークスペース ID またはキーを更新する場合は、次の作業を行います。**</span><span class="sxs-lookup"><span data-stu-id="492d1-139">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="492d1-140">OMS ID とキーを構成するには、-AccountType OMSWorkspace Set-CcCredentialを実行します。</span><span class="sxs-lookup"><span data-stu-id="492d1-140">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="492d1-141">更新プログラムを適用するには、Install-CcOMSAgent を実行します。</span><span class="sxs-lookup"><span data-stu-id="492d1-141">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="492d1-142">**すべてのシナリオで、エージェントが次のように接続されていることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="492d1-142">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="492d1-143">OMS ポータルで、[設定] - [ \> 接続されたソース] - \> [Windows サーバー] に移動します。</span><span class="sxs-lookup"><span data-stu-id="492d1-143">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="492d1-144">接続されているコンピューターの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="492d1-144">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="492d1-145">OMS の構成</span><span class="sxs-lookup"><span data-stu-id="492d1-145">Configure OMS</span></span>

<span data-ttu-id="492d1-146">次に、OMS ポータルを使用して OMS 構成を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="492d1-146">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="492d1-147">具体的には、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="492d1-147">Specifically, you will need to:</span></span>

- <span data-ttu-id="492d1-148">イベント ログとパフォーマンス カウンターに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="492d1-148">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="492d1-149">通知を作成します。</span><span class="sxs-lookup"><span data-stu-id="492d1-149">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="492d1-150">イベント ログとパフォーマンス カウンターに関する情報を指定する</span><span class="sxs-lookup"><span data-stu-id="492d1-150">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="492d1-151">OMS ポータルでは、イベント ログとパフォーマンス カウンターに関する情報を次のように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="492d1-151">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="492d1-152">[設定] - \> [データ] - \> [Windows イベント ログ] に移動し、次のイベント ログを追加します。</span><span class="sxs-lookup"><span data-stu-id="492d1-152">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="492d1-153">Lync Server</span><span class="sxs-lookup"><span data-stu-id="492d1-153">Lync Server</span></span>

   - <span data-ttu-id="492d1-154">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="492d1-154">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="492d1-155">テキスト ボックスに Lync Server を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="492d1-155">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="492d1-156">ドロップダウン リストにオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="492d1-156">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="492d1-157">詳細については [、「Log Analytics の Windows イベント ログ データ ソース」を参照してください。](/azure/log-analytics/log-analytics-data-sources-windows-events)</span><span class="sxs-lookup"><span data-stu-id="492d1-157">For more information, see [Windows event log data sources in Log Analytics](/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="492d1-158">[設定] - \> [データ] - \> [Windows パフォーマンス カウンター] に移動し、次のパフォーマンス カウンターを追加します。</span><span class="sxs-lookup"><span data-stu-id="492d1-158">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="492d1-159">**OS レベルのカウンター**。</span><span class="sxs-lookup"><span data-stu-id="492d1-159">**OS level counters**.</span></span> <span data-ttu-id="492d1-160">プロセッサの使用状況、メモリ使用量、ネットワーク使用量などの OS レベルのカウンターを追加したり、カウンターを明示的に追加せずに、容量やパフォーマンス、ネットワーク パフォーマンス モニターなどの既存のソリューションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="492d1-160">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="492d1-161">監視方法に関係なく、これらの OS カウンターを監視してください。</span><span class="sxs-lookup"><span data-stu-id="492d1-161">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="492d1-162">**Skype for Business カウンター**。</span><span class="sxs-lookup"><span data-stu-id="492d1-162">**Skype for Business counters**.</span></span> <span data-ttu-id="492d1-163">Skype for Business には多数のカウンターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="492d1-163">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="492d1-164">これらのカウンターは、仲介サーバーにログオンし、パフォーマンス モニターを開いて確認できます。</span><span class="sxs-lookup"><span data-stu-id="492d1-164">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="492d1-165">これらのカウンターは、"LS:" で始まる。</span><span class="sxs-lookup"><span data-stu-id="492d1-165">These counters start with "LS:".</span></span> <span data-ttu-id="492d1-166">Microsoft では、少なくとも次の容量カウンターから始め、関心のある他のカウンターを追加してください。</span><span class="sxs-lookup"><span data-stu-id="492d1-166">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="492d1-167">アクティブな通話の合計:</span><span class="sxs-lookup"><span data-stu-id="492d1-167">Total active calls:</span></span>

       - <span data-ttu-id="492d1-168">LS:MediationServer - 受信呼び出し(_Total) \- Current</span><span class="sxs-lookup"><span data-stu-id="492d1-168">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="492d1-169">LS:MediationServer - 発信呼び出し(_Total) \- Current</span><span class="sxs-lookup"><span data-stu-id="492d1-169">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="492d1-170">アクティブ なメディア バイパス呼び出しの合計:</span><span class="sxs-lookup"><span data-stu-id="492d1-170">Total active media bypass calls:</span></span>

       - <span data-ttu-id="492d1-171">LS:MediationServer - 受信通話(_Total) \- アクティブ メディア バイパス呼び出し</span><span class="sxs-lookup"><span data-stu-id="492d1-171">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="492d1-172">LS:MediationServer - 発信通話(_Total) \- アクティブ メディア バイパス呼び出し</span><span class="sxs-lookup"><span data-stu-id="492d1-172">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="492d1-173">テキスト ボックスにパフォーマンス カウンターを手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="492d1-173">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="492d1-174">ドロップダウン リストにオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="492d1-174">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="492d1-175">詳細については [、「Log Analytics」の「Windows および Linux のパフォーマンス データ ソース」を参照してください。](/azure/log-analytics/log-analytics-data-sources-performance-counters)</span><span class="sxs-lookup"><span data-stu-id="492d1-175">For more information, see [Windows and Linux performance data sources in Log Analytics](/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="492d1-176">アラートの作成</span><span class="sxs-lookup"><span data-stu-id="492d1-176">Create alerts</span></span>

<span data-ttu-id="492d1-177">OMS には、結果アラートの数とメトリック測定アラートの 2 種類のアラートがあります。</span><span class="sxs-lookup"><span data-stu-id="492d1-177">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="492d1-178">アラートの作成の詳細については、「Log Analytics でのアラート [ルールの操作」を参照してください](/azure/log-analytics/log-analytics-alerts-creating)。</span><span class="sxs-lookup"><span data-stu-id="492d1-178">For more information about creating alerts, see [Working with alert rules in Log Analytics](/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="492d1-179">アラートを作成する場合は、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="492d1-179">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="492d1-180">アラートが既定の選択である結果の数アラートである必要があります。</span><span class="sxs-lookup"><span data-stu-id="492d1-180">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="492d1-181">デモ クエリでは、"結果の数" が "0 より大きい" に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="492d1-181">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="492d1-182">[タイム ウィンドウ] と [アラートの頻度] の両方を 5 分に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="492d1-182">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="492d1-183">デモアラートの "アラートを抑制する" を有効にしない方が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="492d1-183">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="492d1-184">一般的なアラート シナリオでは、1 つのエラー アラートと 1 つのリセット アラートという 2 つのアラートを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="492d1-184">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="492d1-185">エラーアラートの場合は、重大度レベル [重大] を選択します。[リセットアラート] で、[重大度レベル情報] を選択します。</span><span class="sxs-lookup"><span data-stu-id="492d1-185">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="492d1-186">次のセクションでは、サンプルアラートを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="492d1-186">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="492d1-187">**アラート ペアを作成する: "RTCMEDSRV は仲介サーバーで実行されていない" と "RTCMEDSRV は仲介サーバーで実行中です"**</span><span class="sxs-lookup"><span data-stu-id="492d1-187">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="492d1-188">このアラート ペアを作成するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="492d1-188">To create this alert pair:</span></span>

- <span data-ttu-id="492d1-189">エラー アラートのクエリは次の条件を実行します。</span><span class="sxs-lookup"><span data-stu-id="492d1-189">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="492d1-190">このクエリでは、コンピューターに  *"MediationServer" が含まれるコンピューター フィルターを使用します*  。</span><span class="sxs-lookup"><span data-stu-id="492d1-190">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="492d1-191">フィルターは、名前に "MediationServer" という文字列が含まれているコンピューターのみを選択します。</span><span class="sxs-lookup"><span data-stu-id="492d1-191">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="492d1-192">フィルターを独自のコンピューター フィルターに置き換えるか、単に削除します。</span><span class="sxs-lookup"><span data-stu-id="492d1-192">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="492d1-193">正規表現を使用せずに複雑な文字列フィルターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="492d1-193">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="492d1-194">詳細については [、「String 演算子」を参照してください](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)。</span><span class="sxs-lookup"><span data-stu-id="492d1-194">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="492d1-195">正規表現を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="492d1-195">You can also choose to use regular expressions.</span></span> <span data-ttu-id="492d1-196">さらに、検索クエリを保存し、そのグループをアラート クエリのコンピューター フィルターとして使用して、コンピューター グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="492d1-196">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="492d1-197">詳細については [、「Log Analytics ログ検索のコンピューター グループ」を参照してください](/azure/log-analytics/log-analytics-computer-groups)。</span><span class="sxs-lookup"><span data-stu-id="492d1-197">For more information, see [Computer groups in Log Analytics log searches](/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="492d1-198">各コンピューターについて、エラー クエリは RTCMEDSRV サービスの開始とサービス停止の両方の最後のイベント ログを取得します。</span><span class="sxs-lookup"><span data-stu-id="492d1-198">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="492d1-199">最後のイベントがサービス停止イベントの場合は、ログが 1 つ返されます。最後のイベントがサービス開始イベントの場合は、何も返しません。</span><span class="sxs-lookup"><span data-stu-id="492d1-199">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="492d1-200">つまり、クエリは、RTCMEDSRV がタイム ウィンドウで停止しているサーバーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="492d1-200">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="492d1-201">リセットアラートのクエリは次の条件を実行します。</span><span class="sxs-lookup"><span data-stu-id="492d1-201">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="492d1-202">リセット クエリは、エラー クエリとは正反対の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="492d1-202">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="492d1-203">コンピューターごとに、最後のイベントがサービス開始イベントの場合は 1 つを返します。最後のイベントがサービス停止イベントの場合、何も返しません。</span><span class="sxs-lookup"><span data-stu-id="492d1-203">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="492d1-204">**アラートペアを作成する: "仲介サーバーでの同時呼び出しが多すぎます"と"同時呼び出しが通常の負荷に戻る"**</span><span class="sxs-lookup"><span data-stu-id="492d1-204">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="492d1-205">このアラートを作成するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="492d1-205">To create this alert:</span></span>

- <span data-ttu-id="492d1-206">エラー アラートのクエリは次の条件を実行します。</span><span class="sxs-lookup"><span data-stu-id="492d1-206">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="492d1-207">各コンピューターに対して、クエリは受信呼び出しと発信呼び出しの最後のカウンターを取得し、これらの 2 つの値を合計します。</span><span class="sxs-lookup"><span data-stu-id="492d1-207">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="492d1-208">合計値が 500 を超えると、ログが 1 つ返されます。それ以外の場合は何も返しません。</span><span class="sxs-lookup"><span data-stu-id="492d1-208">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="492d1-209">つまり、クエリは、タイム ウィンドウで同時呼び出しが多すぎるサーバーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="492d1-209">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="492d1-210">リセットアラートのクエリは次の条件を実行します。</span><span class="sxs-lookup"><span data-stu-id="492d1-210">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="492d1-211">リセット クエリは、エラー クエリとは正反対の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="492d1-211">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="492d1-212">各コンピューターに対して、クエリは受信呼び出しと発信呼び出しの最後のカウンターを取得し、これらの 2 つの値を合計します。</span><span class="sxs-lookup"><span data-stu-id="492d1-212">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="492d1-213">合計値が 500 未満の場合は、1 つのログが返されます。それ以外の場合は何も返しません。</span><span class="sxs-lookup"><span data-stu-id="492d1-213">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="492d1-214">**アラートを作成する: "CPU 使用率 \> 90 または RTCMEDIARELAY がサーバーで停止しました" アラート**</span><span class="sxs-lookup"><span data-stu-id="492d1-214">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="492d1-215">このアラートを作成するには、次のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="492d1-215">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="492d1-216">クエリは、すべてのコンピューターからすべてのプロセッサ使用率カウンターとサービス停止イベントを取得し、プロセッサ使用率が 90% を超えた場合、またはサービスが停止した場合に 1 つのログを返します。</span><span class="sxs-lookup"><span data-stu-id="492d1-216">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="492d1-217">Log Analytics リポジトリ内のアラートを分析する</span><span class="sxs-lookup"><span data-stu-id="492d1-217">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="492d1-218">リポジトリ内のアラートを分析するには、アラート管理ソリューションを使用します。</span><span class="sxs-lookup"><span data-stu-id="492d1-218">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="492d1-219">詳細については、「Operations [Management Suite (OMS)のアラート管理ソリューション」を参照してください。](/azure/log-analytics/log-analytics-solution-alert-management)</span><span class="sxs-lookup"><span data-stu-id="492d1-219">For more information, see [Alert Management solution in Operations Management Suite (OMS)](/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="492d1-220">推奨される最小限の監視セット</span><span class="sxs-lookup"><span data-stu-id="492d1-220">Recommended minimal monitoring set</span></span>

<span data-ttu-id="492d1-221">イベント ログとパフォーマンス カウンターに関する問題を特定するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="492d1-221">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="492d1-222">**イベント ログ。**</span><span class="sxs-lookup"><span data-stu-id="492d1-222">**Event logs.**</span></span> <span data-ttu-id="492d1-223">何か問題が発生した場合は、何かが間違っていると示すイベントのセットが 1 つ、もう 1 つのイベントペアが、すべてがうまくいったことを示すイベント ペアが必要です。</span><span class="sxs-lookup"><span data-stu-id="492d1-223">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="492d1-224">特定の期間に対して、記録された最後のイベントで、その期間に何かが間違っているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="492d1-224">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="492d1-225">**パフォーマンス カウンター。**</span><span class="sxs-lookup"><span data-stu-id="492d1-225">**Performance Counters.**</span></span> <span data-ttu-id="492d1-226">監視対象のカウンターにはしきい値が必要です。</span><span class="sxs-lookup"><span data-stu-id="492d1-226">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="492d1-227">次の表に、停止イベントと開始イベントの ID を一覧表示して、Microsoft が監視を推奨するサービスを示します。</span><span class="sxs-lookup"><span data-stu-id="492d1-227">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="492d1-228">サービス名</span><span class="sxs-lookup"><span data-stu-id="492d1-228">Service Name</span></span>  <br/> |<span data-ttu-id="492d1-229">ターゲット サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="492d1-229">Target Server Role</span></span>  <br/> |<span data-ttu-id="492d1-230">Stop イベント ID</span><span class="sxs-lookup"><span data-stu-id="492d1-230">Stop Event ID</span></span>  <br/> |<span data-ttu-id="492d1-231">イベント ID の開始</span><span class="sxs-lookup"><span data-stu-id="492d1-231">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="492d1-232">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="492d1-232">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="492d1-233">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="492d1-233">Mediation Server</span></span>  <br/> |<span data-ttu-id="492d1-234">25003</span><span class="sxs-lookup"><span data-stu-id="492d1-234">25003</span></span>  <br/> |<span data-ttu-id="492d1-235">25002</span><span class="sxs-lookup"><span data-stu-id="492d1-235">25002</span></span>  <br/> |
|<span data-ttu-id="492d1-236">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="492d1-236">RTCSRV</span></span>  <br/> |<span data-ttu-id="492d1-237">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="492d1-237">Edge Server</span></span>  <br/> |<span data-ttu-id="492d1-238">12289</span><span class="sxs-lookup"><span data-stu-id="492d1-238">12289</span></span>  <br/> |<span data-ttu-id="492d1-239">12288</span><span class="sxs-lookup"><span data-stu-id="492d1-239">12288</span></span>  <br/> |
|<span data-ttu-id="492d1-240">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="492d1-240">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="492d1-241">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="492d1-241">Edge Server</span></span>  <br/> |<span data-ttu-id="492d1-242">19003</span><span class="sxs-lookup"><span data-stu-id="492d1-242">19003</span></span>  <br/> |<span data-ttu-id="492d1-243">19002</span><span class="sxs-lookup"><span data-stu-id="492d1-243">19002</span></span>  <br/> |
|<span data-ttu-id="492d1-244">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="492d1-244">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="492d1-245">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="492d1-245">Edge Server</span></span>  <br/> |<span data-ttu-id="492d1-246">22003</span><span class="sxs-lookup"><span data-stu-id="492d1-246">22003</span></span>  <br/> |<span data-ttu-id="492d1-247">22002</span><span class="sxs-lookup"><span data-stu-id="492d1-247">22002</span></span>  <br/> |

<span data-ttu-id="492d1-248">次の表に、Microsoft が監視を推奨するネットワークの問題の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="492d1-248">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="492d1-249">モニター名</span><span class="sxs-lookup"><span data-stu-id="492d1-249">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="492d1-250">ターゲット サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="492d1-250">Target Server Role</span></span>  <br/> | <span data-ttu-id="492d1-251">Success イベント ID 式</span><span class="sxs-lookup"><span data-stu-id="492d1-251">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="492d1-252">Error イベント ID 式</span><span class="sxs-lookup"><span data-stu-id="492d1-252">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="492d1-253">エラーの例</span><span class="sxs-lookup"><span data-stu-id="492d1-253">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="492d1-254">仲介サーバーからゲートウェイへの接続エラー</span><span class="sxs-lookup"><span data-stu-id="492d1-254">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="492d1-255">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="492d1-255">Mediation Server</span></span>  <br/>   | <span data-ttu-id="492d1-256">25062</span><span class="sxs-lookup"><span data-stu-id="492d1-256">25062</span></span>                              |                                  | <span data-ttu-id="492d1-257">25002</span><span class="sxs-lookup"><span data-stu-id="492d1-257">25002</span></span>  <br/>           |
| <span data-ttu-id="492d1-258">仲介サーバーからゲートウェイへの呼び出しの完了エラー</span><span class="sxs-lookup"><span data-stu-id="492d1-258">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="492d1-259">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="492d1-259">Mediation Server</span></span>  <br/>   | <span data-ttu-id="492d1-260">25064</span><span class="sxs-lookup"><span data-stu-id="492d1-260">25064</span></span>                              |                                  | <span data-ttu-id="492d1-261">25002</span><span class="sxs-lookup"><span data-stu-id="492d1-261">25002</span></span>  <br/>           |
| <span data-ttu-id="492d1-262">重大なネットワークの問題</span><span class="sxs-lookup"><span data-stu-id="492d1-262">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="492d1-263">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="492d1-263">Edge Server</span></span>  <br/>        | <span data-ttu-id="492d1-264">14353</span><span class="sxs-lookup"><span data-stu-id="492d1-264">14353</span></span>                              |                                  | <span data-ttu-id="492d1-265">12288</span><span class="sxs-lookup"><span data-stu-id="492d1-265">12288</span></span>  <br/>           |

<span data-ttu-id="492d1-266">次に、監視する必要がある通話容量カウンターの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="492d1-266">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="492d1-267">これらの数値は、Cloud Connector 標準エディションの 500 未満である必要があります。Cloud Connector 最小エディションの場合は 50 未満。</span><span class="sxs-lookup"><span data-stu-id="492d1-267">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="492d1-268">LS:MediationServer - 受信呼び出し(_Total) \- Current</span><span class="sxs-lookup"><span data-stu-id="492d1-268">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="492d1-269">LS:MediationServer - 発信呼び出し(_Total) \- Current</span><span class="sxs-lookup"><span data-stu-id="492d1-269">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="492d1-270">LS:MediationServer - 受信通話(_Total) \- アクティブ メディア バイパス呼び出し</span><span class="sxs-lookup"><span data-stu-id="492d1-270">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="492d1-271">LS:MediationServer - 発信通話(_Total) \- アクティブ メディア バイパス呼び出し</span><span class="sxs-lookup"><span data-stu-id="492d1-271">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="492d1-272">関連項目</span><span class="sxs-lookup"><span data-stu-id="492d1-272">See also</span></span>

<span data-ttu-id="492d1-273">OMS の操作の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="492d1-273">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="492d1-274">Log Analytics でログ検索を使用してデータを検索する</span><span class="sxs-lookup"><span data-stu-id="492d1-274">Find data using log searches in Log Analytics</span></span>](/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="492d1-275">Azure Log Analytics 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="492d1-275">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="492d1-276">Log Analytics でのアラートについて</span><span class="sxs-lookup"><span data-stu-id="492d1-276">Understanding alerts in Log Analytics</span></span>](/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="492d1-277">Azure の Log Analytics サービスに Windows コンピューターを接続する</span><span class="sxs-lookup"><span data-stu-id="492d1-277">Connect Windows computers to the Log Analytics service in Azure</span></span>](/azure/log-analytics/log-analytics-windows-agents)