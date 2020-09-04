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
description: このトピックでは、Microsoft Operations Management Suite (OMS) を使用して Cloud Connector バージョン2.1 以降の展開を監視する方法について説明します。
ms.openlocfilehash: eca2f56bf564e376717a42bd8d297710905f8dc6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359093"
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="39805-103">Operations Management Suite (OMS) を使用した Cloud Connector の監視</span><span class="sxs-lookup"><span data-stu-id="39805-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>

> [!Important]
> <span data-ttu-id="39805-104">Cloud Connector エディションは、2021年7月31日、Skype for Business Online と共に廃止されます。</span><span class="sxs-lookup"><span data-stu-id="39805-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="39805-105">組織が Teams にアップグレードされたら、 [直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを teams に接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="39805-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="39805-106">このトピックでは、Microsoft Operations Management Suite (OMS) を使用して Cloud Connector バージョン2.1 以降の展開を監視する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="39805-106">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>

<span data-ttu-id="39805-107">Microsoft cloud IT management solution である Operations Management Suite (OMS) を使用して、Cloud Connector バージョン2.1 以降の展開を監視できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="39805-107">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="39805-108">OMS ログ分析を使用すると、物理および仮想マシンを含むリソースの可用性とパフォーマンスを監視および分析することができます。</span><span class="sxs-lookup"><span data-stu-id="39805-108">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="39805-109">OMS とログ分析の詳細については、「 [Operations Management Suite (oms) とは](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39805-109">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)</span></span>

<span data-ttu-id="39805-110">このトピックは、以下のセクションで構成されています。</span><span class="sxs-lookup"><span data-stu-id="39805-110">This topic contains the following sections:</span></span>

- <span data-ttu-id="39805-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="39805-111">Prerequisites</span></span>

- <span data-ttu-id="39805-112">OMS を使用するように Cloud Connector を構成する</span><span class="sxs-lookup"><span data-stu-id="39805-112">Configure Cloud Connector to use OMS</span></span>

- <span data-ttu-id="39805-113">OMS を構成する</span><span class="sxs-lookup"><span data-stu-id="39805-113">Configure OMS</span></span>

- <span data-ttu-id="39805-114">ログ分析リポジトリのアラートを分析する</span><span class="sxs-lookup"><span data-stu-id="39805-114">Analyze the alerts in your Log Analytics repository</span></span>

- <span data-ttu-id="39805-115">推奨される監視セット</span><span class="sxs-lookup"><span data-stu-id="39805-115">Recommended monitoring set</span></span>

## <a name="prerequisites"></a><span data-ttu-id="39805-116">前提条件</span><span class="sxs-lookup"><span data-stu-id="39805-116">Prerequisites</span></span>

<span data-ttu-id="39805-117">OMS を使用して Cloud Connector の展開を監視するには、次のものが必要になります。</span><span class="sxs-lookup"><span data-stu-id="39805-117">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>

- <span data-ttu-id="39805-118">**Azure アカウントおよび OMS ワークスペース。**</span><span class="sxs-lookup"><span data-stu-id="39805-118">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="39805-119">まだ Azure アカウントを持っていない場合は、OMS ログ分析を使用するためのアカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39805-119">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="39805-120">Azure アカウントを作成し、OMS ワークスペースをセットアップする方法については、「 [Log Analytics workspace の使用を開始](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39805-120">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/azure/log-analytics/log-analytics-get-started).</span></span>

- <span data-ttu-id="39805-121">**Cloud Connector バージョン2.1 以降**</span><span class="sxs-lookup"><span data-stu-id="39805-121">**Cloud Connector version 2.1 or later**</span></span>

