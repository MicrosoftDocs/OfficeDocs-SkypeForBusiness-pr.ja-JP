---
title: Azure Sentinel および Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: IT 管理者が Sentinel を使用して、Teams で発生する可能性のある脅威を監視し、捜索するためのセキュリティに関するアドバイスと学習です。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1075a2c345bd866266b175a4b62432e9f819b330
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598526"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="171d2-103">Azure Sentinel および Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="171d2-103">Azure Sentinel and Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="171d2-104">Azure Sentinel に統合コネクタが追加されました。</span><span class="sxs-lookup"><span data-stu-id="171d2-104">Azure Sentinel now has an integrated connector.</span></span> <span data-ttu-id="171d2-105">詳細については、「[Connect Office 365 Logs to Azure Sentinel (Office 365 のログを Azure Sentinel に接続する)](/azure/sentinel/connect-office-365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="171d2-105">For more information, see [Connect Office 365 Logs to Azure Sentinel](/azure/sentinel/connect-office-365).</span></span> <span data-ttu-id="171d2-106">これは、これらのログを収集するための推奨ルートであり、以下で説明する収集方法よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-106">This is the recommended route for collecting these logs and supersedes the collection methods described below.</span></span>

<span data-ttu-id="171d2-107">Teams は、Microsoft 365 クラウドでの通信とデータ共有の両方の中心的な役割を担います。</span><span class="sxs-lookup"><span data-stu-id="171d2-107">Teams serves a central role in both communication and data sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="171d2-108">Teams サービスはクラウド内の多くの基になっているテクノロジを使用しているので、*ログの捜索* を行う場合だけではなく *会議をリアルタイムで監視* する場合も手動分析および自動分析を利用することができます。</span><span class="sxs-lookup"><span data-stu-id="171d2-108">Because the Teams service touches on so many underlying technologies in the Cloud, it can benefit from human and automated analysis not only when it comes to *hunting in logs*, but also in *real-time monitoring of meetings*.</span></span> <span data-ttu-id="171d2-109">Azure Sentinel は、管理者に次のようなソリューションを提案します。</span><span class="sxs-lookup"><span data-stu-id="171d2-109">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="171d2-110">Azure Sentinel の概要</span><span class="sxs-lookup"><span data-stu-id="171d2-110">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="171d2-111">[この記事](/azure/sentinel/overview) は、まさにその通りです。</span><span class="sxs-lookup"><span data-stu-id="171d2-111">[This article](/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="171d2-112">Sentinel および Microsoft Teams のアクティビティ ログ</span><span class="sxs-lookup"><span data-stu-id="171d2-112">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="171d2-113">この記事では、Azure Sentinel でチーム アクティビティ ログを収集する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="171d2-113">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span> <span data-ttu-id="171d2-114">管理者は、Sentinel のワークブックおよびランブックがセキュリティ監視を体系的に行うことで、セキュリティ管理を一枚のガラスの下に置くことができます （選択したサード パーティ製のデバイス、Microsoft Threat Protection、およびその他の Microsoft 365ワークロードを含む）。</span><span class="sxs-lookup"><span data-stu-id="171d2-114">Aside from allowing administrators to put security management under one pane of glass (including any selected 3rd party devices, Microsoft Threat Protection, and other Microsoft 365 Workloads), Sentinel workbooks, and runbooks can make security monitoring systematic.</span></span> <span data-ttu-id="171d2-115">このプロセスの最初の手順として、分析に必要なログを収集します。</span><span class="sxs-lookup"><span data-stu-id="171d2-115">A good first step in this process is collecting the needed logs for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="171d2-116">複数の Microsoft 365 サブスクリプションは、Azure Sentinel の同じインスタンスに表示できます。</span><span class="sxs-lookup"><span data-stu-id="171d2-116">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="171d2-117">これにより、[リアルタイム監視](/azure/sentinel/livestream) および履歴ログ ファイルでの脅威の検索ができるようになります。</span><span class="sxs-lookup"><span data-stu-id="171d2-117">This will allow for [realtime monitoring](/azure/sentinel/livestream) and hunting for threats in historical log file s.</span></span> <span data-ttu-id="171d2-118">管理者は、1つのリソース グループ内もしくはリソース グループ間、または別のサブスクリプションで、[クロス リソース クエリ](/azure/azure-monitor/log-query/cross-workspace-query) を使用して検索できます。</span><span class="sxs-lookup"><span data-stu-id="171d2-118">Administrators will be able to hunt using [cross-resource queries](/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs"></a><span data-ttu-id="171d2-119">ステップ 1: チームログを収集する</span><span class="sxs-lookup"><span data-stu-id="171d2-119">Step 1: Collect Teams logs</span></span>

<span data-ttu-id="171d2-120">このセクションには、3つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="171d2-120">This section has three parts:</span></span>

1. <span data-ttu-id="171d2-121">**Microsoft 365** で監査ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="171d2-121">Enabling Audit Logs in **Microsoft 365**.</span></span>
2. <span data-ttu-id="171d2-122">**Microsoft Azure** にアプリを登録して、ログ収集のための認証および承認を許可します。</span><span class="sxs-lookup"><span data-stu-id="171d2-122">Registering an App in **Microsoft Azure** to permit authentication and authorization for log collection.</span></span>
3. <span data-ttu-id="171d2-123">**PowerShell** 経由で、Microsoft 365 API を使用したログ収集を許可する API サブスクリプションを登録します。</span><span class="sxs-lookup"><span data-stu-id="171d2-123">Registering the API subscription that will allow log collection via Microsoft 365 API via **PowerShell**.</span></span>

### <a name="enable-audit-logs-in-microsoft-365"></a><span data-ttu-id="171d2-124">Microsoft 365 で監査ログを有効にする</span><span class="sxs-lookup"><span data-stu-id="171d2-124">Enable Audit logs in Microsoft 365</span></span>

<span data-ttu-id="171d2-125">Teams は Microsoft 365 経由でアクティビティを記録するため、監査ログは既定では収集されません。</span><span class="sxs-lookup"><span data-stu-id="171d2-125">Because Teams logs activity through Microsoft 365, audit logs aren't collected by default.</span></span> <span data-ttu-id="171d2-126">この機能を有効にするには、[次の手順](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0) を実行します。</span><span class="sxs-lookup"><span data-stu-id="171d2-126">Turn on this feature via [these steps](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0).</span></span> <span data-ttu-id="171d2-127">Teams のデータは、*Audit.General* 下にある Microsoft 365 監査で収集されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-127">Teams data is collected in the Microsoft 365 audit under *Audit.General*.</span></span>

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a><span data-ttu-id="171d2-128">ログ収集用 Microsoft Azure にアプリを登録する</span><span class="sxs-lookup"><span data-stu-id="171d2-128">Register an App in Microsoft Azure for log collection</span></span>

> [!TIP]
> <span data-ttu-id="171d2-129">作業を開始する前に、後で使用するための **アプリケーション IDまたはクライアント ID** および **テナント ID** を記録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="171d2-129">Before you begin, you will need to record you **Application ID / Client ID**, and your **Tenant ID** for later use.</span></span> <span data-ttu-id="171d2-130">これらの情報は、次のアプリの登録手順を順番に行うため、必ずキャプチャしてください。</span><span class="sxs-lookup"><span data-stu-id="171d2-130">Be sure to capture them as you walk through app registration steps below.</span></span> <span data-ttu-id="171d2-131">両方の ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-131">You will see both IDs.</span></span>
>- <span data-ttu-id="171d2-132">アプリが作成されたら、クイック起動のサイド バーにある [アプリの登録] をクリックし、新しいアプリの表示名を検出して、[アプリケーション (クライアント) ID をコピーします。</span><span class="sxs-lookup"><span data-stu-id="171d2-132">After your app is created, click App Registration on the quick launch side-bar > Find your new app's display name > copy the Application (client) ID.</span></span>
>- <span data-ttu-id="171d2-133">クイック起動のサイド バーにある [概要] をクリックして、ディレクトリ (テナント) ID をコピーします。</span><span class="sxs-lookup"><span data-stu-id="171d2-133">Click Overview on the quick launch side-bar > copy the Directory (tenant) ID.</span></span>

<span data-ttu-id="171d2-134">Azure Active Directory (Azure AD) アプリを認証し、API からログ データを収集することを承認します。</span><span class="sxs-lookup"><span data-stu-id="171d2-134">Authenticate and authorize an Azure Active Directory (Azure AD) app to collect log data from the API.</span></span>

1. <span data-ttu-id="171d2-135">Azure ポータルで *Azure AD* ブレードに移動します。</span><span class="sxs-lookup"><span data-stu-id="171d2-135">Navigate to your *Azure AD* blade in the Azure portal.</span></span>
2. <span data-ttu-id="171d2-136">クイック起動サイド バーにある *[アプリを登録]* をクリックします。</span><span class="sxs-lookup"><span data-stu-id="171d2-136">Click on *App registrations* in the quick launch side-bar.</span></span>
3. <span data-ttu-id="171d2-137">*[新規登録]* を選択します。</span><span class="sxs-lookup"><span data-stu-id="171d2-137">Select *New registration*.</span></span>
4. <span data-ttu-id="171d2-138">Teams ログ収集アプリの名前を入力し、*[登録]* をクリックします。</span><span class="sxs-lookup"><span data-stu-id="171d2-138">Name your Teams log collecting app and click *Register*.</span></span>
5. <span data-ttu-id="171d2-139">このパスに沿ってクリックします : *API のアクセス許可* > *アクセス許可を追加* > *Office 365 Management APIs* > *Application のアクセス許可*。</span><span class="sxs-lookup"><span data-stu-id="171d2-139">Click along this path: *API Permissions* > *Add a permission* > *Office 365 Management APIs* > *Application permissions*.</span></span>
6. <span data-ttu-id="171d2-140">[アクティビティ フィード] を展開し、 *[ActivityFeed.Read]* を確認します。</span><span class="sxs-lookup"><span data-stu-id="171d2-140">Expand Activity Feed and check *ActivityFeed.Read*.</span></span>
7. <span data-ttu-id="171d2-141">ここでは、*[全体管理者の同意]* を選びます。</span><span class="sxs-lookup"><span data-stu-id="171d2-141">Choose *Grand admin consent* here.</span></span> <span data-ttu-id="171d2-142">確認メッセージが表示されたら、[はい] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="171d2-142">Click Yes when prompted asking if you mean it.</span></span>
8. <span data-ttu-id="171d2-143">サイド バーの *[証明書と秘密]* > *[新規クライアント シークレット]* ボタンの順でクリックします。</span><span class="sxs-lookup"><span data-stu-id="171d2-143">Click *Certificates and Secrets* in the side-bar> *New client secret* button.</span></span>
9. <span data-ttu-id="171d2-144">[新規クライアント シークレット] ウィンドウで新規クライアント シークレットの説明を入力し、[有効期限] に [いいえ] を選択し、*[追加]* をクリックします。</span><span class="sxs-lookup"><span data-stu-id="171d2-144">On the New client secret window, enter a description for the new Client Secret, make sure you choose 'Never' for Expiration, and click *Add*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="171d2-145">新規クライアント シークレットを、新しく作成されたアプリの名前の下にあるパスワード マネージャーのエントリにコピーすることは、**[重要]** です。</span><span class="sxs-lookup"><span data-stu-id="171d2-145">It's **critical** to copy the new client secret into a password manager entry that goes under the name of the newly created app.</span></span> <span data-ttu-id="171d2-146">Azure ブレード (*ブレード* はウィンドウの Azure 用語) を終了した後に、このシークレットを見に戻ることはできません。</span><span class="sxs-lookup"><span data-stu-id="171d2-146">You won't be able to get back to look at this secret after the closing out of the Azure blade (*blade* being the Azure term for window).</span></span>

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a><span data-ttu-id="171d2-147">PowerShell で API を登録してチーム ログを収集する</span><span class="sxs-lookup"><span data-stu-id="171d2-147">Register the API with PowerShell to collect Teams logs</span></span>

<span data-ttu-id="171d2-148">セットアップの最後の手順では、ログ データを収集するために、API サブスクリプションを収集して登録します。</span><span class="sxs-lookup"><span data-stu-id="171d2-148">The final step in setup is to collect and register the API subscription so that you can collect your log data.</span></span> <span data-ttu-id="171d2-149">これは、Microsoft 365 管理アクティビティ API へのPowerShell REST 呼び出しによって行われます。</span><span class="sxs-lookup"><span data-stu-id="171d2-149">This is done via PowerShell REST calls to the Microsoft 365 Management Activity API.</span></span>

<span data-ttu-id="171d2-150">**アプリケーション (クライアント) ID**、新しい **クライアント シークレット**、**M365用の URL ドメイン**、および以下の PowerShell コマンドレットの **ディレクトリ (テナント) ID** 値を提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="171d2-150">Be ready to supply **Application (client) ID**, the new **Client Secret**, your **URL domain for M365**, and **Directory (tenant) ID** values in the PowerShell cmdlet below.</span></span>

```PowerShell
$ClientID = "<Application (client) ID>"  
$ClientSecret = "<Client secret>"  
$loginURL = "https://login.microsoftonline.com/"  
$tenantdomain = "<domain>.onmicrosoft.com"  

$TenantGUID = "<Directory (tenant) ID>"  
$resource = "https://manage.office.com"  
$body = @{grant_type="client_credentials";resource=$resource;client_id=$ClientID;client_secret=$ClientSecret}
$oauth = Invoke-RestMethod -Method Post -Uri $loginURL/$tenantdomain/oauth2/token?api-version=1.0 -Body $body  
$headerParams = @{'Authorization'="$($oauth.token_type) $($oauth.access_token)"}
$publisher = New-Guid
Invoke-WebRequest -Method Post -Headers $headerParams -Uri "https://manage.office.com/api/v1.0/$tenantGuid/activity/feed/subscriptions/start?contentType=Audit.General&PublisherIdentifier=$Publisher"
```

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a><span data-ttu-id="171d2-151">手順 2: チーム ログを取り込むための Sentinel プレイブックを展開する</span><span class="sxs-lookup"><span data-stu-id="171d2-151">Step 2: Deploy a Sentinel Playbook to ingest the Teams logs</span></span>

<span data-ttu-id="171d2-152">Azure Sentinel プレイブック (ロジック アプリとも呼ばれます) を使用すると、収集した Teams データを Azure が取り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="171d2-152">Azure Sentinel Playbooks (also called Logic Apps) will allow Azure to ingest your collected Teams data.</span></span> <span data-ttu-id="171d2-153">ロジック アプリは、Office 365 に対して、Azure Sentinel ワークスペースに書き込まれる監査データを検索します。</span><span class="sxs-lookup"><span data-stu-id="171d2-153">The Logic App queries Office 365 to find the audit data it writes into the Azure Sentinel workspace.</span></span>

<span data-ttu-id="171d2-154">[この](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM テンプレートを使用して、Sentinel プレイブックを展開します。</span><span class="sxs-lookup"><span data-stu-id="171d2-154">Use [this](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM template to deploy your Sentinel Playbook.</span></span>

<span data-ttu-id="171d2-155">留意すべき点がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="171d2-155">Things to remember:</span></span>

1. <span data-ttu-id="171d2-156">ARM テンプレートを通して、特定の値を使用している環境に適した値に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="171d2-156">You will need to walk through the ARM template and replace certain of the values with values appropriate for your own environment.</span></span>
2. <span data-ttu-id="171d2-157">ログを取り込んでから Azure Sentinel で結果を見るまでの時間を確保する必要があります。</span><span class="sxs-lookup"><span data-stu-id="171d2-157">You will need to allow time between the ingestion of logs and looking at the results in Azure Sentinel.</span></span>

   <span data-ttu-id="171d2-158">過去5分間のデータがない場合は、5 ～ 10 分待ってから、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-158">Wait for 5 to 10 minutes, understanding that if there is no data within the past 5 minutes you will see an error message.</span></span> <span data-ttu-id="171d2-159">監査ログを確認し、Teams の情報は監査に含まれていることに注意してください。Teams のログよりも多くの情報を収集する一般的なイベントでは、使用中のシステムで 5 ～ 10 分以内に結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-159">Check Audit logs and keep in mind that because Teams information is in the Audit.General events, which collects more than Teams logs, results should appear within 5 to 10 minutes on systems that are in use.</span></span> <span data-ttu-id="171d2-160">テキスト環境を使用している場合は、ログを生成するために Teams を使用してください。</span><span class="sxs-lookup"><span data-stu-id="171d2-160">If using a text environment, be certain to use Teams in order to generate logging.</span></span>

![ロジック アプリ クラスを示すグラフィック。](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> <span data-ttu-id="171d2-162">グラフィックのアクションの説明:</span><span class="sxs-lookup"><span data-stu-id="171d2-162">Explanation of actions in the graphic:</span></span> 
  </summary>

  <span data-ttu-id="171d2-163">•定期的なパターンは、ワークフローが1時間ごとに実行されるようにするロジック アプリ トリガーです。</span><span class="sxs-lookup"><span data-stu-id="171d2-163">• Recurrence is the Logic App Trigger that tells the workflow to run every hour.</span></span>
  <p>
<span data-ttu-id="171d2-164">•現在の時刻のアクションは、非常に基本的で、現在の時刻だけを取得します。</span><span class="sxs-lookup"><span data-stu-id="171d2-164">• The Current Time action is very basic and just gets the current time.</span></span>
  <p>
<span data-ttu-id="171d2-165">変数を初期化すると、NextPage という名前の変数が作成され、1に設定されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-165">• Initialize Variable creates a variable called NextPage and sets it to 1.</span></span> <span data-ttu-id="171d2-166">これは、O365 API のページネーションを処理するために、後で使用されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-166">This will be used later in order to handle pagination from the O365 API.</span></span>
  <p>
<span data-ttu-id="171d2-167">•変数の初期化2は、開始時刻という空の変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="171d2-167">• Initialize Variable 2 creates an empty variable called Start Time.</span></span>
  <p>
<span data-ttu-id="171d2-168">•クエリおよびリスト結果の実行は、ロジック アプリから最後に入力された O365 ログをワークスペースに問い合わせる Azure モニター アクションです。</span><span class="sxs-lookup"><span data-stu-id="171d2-168">• Run Query and list results is an Azure Monitor action that will query the workspace for the last O365 log that was entered from the Logic App.</span></span>
  <p>
<span data-ttu-id="171d2-169">•条件4は、クエリの実行とリスト結果クエリが何かデータを返したかどうかを確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-169">• Condition 4 is used to check whether the Run Query and list results query returned any data.</span></span> <span data-ttu-id="171d2-170">これは、ロジック アプリが初めて使われるかどうかを確認するために行われます。</span><span class="sxs-lookup"><span data-stu-id="171d2-170">This is done to check if this is the very first time the Logic App has been used.</span></span> <span data-ttu-id="171d2-171">データが返されない場合、StartTime 変数は Now ～ 24 時間に設定されています。</span><span class="sxs-lookup"><span data-stu-id="171d2-171">If no data is returned, StartTime variable is set to Now – 24 hours.</span></span> <span data-ttu-id="171d2-172">データが返される場合、StartTime は最終発生時間に設定されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-172">If data is returned, StartTime is set to the last record TimeGenerated.</span></span> <span data-ttu-id="171d2-173">これは、O365 API に対して、クエリが最後のエントリから今までの時点、またはそれが初めて実行された場合は、直近の24時間の時点までのデータを取得できるように行われます。</span><span class="sxs-lookup"><span data-stu-id="171d2-173">This is done so that the query can get data from the last entry till now in the poll against the O365 API, or in the last 24 hours if this is the first run.</span></span>
  <p>
<span data-ttu-id="171d2-174">•変数の初期化3は、「AvaibleUri」 という名前の変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="171d2-174">• Initialize Variable 3 creates a variable called AvailableUri.</span></span> <span data-ttu-id="171d2-175">これは、StartTime と CurrentTime を使用し、それぞれ開始時刻と終了時刻として作成された URL の文字列です。</span><span class="sxs-lookup"><span data-stu-id="171d2-175">This is a string with the URL built using the StartTime and CurrentTime as start and end times, respectively.</span></span>
  <p>
<span data-ttu-id="171d2-176">•Until 条件は、ロジック アプリが API にポーリングを継続して、データ (ページネーション) があるかどうかを確認するためのループです。</span><span class="sxs-lookup"><span data-stu-id="171d2-176">• The Until condition is a loop that allows the logic app to keep polling the API to see if there is more data (pagination).</span></span> <span data-ttu-id="171d2-177">NextPage 変数が1の場合、ループは続行します。</span><span class="sxs-lookup"><span data-stu-id="171d2-177">As long as NextPage variable is 1 the loop will continue.</span></span> <span data-ttu-id="171d2-178">この変数は、その後、取得するページが残っていない場合に更新されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-178">Later this variable will be updated if there are no more pages left to retrieve.</span></span>
  <p>
<span data-ttu-id="171d2-179">Until ループの内部では、最初の HTTP ステップが AvaibleUri に接続します。</span><span class="sxs-lookup"><span data-stu-id="171d2-179">• Inside the Until loop, the first HTTP step Connects to the AvailableURI.</span></span> <span data-ttu-id="171d2-180">この URI は、使用できるコンテンツと各コンテンツ URI のリストを返します。</span><span class="sxs-lookup"><span data-stu-id="171d2-180">This URI returns a list of available content and each contents URI.</span></span> <span data-ttu-id="171d2-181">この URL での操作方法については、https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content を参照してください。</span><span class="sxs-lookup"><span data-stu-id="171d2-181">There's more on how this works at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="171d2-182">•次に、データが返されることを確認するためのチェックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-182">• Next a check is run to make sure data is returned.</span></span> <span data-ttu-id="171d2-183">本文の長さが0かどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="171d2-183">The Condition checks if the length of the body is 0.</span></span> <span data-ttu-id="171d2-184">この場合、ログ分析に書き込むデータがありません。</span><span class="sxs-lookup"><span data-stu-id="171d2-184">If so there is no data to write to Log Analytics.</span></span> <span data-ttu-id="171d2-185">値が0より大きい場合、処理するデータがあります。</span><span class="sxs-lookup"><span data-stu-id="171d2-185">If the value is greater than 0, there is data to process.</span></span>
  <p>
<span data-ttu-id="171d2-186">•データが検出された場合は、次に処理される必要があります。</span><span class="sxs-lookup"><span data-stu-id="171d2-186">• If data is detected, it must next be processed.</span></span> <span data-ttu-id="171d2-187">JSON 解析は、返されるデータのスキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="171d2-187">Parse JSON defines a schema of the returned data.</span></span> <span data-ttu-id="171d2-188">これにより、ロジック アプリは、後の手順で、解析されたデータをダイナミック コンテンツとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="171d2-188">This allows logic apps to use the parsed data as Dynamic content in later steps.</span></span>
  <p>
<span data-ttu-id="171d2-189">•返される使用可能なデータのリストは配列であるため、For Each アクションを使用して、使用可能なコンテンツのリストをループするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-189">• Since the returned list of available data is an Array, a For Each action is used to loop through the list of available content.</span></span>
  <p>
<span data-ttu-id="171d2-190">•次は、コンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="171d2-190">• Next is grabbing the content.</span></span>  <span data-ttu-id="171d2-191">HTTP を再び使用して、contentUri (JSON 解析で作成された動的プロパティ) を取得します。これは、取得するデータの URL です。</span><span class="sxs-lookup"><span data-stu-id="171d2-191">HTTP is used again to get the contentUri (a dynamic property created from Parse JSON), which is the URL of the data to retrieve.</span></span>
  <p>
<span data-ttu-id="171d2-192">• JSON 解析は、返されるデータの解析にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-192">• Parse JSON is also used to parse the returned data.</span></span> <span data-ttu-id="171d2-193">この URL には、https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content のような、いくつかのサンプルコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="171d2-193">You can find some sample content at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="171d2-194">•返されるデータは、配列です。</span><span class="sxs-lookup"><span data-stu-id="171d2-194">• The data returned is also an array.</span></span> <span data-ttu-id="171d2-195">ここでは、for each ループも使用できます。</span><span class="sxs-lookup"><span data-stu-id="171d2-195">A For Each loop can be used here as well.</span></span> <span data-ttu-id="171d2-196">このループでは、ワークフローは現在のデータ アイテムを取得し、[データの送信] アクションを使用して、ログ分析にデータを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="171d2-196">In this loop, the workflow takes the current item of data and uses the Send Data action to write the data to Log Analytics.</span></span>
  <p>
<span data-ttu-id="171d2-197">•使用可能なコンテンツは複数ページにわたる可能性があるので、NextPageUri が NULL ではないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="171d2-197">• Since there may be multiple pages of available content, a condition checks if the NextPageUri is not NULL.</span></span> <span data-ttu-id="171d2-198">NULL か空白の場合、NextPage は0に設定され、Until ループを終了します。</span><span class="sxs-lookup"><span data-stu-id="171d2-198">If it is NULL, or empty, NextPage is set to 0, which ends the Until loop.</span></span> <span data-ttu-id="171d2-199">URL が含まれている場合は、その URL に AvaibleUri 変数が更新されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-199">If it contains a URL, the AvaibleUri variable is updated to that URL.</span></span> <span data-ttu-id="171d2-200">この方法では、Until ループの次の実行時には、開始 URL ではなく、次に利用可能な URL が使用されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-200">This way, the next run of the Until loop uses a next available URL, and not the starting URL.</span></span>

  </details>

> [!TIP]
> <span data-ttu-id="171d2-201">代わりに、*Azure 関数* を使用して、これらのログを取り込むことができます。その場合は、必要に応じて、展開方法についての詳細な説明は、[こちら](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data) または [こちら](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp) にあります。</span><span class="sxs-lookup"><span data-stu-id="171d2-201">You may choose to use an *Azure Function* to ingest those logs, instead, and if you do, the information on how to deploy is [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data), or [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), depending on your preference.</span></span>

<span data-ttu-id="171d2-202">コネクタ (上記のいずれかのオプション) を実行すると、Azure Sentinel ワークスペースに O365API_CL と呼ばれるカスタム テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-202">With the connector (whichever of the options above you chose) running, you should see a custom table called O365API_CL in the Azure Sentinel workspace.</span></span> <span data-ttu-id="171d2-203">Teams ログが作成されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-203">This will house your Teams logs.</span></span>

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a><span data-ttu-id="171d2-204">手順 3: Sentinel を使用して Microsoft Teams を監視する</span><span class="sxs-lookup"><span data-stu-id="171d2-204">Step 3: Use Sentinel to monitor Microsoft Teams</span></span>

<span data-ttu-id="171d2-205">ID は、Microsoft Teams に関して言えば、監視すべき重要な攻撃ベクトルです。</span><span class="sxs-lookup"><span data-stu-id="171d2-205">Identity is an important attack vector to monitor when it comes to Microsoft Teams.</span></span> <span data-ttu-id="171d2-206">Azure Active Directory (Azure AD) は、Teams を含む、Microsoft 365 ディレクトリの土台であり、Azure AD 認証ログの脅威の収集および検索を行うことにより、ID の不審な動作をキャプチャするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="171d2-206">Because Azure Active Directory (Azure AD) is the underpinning of Microsoft 365's directory, including Teams, collecting and hunting for threats in Azure AD logs around authentication will be useful in capturing suspicious behavior around identity.</span></span> <span data-ttu-id="171d2-207">内蔵コネクタを使用して Azure AD データを Azure Sentinel に引き込み、これらの [検出](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) および [検索](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) クエリを使用して、問題を探すことができます。</span><span class="sxs-lookup"><span data-stu-id="171d2-207">You can use the built-in connector to pull Azure AD data into Azure Sentinel, and use these [detection](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) and [hunting](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) queries to look for problems.</span></span>

<span data-ttu-id="171d2-208">Microsoft Teams に固有の攻撃、データへの脅威については、たとえば、Azure Sentinel にも、それらを監視して追い詰める手段があります。</span><span class="sxs-lookup"><span data-stu-id="171d2-208">Regarding attacks specific to Microsoft Teams, threats to data, for example, Azure Sentinel also has means to monitor for them and hunt them down.</span></span>

### <a name="create-a-parser-for-your-data"></a><span data-ttu-id="171d2-209">データのパーサを作成する</span><span class="sxs-lookup"><span data-stu-id="171d2-209">Create a parser for your data</span></span>

<span data-ttu-id="171d2-210">収集されたデータの集合を理解するために最初に行う必要がある作業は、それを解析して意味づけすることです。</span><span class="sxs-lookup"><span data-stu-id="171d2-210">The first thing to do in order to make sense of the large set of collected data is to give it meaning by parsing it.</span></span> <span data-ttu-id="171d2-211">これは、データを簡単に使用できるようにする Kusto Query 言語 (KQL) 関数で実行されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-211">This is done with a Kusto Query Language (KQL) Function that makes the data easier to use.</span></span>

> [!NOTE]
> <span data-ttu-id="171d2-212">KQL 関数は、「関数」と呼ばれるデータ型で保存された KQL クエリです。</span><span class="sxs-lookup"><span data-stu-id="171d2-212">KQL functions are KQL queries saved as a data-type called 'function'.</span></span> <span data-ttu-id="171d2-213">KQL 関数には、Sentinel のクエリ ボックスに入力できるエイリアスがあるので、クエリをすばやく再実行できます。</span><span class="sxs-lookup"><span data-stu-id="171d2-213">KQL functions have an alias that can be entered into the query box in Sentinel to quickly run the query again.</span></span> <span data-ttu-id="171d2-214">KQL 関数の詳細とパーサ関数の作成方法の詳細については、[この技術コミュニティの記事](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="171d2-214">For more about KQL functions and how to build a parser function, read [this Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>
 
 <span data-ttu-id="171d2-215">以下のパーサは、*Teams* に関連する Office 365 Management API フィールドの一部を選択することを目的とした、カスタマイズ可能な例です。</span><span class="sxs-lookup"><span data-stu-id="171d2-215">The parser below is a customizable example aimed at selecting a subset of the Office 365 Management API fields relevant to *Teams*.</span></span> <span data-ttu-id="171d2-216">また、パーサ [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) も提案されていますが、以下のパーサを変更して、さまざまなニーズや必要に合わせて変更できます。</span><span class="sxs-lookup"><span data-stu-id="171d2-216">There is also a suggested parser [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), but the parser below can be modified to fit different needs and preferences.</span></span>

```kusto
O365API_CL
| where Workload_s =~ "MicrosoftTeams"
| project TimeGenerated,
          Workload=Workload_s,
          Operation=Operation_s,
          TeamName=columnifexists('TeamName_s', ""),
          UserId=columnifexists('UserId_s', ""),
          AddOnName=columnifexists('AddOnName_s', AddOnGuid_g),
          Members=columnifexists('Members_s', ""),
          Settings=iif(Operation_s contains "Setting", pack("Name", columnifexists('Name_s', ""), "Old Value", columnifexists('OldValue_s', ""), "New Value", columnifexists('NewValue_s', "")),""),
          Details=pack("Id", columnifexists('Id_g', ""),  "OrganizationId", columnifexists('OrganizationId_g', ""), "UserType", columnifexists('UserType_d', ""), "UserKey", columnifexists('UserKey_g', ""), "TeamGuid", columnifexists('TeamGuid_s', "")) 
```
 <span data-ttu-id="171d2-217">このパーサを KQL 関数として、Teams データのエイリアスとして保存します。</span><span class="sxs-lookup"><span data-stu-id="171d2-217">Save the parser as a KQL function, with an alias of TeamsData.</span></span> <span data-ttu-id="171d2-218">これは、後に続くクエリに使用されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-218">It will be used for the queries to follow.</span></span> <span data-ttu-id="171d2-219">KQL 関数をパーサとして構成および使用する方法の詳細については、こちらの [技術コミュニティの記事](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="171d2-219">Details on configuring and using a KQL function as a parser can be found in this [Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="171d2-220">KQL クエリの役に立つ検索</span><span class="sxs-lookup"><span data-stu-id="171d2-220">Helpful hunting KQL queries</span></span>

<span data-ttu-id="171d2-221">これらのクエリを使用すると、Teams データとTeams 環境を理解できます。</span><span class="sxs-lookup"><span data-stu-id="171d2-221">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="171d2-222">疑わしいアクティビティを認識するには、最初の手順として環境がどのように見え、どのように振る舞うべきかを理解することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="171d2-222">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="171d2-223">そこから、スレッド ハンティングに進出することができます。</span><span class="sxs-lookup"><span data-stu-id="171d2-223">From there, you can branch out into threat hunting.</span></span>

#### <a name="federated-external-users-query"></a><span data-ttu-id="171d2-224">フェデレーション外部ユーザー クエリ</span><span class="sxs-lookup"><span data-stu-id="171d2-224">Federated external users query</span></span>

<span data-ttu-id="171d2-225">フェデレーション外部ユーザーを有する Teams サイト リストを取得します。</span><span class="sxs-lookup"><span data-stu-id="171d2-225">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="171d2-226">これらのユーザーは、組織によって *所有されていない* ドメイン名または UPN サフィックスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="171d2-226">These users will have a domain name / UPN suffix that *isn't* owned by your organization.</span></span> <span data-ttu-id="171d2-227">この例のクエリでは、組織が contoso.com. を所有しています。</span><span class="sxs-lookup"><span data-stu-id="171d2-227">In this example query, the organization owns contoso.com.</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| extend UPN = tostring(parse_json(Members)[0].Upn)
| where UPN !endswith "contoso.com"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members, UPN
```

> [!TIP]
> <span data-ttu-id="171d2-228">Teams における外部アクセスおよびゲスト アクセスの種類の詳細については、[この記事](./communicate-with-users-from-other-organizations.md) または [Teams セキュリティ ガイド](./teams-security-guide.md) の *参加者の種類* セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="171d2-228">To learn more about External and Guest access types in Teams see [this article](./communicate-with-users-from-other-organizations.md), or the *Participant Types* section in the [Teams Security Guide](./teams-security-guide.md).</span></span>

#### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="171d2-229">最近参加した、または役割を変更したユーザー</span><span class="sxs-lookup"><span data-stu-id="171d2-229">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="171d2-230">特定のユーザーに問い合わせて、過去7日間または1週間以内に、Teams チャネルに追加されたかどうかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="171d2-230">Query a specific user to check if they were added to a Teams channel in the last 7 days, or within a week:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

<span data-ttu-id="171d2-231">過去7日間にチームのユーザーの役割が変更されました。</span><span class="sxs-lookup"><span data-stu-id="171d2-231">Was a user's role changed for a Team in the last 7 days:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="171d2-232">不明または新しい組織からの外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="171d2-232">External users from unknown or new organizations</span></span>

<span data-ttu-id="171d2-233">Teams では、環境やチャネルに外部ユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="171d2-233">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="171d2-234">多くの場合、組織では、キーとなるパートナーシップの数が限られています。また、これらのパートナーの中からユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="171d2-234">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="171d2-235">このKQLは、チームに追加された外部ユーザーが、以前に表示または追加されていない組織から来ているかどうかを見ています。</span><span class="sxs-lookup"><span data-stu-id="171d2-235">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
// If you want to look at users further back than the last day change this value 
let lookback_data = 1d; 
let known_orgs = ( 
TeamsData  
| where TimeGenerated > ago(data_date) 
| where Operation =~ "MemberAdded" or Operation =~ "TeamsSessionStarted" 
// Extract the correct UPN and parse our external organization domain 
| extend UPN = iif(Operation == "MemberAdded", tostring(parse_json(Members)[0].UPN), UserId) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| summarize by Organization); 
TeamsData  
| where TimeGenerated > ago(lookback_data) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| where Organization !in (known_orgs) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UPN 
```

#### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="171d2-236">追加され、後に削除された外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="171d2-236">External users who were added and then removed</span></span>

<span data-ttu-id="171d2-237">ある程度の既存アクセス権を持つ攻撃者は、Teams 新しい外部アカウントを追加して、データにアクセスしたり、データを流出させたりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="171d2-237">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="171d2-238">また、アクセスしたことを隠すために、当該ユーザーをすぐに削除してしまう可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="171d2-238">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="171d2-239">このクエリは、Teams に追加された外部アカウントを検索し、疑わしい動作を特定するために迅速に削除します。</span><span class="sxs-lookup"><span data-stu-id="171d2-239">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

```kusto
// If you want to look at user added further than 7 days ago adjust this value 
let time_ago = 7d; 
// If you want to change the timeframe of how quickly accounts need to be added and removed change this value 
let time_delta = 1h; 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeAdded=TimeGenerated, Operation, UPN, UserWhoAdded = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid) 
| join ( 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberRemoved" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeDeleted=TimeGenerated, Operation, UPN, UserWhoDeleted = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid)) on UPN, TeamGuid 
| where TimeDeleted < (TimeAdded + time_delta) 
| project TimeAdded, TimeDeleted, UPN, UserWhoAdded, UserWhoDeleted, TeamName, TeamGuid 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeAdded, AccountCustomEntity = UPN 
```

#### <a name="new-bot-or-application-added"></a><span data-ttu-id="171d2-240">新しい bot またはアプリケーションが追加されました</span><span class="sxs-lookup"><span data-stu-id="171d2-240">New bot or application added</span></span>

<span data-ttu-id="171d2-241">Teams では、機能セットを拡張するためのアプリや bot をチームに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="171d2-241">Teams has the ability to include apps or bots in a Team to extend the feature set.</span></span> <span data-ttu-id="171d2-242">これには、カスタム アプリと bot が含まれます。</span><span class="sxs-lookup"><span data-stu-id="171d2-242">This includes custom apps and bots.</span></span> <span data-ttu-id="171d2-243">場合によっては、アプリまたは bot を使用して、ユーザー アカウントや、アクセス ファイル、その他のデータを必要とせずに、Teams の永続性を確立できます。</span><span class="sxs-lookup"><span data-stu-id="171d2-243">In some cases, an app or bot could be used to establish persistence in Teams without needing a user account, as well as access files and other data.</span></span> <span data-ttu-id="171d2-244">このクエリは、チームに新たに追加されたアプリや bot を検索します。</span><span class="sxs-lookup"><span data-stu-id="171d2-244">This query hunts for apps or bots that are new to Teams.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
let historical_bots = ( 
TeamsData 
| where TimeGenerated > ago(data_date) 
| where isnotempty(AddOnName) 
| project AddOnName); 
TeamsData 
| where TimeGenerated > ago(1d) 
// Look for add-ins we have never seen before 
| where AddOnName in (historical_bots) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UserId 
```

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="171d2-245">多数のチームの所有者であるユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="171d2-245">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="171d2-246">通常、ユーザーは特定のトピックについて少数のチームを作成して所有していますが、特権を昇格させようとする攻撃者は、多数の異なるチームの所有者権限を自分に割り当てる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="171d2-246">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams, when, usually, users create and own a small number of teams around specific topics.</span></span> <span data-ttu-id="171d2-247">この KQL クエリは不審な動作を検索します。</span><span class="sxs-lookup"><span data-stu-id="171d2-247">This KQL query looks for suspicious behavior.</span></span>

```kusto
// Adjust this value to change how many teams a user is made owner of before detecting 
let max_owner_count = 3; 
// Change this value to adjust how larger timeframe the query is run over. 
let time_window = 1d; 
let high_owner_count = (TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| summarize dcount(TeamName) by Member 
| where dcount_TeamName > max_owner_count 
| project Member); 
TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| where Member in (high_owner_count) 
| extend TeamGuid = tostring(Details.TeamGuid) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = Member 
```

#### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="171d2-248">1人のユーザーによる多くのチームの削除</span><span class="sxs-lookup"><span data-stu-id="171d2-248">Many Team deletions by a single user</span></span>

<span data-ttu-id="171d2-249">攻撃者は、複数のチームを削除することで、プロジェクトやデータを混乱させたり、危険にさらしたりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="171d2-249">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="171d2-250">通常、チームは個人の所有者によって削除されているため、多くのチームを中心に削除されている場合は、問題の徴候になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="171d2-250">Because teams are generally deleted by individual Owners, a central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="171d2-251">この KQL は、複数のチームを削除するユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="171d2-251">This KQL looks for single users who delete multiple teams.</span></span>

```kusto
 // Adjust this value to change how many Teams should be deleted before including
 let max_delete = 3;
 // Adjust this value to change the timewindow the query runs over
 let time_window = 1d;
 let deleting_users = (
 TeamsData 
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | summarize count() by UserId
 | where count_ > max_delete
 | project UserId);
 TeamsData
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | where UserId in (deleting_users)
 | extend TeamGuid = tostring(Details.TeamGuid)
 | project-away AddOnName, Members, Settings
 // Uncomment the following line to map query entities is you plan to use this as a detection query
 //| extend timestamp = TimeGenerated, AccountCustomEntity = UserId
```

#### <a name="expanding-your-thread-hunting-opportunities"></a><span data-ttu-id="171d2-252">スレッド ハンティングの機会を広げる</span><span class="sxs-lookup"><span data-stu-id="171d2-252">Expanding your thread hunting opportunities</span></span>

<span data-ttu-id="171d2-253">Azure Active Directory (Azure AD) などのリソースや他の Office 365 ワークロードからのクエリを Teams のクエリと組み合わせることで、ハンティングを拡大することができます。</span><span class="sxs-lookup"><span data-stu-id="171d2-253">You can expand your hunting by combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads with your Teams queries.</span></span> <span data-ttu-id="171d2-254">一例として、Azure AD SigninLogs の疑わしいパターンの検出を組み合わせて、チーム オーナーを探している間にその情報を使用しています。</span><span class="sxs-lookup"><span data-stu-id="171d2-254">One example is combining detection of suspicious patterns in Azure AD SigninLogs, and using that information while hunting for Team Owners.</span></span>

```kusto
let timeRange = 1d;
let lookBack = 7d;
let threshold_Failed = 5;
let threshold_FailedwithSingleIP = 20;
let threshold_IPAddressCount = 2;
let isGUID = "[0-9a-z]{8}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{12}";
let azPortalSignins = SigninLogs
| where TimeGenerated >= ago(timeRange)
// Azure Portal only and exclude non-failure Result Types
| where AppDisplayName has "Azure Portal" and ResultType !in ("0", "50125", "50140")
// Tagging identities not resolved to friendly names
| extend Unresolved = iff(Identity matches regex isGUID, true, false);
// Lookup up resolved identities from last 7 days
let identityLookup = SigninLogs
| where TimeGenerated >= ago(lookBack)
| where not(Identity matches regex isGUID)
| summarize by UserId, lu_UserDisplayName = UserDisplayName, lu_UserPrincipalName = UserPrincipalName;
// Join resolved names to unresolved list from portal signins
let unresolvedNames = azPortalSignins | where Unresolved == true | join kind= inner (
   identityLookup ) on UserId
| extend UserDisplayName = lu_UserDisplayName, UserPrincipalName = lu_UserPrincipalName
| project-away lu_UserDisplayName, lu_UserPrincipalName;
// Join Signins that had resolved names with list of unresolved that now have a resolved name
let u_azPortalSignins = azPortalSignins | where Unresolved == false | union unresolvedNames;
let failed_signins = (u_azPortalSignins
| extend Status = strcat(ResultType, ": ", ResultDescription), OS = tostring(DeviceDetail.operatingSystem), Browser = tostring(DeviceDetail.browser)
| extend FullLocation = strcat(Location,'|', LocationDetails.state, '|', LocationDetails.city)
| summarize TimeGenerated = makelist(TimeGenerated), Status = makelist(Status), IPAddresses = makelist(IPAddress), IPAddressCount = dcount(IPAddress), FailedLogonCount = count()
by UserPrincipalName, UserId, UserDisplayName, AppDisplayName, Browser, OS, FullLocation
| mvexpand TimeGenerated, IPAddresses, Status
| extend TimeGenerated = todatetime(tostring(TimeGenerated)), IPAddress = tostring(IPAddresses), Status = tostring(Status)
| project-away IPAddresses
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated) by UserPrincipalName, UserId, UserDisplayName, Status, FailedLogonCount, IPAddress, IPAddressCount, AppDisplayName, Browser, OS, FullLocation
| where (IPAddressCount >= threshold_IPAddressCount and FailedLogonCount >= threshold_Failed) or FailedLogonCount >= threshold_FailedwithSingleIP
| project UserPrincipalName);
TeamsData
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| extend Member = tostring(parse_json(Members)[0].UPN) 
| extend NewRole = toint(parse_json(Members)[0].Role) 
| where NewRole == 2
| where Member in (failed_signins)
| extend TeamGuid = tostring(Details.TeamGuid)
```

<span data-ttu-id="171d2-255">また、Teams ベースのサインインのみのフィルターを追加することで、Teams 固有の SigninLogs の検出を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="171d2-255">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based sign-ins by using:</span></span>

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

<span data-ttu-id="171d2-256">`where AppDisplayName starts with "Microsoft Teams"` をさらに使用する方法について、以下の KQL の例では、1つの IP アドレスからのログオンに成功し、異なる IP アドレスからは失敗していますが、Teams のサインインにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="171d2-256">To help explain using `where AppDisplayName starts with "Microsoft Teams"` further, the KQL below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped only to Teams sign-ins:</span></span>

```kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName startswith "Microsoft Teams"
  | project SuccessLogonTime = TimeGenerated, UserPrincipalName, SuccessIPAddress = IPAddress, AppDisplayName, SuccessIPBlock = strcat(split(IPAddress, ".")[0], ".", split(IPAddress, ".")[1])
  | join kind= inner (
      SigninLogs 
      | where TimeGenerated >= ago(timeFrame) 
      | where ResultType !in ("0", "50140") 
      | where ResultDescription !~ "Other"  
      | where AppDisplayName startswith "Microsoft Teams"
      | project FailedLogonTime = TimeGenerated, UserPrincipalName, FailedIPAddress = IPAddress, AppDisplayName, ResultType, ResultDescription
  ) on UserPrincipalName, AppDisplayName 
  | where SuccessLogonTime < FailedLogonTime and FailedLogonTime - SuccessLogonTime <= logonDiff and FailedIPAddress !startswith SuccessIPBlock
  | summarize FailedLogonTime = max(FailedLogonTime), SuccessLogonTime = max(SuccessLogonTime) by UserPrincipalName, SuccessIPAddress, AppDisplayName, FailedIPAddress, ResultType, ResultDescription 
  | extend timestamp = SuccessLogonTime, AccountCustomEntity = UserPrincipalName, IPCustomEntity = SuccessIPAddress
```

## <a name="important-information-and-updates"></a><span data-ttu-id="171d2-257">重要な情報と更新プログラム</span><span class="sxs-lookup"><span data-stu-id="171d2-257">Important information and updates</span></span>

<span data-ttu-id="171d2-258">**Pete Bryan、Nicholas DiCola、および Matthew Lowe によるコンテンツの共同作業に感謝します。**</span><span class="sxs-lookup"><span data-stu-id="171d2-258">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="171d2-259">Pete Bryan や共同作業を行っているユーザーは、チームの検出や検索のクエリを引き続き開発します。そのため、この [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) リポジトリで更新プログラムをチェックできます。</span><span class="sxs-lookup"><span data-stu-id="171d2-259">Pete Bryan and the people he collaborates with will continue to develop detection and hunting queries for Teams, so keep in touch with this [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>  <span data-ttu-id="171d2-260">この記事で使用している [パーサー](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) および [ロジック アプリ](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) の更新プログラムを監視します。</span><span class="sxs-lookup"><span data-stu-id="171d2-260">Monitor for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span> <span data-ttu-id="171d2-261">[Azure Sentinel コミュニティ](https://github.com/Azure/Azure-Sentinel/wiki) に参加して投稿することもできます。</span><span class="sxs-lookup"><span data-stu-id="171d2-261">You can also join and contribute to the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="171d2-262">ご協力ありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="171d2-262">Thank you!</span></span> <span data-ttu-id="171d2-263">良い検索を。</span><span class="sxs-lookup"><span data-stu-id="171d2-263">Happy hunting.</span></span>

[<span data-ttu-id="171d2-264">Azure AD でアプリケーションを登録する</span><span class="sxs-lookup"><span data-stu-id="171d2-264">Registering your application in Azure AD</span></span>](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="171d2-265">監査ログ検索を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="171d2-265">Turn audit log search on or off</span></span>](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%c2%a0)

[<span data-ttu-id="171d2-266">Azure Sentinel とは</span><span class="sxs-lookup"><span data-stu-id="171d2-266">What is Azure Sentinel</span></span>](/azure/sentinel/overview)
