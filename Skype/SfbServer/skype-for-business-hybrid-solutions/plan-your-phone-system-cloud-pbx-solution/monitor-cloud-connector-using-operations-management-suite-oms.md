---
title: 運用管理スイート (OMS) を使用してクラウドのコネクタを監視します。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: edf4a04c-d4c9-4c05-aacc-9e084618bb55
description: 運用管理スイート (OMS) を使用して、クラウド コネクタ バージョン 2.1 とそれ以降の展開を監視する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 8cb454cfcb61bb11e0545ab5ff7dd45d1403ce55
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2018
---
# <a name="monitor-cloud-connector-using-operations-management-suite-oms"></a><span data-ttu-id="15547-103">運用管理スイート (OMS) を使用してクラウドのコネクタを監視します。</span><span class="sxs-lookup"><span data-stu-id="15547-103">Monitor Cloud Connector using Operations Management Suite (OMS)</span></span>
 
<span data-ttu-id="15547-104">運用管理スイート (OMS) を使用して、クラウド コネクタ バージョン 2.1 とそれ以降の展開を監視する方法の詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="15547-104">Read this topic to learn how to monitor your Cloud Connector version 2.1 and later deployment by using Microsoft Operations Management Suite (OMS).</span></span>
  
<span data-ttu-id="15547-105">運用管理スイート (OMS)、マイクロソフトのクラウド IT 管理ソリューションを使用して、クラウド コネクタ バージョン 2.1 とそれ以降の展開を監視できます。</span><span class="sxs-lookup"><span data-stu-id="15547-105">You can now monitor your Cloud Connector version 2.1 and later deployment by using Operations Management Suite (OMS), a Microsoft cloud IT management solution.</span></span> <span data-ttu-id="15547-106">OMS のログ分析機能を使用すると、監視し、可用性となどの物理リソースと仮想マシンのパフォーマンスを分析できます。</span><span class="sxs-lookup"><span data-stu-id="15547-106">OMS Log Analytics enables you to monitor and analyze the availability and performance of resources including physical and virtual machines.</span></span> <span data-ttu-id="15547-107">OMS とログ分析の詳細についてを参照してください[操作の管理スイート (OMS) とは何ですか?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview)。</span><span class="sxs-lookup"><span data-stu-id="15547-107">For more information about OMS and Log Analytics, see [What is Operations Management Suite (OMS)?](https://docs.microsoft.com/en-us/azure/operations-management-suite/operations-management-suite-overview).</span></span>
  
<span data-ttu-id="15547-108">このトピックには次のセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="15547-108">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="15547-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="15547-109">Prerequisites</span></span>
    
- <span data-ttu-id="15547-110">OMS を使用するクラウドのコネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="15547-110">Configure Cloud Connector to use OMS</span></span>
    
- <span data-ttu-id="15547-111">OMS を構成します。</span><span class="sxs-lookup"><span data-stu-id="15547-111">Configure OMS</span></span>
    
- <span data-ttu-id="15547-112">ログ分析リポジトリ内のアラートを分析します。</span><span class="sxs-lookup"><span data-stu-id="15547-112">Analyze the alerts in your Log Analytics repository</span></span>
    
- <span data-ttu-id="15547-113">推奨される監視の設定</span><span class="sxs-lookup"><span data-stu-id="15547-113">Recommended monitoring set</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="15547-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="15547-114">Prerequisites</span></span>

<span data-ttu-id="15547-115">OMS を使用するには、コネクタのクラウドの展開を監視するため、前に、以下が必要。</span><span class="sxs-lookup"><span data-stu-id="15547-115">Before you can use OMS to monitor your Cloud Connector deployment, you will need the following:</span></span>
  
- <span data-ttu-id="15547-116">**Azure アカウントと、OMS のワークスペースです。**</span><span class="sxs-lookup"><span data-stu-id="15547-116">**An Azure account and an OMS workspace.**</span></span> <span data-ttu-id="15547-117">既に Azure アカウントをお持ちでない場合は、OMS のログ分析機能を使用する 1 つを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15547-117">If you don't already have an Azure account, you will need to create one to use OMS Log Analytics.</span></span> <span data-ttu-id="15547-118">Azure アカウントを作成し、OMS のワークスペースを設定する方法の詳細については、[ログ分析機能のワークスペースを使い始める](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15547-118">For information about how to create an Azure account and set up an OMS workspace, see [Get started with a Log Analytics workspace](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-get-started).</span></span>
    
- <span data-ttu-id="15547-119">**クラウド コネクタ 2.1 またはそれ以降のバージョン**</span><span class="sxs-lookup"><span data-stu-id="15547-119">**Cloud Connector version 2.1 or later**</span></span>
    
- <span data-ttu-id="15547-120">**ログ分析の新しいログの検索**では、クラウドのコネクタを監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15547-120">**Log Analytics new log search** is required for Cloud Connector monitoring.</span></span> <span data-ttu-id="15547-121">詳細については、[新しいログの検索対象に Azure のログ分析ワークスペースのアップグレード](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15547-121">For more information, see [Upgrade your Azure Log Analytics workspace to new log search](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-search-upgrade).</span></span>
    
## <a name="configure-cloud-connector-to-use-oms"></a><span data-ttu-id="15547-122">OMS を使用するクラウドのコネクタを構成します。</span><span class="sxs-lookup"><span data-stu-id="15547-122">Configure Cloud Connector to use OMS</span></span>

<span data-ttu-id="15547-123">OMS を使用するクラウド コネクタ、オンプレミス環境を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15547-123">You'll need to configure your Cloud Connector on-premises environment to use OMS.</span></span> <span data-ttu-id="15547-124">これを行うには、する必要があります、OMS ワークスペース ID とキーが、OMS のポータルを使用して次のように、検索することができます: 設定 -\>ソースの接続 -\> Windows サーバー。</span><span class="sxs-lookup"><span data-stu-id="15547-124">To do this, you will need your OMS workspace ID and key, which you can find by using the OMS portal as follows: Settings --\>Connected Sources --\> Windows Servers:</span></span>
  
![Cloud Connector OMS のスクリーンショット](../../media/a4bb0a96-c940-435e-a3f5-5ef3062dea83.png)
  
<span data-ttu-id="15547-126">OMS を使用するクラウドのコネクタを構成する方法は、シナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="15547-126">How you configure Cloud Connector to use OMS depends on your scenario:</span></span>
  
- <span data-ttu-id="15547-127">**クラウド コネクタの新しいアプライアンスをインストールするか、アプライアンスを再配置する場合**、インストール CcAppliance を実行する前にこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="15547-127">**If you are installing a new Cloud Connector appliance or you want to re-deploy an appliance**, follow these steps before you run Install-CcAppliance:</span></span>
    
1. <span data-ttu-id="15547-128">CloudConnector.ini ファイルの [共通] セクションに OMSEnabled パラメーターを True に設定します。</span><span class="sxs-lookup"><span data-stu-id="15547-128">In the CloudConnector.ini file [Common] section, set the OMSEnabled parameter to True.</span></span>
    
    <span data-ttu-id="15547-129">クラウド コネクタを展開またはアップグレードするたびにしようと、Vm 上に自動的に OMS のエージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="15547-129">Each time Cloud Connector is deployed or upgraded, it will try to install the OMS agent automatically onto the VMs.</span></span> <span data-ttu-id="15547-130">OMS のエージェントは、クラウド コネクタの自動更新を生き残ることができますので、この機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="15547-130">Enable this feature so the OMS agent can survive the Cloud Connector automatic update.</span></span>
    
2. <span data-ttu-id="15547-131">OMS の ID とキーを構成するには、セット CcCredential AccountType の OMSWorkspace を実行します。</span><span class="sxs-lookup"><span data-stu-id="15547-131">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 
    
- <span data-ttu-id="15547-132">**既存のコネクタのクラウド アプライアンスに OMS エージェントをインストールするかどうかは**、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="15547-132">**If you are installing an OMS agent onto an existing Cloud Connector appliance**, follow these steps:</span></span>
    
1. <span data-ttu-id="15547-133">CloudConnector.ini [共通] セクションで、ファイル内の設定 OMSEnabled = true です。</span><span class="sxs-lookup"><span data-stu-id="15547-133">In the CloudConnector.ini file [Common] section, set OMSEnabled=true.</span></span> 
    
2. <span data-ttu-id="15547-134">インポート-CcConfiguration を実行します。</span><span class="sxs-lookup"><span data-stu-id="15547-134">Run Import-CcConfiguration.</span></span> 
    
3. <span data-ttu-id="15547-135">インストール CcOMSAgent を実行します。</span><span class="sxs-lookup"><span data-stu-id="15547-135">Run Install-CcOMSAgent.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="15547-136">OMSWorkspace の資格情報が設定されていることはない場合は、インストール CcOMSAgent を実行すると、資格情報の求められます。</span><span class="sxs-lookup"><span data-stu-id="15547-136">If the OMSWorkspace credential has never been set, you are prompted for the credential when you run install-CcOMSAgent.</span></span> 
  
- <span data-ttu-id="15547-137">**OMS ワークスペース ID またはコネクタのクラウド アプライアンス内のキーを更新する場合、OMS エージェントを既にインストールされているには。**</span><span class="sxs-lookup"><span data-stu-id="15547-137">**If you want to update the OMS workspace ID or key in a Cloud Connector appliance that has already installed an OMS agent:**</span></span>
    
1. <span data-ttu-id="15547-138">OMS の ID とキーを構成するには、セット CcCredential AccountType の OMSWorkspace を実行します。</span><span class="sxs-lookup"><span data-stu-id="15547-138">To configure the OMS ID and key, run Set-CcCredential -AccountType OMSWorkspace.</span></span> 
    
2. <span data-ttu-id="15547-139">更新プログラムを適用するには、インストール CcOMSAgent を実行します。</span><span class="sxs-lookup"><span data-stu-id="15547-139">To apply the updates, run Install-CcOMSAgent.</span></span> 
    
- <span data-ttu-id="15547-140">**すべてのシナリオでは、エージェントが次のように接続されていることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="15547-140">**For all scenarios, verify that the agents are connected as follows:**</span></span>
    
    <span data-ttu-id="15547-141">OMS ポータルで、[設定] -\> - [ソースの接続されている\>Windows サーバーです。</span><span class="sxs-lookup"><span data-stu-id="15547-141">In the OMS portal, go to Settings -\> Connected Sources -\> Windows Servers.</span></span> <span data-ttu-id="15547-142">接続されているマシンの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="15547-142">You will see a list of connected machines.</span></span> 
    
## <a name="configure-oms"></a><span data-ttu-id="15547-143">OMS を構成します。</span><span class="sxs-lookup"><span data-stu-id="15547-143">Configure OMS</span></span>

<span data-ttu-id="15547-144">次に、OMS のポータルを使用して、OMS の構成を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15547-144">Next, you will need to specify your OMS configuration by using the OMS portal.</span></span> <span data-ttu-id="15547-145">具体的には、する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15547-145">Specifically, you will need to:</span></span>
  
- <span data-ttu-id="15547-146">イベント ログおよびパフォーマンス カウンターに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="15547-146">Specify information about event logs and performance counters.</span></span>
    
- <span data-ttu-id="15547-147">アラートを作成します。</span><span class="sxs-lookup"><span data-stu-id="15547-147">Create alerts.</span></span> 
    
### <a name="specify-information-about-event-logs-and-performance-counters"></a><span data-ttu-id="15547-148">イベント ログおよびパフォーマンス カウンターに関する情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="15547-148">Specify information about event logs and performance counters</span></span>

<span data-ttu-id="15547-149">OMS ポータルでは、次のように、イベント ログおよびパフォーマンス カウンターに関する情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15547-149">In the OMS portal, you must specify information about the event logs and performance counters as follows:</span></span>
  
1. <span data-ttu-id="15547-150">設定 - を参照して\>データ ・\>Windows イベント ログのイベント ログを追加し、。</span><span class="sxs-lookup"><span data-stu-id="15547-150">Go to Settings-\>Data-\>Windows Event logs, and add event logs for:</span></span> 
    
  - <span data-ttu-id="15547-151">Lync Server</span><span class="sxs-lookup"><span data-stu-id="15547-151">Lync Server</span></span>
    
  - <span data-ttu-id="15547-152">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="15547-152">Application</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="15547-153">テキスト ボックスに、Lync Server を手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15547-153">You must manually enter Lync Server in the text box.</span></span> <span data-ttu-id="15547-154">ドロップ ダウン リストでオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="15547-154">It does not appear as an option in the drop-down list.</span></span> 
  
    <span data-ttu-id="15547-155">詳細については、[ログの分析では、Windows イベント ログ データ ソース](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15547-155">For more information, see [Windows event log data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-windows-events)</span></span>
    
2. <span data-ttu-id="15547-156">設定 -\>データ -\> 、Windows パフォーマンス カウンターのパフォーマンス カウンターを追加し、。</span><span class="sxs-lookup"><span data-stu-id="15547-156">Go to Settings-\>Data-\> Windows Performance Counters, and add performance counters for:</span></span> 
    
  - <span data-ttu-id="15547-157">**OS レベルのカウンター**です。</span><span class="sxs-lookup"><span data-stu-id="15547-157">**OS level counters**.</span></span> <span data-ttu-id="15547-158">プロセッサ使用率、メモリ使用量、ネットワークの使用率など、OS レベルのカウンターを追加することができますや容量などのパフォーマンス、ネットワークのパフォーマンス モニター カウンターを明示的に追加することがなく既存のソリューションを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="15547-158">You can add OS level counters, such as processor usage, memory usage, network usage, or you can use existing solutions such as Capacity and Performance, Network Performance Monitor without adding counters explicitly.</span></span> <span data-ttu-id="15547-159">それらを監視するを決定する方法に関係なく、これらの OS のカウンターを監視することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15547-159">No matter how you decide to monitor them, Microsoft recommends that you monitor these OS counters.</span></span>
    
  - <span data-ttu-id="15547-160">**Skype ビジネスのカウンター**です。</span><span class="sxs-lookup"><span data-stu-id="15547-160">**Skype for Business counters**.</span></span> <span data-ttu-id="15547-161">ビジネス用の Skype によって提供される多数のカウンターがあります。</span><span class="sxs-lookup"><span data-stu-id="15547-161">There are numerous counters provided by Skype for Business.</span></span> <span data-ttu-id="15547-162">任意の仲介サーバーにログオンするいると、パフォーマンス モニターを開くには、これらのカウンターがあります。</span><span class="sxs-lookup"><span data-stu-id="15547-162">You can find these counters by logging on to any Mediation Server and opening the Performance Monitor.</span></span> <span data-ttu-id="15547-163">これらのカウンターが始まる"LS:"です。</span><span class="sxs-lookup"><span data-stu-id="15547-163">These counters start with "LS:".</span></span> <span data-ttu-id="15547-164">マイクロソフトでは、最低限、次の容量のカウンターを使用して開始し、興味のある他のユーザーを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15547-164">Microsoft recommends that you start with the following capacity counters at a minimum, and add others that are of interest:</span></span>
    
    <span data-ttu-id="15547-165">アクティブな呼び出しの合計:</span><span class="sxs-lookup"><span data-stu-id="15547-165">Total active calls:</span></span>
    
  - <span data-ttu-id="15547-166">LS:MediationServer - 受信 Calls(_Total)\-現在</span><span class="sxs-lookup"><span data-stu-id="15547-166">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 
    
  - <span data-ttu-id="15547-167">LS:MediationServer - 送信 Calls(_Total)\-現在</span><span class="sxs-lookup"><span data-stu-id="15547-167">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 
    
    <span data-ttu-id="15547-168">アクティブなメディアの合計は、呼び出しを使用しません。</span><span class="sxs-lookup"><span data-stu-id="15547-168">Total active media bypass calls:</span></span>
    
  - <span data-ttu-id="15547-169">LS:MediationServer - 受信 Calls(_Total)\-アクティブなメディアの呼び出しをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="15547-169">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span> 
    
  - <span data-ttu-id="15547-170">LS:MediationServer - 送信 Calls(_Total)\-アクティブなメディアの呼び出しをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="15547-170">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="15547-171">テキスト ボックスに、パフォーマンス カウンターを手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15547-171">You must manually enter the performance counters in the text box.</span></span> <span data-ttu-id="15547-172">ドロップ ダウン リストでオプションとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="15547-172">They do not appear as options in the drop-down list.</span></span> 
  
    <span data-ttu-id="15547-173">詳細については、[ログ分析機能で、Windows と Linux のパフォーマンス データ ソース](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15547-173">For more information, see [Windows and Linux performance data sources in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-data-sources-performance-counters)</span></span>
    
### <a name="create-alerts"></a><span data-ttu-id="15547-174">アラートを作成します。</span><span class="sxs-lookup"><span data-stu-id="15547-174">Create alerts</span></span>

<span data-ttu-id="15547-175">OMS のアラートの 2 種類があります: 結果の通知とメートル法の警告の数。</span><span class="sxs-lookup"><span data-stu-id="15547-175">There are two types of alerts in OMS: Number of results alerts and Metric measurement alerts.</span></span> <span data-ttu-id="15547-176">警告の作成の詳細については、[ログ分析の警告ルールの操作](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15547-176">For more information about creating alerts, see [Working with alert rules in Log Analytics](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts-creating).</span></span>
  
<span data-ttu-id="15547-177">アラートを作成するときは、以下を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="15547-177">You should consider the following when creating alerts:</span></span>
  
- <span data-ttu-id="15547-178">アラートは、デフォルトの選択、数値の結果のアラートを確認します。</span><span class="sxs-lookup"><span data-stu-id="15547-178">Make sure the alert is a Number-of-results alert, which is the default selection.</span></span> 
    
- <span data-ttu-id="15547-179">デモのクエリは、「結果の数」を"よりも長く 0"に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="15547-179">The demo queries require that "Number of results" is set to "Greater than 0".</span></span> 
    
- <span data-ttu-id="15547-180">5 分のタイム ・ ウィンドウおよび [通知の頻度を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15547-180">It is recommended that you set both Time window and Alert frequency to 5 minutes.</span></span> 
    
- <span data-ttu-id="15547-181">デモのアラートの「警告を抑制する」を有効にするいることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="15547-181">It is recommended that you do not enable "Suppress alerts" for demo alerts.</span></span> 
    
- <span data-ttu-id="15547-182">一般的には、アラートのアラートのペアの作成をお勧めします。: 1 つのエラー メッセージと警告の 1 つのリセットします。</span><span class="sxs-lookup"><span data-stu-id="15547-182">For typical alert scenarios, Microsoft recommends creating a pair of alerts: one error alert and one reset alert.</span></span> <span data-ttu-id="15547-183">エラーのアラートの重大度レベル重大な; を選択しますリセット警告の重大度レベルの情報を選択します。</span><span class="sxs-lookup"><span data-stu-id="15547-183">For the error alert, select severity level Critical; for the reset alert, select severity level Informational .</span></span>
    
<span data-ttu-id="15547-184">次のセクションでは、サンプルの通知を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="15547-184">The following sections describe how to create sample alerts.</span></span>
  
 <span data-ttu-id="15547-185">**アラートのペアを作成:「RTCMEDSRV は仲介サーバーで実行されていない」と「RTCMEDSRV は、仲介サーバーで実行するのには」**</span><span class="sxs-lookup"><span data-stu-id="15547-185">**Create an alert pair: "RTCMEDSRV is NOT running in Mediation Servers" and "RTCMEDSRV is back in running in Mediation Servers"**</span></span>
  
<span data-ttu-id="15547-186">このアラートのペアを作成します。</span><span class="sxs-lookup"><span data-stu-id="15547-186">To create this alert pair:</span></span>
  
- <span data-ttu-id="15547-187">エラー メッセージのクエリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="15547-187">The query for the error alert is:</span></span>
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer | where EventID == 25003
  ```

    <span data-ttu-id="15547-188">クエリを使用して、コンピューターのフィルターで*コンピューターに"MediationServer"が含まれている場合*。</span><span class="sxs-lookup"><span data-stu-id="15547-188">The query uses the computer filter  *where Computer contains "MediationServer"*  .</span></span> <span data-ttu-id="15547-189">フィルターは、名前に文字列"MediationServer"が含まれているコンピューターのみを選択します。</span><span class="sxs-lookup"><span data-stu-id="15547-189">The filter selects only the computer whose name contains the string "MediationServer".</span></span>
    
     <span data-ttu-id="15547-190">コンピューター フィルターでフィルターを交換してか、削除するだけとします。</span><span class="sxs-lookup"><span data-stu-id="15547-190">You would replace the filter with your own computer filter or simply remove it.</span></span> <span data-ttu-id="15547-191">正規表現のない複雑な文字列のフィルターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="15547-191">You can create complex string filters without regular expressions.</span></span> <span data-ttu-id="15547-192">詳細については、[文字列演算子](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15547-192">For more information, see [String operators](https://docs.loganalytics.io/docs/Language-Reference/Scalar-operators/String-operators).</span></span> <span data-ttu-id="15547-193">正規表現を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="15547-193">You can also choose to use regular expressions.</span></span> <span data-ttu-id="15547-194">さらに、検索クエリを保存し、そのグループを使用して、警告のクエリで、コンピューターのフィルターとしてコンピューター グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="15547-194">Moreover, you can create a computer group by saving a search query and using that group as your computer filter in your alert query.</span></span> <span data-ttu-id="15547-195">詳細については、[コンピューター グループのログの分析ログの検索](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15547-195">For more information, see [Computer groups in Log Analytics log searches](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-computer-groups).</span></span>
    
    <span data-ttu-id="15547-196">各コンピューターでは、クエリのエラーは RTCMEDSRV の両方のサービス開始の最後のイベント ログを取得して、サービスの停止。</span><span class="sxs-lookup"><span data-stu-id="15547-196">For each computer, the error query will get the last event log for both the RTCMEDSRV service start and service stop.</span></span> <span data-ttu-id="15547-197">いずれかが返されます場合は、最後のイベントは、サービスの停止イベントをログに記録nothing が返されます場合は、最後のイベントは、サービスの開始イベントです。</span><span class="sxs-lookup"><span data-stu-id="15547-197">It will return one log if the last event is the service stop event; it will return nothing if the last event is the service start event.</span></span> <span data-ttu-id="15547-198">つまり、クエリが RTCMEDSRV を停止する時間帯にサーバーのリストが返されます。</span><span class="sxs-lookup"><span data-stu-id="15547-198">In short, the query would return a list of servers whose RTCMEDSRV is stopped in the time window.</span></span> 
    
- <span data-ttu-id="15547-199">リセット警告のクエリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="15547-199">The query for the reset alert is:</span></span>
    
  ```
  Event | where Computer contains "MediationServer" | where EventLog == "Lync Server" and (EventID == 25002 or EventID == 25003)
 | summarize arg_max(TimeGenerated, EventID) by Computer  | where EventID == 2500
  ```

    <span data-ttu-id="15547-200">リセットのクエリは、まったく逆クエリ エラーのことです。</span><span class="sxs-lookup"><span data-stu-id="15547-200">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="15547-201">各コンピューターの場合を返しますいずれかの最後のイベントは、サービスを開始するイベントです。nothing が返されます場合、最後のイベントは、サービスの停止イベントです。</span><span class="sxs-lookup"><span data-stu-id="15547-201">For each computer, it will return one if the last event is the service start event; it will return nothing if the last event is the service stop event.</span></span>
    
 <span data-ttu-id="15547-202">**アラートのペアを作成:"が仲介サーバーでの同時通話の数」「同時通話に戻る通常の負荷」と**</span><span class="sxs-lookup"><span data-stu-id="15547-202">**Create an alert pair: " Too many concurrent calls in Mediation Servers" and "Concurrent calls fall back to normal load"**</span></span>
  
<span data-ttu-id="15547-203">この警告を作成します。</span><span class="sxs-lookup"><span data-stu-id="15547-203">To create this alert:</span></span>
  
- <span data-ttu-id="15547-204">エラー メッセージのクエリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="15547-204">The query for the error alert is:</span></span>
    
  ```
  Perf | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName 
== "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls >= 500
  ```

    <span data-ttu-id="15547-205">各コンピューターのクエリが表示されます着信呼び出しおよび発信呼び出しの合計の最後のカウンター、2 つの値。</span><span class="sxs-lookup"><span data-stu-id="15547-205">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="15547-206">いずれかが返されますを合計した値が 500 を超えている場合にログを記録nothing が返されますされていない場合。</span><span class="sxs-lookup"><span data-stu-id="15547-206">It will return one log if the sum value exceeds 500; it will return nothing if it doesn't.</span></span> <span data-ttu-id="15547-207">つまり、クエリ サーバーの同時呼び出しを時間帯に多くのリストが返されます。</span><span class="sxs-lookup"><span data-stu-id="15547-207">In short, the query would return a list of servers whose concurrent calls are too many in the time window.</span></span>
    
- <span data-ttu-id="15547-208">リセット警告のクエリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="15547-208">The query for the reset alert is:</span></span>
    
  ```
  Perf  | where Computer contains "MediationServer" | where (ObjectName == "LS:MediationServer - Outbound Calls" or ObjectName ==
 "LS:MediationServer - Inbound Calls") | summarize arg_max(TimeGenerated, CounterValue) by ObjectName, Computer | summarize
 TotalCalls = sum(CounterValue) by Computer| where TotalCalls < 500

  ```

    <span data-ttu-id="15547-209">リセットのクエリは、まったく逆クエリ エラーのことです。</span><span class="sxs-lookup"><span data-stu-id="15547-209">The reset query does exactly the opposite thing of the error query.</span></span> <span data-ttu-id="15547-210">各コンピューターのクエリが表示されます着信呼び出しおよび発信呼び出しの合計の最後のカウンター、2 つの値。</span><span class="sxs-lookup"><span data-stu-id="15547-210">For each computer, the query will get the last counters for inbound call and outbound call and sum those two values.</span></span> <span data-ttu-id="15547-211">500 未満の場合は、合計値は 1 つのログが返されますそれ以外は何も返されます。</span><span class="sxs-lookup"><span data-stu-id="15547-211">It will return one log if the sum value is less than 500; it will return nothing otherwise.</span></span>
    
 <span data-ttu-id="15547-212">**警告を作成する:"CPU 使用率\>90 または RTCMEDIARELAY は、サーバーで停止している"アラート**</span><span class="sxs-lookup"><span data-stu-id="15547-212">**Create an alert: "CPU usage \> 90 or RTCMEDIARELAY stopped in Servers" alert**</span></span>
  
<span data-ttu-id="15547-213">この警告を作成するには、クエリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="15547-213">To create this alert, the query is:</span></span>
  
```
search *| where Computer contains "MediationServer" | where (Type == "Perf" or Type == "Event") | where ((ObjectName ==
 "Processor" and CounterName == "% Processor Time") or EventLog == "Lync Server") | where (CounterValue > 90 or EventID == 22003)
```

<span data-ttu-id="15547-214">クエリは、すべてのコンピューターと戻り値のいずれかのプロセッサ使用率が 90%、またはサービスを超えた場合、1 つのログが停止したことから、すべてのプロセッサの使用状況カウンターとサービスの停止イベントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="15547-214">The query will get all processor usage counter and service stop event from all computers and return one log if either processor usage exceeds 90% or service is ever stopped.</span></span> 
  
## <a name="analyze-the-alerts-in-your-log-analytics-repository"></a><span data-ttu-id="15547-215">ログ分析リポジトリ内のアラートを分析します。</span><span class="sxs-lookup"><span data-stu-id="15547-215">Analyze the alerts in your Log Analytics repository</span></span>

<span data-ttu-id="15547-216">リポジトリ内の警告を分析するには、アラートの管理ソリューションを使用します。</span><span class="sxs-lookup"><span data-stu-id="15547-216">To analyze the alerts in your repository, use the Alert Management solution.</span></span> <span data-ttu-id="15547-217">詳細については、[警告の管理ソリューションで操作管理スイート (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15547-217">For more information, see [Alert Management solution in Operations Management Suite (OMS)](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-solution-alert-management)</span></span>
  
## <a name="recommended-minimal-monitoring-set"></a><span data-ttu-id="15547-218">推奨される最低限監視</span><span class="sxs-lookup"><span data-stu-id="15547-218">Recommended minimal monitoring set</span></span>

<span data-ttu-id="15547-219">イベント ログおよびパフォーマンス カウンターと問題を特定します。</span><span class="sxs-lookup"><span data-stu-id="15547-219">To identify issues with event logs and performance counters:</span></span> 
  
- <span data-ttu-id="15547-220">**イベント ログです。**</span><span class="sxs-lookup"><span data-stu-id="15547-220">**Event logs.**</span></span> <span data-ttu-id="15547-221">すべての問題のすべてが適切であることを示します、他の何かが間違っている場合は、通知するイベントの 1 つのセットを使用して、イベントのペアがあります。</span><span class="sxs-lookup"><span data-stu-id="15547-221">For any issue, there should be an events pair, with one set of events to indicate something is wrong, while the other indicates that everything is well.</span></span> <span data-ttu-id="15547-222">最後には、一定期間、その期間はまずい何かがあるかどうかを示すイベントが記録します。</span><span class="sxs-lookup"><span data-stu-id="15547-222">For any given time period, it is the last event recorded that will indicate whether something is amiss for that time period.</span></span>
    
- <span data-ttu-id="15547-223">**パフォーマンス カウンターです。**</span><span class="sxs-lookup"><span data-stu-id="15547-223">**Performance Counters.**</span></span> <span data-ttu-id="15547-224">監視対象のカウンターのしきい値が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="15547-224">There should be a threshold for the monitored counters.</span></span>
    
<span data-ttu-id="15547-225">次の表に、マイクロソフトは、停止と開始のイベント Id をリストすることによって監視することをお勧めするサービスを示します。</span><span class="sxs-lookup"><span data-stu-id="15547-225">The following table lists the services that Microsoft recommends monitoring by listing the stop and start event IDs:</span></span>
  
|<span data-ttu-id="15547-226">サービス名</span><span class="sxs-lookup"><span data-stu-id="15547-226">Service Name</span></span>  <br/> |<span data-ttu-id="15547-227">ターゲット サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="15547-227">Target Server Role</span></span>  <br/> |<span data-ttu-id="15547-228">イベント ID を停止します。</span><span class="sxs-lookup"><span data-stu-id="15547-228">Stop Event ID</span></span>  <br/> |<span data-ttu-id="15547-229">イベント ID を開始します。</span><span class="sxs-lookup"><span data-stu-id="15547-229">Start Event ID</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="15547-230">RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="15547-230">RTCMEDSRV</span></span>  <br/> |<span data-ttu-id="15547-231">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="15547-231">Mediation Server</span></span>  <br/> |<span data-ttu-id="15547-232">25003</span><span class="sxs-lookup"><span data-stu-id="15547-232">25003</span></span>  <br/> |<span data-ttu-id="15547-233">25002</span><span class="sxs-lookup"><span data-stu-id="15547-233">25002</span></span>  <br/> |
|<span data-ttu-id="15547-234">RTCSRV</span><span class="sxs-lookup"><span data-stu-id="15547-234">RTCSRV</span></span>  <br/> |<span data-ttu-id="15547-235">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="15547-235">Edge Server</span></span>  <br/> |<span data-ttu-id="15547-236">12289</span><span class="sxs-lookup"><span data-stu-id="15547-236">12289</span></span>  <br/> |<span data-ttu-id="15547-237">12288</span><span class="sxs-lookup"><span data-stu-id="15547-237">12288</span></span>  <br/> |
|<span data-ttu-id="15547-238">RTCMRAUTH</span><span class="sxs-lookup"><span data-stu-id="15547-238">RTCMRAUTH</span></span>  <br/> |<span data-ttu-id="15547-239">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="15547-239">Edge Server</span></span>  <br/> |<span data-ttu-id="15547-240">19003</span><span class="sxs-lookup"><span data-stu-id="15547-240">19003</span></span>  <br/> |<span data-ttu-id="15547-241">19002</span><span class="sxs-lookup"><span data-stu-id="15547-241">19002</span></span>  <br/> |
|<span data-ttu-id="15547-242">RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="15547-242">RTCMEDIARELAY</span></span>  <br/> |<span data-ttu-id="15547-243">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="15547-243">Edge Server</span></span>  <br/> |<span data-ttu-id="15547-244">22003</span><span class="sxs-lookup"><span data-stu-id="15547-244">22003</span></span>  <br/> |<span data-ttu-id="15547-245">22002</span><span class="sxs-lookup"><span data-stu-id="15547-245">22002</span></span>  <br/> |
   
<span data-ttu-id="15547-246">監視をお勧めするネットワークの問題を次の表に一覧します。</span><span class="sxs-lookup"><span data-stu-id="15547-246">The following table lists the network issues that Microsoft recommends monitoring:</span></span>
  
|<span data-ttu-id="15547-247">モニター名</span><span class="sxs-lookup"><span data-stu-id="15547-247">Monitor Name</span></span>  <br/> |<span data-ttu-id="15547-248">ターゲット サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="15547-248">Target Server Role</span></span>  <br/> |<span data-ttu-id="15547-249">成功のイベント ID の式</span><span class="sxs-lookup"><span data-stu-id="15547-249">Success Event ID expression</span></span>  <br/> |<span data-ttu-id="15547-250">エラー イベント ID 式</span><span class="sxs-lookup"><span data-stu-id="15547-250">Error Event ID expression</span></span>  <br/> |<span data-ttu-id="15547-251">障害の例</span><span class="sxs-lookup"><span data-stu-id="15547-251">Failure example</span></span>  <br/> |
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="15547-252">ゲートウェイの接続障害が発生する仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="15547-252">Mediation Server to gateway connectivity failure</span></span>  <br/> |<span data-ttu-id="15547-253">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="15547-253">Mediation Server</span></span>  <br/> |<span data-ttu-id="15547-254">25062</span><span class="sxs-lookup"><span data-stu-id="15547-254">25062</span></span> || <span data-ttu-id="15547-255">25002</span><span class="sxs-lookup"><span data-stu-id="15547-255">25002</span></span>  <br/> |<span data-ttu-id="15547-256">25061</span><span class="sxs-lookup"><span data-stu-id="15547-256">25061</span></span>  <br/> |<span data-ttu-id="15547-257">MS PING (オプション) をゲートウェイが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="15547-257">MS PING (option) Gateway failed</span></span>  <br/> |
|<span data-ttu-id="15547-258">ゲートウェイに仲介サーバーの呼び出し完了障害</span><span class="sxs-lookup"><span data-stu-id="15547-258">Mediation Server to gateway call completion failure</span></span>  <br/> |<span data-ttu-id="15547-259">仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="15547-259">Mediation Server</span></span>  <br/> |<span data-ttu-id="15547-260">25064</span><span class="sxs-lookup"><span data-stu-id="15547-260">25064</span></span> || <span data-ttu-id="15547-261">25002</span><span class="sxs-lookup"><span data-stu-id="15547-261">25002</span></span>  <br/> |<span data-ttu-id="15547-262">25063</span><span class="sxs-lookup"><span data-stu-id="15547-262">25063</span></span>  <br/> |<span data-ttu-id="15547-263">MS のゲートウェイへの呼び出しを作成しようとして失敗しました。</span><span class="sxs-lookup"><span data-stu-id="15547-263">MS trying to make call to Gateway failed</span></span>  <br/> |
|<span data-ttu-id="15547-264">重要なネットワークの問題</span><span class="sxs-lookup"><span data-stu-id="15547-264">Critical network problems</span></span>  <br/> |<span data-ttu-id="15547-265">エッジ サーバー</span><span class="sxs-lookup"><span data-stu-id="15547-265">Edge Server</span></span>  <br/> |<span data-ttu-id="15547-266">14353</span><span class="sxs-lookup"><span data-stu-id="15547-266">14353</span></span> || <span data-ttu-id="15547-267">12288</span><span class="sxs-lookup"><span data-stu-id="15547-267">12288</span></span>  <br/> |<span data-ttu-id="15547-268">14624</span><span class="sxs-lookup"><span data-stu-id="15547-268">14624</span></span>  <br/> |<span data-ttu-id="15547-269">TLS をトランスポートは、ローカル IP アドレス ポート 5061 で 192.168.231.14 の開始に失敗しました</span><span class="sxs-lookup"><span data-stu-id="15547-269">Transport TLS has failed to start on local IP address 192.168.231.14 at port 5061</span></span>  <br/> |
   
<span data-ttu-id="15547-270">呼び出し容量のカウンターを監視する必要がありますを次に示します。</span><span class="sxs-lookup"><span data-stu-id="15547-270">The following lists the call capacity counters that should be monitored.</span></span> <span data-ttu-id="15547-271">これらの数値は、以下をする必要があります 500 のクラウドのコネクタの標準的なエディションです。クラウド コネクタの最小のエディションの 50 よりも小さい。</span><span class="sxs-lookup"><span data-stu-id="15547-271">These numbers should be less that 500 for Cloud Connector standard edition; less than 50 for Cloud Connector minimum edition.</span></span>
  
- <span data-ttu-id="15547-272">LS:MediationServer - 受信 Calls(_Total)\-現在</span><span class="sxs-lookup"><span data-stu-id="15547-272">LS:MediationServer - Inbound Calls(_Total)\- Current</span></span> 
    
- <span data-ttu-id="15547-273">LS:MediationServer - 送信 Calls(_Total)\-現在</span><span class="sxs-lookup"><span data-stu-id="15547-273">LS:MediationServer - Outbound Calls(_Total)\- Current</span></span> 
    
- <span data-ttu-id="15547-274">LS:MediationServer - 受信 Calls(_Total)\-アクティブなメディアの呼び出しをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="15547-274">LS:MediationServer - Inbound Calls(_Total)\- Active media bypass calls</span></span>
    
- <span data-ttu-id="15547-275">LS:MediationServer - 送信 Calls(_Total)\-アクティブなメディアの呼び出しをバイパスします。</span><span class="sxs-lookup"><span data-stu-id="15547-275">LS:MediationServer - Outbound Calls(_Total)\- Active media bypass calls</span></span>
    
## <a name="see-also"></a><span data-ttu-id="15547-276">関連項目</span><span class="sxs-lookup"><span data-stu-id="15547-276">See also</span></span>

<span data-ttu-id="15547-277">OMS を使用して操作の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15547-277">For more information about working with OMS, see the following:</span></span>
  
- [<span data-ttu-id="15547-278">ログ分析でログの検索を使用してデータを検索します。</span><span class="sxs-lookup"><span data-stu-id="15547-278">Find data using log searches in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-log-searches)
    
- [<span data-ttu-id="15547-279">Azure のログ分析の言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="15547-279">Azure Log Analytics Language Reference</span></span>](https://docs.loganalytics.io/docs/Language-Reference)
    
- [<span data-ttu-id="15547-280">ログ分析機能で通知を理解します。</span><span class="sxs-lookup"><span data-stu-id="15547-280">Understanding alerts in Log Analytics</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-alerts)
    
- [<span data-ttu-id="15547-281">Azure のログ分析サービスを Windows コンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="15547-281">Connect Windows computers to the Log Analytics service in Azure</span></span>](https://docs.microsoft.com/en-us/azure/log-analytics/log-analytics-windows-agents)
    

