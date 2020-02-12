---
title: Operations Management Suite (OMS) を使用した Cloud Connector の監視
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
description: このトピックでは、Microsoft Operations Management Suite (OMS) を使用してクラウドコネクタバージョン2.1 およびそれ以降の展開を監視する方法について説明します。
ms.openlocfilehash: 6c63baf078dc865a4e3aef574cff30bedabf3819
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888636"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="8ea4c-103">Operations Management Suite (OMS) を使用した Cloud Connector の監視</span><span class="sxs-lookup"><span data-stu-id="8ea4c-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

<span data-ttu-id="8ea4c-104">このトピックでは、Microsoft Operations Management Suite (OMS) を使用してクラウドコネクタバージョン2.1 およびそれ以降の展開を監視する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="8ea4c-105">Operations Management Suite (OMS)、Microsoft cloud IT Management solution を使用して、クラウドコネクタバージョン2.1 およびそれ以降の展開を監視できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="8ea4c-106">OMS ログ分析を使用すると、物理および仮想マシンを含むリソースの可用性とパフォーマンスを監視および分析できます。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="8ea4c-107">OMS とログ分析の詳細については、「 [Operations Management Suite (OMS) とは](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="8ea4c-108">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-108">This topic contains the following sections:</span></span>

- <span data-ttu-id="8ea4c-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="8ea4c-109">Prerequisites</span></span>

- <span data-ttu-id="8ea4c-110">OMS を使用するようにクラウドコネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="8ea4c-110">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="8ea4c-111">OMS を設定する</span><span class="sxs-lookup"><span data-stu-id="8ea4c-111">Configure OMS</span></span>

- <span data-ttu-id="8ea4c-112">ログ分析リポジトリのアラートを分析する</span><span class="sxs-lookup"><span data-stu-id="8ea4c-112">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="8ea4c-113">推奨される監視セット</span><span class="sxs-lookup"><span data-stu-id="8ea4c-113">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8ea4c-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="8ea4c-114">Prerequisites</span></span>

<span data-ttu-id="8ea4c-115">OMS を使ってクラウドコネクタの展開を監視するには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="8ea4c-116">**Azure アカウントと OMS ワークスペース。**</span><span class="sxs-lookup"><span data-stu-id="8ea4c-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="8ea4c-117">まだ Azure アカウントを持っていない場合は、OMS ログ分析を使用するようにアカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="8ea4c-118">Azure アカウントを作成して OMS ワークスペースを設定する方法については、「[ログ分析ワークスペースの使用を開始](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="8ea4c-119">**Cloud Connector バージョン2.1 以降**</span><span class="sxs-lookup"><span data-stu-id="8ea4c-119">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="8ea4c-120">**ログ分析**クラウドコネクタを監視するには、新しいログの検索が必要です。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="8ea4c-121">詳細については、「[新しいログの検索に Azure Log Analytics ワークスペースをアップグレードする](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="8ea4c-122">OMS を使用するようにクラウドコネクタを構成する</span><span class="sxs-lookup"><span data-stu-id="8ea4c-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="8ea4c-123">OMS を使用するには、クラウドコネクタのオンプレミス環境を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="8ea4c-124">これを行うには、OMS のワークスペース ID とキーが必要です。これは、次のように OMS ポータルを使って\>確認できます。\>設定--接続されているソース--Windows server:</span><span class="sxs-lookup"><span data-stu-id="8ea4c-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Cloud Connector OMS のスクリーンショット](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="8ea4c-126">OMS を使用するようにクラウドコネクタを構成する方法は、シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="8ea4c-127">**新しいクラウドコネクタアプライアンスをインストールする場合、またはアプライアンスを再展開する場合は**、次の手順に従って、Install-ccappliance を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="8ea4c-128">CloudConnector .ini ファイルの [Common] セクションで、OMSEnabled パラメーターを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="8ea4c-129">クラウドコネクタが展開またはアップグレードされるたびに、OMS エージェントを Vm に自動的にインストールしようとします。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="8ea4c-130">この機能を有効にして、OMS エージェントがクラウドコネクタの自動更新を利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="8ea4c-131">OMS ID とキーを構成するには、Set-CcCredential-AccountType OMSWorkspace を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="8ea4c-132">**既存のクラウドコネクタアプライアンスに OMS エージェントをインストールする場合**は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="8ea4c-133">CloudConnector の [Common] セクションで、OMSEnabled = true を設定します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="8ea4c-134">インポート-CcConfiguration を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-134">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="8ea4c-135">CcOMSAgent を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-135">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="8ea4c-136">OMSWorkspace 資格情報がまだ設定されていない場合は、CcOMSAgent を実行するときに資格情報の入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="8ea4c-137">**OMS エージェントが既にインストールされているクラウドコネクタのアプライアンスで、OMS ワークスペース ID またはキーを更新する場合は、次の操作を行います。**</span><span class="sxs-lookup"><span data-stu-id="8ea4c-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="8ea4c-138">OMS ID とキーを構成するには、Set-CcCredential-AccountType OMSWorkspace を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="8ea4c-139">更新プログラムを適用するには、CcOMSAgent を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-139">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="8ea4c-140">**すべてのシナリオで、エージェントが次のように接続されていることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="8ea4c-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="8ea4c-141">OMS ポータルで、[設定-\>接続されている\>ソース-Windows サーバー] に移動します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="8ea4c-142">接続されているコンピューターの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-142">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="8ea4c-143">OMS を設定する</span><span class="sxs-lookup"><span data-stu-id="8ea4c-143">Configure OMS</span></span>

<span data-ttu-id="8ea4c-144">次に、OMS ポータルを使って OMS の設定を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="8ea4c-145">具体的には、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-145">Specifically, you will need to:</span></span>

- <span data-ttu-id="8ea4c-146">イベントログとパフォーマンスカウンターに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-146">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="8ea4c-147">通知を作成する。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-147">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="8ea4c-148">イベントログとパフォーマンスカウンターに関する情報を指定する</span><span class="sxs-lookup"><span data-stu-id="8ea4c-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="8ea4c-149">OMS ポータルでは、次のようにイベントログとパフォーマンスカウンターに関する情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="8ea4c-150">[設定-\>データ-\>Windows イベントログ] に移動し、次のイベントログを追加します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="8ea4c-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="8ea4c-151">Lync Server</span></span>

   - <span data-ttu-id="8ea4c-152">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="8ea4c-152">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="8ea4c-153">テキストボックスに Lync Server を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="8ea4c-154">ドロップダウンリストにオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-154">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="8ea4c-155">詳細については、「[ログ分析の Windows イベントログデータソース](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="8ea4c-156">[設定-\>データ-\> Windows パフォーマンスカウンター] に移動して、次のパフォーマンスカウンターを追加します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="8ea4c-157">**OS レベルカウンター**。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-157">**OS level counters**.</span></span> <span data-ttu-id="8ea4c-158">OS レベルのカウンター (プロセッサの使用状況、メモリ使用量、ネットワークの使用率など) を追加したり、カウンターを明示的に追加することなく、容量とパフォーマンスなどの既存のソリューションを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="8ea4c-159">どのように監視するかにかかわらず、Microsoft は、これらの OS カウンターを監視することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="8ea4c-160">**Skype For business のカウンター**。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-160">**Skype for Business counters**.</span></span> <span data-ttu-id="8ea4c-161">Skype for Business には、多数のカウンターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="8ea4c-162">これらのカウンターは、任意の仲介サーバーにログオンして、パフォーマンスモニターを開くことで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="8ea4c-163">これらのカウンターは "LS:" で始まります。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-163">These counters start with "LS:".</span></span> <span data-ttu-id="8ea4c-164">Microsoft では、少なくとも次の容量カウンターから開始して、興味のあるユーザーを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="8ea4c-165">アクティブな通話の合計:</span><span class="sxs-lookup"><span data-stu-id="8ea4c-165">Total active calls:</span></span>

       - <span data-ttu-id="8ea4c-166">LS: MediationServer-Inbound Calls (_Total)\- Current</span><span class="sxs-lookup"><span data-stu-id="8ea4c-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="8ea4c-167">LS: MediationServer-送信通話 (_Total)\- Current</span><span class="sxs-lookup"><span data-stu-id="8ea4c-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="8ea4c-168">アクティブなメディアの合計通話のバイパス:</span><span class="sxs-lookup"><span data-stu-id="8ea4c-168">Total active media bypass calls:</span></span>

       - <span data-ttu-id="8ea4c-169">LS: MediationServer-着信通話 (_Total)\-アクティブメディアでの通話のバイパス</span><span class="sxs-lookup"><span data-stu-id="8ea4c-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="8ea4c-170">LS: MediationServer-送信通話 (_Total)\-アクティブメディアでの通話のバイパス</span><span class="sxs-lookup"><span data-stu-id="8ea4c-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="8ea4c-171">テキストボックスにパフォーマンスカウンターを手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="8ea4c-172">ドロップダウンリストにオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-172">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="8ea4c-173">詳細については、「[ログ分析の Windows と Linux のパフォーマンスデータソース](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="8ea4c-174">通知を作成する</span><span class="sxs-lookup"><span data-stu-id="8ea4c-174">Create alerts</span></span>

<span data-ttu-id="8ea4c-175">OMS には2種類の通知があります。結果アラートの数と測定指標のアラートがあります。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="8ea4c-176">通知の作成の詳細については、「[ログ分析で通知ルールを](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="8ea4c-177">通知を作成する場合は、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-177">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="8ea4c-178">[通知] が、既定の選択である [結果を表示する] 通知であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="8ea4c-179">デモクエリでは、"結果の数" が "0 より大きい" に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="8ea4c-180">タイムウィンドウと通知頻度の両方を5分に設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="8ea4c-181">デモの警告に対して [通知を表示しない] を有効にしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="8ea4c-182">一般的なアラートシナリオの場合は、1つのエラー通知と1つのリセット通知のペアを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="8ea4c-183">エラーメッセージについては、[重要度] を選択します。アラートのリセットで、[重大度レベルの情報] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="8ea4c-184">以下のセクションでは、サンプル通知の作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-184">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="8ea4c-185">**"RTCMEDSRV は仲介サーバーで実行されていません" という通知のペアを作成し、"RTCMEDSRV は仲介サーバーで実行中です" というメッセージが返されます。**</span><span class="sxs-lookup"><span data-stu-id="8ea4c-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="8ea4c-186">この通知のペアを作成するには:</span><span class="sxs-lookup"><span data-stu-id="8ea4c-186">To create this alert pair:</span></span>

- <span data-ttu-id="8ea4c-187">エラーアラートのクエリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-187">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="8ea4c-188">このクエリは、コンピューターに *"MediationServer" が含まれて*いるコンピューターフィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="8ea4c-189">フィルターでは、名前に "MediationServer" という文字列が含まれているコンピューターのみが選択されます。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="8ea4c-190">フィルターを独自のコンピューターフィルターに置き換えるか、削除するだけです。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="8ea4c-191">正規表現なしで複雑な文字列フィルターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="8ea4c-192">詳細については、「[文字列演算子](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="8ea4c-193">正規表現を使用するように選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="8ea4c-194">さらに、コンピューターグループを作成するには、検索クエリを保存し、そのグループを警告クエリのコンピューターフィルターとして使用します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="8ea4c-195">詳細については、「[ログ分析ログの検索のコンピューターグループ](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="8ea4c-196">コンピューターごとに、エラークエリにより、RTCMEDSRV service の start と service stop の両方の最後のイベントログが取得されます。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="8ea4c-197">最後のイベントがサービス停止イベントの場合は、1つのログが返されます。最後のイベントがサービス開始イベントの場合は、nothing が返されます。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="8ea4c-198">つまり、このクエリは、時間ウィンドウで RTCMEDSRV が停止しているサーバーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="8ea4c-199">リセット通知のクエリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-199">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="8ea4c-200">リセットクエリは、エラークエリの反対の部分とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="8ea4c-201">各コンピューターについて、最後のイベントがサービス開始イベントの場合は1を返します。最後のイベントがサービス停止イベントの場合は、nothing が返されます。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="8ea4c-202">**通知のペアを作成する: "仲介サーバーでの同時呼び出しが多すぎる" と "同時呼び出しが通常の負荷に戻ります"**</span><span class="sxs-lookup"><span data-stu-id="8ea4c-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="8ea4c-203">この通知を作成するには:</span><span class="sxs-lookup"><span data-stu-id="8ea4c-203">To create this alert:</span></span>

- <span data-ttu-id="8ea4c-204">エラーアラートのクエリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-204">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="8ea4c-205">各コンピューターについて、クエリによって、着信呼び出しと発信通話の最後のカウンターが取得され、これら2つの値が合計されます。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="8ea4c-206">Sum 値が500を超えると、1つのログが返されます。そうでない場合は何も返されません。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="8ea4c-207">つまり、このクエリは、同時呼び出しの時間ウィンドウの数が多すぎるサーバーのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="8ea4c-208">リセット通知のクエリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-208">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="8ea4c-209">リセットクエリは、エラークエリの反対の部分とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="8ea4c-210">各コンピューターについて、クエリによって、着信呼び出しと発信通話の最後のカウンターが取得され、これら2つの値が合計されます。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="8ea4c-211">Sum 値が500よりも小さい場合は、1つのログが返されます。それ以外の場合は何も返されません。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="8ea4c-212">**"CPU 使用率\> 90 または RTCMEDIARELAY はサーバーで停止しました" アラートを作成します。**</span><span class="sxs-lookup"><span data-stu-id="8ea4c-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="8ea4c-213">この通知を作成するには、次のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-213">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="8ea4c-214">このクエリは、すべてのコンピューターからすべてのプロセッサ使用量カウンターとサービス停止イベントを取得し、いずれかのプロセッサ使用状況が90% を超えた場合、またはサービスが停止している場合に1つのログを返します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="8ea4c-215">ログ分析リポジトリのアラートを分析する</span><span class="sxs-lookup"><span data-stu-id="8ea4c-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="8ea4c-216">リポジトリ内の通知を分析するには、アラート管理ソリューションを使用します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="8ea4c-217">詳細については、「 [Operations Management Suite (OMS) でのアラート管理ソリューション](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="8ea4c-218">推奨される最小の監視セット</span><span class="sxs-lookup"><span data-stu-id="8ea4c-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="8ea4c-219">イベントログとパフォーマンスカウンターの問題を特定するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-219">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="8ea4c-220">**イベントログ。**</span><span class="sxs-lookup"><span data-stu-id="8ea4c-220">**Event logs.**</span></span> <span data-ttu-id="8ea4c-221">問題が発生した場合は、イベントのペアと、何かが間違っていることを示すイベントのセットがあります。もう1つは、すべてが適切であることを示します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="8ea4c-222">指定された期間が経過すると、その期間に対してさんが指定されているかどうかを示す最後のイベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="8ea4c-223">**パフォーマンスカウンター。**</span><span class="sxs-lookup"><span data-stu-id="8ea4c-223">**Performance Counters.**</span></span> <span data-ttu-id="8ea4c-224">監視対象カウンターには、しきい値が必要です。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-224">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="8ea4c-225">次の表に、stop イベント Id と start イベント Id の一覧を表示することにより、監視が推奨されるサービスを示します。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="8ea4c-226">サービス名</span><span class="sxs-lookup"><span data-stu-id="8ea4c-226">Service Name</span></span>  <br/> |<span data-ttu-id="8ea4c-227">ターゲットサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="8ea4c-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="8ea4c-228">イベント ID の停止</span><span class="sxs-lookup"><span data-stu-id="8ea4c-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="8ea4c-229">開始イベント ID</span><span class="sxs-lookup"><span data-stu-id="8ea4c-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8ea4c-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="8ea4c-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="8ea4c-231">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="8ea4c-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="8ea4c-232">25003</span><span class="sxs-lookup"><span data-stu-id="8ea4c-232">25003</span></span>  <br/> |<span data-ttu-id="8ea4c-233">25002</span><span class="sxs-lookup"><span data-stu-id="8ea4c-233">25002</span></span>  <br/> |
|<span data-ttu-id="8ea4c-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="8ea4c-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="8ea4c-235">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="8ea4c-235">Edge Server</span></span>  <br/> |<span data-ttu-id="8ea4c-236">12289</span><span class="sxs-lookup"><span data-stu-id="8ea4c-236">12289</span></span>  <br/> |<span data-ttu-id="8ea4c-237">12288</span><span class="sxs-lookup"><span data-stu-id="8ea4c-237">12288</span></span>  <br/> |
|<span data-ttu-id="8ea4c-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="8ea4c-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="8ea4c-239">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="8ea4c-239">Edge Server</span></span>  <br/> |<span data-ttu-id="8ea4c-240">19003</span><span class="sxs-lookup"><span data-stu-id="8ea4c-240">19003</span></span>  <br/> |<span data-ttu-id="8ea4c-241">19002</span><span class="sxs-lookup"><span data-stu-id="8ea4c-241">19002</span></span>  <br/> |
|<span data-ttu-id="8ea4c-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="8ea4c-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="8ea4c-243">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="8ea4c-243">Edge Server</span></span>  <br/> |<span data-ttu-id="8ea4c-244">22003</span><span class="sxs-lookup"><span data-stu-id="8ea4c-244">22003</span></span>  <br/> |<span data-ttu-id="8ea4c-245">22002</span><span class="sxs-lookup"><span data-stu-id="8ea4c-245">22002</span></span>  <br/> |

<span data-ttu-id="8ea4c-246">次の表は、Microsoft が監視を推奨するネットワークの問題を示しています。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="8ea4c-247">モニター名</span><span class="sxs-lookup"><span data-stu-id="8ea4c-247">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="8ea4c-248">ターゲットサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="8ea4c-248">Target Server Role</span></span>  <br/> | <span data-ttu-id="8ea4c-249">成功イベント ID の式</span><span class="sxs-lookup"><span data-stu-id="8ea4c-249">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="8ea4c-250">エラーイベント ID 式</span><span class="sxs-lookup"><span data-stu-id="8ea4c-250">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="8ea4c-251">エラーの例</span><span class="sxs-lookup"><span data-stu-id="8ea4c-251">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="8ea4c-252">仲介サーバーからゲートウェイへの接続エラー</span><span class="sxs-lookup"><span data-stu-id="8ea4c-252">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="8ea4c-253">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="8ea4c-253">Mediation Server</span></span>  <br/>   | <span data-ttu-id="8ea4c-254">25062</span><span class="sxs-lookup"><span data-stu-id="8ea4c-254">25062</span></span>                              |                                  | <span data-ttu-id="8ea4c-255">25002</span><span class="sxs-lookup"><span data-stu-id="8ea4c-255">25002</span></span>  <br/>           |
| <span data-ttu-id="8ea4c-256">ゲートウェイ間の呼び出しの完了エラー</span><span class="sxs-lookup"><span data-stu-id="8ea4c-256">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="8ea4c-257">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="8ea4c-257">Mediation Server</span></span>  <br/>   | <span data-ttu-id="8ea4c-258">25064</span><span class="sxs-lookup"><span data-stu-id="8ea4c-258">25064</span></span>                              |                                  | <span data-ttu-id="8ea4c-259">25002</span><span class="sxs-lookup"><span data-stu-id="8ea4c-259">25002</span></span>  <br/>           |
| <span data-ttu-id="8ea4c-260">重大なネットワークの問題</span><span class="sxs-lookup"><span data-stu-id="8ea4c-260">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="8ea4c-261">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="8ea4c-261">Edge Server</span></span>  <br/>        | <span data-ttu-id="8ea4c-262">14353</span><span class="sxs-lookup"><span data-stu-id="8ea4c-262">14353</span></span>                              |                                  | <span data-ttu-id="8ea4c-263">12288</span><span class="sxs-lookup"><span data-stu-id="8ea4c-263">12288</span></span>  <br/>           |

<span data-ttu-id="8ea4c-264">以下は、監視する必要がある通話容量カウンターの一覧です。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-264">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="8ea4c-265">これらの数値は、クラウドコネクタの標準エディションでは500より少なくなります。クラウドコネクタの最小エディションの場合は、50未満です。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-265">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="8ea4c-266">LS: MediationServer-Inbound Calls (_Total)\- Current</span><span class="sxs-lookup"><span data-stu-id="8ea4c-266">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="8ea4c-267">LS: MediationServer-送信通話 (_Total)\- Current</span><span class="sxs-lookup"><span data-stu-id="8ea4c-267">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="8ea4c-268">LS: MediationServer-着信通話 (_Total)\-アクティブメディアでの通話のバイパス</span><span class="sxs-lookup"><span data-stu-id="8ea4c-268">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="8ea4c-269">LS: MediationServer-送信通話 (_Total)\-アクティブメディアでの通話のバイパス</span><span class="sxs-lookup"><span data-stu-id="8ea4c-269">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="8ea4c-270">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ea4c-270">See also</span></span>

<span data-ttu-id="8ea4c-271">OMS の使い方の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ea4c-271">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="8ea4c-272">ログ分析でログの検索を使用してデータを検索する</span><span class="sxs-lookup"><span data-stu-id="8ea4c-272">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="8ea4c-273">Azure Log Analytics の言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="8ea4c-273">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="8ea4c-274">ログ分析の警告について</span><span class="sxs-lookup"><span data-stu-id="8ea4c-274">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="8ea4c-275">Windows コンピューターを Azure のログ分析サービスに接続する</span><span class="sxs-lookup"><span data-stu-id="8ea4c-275">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