- <span data-ttu-id="39805-122">**Log Analytics 新しいログの検索** は、Cloud Connector の監視に必要です。</span><span class="sxs-lookup"><span data-stu-id="39805-122">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="39805-123">詳細については、「 [Azure Log Analytics workspace を新しいログ検索にアップグレードする](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39805-123">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>

## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="39805-124">OMS を使用するように Cloud Connector を構成する</span><span class="sxs-lookup"><span data-stu-id="39805-124">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="39805-125">OMS を使用するには、Cloud Connector のオンプレミス環境を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39805-125">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="39805-126">これを行うには、OMS ワークスペース ID とキーが必要です。これは、次のように、OMS ポータルを使用して確認できます。設定-- \> 接続されているソース-- \> Windows サーバー:</span><span class="sxs-lookup"><span data-stu-id="39805-126">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>

![Cloud Connector OMS のスクリーンショット](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)

<span data-ttu-id="39805-128">OMS を使用するように Cloud Connector を構成する方法は、シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="39805-128">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>

- <span data-ttu-id="39805-129">**新しい Cloud Connector アプライアンスをインストールする場合、またはアプライアンスを再展開する場合は**、次の手順に従ってインストール-ccappliance を実行してください。</span><span class="sxs-lookup"><span data-stu-id="39805-129">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>

    1. <span data-ttu-id="39805-130">[CloudConnector.ini ファイル [Common]] セクションで、OMSEnabled パラメーターを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="39805-130">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>

        <span data-ttu-id="39805-131">Cloud Connector が展開またはアップグレードされるたびに、OMS エージェントを Vm に自動的にインストールしようとします。</span><span class="sxs-lookup"><span data-stu-id="39805-131">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="39805-132">この機能を有効にすると、OMS エージェントは Cloud Connector の自動更新を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="39805-132">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>

    2. <span data-ttu-id="39805-133">OMS ID とキーを構成するには、「Set-CcCredential-AccountType OMSWorkspace」を実行します。</span><span class="sxs-lookup"><span data-stu-id="39805-133">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

- <span data-ttu-id="39805-134">**既存の Cloud Connector アプライアンスに OMS エージェントをインストールする場合**は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="39805-134">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>

    1. <span data-ttu-id="39805-135">CloudConnector.ini ファイル [Common] セクションで、OMSEnabled = true に設定します。</span><span class="sxs-lookup"><span data-stu-id="39805-135">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 

    2. <span data-ttu-id="39805-136">Import-CcConfiguration を実行します。</span><span class="sxs-lookup"><span data-stu-id="39805-136">Run Import-CcConfiguration.</span></span> 

    3. <span data-ttu-id="39805-137">CcOMSAgent を実行します。</span><span class="sxs-lookup"><span data-stu-id="39805-137">Run Install-CcOMSAgent.</span></span> 

        > [!NOTE]
        > <span data-ttu-id="39805-138">OMSWorkspace 資格情報が設定されていない場合は、CcOMSAgent を実行するときに資格情報の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="39805-138">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 

- <span data-ttu-id="39805-139">**Oms エージェントが既にインストールされている Cloud Connector アプライアンスで、OMS ワークスペース ID またはキーを更新する場合は、次のようにします。**</span><span class="sxs-lookup"><span data-stu-id="39805-139">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>

    1. <span data-ttu-id="39805-140">OMS ID とキーを構成するには、「Set-CcCredential-AccountType OMSWorkspace」を実行します。</span><span class="sxs-lookup"><span data-stu-id="39805-140">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 

    2. <span data-ttu-id="39805-141">更新プログラムを適用するには、CcOMSAgent を実行します。</span><span class="sxs-lookup"><span data-stu-id="39805-141">To apply the updates, run Install-CcOMSAgent.</span></span> 

- <span data-ttu-id="39805-142">**すべてのシナリオで、エージェントが次のように接続されていることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="39805-142">**For all scenarios, verify that the agents are connected as follows:**</span></span>

    <span data-ttu-id="39805-143">OMS ポータルで、[設定- \> 接続されたソース-Windows サーバー] に移動し \> ます。</span><span class="sxs-lookup"><span data-stu-id="39805-143">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="39805-144">接続されているコンピューターの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39805-144">You will see a list of connected machines.</span></span> 

## <a name="configure-oms"></a><span data-ttu-id="39805-145">OMS を構成する</span><span class="sxs-lookup"><span data-stu-id="39805-145">Configure OMS</span></span>

<span data-ttu-id="39805-146">次に、OMS ポータルを使用して OMS 構成を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39805-146">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="39805-147">具体的には、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="39805-147">Specifically, you will need to:</span></span>

- <span data-ttu-id="39805-148">イベントログとパフォーマンスカウンターに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="39805-148">Specify information about event logs and performance counters.</span></span>

- <span data-ttu-id="39805-149">通知を作成します。</span><span class="sxs-lookup"><span data-stu-id="39805-149">Create alerts.</span></span> 

### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="39805-150">イベントログとパフォーマンスカウンターに関する情報を指定する</span><span class="sxs-lookup"><span data-stu-id="39805-150">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="39805-151">OMS ポータルでは、次のように、イベントログとパフォーマンスカウンターに関する情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39805-151">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>

1. <span data-ttu-id="39805-152">[設定- \> データ- \> Windows イベントログ] に移動し、イベントログを次のように追加します。</span><span class="sxs-lookup"><span data-stu-id="39805-152">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 

   - <span data-ttu-id="39805-153">Lync Server</span><span class="sxs-lookup"><span data-stu-id="39805-153">Lync Server</span></span>

   - <span data-ttu-id="39805-154">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="39805-154">Application</span></span>

     > [!NOTE]
     > <span data-ttu-id="39805-155">テキストボックスには、Lync Server を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39805-155">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="39805-156">ドロップダウンリストにはオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="39805-156">It does not appear as an option in the drop-down list.</span></span> 

     <span data-ttu-id="39805-157">詳細については、「 [Log Analytics の Windows イベントログデータソース](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39805-157">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>

2. <span data-ttu-id="39805-158">[設定- \> データ- \> Windows パフォーマンスカウンター] に移動し、以下のパフォーマンスカウンターを追加します。</span><span class="sxs-lookup"><span data-stu-id="39805-158">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 

   - <span data-ttu-id="39805-159">**OS レベルのカウンター**。</span><span class="sxs-lookup"><span data-stu-id="39805-159">**OS level counters**.</span></span> <span data-ttu-id="39805-160">OS レベルのカウンター (プロセッサの使用状況、メモリ使用率、ネットワークの使用状況など) を追加したり、カウンターを明示的に追加せずに容量やパフォーマンスなどの既存のソリューションを使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="39805-160">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="39805-161">これらの監視をどのように決定するかにかかわらず、Microsoft では、これらの OS カウンターを監視することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39805-161">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>

   - <span data-ttu-id="39805-162">**Skype For business のカウンター**。</span><span class="sxs-lookup"><span data-stu-id="39805-162">**Skype for Business counters**.</span></span> <span data-ttu-id="39805-163">Skype for Business で提供されるカウンターは多数あります。</span><span class="sxs-lookup"><span data-stu-id="39805-163">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="39805-164">これらのカウンターは、仲介サーバーにログオンしてパフォーマンスモニターを開くことで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="39805-164">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="39805-165">これらのカウンターは、"LS:" から始まります。</span><span class="sxs-lookup"><span data-stu-id="39805-165">These counters start with "LS:".</span></span> <span data-ttu-id="39805-166">Microsoft では、少なくとも次の容量カウンターから始めて、興味のあるユーザーを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39805-166">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>

     <span data-ttu-id="39805-167">アクティブな通話の合計数:</span><span class="sxs-lookup"><span data-stu-id="39805-167">Total active calls:</span></span>

       - <span data-ttu-id="39805-168">LS: MediationServer-着信呼び出し (_Total) \- Current</span><span class="sxs-lookup"><span data-stu-id="39805-168">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

       - <span data-ttu-id="39805-169">LS: MediationServer-送信呼び出し (_Total) \- Current</span><span class="sxs-lookup"><span data-stu-id="39805-169">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

     <span data-ttu-id="39805-170">アクティブなメディアバイパス呼び出しの合計数:</span><span class="sxs-lookup"><span data-stu-id="39805-170">Total active media bypass calls:</span></span>

       - <span data-ttu-id="39805-171">LS: MediationServer-着信呼び出し (_Total) \- アクティブメディアバイパス呼び出し</span><span class="sxs-lookup"><span data-stu-id="39805-171">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 

       - <span data-ttu-id="39805-172">LS: MediationServer-送信呼び出し (_Total) \- アクティブメディアバイパス呼び出し</span><span class="sxs-lookup"><span data-stu-id="39805-172">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 

     > [!NOTE]
     > <span data-ttu-id="39805-173">テキストボックスには、パフォーマンスカウンターを手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39805-173">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="39805-174">ドロップダウンリストにはオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="39805-174">They do not appear as options in the drop-down list.</span></span> 

     <span data-ttu-id="39805-175">詳細については、「 [Windows と Linux のパフォーマンスデータソース (ログ分析](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39805-175">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>

### <a name="create-alerts"></a><span data-ttu-id="39805-176">通知を作成する</span><span class="sxs-lookup"><span data-stu-id="39805-176">Create alerts</span></span>

<span data-ttu-id="39805-177">OMS には、結果アラート数と指標測定通知の2種類の通知があります。</span><span class="sxs-lookup"><span data-stu-id="39805-177">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="39805-178">通知の作成の詳細については、「 [Log Analytics で通知ルール](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating)を使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39805-178">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts-creating).</span></span>

<span data-ttu-id="39805-179">通知を作成するときは、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39805-179">You should consider the following when creating alerts:</span></span>

- <span data-ttu-id="39805-180">通知は、既定の選択である [結果の数] 通知であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="39805-180">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 

- <span data-ttu-id="39805-181">デモクエリでは、"結果の数" が "0 より大きい" に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="39805-181">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 

- <span data-ttu-id="39805-182">時間枠と警告頻度の両方を5分に設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39805-182">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 

- <span data-ttu-id="39805-183">デモ通知に対して [通知の抑制] を有効にしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39805-183">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 

- <span data-ttu-id="39805-184">一般的な警告シナリオでは、1つのエラー通知と1つのリセット通知のペアを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39805-184">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="39805-185">エラーアラートの場合は、[重要度レベル] を選択します。[リセット] 通知で、[重大度レベルの情報] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39805-185">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>

<span data-ttu-id="39805-186">次のセクションでは、サンプル通知を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="39805-186">The following sections describe how to create sample alerts.</span></span>

 <span data-ttu-id="39805-187">**通知のペアを作成する: "RTCMEDSRV は、仲介サーバーで実行されていません" および "RTCMEDSRV は、仲介サーバーで実行中です" というメッセージが返されます。**</span><span class="sxs-lookup"><span data-stu-id="39805-187">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>

<span data-ttu-id="39805-188">このアラートのペアを作成するには</span><span class="sxs-lookup"><span data-stu-id="39805-188">To create this alert pair:</span></span>

- <span data-ttu-id="39805-189">エラーアラートのクエリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="39805-189">The query for the error alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)  | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="39805-190">このクエリは、コンピューターに  *"MediationServer" が含まれて*  いるコンピューターフィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="39805-190">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="39805-191">このフィルターでは、名前に "MediationServer" という文字列が含まれているコンピューターのみが選択されます。</span><span class="sxs-lookup"><span data-stu-id="39805-191">The filter selects only the computer whose name contains the string "MediationServer".</span></span>

     <span data-ttu-id="39805-192">フィルターを自分のコンピューターフィルターに置き換えるか、削除するだけです。</span><span class="sxs-lookup"><span data-stu-id="39805-192">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="39805-193">正規表現を使用せずに複雑な文字列フィルターを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="39805-193">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="39805-194">詳細については、「 [文字列演算子](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39805-194">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="39805-195">正規表現を使用するように選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="39805-195">You can also choose to use regular expressions.</span></span> <span data-ttu-id="39805-196">さらに、検索クエリを保存し、そのグループを警告クエリのコンピューターフィルターとして使用することによって、コンピューターグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="39805-196">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="39805-197">詳細については、「 [Log Analytics log 検索のコンピューターグループ](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39805-197">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/azure/log-analytics/log-analytics-computer-groups).</span></span>

    <span data-ttu-id="39805-198">エラークエリは、各コンピューターについて、RTCMEDSRV サービス開始とサービス停止の両方の最後のイベントログを取得します。</span><span class="sxs-lookup"><span data-stu-id="39805-198">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="39805-199">最後のイベントがサービス停止イベントの場合は、1つのログが返されます。最後のイベントがサービス開始イベントの場合、nothing が返されます。</span><span class="sxs-lookup"><span data-stu-id="39805-199">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="39805-200">省略すると、クエリは、時間枠で RTCMEDSRV が停止しているサーバーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="39805-200">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 

- <span data-ttu-id="39805-201">リセット警告のクエリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="39805-201">The query for the reset alert is:</span></span>

  ```Kusto
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003) | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="39805-202">リセットクエリは、エラークエリの逆の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="39805-202">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="39805-203">各コンピュータでは、最後のイベントがサービス開始イベントの場合は1を返します。最後のイベントがサービス停止イベントの場合は、nothing が返されます。</span><span class="sxs-lookup"><span data-stu-id="39805-203">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>

<span data-ttu-id="39805-204">**通知のペアを作成する: "仲介サーバーでの同時通話が多すぎます" および "同時呼び出しは通常の負荷に戻されます"**</span><span class="sxs-lookup"><span data-stu-id="39805-204">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>

<span data-ttu-id="39805-205">この通知を作成するには:</span><span class="sxs-lookup"><span data-stu-id="39805-205">To create this alert:</span></span>

- <span data-ttu-id="39805-206">エラーアラートのクエリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="39805-206">The query for the error alert is:</span></span>

  ```Kusto
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName == "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="39805-207">各コンピューターに対して、クエリは着信呼び出しと発信呼び出しの最後のカウンターを取得し、これら2つの値を合計します。</span><span class="sxs-lookup"><span data-stu-id="39805-207">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="39805-208">合計値が500を超えた場合、1つのログを返します。そうでない場合は nothing を返します。</span><span class="sxs-lookup"><span data-stu-id="39805-208">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="39805-209">省略すると、クエリは、時間枠に同時呼び出しが多すぎるサーバーの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="39805-209">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>

- <span data-ttu-id="39805-210">リセット警告のクエリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="39805-210">The query for the reset alert is:</span></span>

  ```Kusto
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==  "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize  TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500
  ```

    <span data-ttu-id="39805-211">リセットクエリは、エラークエリの逆の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="39805-211">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="39805-212">各コンピューターに対して、クエリは着信呼び出しと発信呼び出しの最後のカウンターを取得し、これら2つの値を合計します。</span><span class="sxs-lookup"><span data-stu-id="39805-212">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="39805-213">Sum 値が500より小さい場合は、1つのログを返します。それ以外の場合は何も返しません。</span><span class="sxs-lookup"><span data-stu-id="39805-213">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>

<span data-ttu-id="39805-214">**アラートを作成する: "CPU 使用率 \> 90 または RTCMEDIARELAY がサーバーで停止されました" アラート**</span><span class="sxs-lookup"><span data-stu-id="39805-214">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>

<span data-ttu-id="39805-215">この警告を作成するには、次のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="39805-215">To create this alert, the query is:</span></span>

```Kusto
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==  "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="39805-216">このクエリは、すべてのコンピューターからすべてのプロセッサ使用率カウンターとサービス停止イベントを取得し、プロセッサの使用率が90% を超えた場合またはサービスが停止した場合に、1つのログを返します。</span><span class="sxs-lookup"><span data-stu-id="39805-216">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 

## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="39805-217">ログ分析リポジトリのアラートを分析する</span><span class="sxs-lookup"><span data-stu-id="39805-217">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="39805-218">リポジトリ内のアラートを分析するには、アラート管理ソリューションを使用します。</span><span class="sxs-lookup"><span data-stu-id="39805-218">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="39805-219">詳細については、「 [Operations Management Suite (OMS)」の「Alert management solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39805-219">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/azure/log-analytics/log-analytics-solution-alert-management)</span></span>

## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="39805-220">推奨される最小の監視セット</span><span class="sxs-lookup"><span data-stu-id="39805-220">Recommended minimal monitoring set</span></span>

<span data-ttu-id="39805-221">イベントログとパフォーマンスカウンターに関する問題を特定するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="39805-221">To identify issues with event logs and performance counters:</span></span> 

- <span data-ttu-id="39805-222">**イベントログ**</span><span class="sxs-lookup"><span data-stu-id="39805-222">**Event logs.**</span></span> <span data-ttu-id="39805-223">問題がある場合は、イベントのペアがあり、何らかのイベントが発生していることを示すイベントセットがあり、もう1つはすべてが適切であることを示します。</span><span class="sxs-lookup"><span data-stu-id="39805-223">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="39805-224">指定した任意の期間について、その期間に amiss があるかどうかを示す最後のイベントが記録されます。</span><span class="sxs-lookup"><span data-stu-id="39805-224">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>

- <span data-ttu-id="39805-225">**パフォーマンスカウンター。**</span><span class="sxs-lookup"><span data-stu-id="39805-225">**Performance Counters.**</span></span> <span data-ttu-id="39805-226">監視対象のカウンターにはしきい値が必要です。</span><span class="sxs-lookup"><span data-stu-id="39805-226">There should be a threshold for the monitored counters.</span></span>

<span data-ttu-id="39805-227">次の表に、停止イベントと開始イベントの Id を一覧表示することによって監視を推奨するサービスを示します。</span><span class="sxs-lookup"><span data-stu-id="39805-227">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>

|<span data-ttu-id="39805-228">サービス名</span><span class="sxs-lookup"><span data-stu-id="39805-228">Service Name</span></span>  <br/> |<span data-ttu-id="39805-229">ターゲットサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="39805-229">Target Server Role</span></span>  <br/> |<span data-ttu-id="39805-230">停止イベント ID</span><span class="sxs-lookup"><span data-stu-id="39805-230">Stop Event ID</span></span>  <br/> |<span data-ttu-id="39805-231">開始イベント ID</span><span class="sxs-lookup"><span data-stu-id="39805-231">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="39805-232">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="39805-232">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="39805-233">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="39805-233">Mediation Server</span></span>  <br/> |<span data-ttu-id="39805-234">25003</span><span class="sxs-lookup"><span data-stu-id="39805-234">25003</span></span>  <br/> |<span data-ttu-id="39805-235">25002</span><span class="sxs-lookup"><span data-stu-id="39805-235">25002</span></span>  <br/> |
|<span data-ttu-id="39805-236">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="39805-236">RTCSRV</span></span>  <br/> |<span data-ttu-id="39805-237">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="39805-237">Edge Server</span></span>  <br/> |<span data-ttu-id="39805-238">12289</span><span class="sxs-lookup"><span data-stu-id="39805-238">12289</span></span>  <br/> |<span data-ttu-id="39805-239">12288</span><span class="sxs-lookup"><span data-stu-id="39805-239">12288</span></span>  <br/> |
|<span data-ttu-id="39805-240">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="39805-240">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="39805-241">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="39805-241">Edge Server</span></span>  <br/> |<span data-ttu-id="39805-242">19003</span><span class="sxs-lookup"><span data-stu-id="39805-242">19003</span></span>  <br/> |<span data-ttu-id="39805-243">19002</span><span class="sxs-lookup"><span data-stu-id="39805-243">19002</span></span>  <br/> |
|<span data-ttu-id="39805-244">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="39805-244">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="39805-245">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="39805-245">Edge Server</span></span>  <br/> |<span data-ttu-id="39805-246">22003</span><span class="sxs-lookup"><span data-stu-id="39805-246">22003</span></span>  <br/> |<span data-ttu-id="39805-247">22002</span><span class="sxs-lookup"><span data-stu-id="39805-247">22002</span></span>  <br/> |

<span data-ttu-id="39805-248">次の表に、Microsoft が監視を推奨するネットワークの問題を示します。</span><span class="sxs-lookup"><span data-stu-id="39805-248">The following table lists the network issues that Microsoft recommends monitoring:</span></span>


| <span data-ttu-id="39805-249">モニター名</span><span class="sxs-lookup"><span data-stu-id="39805-249">Monitor Name</span></span>  <br/>                                        | <span data-ttu-id="39805-250">ターゲットサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="39805-250">Target Server Role</span></span>  <br/> | <span data-ttu-id="39805-251">成功イベント ID 式</span><span class="sxs-lookup"><span data-stu-id="39805-251">Success Event ID expression</span></span>  <br/> | <span data-ttu-id="39805-252">エラーイベント ID 式</span><span class="sxs-lookup"><span data-stu-id="39805-252">Error Event ID expression</span></span>  <br/> | <span data-ttu-id="39805-253">エラーの例</span><span class="sxs-lookup"><span data-stu-id="39805-253">Failure example</span></span>  <br/> |
|:-----------------------------------------------------------|:--------------------------|:-----------------------------------|:---------------------------------|:-----------------------|
| <span data-ttu-id="39805-254">仲介サーバーからゲートウェイへの接続エラー</span><span class="sxs-lookup"><span data-stu-id="39805-254">Mediation Server to gateway connectivity failure</span></span>  <br/>    | <span data-ttu-id="39805-255">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="39805-255">Mediation Server</span></span>  <br/>   | <span data-ttu-id="39805-256">25062</span><span class="sxs-lookup"><span data-stu-id="39805-256">25062</span></span>                              |                                  | <span data-ttu-id="39805-257">25002</span><span class="sxs-lookup"><span data-stu-id="39805-257">25002</span></span>  <br/>           |
| <span data-ttu-id="39805-258">仲介サーバーからゲートウェイへの通話完了エラー</span><span class="sxs-lookup"><span data-stu-id="39805-258">Mediation Server to gateway call completion failure</span></span>  <br/> | <span data-ttu-id="39805-259">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="39805-259">Mediation Server</span></span>  <br/>   | <span data-ttu-id="39805-260">25064</span><span class="sxs-lookup"><span data-stu-id="39805-260">25064</span></span>                              |                                  | <span data-ttu-id="39805-261">25002</span><span class="sxs-lookup"><span data-stu-id="39805-261">25002</span></span>  <br/>           |
| <span data-ttu-id="39805-262">重大なネットワークの問題</span><span class="sxs-lookup"><span data-stu-id="39805-262">Critical network problems</span></span>  <br/>                           | <span data-ttu-id="39805-263">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="39805-263">Edge Server</span></span>  <br/>        | <span data-ttu-id="39805-264">14353</span><span class="sxs-lookup"><span data-stu-id="39805-264">14353</span></span>                              |                                  | <span data-ttu-id="39805-265">12288</span><span class="sxs-lookup"><span data-stu-id="39805-265">12288</span></span>  <br/>           |

<span data-ttu-id="39805-266">以下に、監視する必要がある通話能力カウンターの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="39805-266">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="39805-267">これらの数値は、Cloud Connector standard edition の場合は500未満である必要があります。Cloud Connector の最小版の50未満。</span><span class="sxs-lookup"><span data-stu-id="39805-267">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>

- <span data-ttu-id="39805-268">LS: MediationServer-着信呼び出し (_Total) \- Current</span><span class="sxs-lookup"><span data-stu-id="39805-268">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="39805-269">LS: MediationServer-送信呼び出し (_Total) \- Current</span><span class="sxs-lookup"><span data-stu-id="39805-269">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 

- <span data-ttu-id="39805-270">LS: MediationServer-着信呼び出し (_Total) \- アクティブメディアバイパス呼び出し</span><span class="sxs-lookup"><span data-stu-id="39805-270">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>

- <span data-ttu-id="39805-271">LS: MediationServer-送信呼び出し (_Total) \- アクティブメディアバイパス呼び出し</span><span class="sxs-lookup"><span data-stu-id="39805-271">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>

## <a name="see-also"></a><span data-ttu-id="39805-272">関連項目</span><span class="sxs-lookup"><span data-stu-id="39805-272">See also</span></span>

<span data-ttu-id="39805-273">OMS の使用の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39805-273">For more information about working with OMS, see the following:</span></span>

- [<span data-ttu-id="39805-274">ログ分析でログ検索を使用してデータを検索する</span><span class="sxs-lookup"><span data-stu-id="39805-274">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-log-searches)

- [<span data-ttu-id="39805-275">Azure Log Analytics Language リファレンス</span><span class="sxs-lookup"><span data-stu-id="39805-275">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)

- [<span data-ttu-id="39805-276">ログ分析の警告について</span><span class="sxs-lookup"><span data-stu-id="39805-276">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-alerts)

- [<span data-ttu-id="39805-277">Windows コンピューターを Azure の Log Analytics サービスに接続する</span><span class="sxs-lookup"><span data-stu-id="39805-277">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)


