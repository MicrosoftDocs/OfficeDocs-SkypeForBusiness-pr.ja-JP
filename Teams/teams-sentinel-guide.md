---
title: Azure Sentinel および Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: IT 管理者が Sentinel を使用して、Teams で発生する可能性のある脅威を監視し、捜索するためのセキュリティ通知とラーニングです。
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
ms.openlocfilehash: a59609404e51287be02dafc961561bd03e9efb9b
ms.sourcegitcommit: 8b172e9a0d0626c9a88998600d4b17c6c8cdadd2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761485"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="d1ef3-103">Azure Sentinel および Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1ef3-103">Azure Sentinel and Microsoft Teams</span></span>

<span data-ttu-id="d1ef3-104">Teams は、Microsoft 365 クラウドでの通信とデータ共有の両方の中心的な役割を担います。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-104">Teams serves a central role in both communication and data sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="d1ef3-105">Teams サービスはクラウド内の多くの基になっているテクノロジを使用しているので、*ログの捜索* を行う場合だけではなく *会議をリアルタイムで監視* する場合も手動分析および自動分析を利用することができます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-105">Because the Teams service touches on so many underlying technologies in the Cloud, it can benefit from human and automated analysis not only when it comes to *hunting in logs*, but also in *real-time monitoring of meetings*.</span></span> <span data-ttu-id="d1ef3-106">Azure Sentinel は、管理者に次のようなソリューションを提案します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-106">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="d1ef3-107">Azure Sentinel の概要</span><span class="sxs-lookup"><span data-stu-id="d1ef3-107">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="d1ef3-108">[この記事](https://docs.microsoft.com/azure/sentinel/overview) は、まさにその通りです。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-108">[This article](https://docs.microsoft.com/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="d1ef3-109">Sentinel および Microsoft Teams のアクティビティ ログ</span><span class="sxs-lookup"><span data-stu-id="d1ef3-109">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="d1ef3-110">この記事では、Azure Sentinel でチーム アクティビティ ログを収集する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-110">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span> <span data-ttu-id="d1ef3-111">管理者は、Sentinel のワークブックおよびランブックがセキュリティ監視を体系的に行うことで、セキュリティ管理を一枚のガラスの下に置くことができます （選択したサード パーティ製のデバイス、Microsoft Threat Protection、およびその他の Microsoft 365ワークロードを含む）。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-111">Aside from allowing administrators to put security management under one pane of glass (including any selected 3rd party devices, Microsoft Threat Protection, and other Microsoft 365 Workloads), Sentinel workbooks, and runbooks can make security monitoring systematic.</span></span> <span data-ttu-id="d1ef3-112">このプロセスの最初の手順として、分析に必要なログを収集します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-112">A good first step in this process is collecting the needed logs for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="d1ef3-113">複数の Microsoft 365 サブスクリプションは、Azure Sentinel の同じインスタンスに表示できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-113">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="d1ef3-114">これにより、[リアルタイム監視](https://docs.microsoft.com/azure/sentinel/livestream) および履歴ログ ファイルでの脅威の検索ができるようになります。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-114">This will allow for [realtime monitoring](https://docs.microsoft.com/azure/sentinel/livestream) and hunting for threats in historical log file s.</span></span> <span data-ttu-id="d1ef3-115">管理者は、1つのリソース グループ内もしくはリソース グループ間、または別のサブスクリプションで、[クロス リソース クエリ](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query) を使用して検索できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-115">Administrators will be able to hunt using [cross-resource queries](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs"></a><span data-ttu-id="d1ef3-116">ステップ 1: チームログを収集する</span><span class="sxs-lookup"><span data-stu-id="d1ef3-116">Step 1: Collect Teams logs</span></span>

<span data-ttu-id="d1ef3-117">このセクションには、3つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-117">This section has three parts:</span></span>

1. <span data-ttu-id="d1ef3-118">**Microsoft 365** (M365) で監査ログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-118">Enabling Audit Logs in **Microsoft 365** (M365).</span></span>
2. <span data-ttu-id="d1ef3-119">**Microsoft Azure** にアプリを登録して、認証とログ収集の承認を許可します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-119">Registering an App in **Microsoft Azure** to permit authentication and authorization for log collection.</span></span>
3. <span data-ttu-id="d1ef3-120">**PowerShell**経由で、M365 API を使用してログ収集を許可する API サブスクリプションを登録します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-120">Registering the API subscription that will allow log collection via M365 API via **PowerShell**.</span></span>

### <a name="enable-audit-logs-in-m365"></a><span data-ttu-id="d1ef3-121">M365 で監査ログを有効にする</span><span class="sxs-lookup"><span data-stu-id="d1ef3-121">Enable Audit logs in M365</span></span>

<span data-ttu-id="d1ef3-122">Teams は M365 経由でアクティビティを記録するため、監査ログは既定では収集されません。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-122">Because Teams logs activity through M365, audit logs aren't collected by default.</span></span> <span data-ttu-id="d1ef3-123">この機能を有効にするには、[次の手順](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0) を経由します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-123">Turn on this feature via [these steps](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0).</span></span> <span data-ttu-id="d1ef3-124">Teams のデータは、*Audit.General* 下の M365 audit に収集されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-124">Teams data is collected in the M365 audit under *Audit.General*.</span></span>

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a><span data-ttu-id="d1ef3-125">ログ収集用 Microsoft Azure にアプリを登録する</span><span class="sxs-lookup"><span data-stu-id="d1ef3-125">Register an App in Microsoft Azure for log collection</span></span>

> [!TIP]
> <span data-ttu-id="d1ef3-126">作業を開始する前に、後で使用するための **アプリケーション IDまたはクライアント ID** および **テナント ID** を記録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-126">Before you begin, you will need to record you **Application ID / Client ID**, and your **Tenant ID** for later use.</span></span> <span data-ttu-id="d1ef3-127">これらの情報は、次のアプリの登録手順を順番に行うため、必ずキャプチャしてください。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-127">Be sure to capture them as you walk through app registration steps below.</span></span> <span data-ttu-id="d1ef3-128">両方の ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-128">You will see both IDs.</span></span>
>- <span data-ttu-id="d1ef3-129">アプリが作成されたら、クイック起動のサイド バーにある [アプリの登録] をクリックし、新しいアプリの表示名を検出して、[アプリケーション (クライアント) ID をコピーします。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-129">After your app is created, click App Registration on the quick launch side-bar > Find your new app's display name > copy the Application (client) ID.</span></span>
>- <span data-ttu-id="d1ef3-130">クイック起動のサイド バーにある [概要] をクリックして、ディレクトリ (テナント) ID をコピーします。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-130">Click Overview on the quick launch side-bar > copy the Directory (tenant) ID.</span></span>

<span data-ttu-id="d1ef3-131">Azure Active Directory (Azure AD) アプリを認証し、API からログ データを収集することを承認します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-131">Authenticate and authorize an Azure Active Directory (Azure AD) app to collect log data from the API.</span></span>

1. <span data-ttu-id="d1ef3-132">Azure ポータルで *Azure AD* ブレードに移動します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-132">Navigate to your *Azure AD* blade in the Azure portal.</span></span>
2. <span data-ttu-id="d1ef3-133">クイック起動サイド バーにある *[アプリを登録]* をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-133">Click on *App registrations* in the quick launch side-bar.</span></span>
3. <span data-ttu-id="d1ef3-134">*[新規登録]* を選択します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-134">Select *New registration*.</span></span>
4. <span data-ttu-id="d1ef3-135">Teams ログ収集アプリの名前を入力し、*[登録]* をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-135">Name your Teams log collecting app and click *Register*.</span></span>
5. <span data-ttu-id="d1ef3-136">このパスに沿ってクリックします : *API のアクセス許可* > *アクセス許可を追加* > *Office 365 Management APIs* > *Application のアクセス許可*。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-136">Click along this path: *API Permissions* > *Add a permission* > *Office 365 Management APIs* > *Application permissions*.</span></span>
6. <span data-ttu-id="d1ef3-137">[アクティビティ フィード] を展開し、 *[ActivityFeed.Read]* を確認します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-137">Expand Activity Feed and check *ActivityFeed.Read*.</span></span>
7. <span data-ttu-id="d1ef3-138">ここでは、*[全体管理者の同意]* を選びます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-138">Choose *Grand admin consent* here.</span></span> <span data-ttu-id="d1ef3-139">確認メッセージが表示されたら、[はい] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-139">Click Yes when prompted asking if you mean it.</span></span>
8. <span data-ttu-id="d1ef3-140">サイド バーの *[証明書と秘密]* > *[新規クライアント シークレット]* ボタンの順でクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-140">Click *Certificates and Secrets* in the side-bar> *New client secret* button.</span></span>
9. <span data-ttu-id="d1ef3-141">[新規クライアント シークレット] ウィンドウで新規クライアント シークレットの説明を入力し、[有効期限] に [いいえ] を選択し、*[追加]* をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-141">On the New client secret window, enter a description for the new Client Secret, make sure you choose 'Never' for Expiration, and click *Add*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1ef3-142">新規クライアント シークレットを、新しく作成されたアプリの名前の下にあるパスワード マネージャーのエントリにコピーすることは、**[重要]** です。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-142">It's **critical** to copy the new client secret into a password manager entry that goes under the name of the newly created app.</span></span> <span data-ttu-id="d1ef3-143">Azure ブレード (*ブレード* はウィンドウの Azure 用語) を終了した後に、このシークレットを見に戻ることはできません。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-143">You won't be able to get back to look at this secret after the closing out of the Azure blade (*blade* being the Azure term for window).</span></span>

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a><span data-ttu-id="d1ef3-144">PowerShell で API を登録してチーム ログを収集する</span><span class="sxs-lookup"><span data-stu-id="d1ef3-144">Register the API with PowerShell to collect Teams logs</span></span>

<span data-ttu-id="d1ef3-145">セットアップの最後の手順では、ログ データを収集するために、API サブスクリプションを収集して登録します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-145">The final step in setup is to collect and register the API subscription so that you can collect your log data.</span></span> <span data-ttu-id="d1ef3-146">これを行うには、PowerShell REST を M365 管理アクティビティ API に呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-146">This is done via PowerShell REST calls to the M365 Management Activity API.</span></span>

<span data-ttu-id="d1ef3-147">**アプリケーション (クライアント) ID**、新しい **クライアント シークレット**、**M365用の URL ドメイン**、および以下の PowerShell コマンドレットの **ディレクトリ (テナント) ID** 値を提供できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-147">Be ready to supply **Application (client) ID**, the new **Client Secret**, your **URL domain for M365**, and **Directory (tenant) ID** values in the PowerShell cmdlet below.</span></span>

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

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a><span data-ttu-id="d1ef3-148">手順 2: チーム ログを取り込むための Sentinel プレイブックを展開する</span><span class="sxs-lookup"><span data-stu-id="d1ef3-148">Step 2: Deploy a Sentinel Playbook to ingest the Teams logs</span></span>

<span data-ttu-id="d1ef3-149">Azure Sentinel プレイブック (ロジック アプリとも呼ばれます) を使用すると、収集した Teams データを Azure が取り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-149">Azure Sentinel Playbooks (also called Logic Apps) will allow Azure to ingest your collected Teams data.</span></span> <span data-ttu-id="d1ef3-150">ロジック アプリは、Office 365 に対して、Azure Sentinel ワークスペースに書き込まれる監査データを検索します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-150">The Logic App queries Office 365 to find the audit data it writes into the Azure Sentinel workspace.</span></span>

<span data-ttu-id="d1ef3-151">[この](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM テンプレートを使用して、Sentinel プレイブックを展開します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-151">Use [this](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM template to deploy your Sentinel Playbook.</span></span>

<span data-ttu-id="d1ef3-152">留意すべき点がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-152">Things to remember:</span></span>

1. <span data-ttu-id="d1ef3-153">ARM テンプレートを通して、特定の値を使用している環境に適した値に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-153">You will need to walk through the ARM template and replace certain of the values with values appropriate for your own environment.</span></span>
2. <span data-ttu-id="d1ef3-154">ログを取り込んでから Azure Sentinel で結果を見るまでの時間を確保する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-154">You will need to allow time between the ingestion of logs and looking at the results in Azure Sentinel.</span></span>

   <span data-ttu-id="d1ef3-155">過去5分間のデータがない場合は、5 ～ 10 分待ってから、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-155">Wait for 5 to 10 minutes, understanding that if there is no data within the past 5 minutes you will see an error message.</span></span> <span data-ttu-id="d1ef3-156">監査ログを確認し、Teams の情報は監査に含まれていることに注意してください。Teams のログよりも多くの情報を収集する一般的なイベントでは、使用中のシステムで 5 ～ 10 分以内に結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-156">Check Audit logs and keep in mind that because Teams information is in the Audit.General events, which collects more than Teams logs, results should appear within 5 to 10 minutes on systems that are in use.</span></span> <span data-ttu-id="d1ef3-157">テキスト環境を使用している場合は、ログを生成するために Teams を使用してください。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-157">If using a text environment, be certain to use Teams in order to generate logging.</span></span>

![ロジック アプリ クラスを示すグラフィック。](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> <span data-ttu-id="d1ef3-159">グラフィックのアクションの説明:</span><span class="sxs-lookup"><span data-stu-id="d1ef3-159">Explanation of actions in the graphic:</span></span> 
  </summary>

  <span data-ttu-id="d1ef3-160">•定期的なパターンは、ワークフローが1時間ごとに実行されるようにするロジック アプリ トリガーです。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-160">• Recurrence is the Logic App Trigger that tells the workflow to run every hour.</span></span>
  <p>
<span data-ttu-id="d1ef3-161">•現在の時刻のアクションは、非常に基本的で、現在の時刻だけを取得します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-161">• The Current Time action is very basic and just gets the current time.</span></span>
  <p>
<span data-ttu-id="d1ef3-162">変数を初期化すると、NextPage という名前の変数が作成され、1に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-162">• Initialize Variable creates a variable called NextPage and sets it to 1.</span></span> <span data-ttu-id="d1ef3-163">これは、O365 API のページネーションを処理するために、後で使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-163">This will be used later in order to handle pagination from the O365 API.</span></span>
  <p>
<span data-ttu-id="d1ef3-164">•変数の初期化2は、開始時刻という空の変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-164">• Initialize Variable 2 creates an empty variable called Start Time.</span></span>
  <p>
<span data-ttu-id="d1ef3-165">•クエリおよびリスト結果の実行は、ロジック アプリから最後に入力された O365 ログをワークスペースに問い合わせる Azure モニター アクションです。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-165">• Run Query and list results is an Azure Monitor action that will query the workspace for the last O365 log that was entered from the Logic App.</span></span>
  <p>
<span data-ttu-id="d1ef3-166">•条件4は、クエリの実行とリスト結果クエリが何かデータを返したかどうかを確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-166">• Condition 4 is used to check whether the Run Query and list results query returned any data.</span></span> <span data-ttu-id="d1ef3-167">これは、ロジック アプリが初めて使われるかどうかを確認するために行われます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-167">This is done to check if this is the very first time the Logic App has been used.</span></span> <span data-ttu-id="d1ef3-168">データが返されない場合、StartTime 変数は Now ～ 24 時間に設定されています。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-168">If no data is returned, StartTime variable is set to Now – 24 hours.</span></span> <span data-ttu-id="d1ef3-169">データが返される場合、StartTime は最終発生時間に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-169">If data is returned, StartTime is set to the last record TimeGenerated.</span></span> <span data-ttu-id="d1ef3-170">これは、O365 API に対して、クエリが最後のエントリから今までの時点、またはそれが初めて実行された場合は、直近の24時間の時点までのデータを取得できるように行われます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-170">This is done so that the query can get data from the last entry till now in the poll against the O365 API, or in the last 24 hours if this is the first run.</span></span>
  <p>
<span data-ttu-id="d1ef3-171">•変数の初期化3は、「AvaibleUri」 という名前の変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-171">• Initialize Variable 3 creates a variable called AvailableUri.</span></span> <span data-ttu-id="d1ef3-172">これは、StartTime と CurrentTime を使用し、それぞれ開始時刻と終了時刻として作成された URL の文字列です。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-172">This is a string with the URL built using the StartTime and CurrentTime as start and end times, respectively.</span></span>
  <p>
<span data-ttu-id="d1ef3-173">•Until 条件は、ロジック アプリが API にポーリングを継続して、データ (ページネーション) があるかどうかを確認するためのループです。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-173">• The Until condition is a loop that allows the logic app to keep polling the API to see if there is more data (pagination).</span></span> <span data-ttu-id="d1ef3-174">NextPage 変数が1の場合、ループは続行します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-174">As long as NextPage variable is 1 the loop will continue.</span></span> <span data-ttu-id="d1ef3-175">この変数は、その後、取得するページが残っていない場合に更新されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-175">Later this variable will be updated if there are no more pages left to retrieve.</span></span>
  <p>
<span data-ttu-id="d1ef3-176">Until ループの内部では、最初の HTTP ステップが AvaibleUri に接続します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-176">• Inside the Until loop, the first HTTP step Connects to the AvailableURI.</span></span> <span data-ttu-id="d1ef3-177">この URI は、使用できるコンテンツと各コンテンツ URI のリストを返します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-177">This URI returns a list of available content and each contents URI.</span></span> <span data-ttu-id="d1ef3-178">この URL での操作方法については、https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-178">There's more on how this works at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="d1ef3-179">•次に、データが返されることを確認するためのチェックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-179">• Next a check is run to make sure data is returned.</span></span> <span data-ttu-id="d1ef3-180">本文の長さが0かどうかを調べます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-180">The Condition checks if the length of the body is 0.</span></span> <span data-ttu-id="d1ef3-181">この場合、ログ分析に書き込むデータがありません。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-181">If so there is no data to write to Log Analytics.</span></span> <span data-ttu-id="d1ef3-182">値が0より大きい場合、処理するデータがあります。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-182">If the value is greater than 0, there is data to process.</span></span>
  <p>
<span data-ttu-id="d1ef3-183">•データが検出された場合は、次に処理される必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-183">• If data is detected, it must next be processed.</span></span> <span data-ttu-id="d1ef3-184">JSON 解析は、返されるデータのスキーマを定義します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-184">Parse JSON defines a schema of the returned data.</span></span> <span data-ttu-id="d1ef3-185">これにより、ロジック アプリは、後の手順で、解析されたデータをダイナミック コンテンツとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-185">This allows logic apps to use the parsed data as Dynamic content in later steps.</span></span>
  <p>
<span data-ttu-id="d1ef3-186">•返される使用可能なデータのリストは配列であるため、For Each アクションを使用して、使用可能なコンテンツのリストをループするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-186">• Since the returned list of available data is an Array, a For Each action is used to loop through the list of available content.</span></span>
  <p>
<span data-ttu-id="d1ef3-187">•次は、コンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-187">• Next is grabbing the content.</span></span>  <span data-ttu-id="d1ef3-188">HTTP を再び使用して、contentUri (JSON 解析で作成された動的プロパティ) を取得します。これは、取得するデータの URL です。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-188">HTTP is used again to get the contentUri (a dynamic property created from Parse JSON), which is the URL of the data to retrieve.</span></span>
  <p>
<span data-ttu-id="d1ef3-189">• JSON 解析は、返されるデータの解析にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-189">• Parse JSON is also used to parse the returned data.</span></span> <span data-ttu-id="d1ef3-190">この URL には、https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content のような、いくつかのサンプルコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-190">You can find some sample content at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="d1ef3-191">•返されるデータは、配列です。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-191">• The data returned is also an array.</span></span> <span data-ttu-id="d1ef3-192">ここでは、for each ループも使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-192">A For Each loop can be used here as well.</span></span> <span data-ttu-id="d1ef3-193">このループでは、ワークフローは現在のデータ アイテムを取得し、[データの送信] アクションを使用して、ログ分析にデータを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-193">In this loop, the workflow takes the current item of data and uses the Send Data action to write the data to Log Analytics.</span></span>
  <p>
<span data-ttu-id="d1ef3-194">•使用可能なコンテンツは複数ページにわたる可能性があるので、NextPageUri が NULL ではないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-194">• Since there may be multiple pages of available content, a condition checks if the NextPageUri is not NULL.</span></span> <span data-ttu-id="d1ef3-195">NULL か空白の場合、NextPage は0に設定され、Until ループを終了します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-195">If it is NULL, or empty, NextPage is set to 0, which ends the Until loop.</span></span> <span data-ttu-id="d1ef3-196">URL が含まれている場合は、その URL に AvaibleUri 変数が更新されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-196">If it contains a URL, the AvaibleUri variable is updated to that URL.</span></span> <span data-ttu-id="d1ef3-197">この方法では、Until ループの次の実行時には、開始 URL ではなく、次に利用可能な URL が使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-197">This way, the next run of the Until loop uses a next available URL, and not the starting URL.</span></span>

  </details>

> [!TIP]
> <span data-ttu-id="d1ef3-198">代わりに、*Azure 関数* を使用して、これらのログを取り込むことができます。その場合は、必要に応じて、展開方法についての詳細な説明は、[こちら](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data) または [こちら](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp) にあります。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-198">You may choose to use an *Azure Function* to ingest those logs, instead, and if you do, the information on how to deploy is [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data), or [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), depending on your preference.</span></span>

<span data-ttu-id="d1ef3-199">コネクタ (上記のいずれかのオプション) を実行すると、Azure Sentinel ワークスペースに O365API_CL と呼ばれるカスタム テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-199">With the connector (whichever of the options above you chose) running, you should see a custom table called O365API_CL in the Azure Sentinel workspace.</span></span> <span data-ttu-id="d1ef3-200">Teams ログが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-200">This will house your Teams logs.</span></span>

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a><span data-ttu-id="d1ef3-201">手順 3: Sentinel を使用して Microsoft Teams を監視する</span><span class="sxs-lookup"><span data-stu-id="d1ef3-201">Step 3: Use Sentinel to monitor Microsoft Teams</span></span>

<span data-ttu-id="d1ef3-202">ID は、Microsoft Teams に関して言えば、監視すべき重要な攻撃ベクトルです。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-202">Identity is an important attack vector to monitor when it comes to Microsoft Teams.</span></span> <span data-ttu-id="d1ef3-203">Azure Active Directory (Azure AD) は、Teams を含む、Microsoft 365 のディレクトリの土台であり、Azure AD 認証ログの脅威の収集および検索を行うことにより、ID の不審な動作をキャプチャするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-203">Because Azure Active Directory (Azure AD) is the underpinning of Microsoft 365's directory, including Teams, collecting and hunting for threats in Azure AD logs around authentication will be useful in capturing suspicious behaviour around identity.</span></span> <span data-ttu-id="d1ef3-204">内蔵コネクタを使用して Azure AD データを Azure Sentinel に引き込み、これらの [検出](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) および [検索](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) クエリを使用して、問題を探すことができます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-204">You can use the built-in connector to pull Azure AD data into Azure Sentinel, and use these [detection](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) and [hunting](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) queries to look for problems.</span></span>

<span data-ttu-id="d1ef3-205">Microsoft Teams に固有の攻撃、データへの脅威については、たとえば、Azure Sentinel にも、それらを監視して追い詰める手段があります。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-205">Regarding attacks specific to Microsoft Teams, threats to data, for example, Azure Sentinel also has means to monitor for them and hunt them down.</span></span>

### <a name="create-a-parser-for-your-data"></a><span data-ttu-id="d1ef3-206">データのパーサを作成する</span><span class="sxs-lookup"><span data-stu-id="d1ef3-206">Create a parser for your data</span></span>

<span data-ttu-id="d1ef3-207">収集されたデータの集合を理解するために最初に行う必要がある作業は、それを解析して意味づけすることです。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-207">The first thing to do in order to make sense of the large set of collected data is to give it meaning by parsing it.</span></span> <span data-ttu-id="d1ef3-208">これは、データを簡単に使用できるようにする Kusto Query 言語 (KQL) 関数で実行されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-208">This is done with a Kusto Query Language (KQL) Function that makes the data easier to use.</span></span>

> [!NOTE]
> <span data-ttu-id="d1ef3-209">KQL 関数は、「関数」と呼ばれるデータ型で保存された KQL クエリです。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-209">KQL functions are KQL queries saved as a data-type called 'function'.</span></span> <span data-ttu-id="d1ef3-210">KQL 関数には、Sentinel のクエリ ボックスに入力できるエイリアスがあるので、クエリをすばやく再実行できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-210">KQL functions have an alias that can be entered into the query box in Sentinel to quickly run the query again.</span></span> <span data-ttu-id="d1ef3-211">KQL 関数の詳細とパーサ関数の作成方法の詳細については、[この技術コミュニティの記事](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-211">For more about KQL functions and how to build a parser function, read [this Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>
 
 <span data-ttu-id="d1ef3-212">以下のパーサは、*Teams* に関連する Office 365 Management API フィールドの一部を選択することを目的とした、カスタマイズ可能な例です。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-212">The parser below is a customizable example aimed at selecting a subset of the Office 365 Management API fields relevant to *Teams*.</span></span> <span data-ttu-id="d1ef3-213">また、パーサ [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) も提案されていますが、以下のパーサを変更して、さまざまなニーズや必要に合わせて変更できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-213">There is also a suggested parser [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), but the parser below can be modified to fit different needs and preferences.</span></span>

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
 <span data-ttu-id="d1ef3-214">このパーサを KQL 関数として、Teams データのエイリアスとして保存します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-214">Save the parser as a KQL function, with an alias of TeamsData.</span></span> <span data-ttu-id="d1ef3-215">これは、後に続くクエリに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-215">It will be used for the queries to follow.</span></span> <span data-ttu-id="d1ef3-216">KQL 関数をパーサとして構成および使用する方法の詳細については、こちらの [技術コミュニティの記事](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-216">Details on configuring and using a KQL function as a parser can be found in this [Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>

## <a name="helfpul-hunting-kql-queries"></a><span data-ttu-id="d1ef3-217">KQL クエリの役に立つ検索</span><span class="sxs-lookup"><span data-stu-id="d1ef3-217">Helfpul hunting KQL queries</span></span>

<span data-ttu-id="d1ef3-218">これらのクエリを使用すると、Teams データとTeams 環境を理解できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-218">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="d1ef3-219">疑わしいアクティビティを認識するには、最初の手順として環境がどのように見え、どのように振る舞うべきかを理解することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-219">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="d1ef3-220">そこから、スレッド ハンティングに進出することができます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-220">From there, you can branch out into threat hunting.</span></span>

#### <a name="federated-external-users-query"></a><span data-ttu-id="d1ef3-221">フェデレーション外部ユーザー クエリ</span><span class="sxs-lookup"><span data-stu-id="d1ef3-221">Federated external users query</span></span>

<span data-ttu-id="d1ef3-222">フェデレーション外部ユーザーを有する Teams サイト リストを取得します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-222">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="d1ef3-223">これらのユーザーは、組織によって *所有されていない* ドメイン名または UPN サフィックスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-223">These users will have a domain name / UPN suffix that *isn't* owned by your organization.</span></span> <span data-ttu-id="d1ef3-224">この例のクエリでは、組織が contoso.com. を所有しています。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-224">In this example query, the organization owns contoso.com.</span></span>

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
> <span data-ttu-id="d1ef3-225">Teams における外部アクセスおよびゲスト アクセスの種類の詳細については、[この記事](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations) または [Teams セキュリティ ガイド](https://docs.microsoft.com/microsoftteams/teams-security-guide) の *参加者の種類* セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-225">To learn more about External and Guest access types in Teams see [this article](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations), or the *Participant Types* section in the [Teams Security Guide](https://docs.microsoft.com/microsoftteams/teams-security-guide).</span></span>

#### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="d1ef3-226">最近参加した、または役割を変更したユーザー</span><span class="sxs-lookup"><span data-stu-id="d1ef3-226">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="d1ef3-227">特定のユーザーに問い合わせて、過去7日間または1週間以内に、Teams チャネルに追加されたかどうかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-227">Query a specific user to check if they were added to a Teams channel in the last 7 days, or within a week:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

<span data-ttu-id="d1ef3-228">過去7日間にチームのユーザーの役割が変更されました。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-228">Was a user's role changed for a Team in the last 7 days:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="d1ef3-229">不明または新しい組織からの外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="d1ef3-229">External users from unknown or new organizations</span></span>

<span data-ttu-id="d1ef3-230">Teams では、環境やチャネルに外部ユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-230">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="d1ef3-231">多くの場合、組織では、キーとなるパートナーシップの数が限られています。また、これらのパートナーの中からユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-231">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="d1ef3-232">このKQLは、チームに追加された外部ユーザーが、以前に表示または追加されていない組織から来ているかどうかを見ています。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-232">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

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

#### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="d1ef3-233">追加され、後に削除された外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="d1ef3-233">External users who were added and then removed</span></span>

<span data-ttu-id="d1ef3-234">ある程度の既存アクセス権を持つ攻撃者は、Teams 新しい外部アカウントを追加して、データにアクセスしたり、データを流出させたりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-234">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="d1ef3-235">また、アクセスしたことを隠すために、当該ユーザーをすぐに削除してしまう可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-235">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="d1ef3-236">このクエリは、Teams に追加された外部アカウントを検索し、疑わしい動作を特定するために迅速に削除します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-236">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

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

#### <a name="new-bot-or-application-added"></a><span data-ttu-id="d1ef3-237">新しい bot またはアプリケーションが追加されました</span><span class="sxs-lookup"><span data-stu-id="d1ef3-237">New bot or application added</span></span>

<span data-ttu-id="d1ef3-238">Teams では、機能セットを拡張するためのアプリや bot をチームに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-238">Teams has the ability to include apps or bots in a Team to extend the feature set.</span></span> <span data-ttu-id="d1ef3-239">これには、カスタム アプリと bot が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-239">This includes custom apps and bots.</span></span> <span data-ttu-id="d1ef3-240">場合によっては、アプリまたは bot を使用して、ユーザー アカウントや、アクセス ファイル、その他のデータを必要とせずに、Teams の永続性を確立できます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-240">In some cases, an app or bot could be used to establish persistence in Teams without needing a user account, as well as access files and other data.</span></span> <span data-ttu-id="d1ef3-241">このクエリは、チームに新たに追加されたアプリや bot を検索します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-241">This query hunts for apps or bots that are new to Teams.</span></span>

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

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="d1ef3-242">多数のチームの所有者であるユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="d1ef3-242">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="d1ef3-243">通常、ユーザーは特定のトピックについて少数のチームを作成して所有していますが、権限を高めようとする攻撃者は、多くの異なるチームの所有者権限を割り当てようとする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-243">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse Teams, when, usually, users create and own a small number of Teams around specific topics.</span></span> <span data-ttu-id="d1ef3-244">この KQL クエリは不審な動作を検索します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-244">This KQL query looks for suspicious behaviour.</span></span>

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

#### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="d1ef3-245">1人のユーザーによる多くのチームの削除</span><span class="sxs-lookup"><span data-stu-id="d1ef3-245">Many Team deletions by a single user</span></span>

<span data-ttu-id="d1ef3-246">攻撃者は、複数のチームを削除することで、プロジェクトやデータを混乱させたり、危険にさらしたりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-246">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="d1ef3-247">通常、チームは個人の所有者によって削除されているため、多くのチームを中心に削除されている場合は、問題の徴候になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-247">Because teams are generally deleted by individual Owners, a central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="d1ef3-248">この KQL は、複数のチームを削除するユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-248">This KQL looks for single users who delete multiple teams.</span></span>

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

#### <a name="expanding-your-thread-hunting-opportunities"></a><span data-ttu-id="d1ef3-249">スレッド ハンティングの機会を広げる</span><span class="sxs-lookup"><span data-stu-id="d1ef3-249">Expanding your thread hunting opportunities</span></span>

<span data-ttu-id="d1ef3-250">Azure Active Directory (Azure AD) などのリソースや他の Office 365 ワークロードからのクエリを Teams のクエリと組み合わせることで、ハンティングを拡大することができます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-250">You can expand your hunting by combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads with your Teams queries.</span></span> <span data-ttu-id="d1ef3-251">一例として、Azure AD SigninLogs の疑わしいパターンの検出を組み合わせて、チーム オーナーを探している間にその情報を使用しています。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-251">One example is combining detection of suspicious patterns in Azure AD SigninLogs, and using that information while hunting for Team Owners.</span></span>

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

<span data-ttu-id="d1ef3-252">また、Teams ベースのサインインのみのフィルターを追加することで、Teams 固有の SigninLogs の検出を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-252">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based sign-ins by using:</span></span>

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

<span data-ttu-id="d1ef3-253">`where AppDisplayName starts with "Microsoft Teams"` をさらに使用する方法について、以下の KQL の例では、1つの IP アドレスからのログオンに成功し、異なる IP アドレスからは失敗していますが、Teams のサインインにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-253">To help explain using `where AppDisplayName starts with "Microsoft Teams"` further, the KQL below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped only to Teams sign-ins:</span></span>

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

## <a name="important-information-and-updates"></a><span data-ttu-id="d1ef3-254">重要な情報と更新プログラム</span><span class="sxs-lookup"><span data-stu-id="d1ef3-254">Important information and updates</span></span>

<span data-ttu-id="d1ef3-255">**Pete Bryan、Nicholas DiCola、および Matthew Lowe によるコンテンツの共同作業に感謝します。**</span><span class="sxs-lookup"><span data-stu-id="d1ef3-255">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="d1ef3-256">Pete Bryan や共同作業を行っているユーザーは、チームの検出や検索のクエリを引き続き開発します。そのため、この [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) リポジトリで更新プログラムをチェックできます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-256">Pete Bryan and the people he collaborates with will continue to develop detection and hunting queries for Teams, so keep in touch with this [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>  <span data-ttu-id="d1ef3-257">この記事で使用している [パーサー](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) および [ロジック アプリ](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) の更新プログラムを監視します。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-257">Monitor for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span> <span data-ttu-id="d1ef3-258">[Azure Sentinel コミュニティ](https://github.com/Azure/Azure-Sentinel/wiki) に参加して投稿することもできます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-258">You can also join and contribute to the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="d1ef3-259">ご協力ありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-259">Thank you!</span></span> <span data-ttu-id="d1ef3-260">良い検索を。</span><span class="sxs-lookup"><span data-stu-id="d1ef3-260">Happy hunting.</span></span>

[<span data-ttu-id="d1ef3-261">Azure AD でアプリケーションを登録する</span><span class="sxs-lookup"><span data-stu-id="d1ef3-261">Registering your application in Azure AD</span></span>](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="d1ef3-262">監査ログ検索を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="d1ef3-262">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[<span data-ttu-id="d1ef3-263">Azure Sentinel とは</span><span class="sxs-lookup"><span data-stu-id="d1ef3-263">What is Azure Sentinel</span></span>](https://docs.microsoft.com/azure/sentinel/overview)