---
title: Firstline Workers 用に規模に応じて Microsoft Teams をプロビジョニングする
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: keschm
description: Firstline Worker 用に Microsoft Teams を展開またはプロビジョニングするスクリプトの使用する際のガイダンス。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: caecd0d97e760470604fa164e6356a59699e57ad
ms.sourcegitcommit: bc1d2e0478a429f981b53765e6194443b32ae35c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "43122921"
---
# <a name="how-to-provision-teams-at-scale-for-firstline-workers"></a><span data-ttu-id="ad801-103">現場担当者向けにTeams 大規模にプロビジョニングする方法</span><span class="sxs-lookup"><span data-stu-id="ad801-103">How to provision Teams at scale for Firstline Workers</span></span>

<span data-ttu-id="ad801-104">Microsoft Teams に多数のユーザーをすばやく登録し、作業を効率化する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="ad801-104">Do you need to rapidly onboard a large number of users to Microsoft Teams and configure a streamlined experience for them?</span></span> <span data-ttu-id="ad801-105">次の手順を実行して、ID のプロビジョニング、Teams のプロビジョニング、関連するすべてのポリシーの割り当てをすばやく行い、エンド ユーザー エクスペリエンスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="ad801-105">You can quickly provision identities, provision teams, and assign all relevant policies to control the end user experience by walking through the following instructions.</span></span>

<span data-ttu-id="ad801-106">このチュートリアルでは、以下の操作を実行する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ad801-106">In this walkthrough, you'll learn how to:</span></span>

- <span data-ttu-id="ad801-107">多数のユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad801-107">Create a large number of users.</span></span>
- <span data-ttu-id="ad801-108">多数のチームを作成し、適切なチャネルを設定します。</span><span class="sxs-lookup"><span data-stu-id="ad801-108">Create a large number of teams and set up the appropriate channels.</span></span>
- <span data-ttu-id="ad801-109">規模に応じてライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ad801-109">Assign licensing at scale.</span></span>
- <span data-ttu-id="ad801-110">適切な Teams メッセージング ポリシー、アプリ セットアップ ポリシー、アプリ アクセス許可ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad801-110">Create appropriate Teams Messaging Policies, App Setup Policies, and App Permission Policies.</span></span>
- <span data-ttu-id="ad801-111">ユーザーにこれらのポリシーを規模に応じて適用します。</span><span class="sxs-lookup"><span data-stu-id="ad801-111">Apply those policies to users at scale.</span></span>
- <span data-ttu-id="ad801-112">指定されたチームに多数のユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ad801-112">Assign a large number of users into a designated team.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ad801-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="ad801-113">Prerequisites</span></span>

<span data-ttu-id="ad801-114">[この場所](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true)から資産をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ad801-114">Download the assets from [this location](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad801-115">上記のリンクに掲載されているスクリプトは、Microsoft が現状のまま提供しているもので、個別のニーズに合わせて変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad801-115">The scripts in the link provided above are provided as-is by Microsoft, and must be modified for your individual needs.</span></span>

## <a name="technical-requirements"></a><span data-ttu-id="ad801-116">技術的要件</span><span class="sxs-lookup"><span data-stu-id="ad801-116">Technical requirements</span></span>

- <span data-ttu-id="ad801-117">テナントには、Microsoft Teams を含む適切な数の使用可能なライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ad801-117">Your tenant must have the appropriate number of licenses available that include Microsoft Teams.</span></span> <span data-ttu-id="ad801-118">これらのライセンスをまだお持ちでない場合は、以下の手順に従って、[Office 365 E1 無料試用版](e1-trial-license.md)を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="ad801-118">If you do not already have these licenses, follow the instructions here to activate the [Office 365 E1 Free Trial](e1-trial-license.md).</span></span>
- <span data-ttu-id="ad801-119">これらの手順を実行するには、Azure AD のグローバル管理者またはユーザー管理者の役割で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad801-119">The user taking these steps must do so in the role of Global Admin or User Admin in Azure AD.</span></span>
- <span data-ttu-id="ad801-120">ユーザーには、ローカル コンピューターにソフトウェアをインストールして構成する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="ad801-120">User must have the rights to install and configure software on their local machine.</span></span>

## <a name="step-by-step-process-overview"></a><span data-ttu-id="ad801-121">手順を追ったプロセスの概要</span><span class="sxs-lookup"><span data-stu-id="ad801-121">Step-by-step process overview</span></span>

1. <span data-ttu-id="ad801-122">**環境を設定する**</span><span class="sxs-lookup"><span data-stu-id="ad801-122">**Setup Your Environment**</span></span>
    1. <span data-ttu-id="ad801-123">サンプルの PowerShell スクリプトとドキュメントが含まれている ZIP ファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="ad801-123">Download the ZIP file containing the sample PowerShell scripts and documentation</span></span>
    1. <span data-ttu-id="ad801-124">資格情報を設定する</span><span class="sxs-lookup"><span data-stu-id="ad801-124">Setup credentials</span></span>
    1. <span data-ttu-id="ad801-125">ローカル環境を構成する</span><span class="sxs-lookup"><span data-stu-id="ad801-125">Configure local environment</span></span>
    1. <span data-ttu-id="ad801-126">PowerShell のモジュールと環境変数を構成する</span><span class="sxs-lookup"><span data-stu-id="ad801-126">Configure PowerShell Modules and Environmental Variables</span></span>
    1. <span data-ttu-id="ad801-127">アプリ登録を作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-127">Create App Registration</span></span>
1. <span data-ttu-id="ad801-128">**チームを作成して設定する**</span><span class="sxs-lookup"><span data-stu-id="ad801-128">**Create and Setup Teams**</span></span>
    1. <span data-ttu-id="ad801-129">チームを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-129">Create Teams</span></span>
    1. <span data-ttu-id="ad801-130">チームのチャネルを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-130">Create Channels for Teams</span></span>
1. <span data-ttu-id="ad801-131">**チームのポリシーを作成する**</span><span class="sxs-lookup"><span data-stu-id="ad801-131">**Create Teams Policies**</span></span>
    1. <span data-ttu-id="ad801-132">チームのメッセージング ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-132">Create Teams Messaging Policies</span></span>
    1. <span data-ttu-id="ad801-133">Teams アプリのセットアップ ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-133">Create Teams App Setup Policies</span></span>
    1. <span data-ttu-id="ad801-134">Teams アプリのアクセス許可ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-134">Create Teams App Permission Policies</span></span>
1. <span data-ttu-id="ad801-135">**ユーザーを作成し設定する**</span><span class="sxs-lookup"><span data-stu-id="ad801-135">**Create and Setup Users**</span></span>
    1. <span data-ttu-id="ad801-136">ユーザーとセキュリティ グループを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-136">Create users and security groups</span></span>
    1. <span data-ttu-id="ad801-137">グループベースのライセンスを通じてユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ad801-137">Assign licensing to users via group-based licensing</span></span>
1. <span data-ttu-id="ad801-138">**ユーザーとポリシーを割り当てる**</span><span class="sxs-lookup"><span data-stu-id="ad801-138">**Assign Users and Policies**</span></span>
    1. <span data-ttu-id="ad801-139">チームにユーザーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ad801-139">Assign users to Teams</span></span>
    1. <span data-ttu-id="ad801-140">ユーザーとグループにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ad801-140">Assign policies to User and Groups</span></span>
1. <span data-ttu-id="ad801-141">**テストと検証**</span><span class="sxs-lookup"><span data-stu-id="ad801-141">**Test and Validate**</span></span>
    1. <span data-ttu-id="ad801-142">エラーをチェックする</span><span class="sxs-lookup"><span data-stu-id="ad801-142">Check for errors</span></span>
    1. <span data-ttu-id="ad801-143">テスト ユーザーで Teams にログインする</span><span class="sxs-lookup"><span data-stu-id="ad801-143">Login to Teams with a test user</span></span>

## <a name="set-up-your-environment"></a><span data-ttu-id="ad801-144">環境を設定する</span><span class="sxs-lookup"><span data-stu-id="ad801-144">Set up your environment</span></span>

<span data-ttu-id="ad801-145">次の手順で、環境を設定できます。</span><span class="sxs-lookup"><span data-stu-id="ad801-145">The following steps will allow you to set up your environment:</span></span>

### <a name="download-zip-file-containing-sample-powershell-scripts"></a><span data-ttu-id="ad801-146">サンプル PowerShell スクリプトを含む .zip ファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="ad801-146">Download .zip file containing sample PowerShell scripts</span></span>

<span data-ttu-id="ad801-147">続行する前に、[この場所](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true)からスクリプトをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad801-147">Before you can proceed, you'll need to download the scripts at [this location](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true).</span></span>

### <a name="setup-credentials"></a><span data-ttu-id="ad801-148">資格情報を設定する</span><span class="sxs-lookup"><span data-stu-id="ad801-148">Setup Credentials</span></span>

<span data-ttu-id="ad801-149">このドキュメントとサンプル スクリプトでは、簡単にするために、ユーザーの資格情報を含む参照ファイルを作成することを選択しました。</span><span class="sxs-lookup"><span data-stu-id="ad801-149">In this document and the sample scripts we've chosen to create a reference file that contains your credentials in order to make things easier.</span></span> <span data-ttu-id="ad801-150">この手法により、ローカル ストアで資格情報を維持しながら、さまざまなサービス エンドポイントすべてに対して認証を行う必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="ad801-150">This technique removes the need for you to authenticate to all the various service endpoints while maintaining the credentials in a local store.</span></span> <span data-ttu-id="ad801-151">後続のスクリプトを実行するには、ユーザーと環境に固有の資格情報を使用して参照ファイルを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad801-151">In order to run the subsequent scripts, you'll need to update that reference file with the credentials that are unique to you and your environment.</span></span> <span data-ttu-id="ad801-152">後続の各スクリプト内から、適切な資格情報が **GetCreds** と呼ばれるヘルパー関数で読み取られ、それらの認証情報はさまざまなサービスへの接続に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ad801-152">From within each subsequent script, the appropriate credentials are read with the helper function  we've called **GetCreds**, and those credentials are used to connect to the various services.</span></span>

<span data-ttu-id="ad801-153">異なるサービスが異なる資格情報を必要とすることは珍しいことではありません。</span><span class="sxs-lookup"><span data-stu-id="ad801-153">It's not uncommon for different services to require different credentials.</span></span> <span data-ttu-id="ad801-154">たとえば、Microsoft Teams、AzureAD、MSonline に異なる資格情報がある場合、SetCred を実行して、各資格情報ファイルを独自の意味のある名前を付けて保存できます。</span><span class="sxs-lookup"><span data-stu-id="ad801-154">For example you might have different credentials for MicrosoftTeams, AzureAD, and MSonline, in which case you can run SetCred saving each credential file with its own meaningful name.</span></span>

<span data-ttu-id="ad801-155">例: SetCreds msol-cred.xml SetCreds azuread-cred.xml SetCreds teams-cred.xml</span><span class="sxs-lookup"><span data-stu-id="ad801-155">Examples: SetCreds msol-cred.xml SetCreds azuread-cred.xml SetCreds teams-cred.xml</span></span>

> [!NOTE]
> <span data-ttu-id="ad801-156">資格情報に使用されるアカウントでは、MFA を要求することはできません。</span><span class="sxs-lookup"><span data-stu-id="ad801-156">The account used for the credentials cannot require MFA.</span></span>

<span data-ttu-id="ad801-157">次に、さまざまなスクリプトが保存された資格情報を使用して認証する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="ad801-157">Here is an example of how the various scripts then use the saved credentials to authenticate:</span></span>

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = GetCreds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

<span data-ttu-id="ad801-158">資格情報を設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad801-158">In order to set your credentials, complete the following:</span></span>

1. <span data-ttu-id="ad801-159">.zip ファイル資産に含まれている **SetCreds.ps1** を見つけます。</span><span class="sxs-lookup"><span data-stu-id="ad801-159">Find the **SetCreds.ps1** in the .zip file assets.</span></span>
1. <span data-ttu-id="ad801-160">PowerShell から **SetCreds. ps1** スクリプトを実行して、資格情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="ad801-160">From PowerShell run the **SetCreds.ps1** script to save your credentials.</span></span>
    1. <span data-ttu-id="ad801-161">"操作 "Export-Clixml" の実行中です..." をいうメッセージが表示されます。承認するには 'Y' を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad801-161">You'll be prompted with "Performing the operation "Export-Clixml"..." and you'll need to enter 'Y' to approve.</span></span>

### <a name="configure-the-local-environment"></a><span data-ttu-id="ad801-162">ローカル環境を構成する</span><span class="sxs-lookup"><span data-stu-id="ad801-162">Configure the local environment</span></span>

1. <span data-ttu-id="ad801-163">.zip ファイル資産に含まれている **SetConfig.ps1** を見つけます。</span><span class="sxs-lookup"><span data-stu-id="ad801-163">Find the **SetConfig.ps1** in the .zip file assets.</span></span>
1. <span data-ttu-id="ad801-164">PowerShell から次のコマンドを実行し、括弧で囲まれたエントリを特定の情報に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ad801-164">From PowerShell run the following command, replacing the bracketed entries with your specific information.</span></span>
    1. <span data-ttu-id="ad801-165">**SetConfig.ps1** -tenantName [your tenant name] -rootPath "[full path to the root of the git repo]"</span><span class="sxs-lookup"><span data-stu-id="ad801-165">**SetConfig.ps1** -tenantName [your tenant name] -rootPath "[full path to the root of the git repo]"</span></span>

<span data-ttu-id="ad801-166">例: `.\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"`</span><span class="sxs-lookup"><span data-stu-id="ad801-166">For example: `.\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"`</span></span>

### <a name="configure-powershell-modules-and-environmental-variables"></a><span data-ttu-id="ad801-167">PowerShell のモジュールと環境変数を構成する</span><span class="sxs-lookup"><span data-stu-id="ad801-167">Configure PowerShell modules and environmental variables</span></span>

<span data-ttu-id="ad801-168">先に進む前に、Azure AD、MSAL、MSCloudUtils、MicrosoftTeams などのいくつかの PowerShell モジュールをインストールして接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad801-168">Before you go further, you'll need to install and connect to several PowerShell modules, including Azure AD, MSAL, MSCloudUtils, and MicrosoftTeams.</span></span>

1. <span data-ttu-id="ad801-169">.zip ファイル資産に含まれる **ConfigurePowerShellModules.ps1** を見つけます。</span><span class="sxs-lookup"><span data-stu-id="ad801-169">Find the **ConfigurePowerShellModules.ps1** in the .zip file assets.</span></span>
1. <span data-ttu-id="ad801-170">変数を使用して、次の環境変数を編集して置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ad801-170">Edit and replace the following environmental variables with your variables:</span></span>
1. <span data-ttu-id="ad801-171">PowerShell から、**ConfigurePowerShellModules.ps1** スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad801-171">From PowerShell, run the **ConfigurePowerShellModules.ps1** script.</span></span>

## <a name="create-and-set-up-teams"></a><span data-ttu-id="ad801-172">チームを作成して設定する</span><span class="sxs-lookup"><span data-stu-id="ad801-172">Create and set up Teams</span></span>

<span data-ttu-id="ad801-173">Firstline Worker と通信して共同作業を行うには、最初に一連のチームを確立し、これらのチームに標準チャネルを追加する必要があります。これについては、次に説明します。</span><span class="sxs-lookup"><span data-stu-id="ad801-173">In order to communicate and collaborate with your Firstline Workers, you will first need to establish a series of Teams and add standard Channels to those teams, which we'll walk through next.</span></span>

### <a name="create-teams"></a><span data-ttu-id="ad801-174">チームを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-174">Create teams</span></span>

<span data-ttu-id="ad801-175">チームは、組織内のユーザー、コンテンツ、ツールの集合です。</span><span class="sxs-lookup"><span data-stu-id="ad801-175">Teams are a collection of people, content, and tools within your organization.</span></span> <span data-ttu-id="ad801-176">ほとんどの Firstline Worker 中心の組織では、チームを実際の場所に固定するのがベスト プラクティスです。</span><span class="sxs-lookup"><span data-stu-id="ad801-176">For most Firstline Worker-centric organizations, it is best practice to anchor a Team around a physical location.</span></span> <span data-ttu-id="ad801-177">たとえば、次の各チームがあります。</span><span class="sxs-lookup"><span data-stu-id="ad801-177">For example, a Team for each of the following:</span></span>

- <span data-ttu-id="ad801-178">ストア</span><span class="sxs-lookup"><span data-stu-id="ad801-178">Store</span></span>
- <span data-ttu-id="ad801-179">配布センター</span><span class="sxs-lookup"><span data-stu-id="ad801-179">Distribution Center</span></span>
- <span data-ttu-id="ad801-180">製造工場</span><span class="sxs-lookup"><span data-stu-id="ad801-180">Manufacturing Plant</span></span>
- <span data-ttu-id="ad801-181">病院</span><span class="sxs-lookup"><span data-stu-id="ad801-181">Hospital</span></span>
- <span data-ttu-id="ad801-182">食品店</span><span class="sxs-lookup"><span data-stu-id="ad801-182">Grocery Store</span></span>

<span data-ttu-id="ad801-183">*ベスト プラクティス ディスカッション*: チームを設計するときは、[Teams の制限と仕様](limits-specifications-teams.md)に留意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ad801-183">*Best Practice Discussion*: When designing your teams, it's important to keep in mind [Teams limits and specifications](limits-specifications-teams.md).</span></span> <span data-ttu-id="ad801-184">小規模な組織では、組織全体のチームを使用してコミュニケーションを合理化し、物理的な場所の構造を補完できます。</span><span class="sxs-lookup"><span data-stu-id="ad801-184">For smaller organizations, an org-wide team can be used to streamline communication and complement a physical location structure.</span></span> <span data-ttu-id="ad801-185">構造化された物理的な場所のチームの命名規則により、他のユーザーは、複数チームに対して同時にクロス投稿を使って、社内コミュニケーションを容易に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ad801-185">For others, a structured physical location Team naming convention helps assist Corporate Communications with Cross Posting to multiple teams simultaneously with ease.</span></span> <span data-ttu-id="ad801-186">たとえば、名前に US が含まれるすべてのチームを検索してクロス投稿し、米国のすべての場所を対象にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad801-186">For example, you can search and cross-post to all Teams with US in the name to target all US locations.</span></span> <span data-ttu-id="ad801-187">クロス投稿の詳細については、[こちら](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ad801-187">More information on cross-posting can be found [here](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295).</span></span>

#### <a name="steps-to-create-teams"></a><span data-ttu-id="ad801-188">チームを作成する手順</span><span class="sxs-lookup"><span data-stu-id="ad801-188">Steps to create teams</span></span>

1. <span data-ttu-id="ad801-189">資産に含まれる **Teams Information.csv** ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="ad801-189">Find the **Teams Information.csv** file in the assets.</span></span>
1. <span data-ttu-id="ad801-190">組織固有の情報を使用して、**Teams Information.csv** ファイル内の情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="ad801-190">Update the information in the **Teams Information.csv** file with your organization's specific information.</span></span> <span data-ttu-id="ad801-191">上記のベスト プラクティスに留意してください。</span><span class="sxs-lookup"><span data-stu-id="ad801-191">Keep in mind our best practices above.</span></span>
1. <span data-ttu-id="ad801-192">**CreateTeams. ps1** スクリプトを見つけます。</span><span class="sxs-lookup"><span data-stu-id="ad801-192">Find the **CreateTeams.ps1** script.</span></span>
1. <span data-ttu-id="ad801-193">PowerShell から **CreateTeams.ps1** スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad801-193">From PowerShell, run the **CreateTeams.ps1** script.</span></span>

### <a name="create-channels-for-teams"></a><span data-ttu-id="ad801-194">チームのチャネルを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-194">Create channels for teams</span></span>

<span data-ttu-id="ad801-195">チャネルは、特定のトピック、プロジェクト、分野などごとに会話を整理するチーム内の専用セクションです。</span><span class="sxs-lookup"><span data-stu-id="ad801-195">Channels are dedicated sections within a team to keep conversations organized by specific topic, project, discipline, and more.</span></span> <span data-ttu-id="ad801-196">すべてのチームは自動的に全般チャネルを取得しますが、そこからビジネス ニーズに応じて構造をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="ad801-196">Every Team automatically gets a General channel, but from there you can customize your structure according to the needs of your business.</span></span> <span data-ttu-id="ad801-197">たとえば、チャネル構造には以下が追加されます。</span><span class="sxs-lookup"><span data-stu-id="ad801-197">For example, your additional channel structure could include:</span></span>

- <span data-ttu-id="ad801-198">**製造** - 安全、ライン 1、ライン 2、社内コミュニケーション、トレーニング</span><span class="sxs-lookup"><span data-stu-id="ad801-198">**Manufacturing** - Safety, Line 1, Line 2, Corporate Communications, Training</span></span>
- <span data-ttu-id="ad801-199">**食料品** - パン屋、農産物、肉、社内コミュニケーション、トレーニング</span><span class="sxs-lookup"><span data-stu-id="ad801-199">**Grocery** - Bakery, Produce, Meat, Corporate Communications, Training</span></span>
- <span data-ttu-id="ad801-200">**医療** - 看護師、医師、重症管理室 1、重症管理室 2</span><span class="sxs-lookup"><span data-stu-id="ad801-200">**Healthcare** - Nurses, Doctors, Critical Care Unit 1, Critical Care Unit 2</span></span>
- <span data-ttu-id="ad801-201">**サービス業** - フロント デスク、メンテナンス、ハウスキーピング、ベルボーイ、社内コミュニケーション、トレーニング</span><span class="sxs-lookup"><span data-stu-id="ad801-201">**Hospitality** - Front Desk, Maintenance, Housekeeping, Valet and Baggage, Corporate Communications, Training</span></span>
- <span data-ttu-id="ad801-202">**小売店** - 店頭、バックヤード、社内コミュニケーション、トレーニング</span><span class="sxs-lookup"><span data-stu-id="ad801-202">**Retail** - Front of Store, Back of Store, Corporate Communications, Training</span></span>

> [!NOTE]
> <span data-ttu-id="ad801-203">チャネルをセキュリティの境界と見なすべきではありません。</span><span class="sxs-lookup"><span data-stu-id="ad801-203">Channels should not be thought of as a security boundary.</span></span> <span data-ttu-id="ad801-204">これらは、共同作業を行うために、作業者を整理する手段です。</span><span class="sxs-lookup"><span data-stu-id="ad801-204">They are a means of organizing your workers for the purposes of collaboration.</span></span>

<span data-ttu-id="ad801-205">*ベスト プラクティス ディスカッション*: チャネル構造を設計するとき、特に多数のユーザーを登録する必要がある場合は、シンプルなものにすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="ad801-205">*Best Practice Discussion*: When designing your channel structure, it's important to keep things simple, especially when you're looking to onboard a lot of users.</span></span> <span data-ttu-id="ad801-206">トレーニングの必要性を最小限に抑えるために、あらゆる状況、役割、またはトピックのチャネルを作成しようとする衝動を抑えてください。</span><span class="sxs-lookup"><span data-stu-id="ad801-206">Resist the urge to create channels for every situation, role, or topic in order to minimize the need for training.</span></span> <span data-ttu-id="ad801-207">最大 3 ～ 5 チャネルから開始してください。</span><span class="sxs-lookup"><span data-stu-id="ad801-207">Pick 3-5 channels at most to get started.</span></span> <span data-ttu-id="ad801-208">必要に応じて、追加のチャネルを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="ad801-208">Additional channels can easily be created as the need arises.</span></span> <span data-ttu-id="ad801-209">実際には、全般チャネルだけを使用しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="ad801-209">In fact, it's okay to just use the General channel alone for now!</span></span>

#### <a name="steps-to-create-channels-for-teams"></a><span data-ttu-id="ad801-210">チームのチャネルを作成する手順</span><span class="sxs-lookup"><span data-stu-id="ad801-210">Steps to Create Channels for Teams</span></span>

1. <span data-ttu-id="ad801-211">.zip ファイル資産に含まれる **TeamsChannels.csv** ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="ad801-211">Find the **TeamsChannels.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="ad801-212">組織固有の情報を使用して、**Teams Information.csv** ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="ad801-212">Update the **TeamsChannels.csv** file with your organization's specific information.</span></span> <span data-ttu-id="ad801-213">上記のベスト プラクティスに留意してください。</span><span class="sxs-lookup"><span data-stu-id="ad801-213">Keep in mind our best practices above.</span></span>
1. <span data-ttu-id="ad801-214">.zip ファイル資産に含まれる **CreateTeamsChannels.ps1** スクリプトを見つけます。</span><span class="sxs-lookup"><span data-stu-id="ad801-214">Find the **CreateTeamsChannels.ps1** script in the .zip file assets.</span></span>
1. <span data-ttu-id="ad801-215">PowerShell から **TeamsChannels.ps1** スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad801-215">From PowerShell, run the **TeamsChannels.ps1** script.</span></span>

## <a name="create-teams-policies"></a><span data-ttu-id="ad801-216">チーム ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-216">Create Teams policies</span></span>

<span data-ttu-id="ad801-217">管理者は、Microsoft Teams でチーム ポリシーを使用して、組織内のユーザーが閲覧できる内容や実行できる操作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="ad801-217">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization see and can.</span></span> <span data-ttu-id="ad801-218">たとえば、多数のユーザーを登録するとき、エンド ユーザー エクスペリエンスを簡素化するために、デスクトップまたは Web ブラウザーの左のレールにピン留めするアプリケーション、またはモバイル デバイスの下部バーにピン留めするアプリケーションを制御できます。</span><span class="sxs-lookup"><span data-stu-id="ad801-218">For example, you can control which applications are pinned to the left rail on your Desktop or Web browser, or the bottom bar on mobile devices, in order to simplify the end user experience when onboarding a large amount of users.</span></span> <span data-ttu-id="ad801-219">これらのポリシーには PowerShell で作成できるものと、Teams 管理コンソールで手動で作成する必要があるものがあります。</span><span class="sxs-lookup"><span data-stu-id="ad801-219">Some of these policies can be created with PowerShell, and others have to be manually created in the Teams Admin Console.</span></span>

<span data-ttu-id="ad801-220">*ベスト プラクティス ディスカッション*: 次の各ポリシーについて、実際には 2 つのポリシーを作成することを選択しています。1 つは Firstline Workers 用で、もう 1 つは Firstline Manager 用です。</span><span class="sxs-lookup"><span data-stu-id="ad801-220">*Best Practice Discussion*: For each of the following policies, we're choosing to actually create two policies: one for Firstline Workers and one for Firstline Managers.</span></span> <span data-ttu-id="ad801-221">必要な数だけ作成できます。</span><span class="sxs-lookup"><span data-stu-id="ad801-221">You can choose to create as many or as few as you like.</span></span> <span data-ttu-id="ad801-222">ほとんどのお客様にとって、最初に各グループに同じ設定を適用した場合でも、2 つから開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ad801-222">For most customers, two is a good place to start, even if you give the same settings to each group initially.</span></span> <span data-ttu-id="ad801-223">Teams での経験が増えるにつれて、彼らの経験をさらに差別化することを選択できます。すでに作成されている 2 つの個別のポリシーがあると、それがさらに簡単になります。</span><span class="sxs-lookup"><span data-stu-id="ad801-223">As your experience with Teams grows, you may choose to differentiate their experience further and having the two separate policies already created can make that simpler.</span></span>

### <a name="create-teams-message-policies"></a><span data-ttu-id="ad801-224">チームのメッセージング ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-224">Create Teams message policies</span></span>

<span data-ttu-id="ad801-225">メッセージング ポリシーを使用して、Microsoft Teams のユーザーが、チャットおよびチャネルのどのメッセージング機能を使用できるかを制御します。</span><span class="sxs-lookup"><span data-stu-id="ad801-225">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span>

<span data-ttu-id="ad801-226">*ベスト プラクティス ディスカッション*: 自動的に作成される既定のグローバル ポリシーを使用できますが、Firstline Managers と Firstline Worker にロックダウンされたシンプルで差別化されたエクスペリエンスを提供するために、以下の手順を使用してカスタム ポリシーを作成することを選択しました。</span><span class="sxs-lookup"><span data-stu-id="ad801-226">*Best Practice Discussion*: While you can use the default Global policy that is created automatically, we have opted to create a custom policy using the steps below to provide a more locked down, simple, and differentiated experience for Firstline Managers and Firstline Workers.</span></span>

#### <a name="steps-to-create-teams-message-policies"></a><span data-ttu-id="ad801-227">チームのメッセージング ポリシーを作成する手順</span><span class="sxs-lookup"><span data-stu-id="ad801-227">Steps to Create Teams Message Policies</span></span>

1. <span data-ttu-id="ad801-228">.zip ファイル資産に含まれる **TeamsMessagingPolicies.csv** ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="ad801-228">Find the **TeamsMessagingPolicies.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="ad801-229">組織固有の情報を使用して、**TeamsMessagingPolicies.csv** ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="ad801-229">Update the **TeamsMessagingPolicies.csv** file with your organization's specific information.</span></span> <span data-ttu-id="ad801-230">さまざまなオプションのいくつかの詳細については、[こちら](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ad801-230">Additional information on some of the various options can be found [here](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings).</span></span>
1. <span data-ttu-id="ad801-231">資産に含まれる **CreateTeamsMessagePolicies.ps1** スクリプトを見つけます。</span><span class="sxs-lookup"><span data-stu-id="ad801-231">Find the **CreateTeamsMessagePolicies.ps1** script in the assets.</span></span>
1. <span data-ttu-id="ad801-232">PowerShell から **TeamsMessagePolicies.ps1** スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad801-232">From PowerShell, run the **TeamsMessagePolicies.ps1** script.</span></span>

### <a name="create-teams-app-setup-policies"></a><span data-ttu-id="ad801-233">Teams アプリのセットアップ ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-233">Create Teams app setup policies</span></span>

<span data-ttu-id="ad801-234">管理者は、アプリ セットアップポリシーを使用して、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ad801-234">As an admin, you can use app setup policies to do the following:</span></span>

- <span data-ttu-id="ad801-235">Teams をカスタマイズして、ユーザーにとって最も重要なアプリを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="ad801-235">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="ad801-236">ピン留めするアプリを選択し、表示する順序を設定します。</span><span class="sxs-lookup"><span data-stu-id="ad801-236">You choose the apps to pin and set the order in which they appear.</span></span> <span data-ttu-id="ad801-237">アプリをピン留めすると、サード パーティ製のアプリや組織内の開発者が作成したアプリなど、組織内のユーザーが必要とするアプリを提示できます。</span><span class="sxs-lookup"><span data-stu-id="ad801-237">Pinning apps lets you showcase apps that users in your organization need, including those built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="ad801-238">ユーザーがアプリを Teams にピン留めできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="ad801-238">Control whether users can pin apps to Teams.</span></span>

<span data-ttu-id="ad801-239">アプリは、アプリ バーにピン留めされます。</span><span class="sxs-lookup"><span data-stu-id="ad801-239">Apps are pinned to the app bar.</span></span> <span data-ttu-id="ad801-240">このバーは、Teams デスクトップ クライアントの横側および Teams モバイル クライアント (iOS および Android) の下側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ad801-240">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="ad801-241">Teams デスクトップ クライアント</span><span class="sxs-lookup"><span data-stu-id="ad801-241">Teams Desktop Client</span></span>  |         |<span data-ttu-id="ad801-242">Teams モバイル クライアント</span><span class="sxs-lookup"><span data-stu-id="ad801-242">Teams Mobile Client</span></span>  |
|---------|---------|---------|
|![*アプリ* バーにアプリがピン留めされた Teams デスクトップ クライアントのスクリーンショット。](media/FLW-Teams-Desktop-Client.png)         |         |![*下部の* バーにアプリがピン留めされた Teams デスクトップ クライアントのスクリーンショット。](media/FLW-Teams-Mobile-Client.png) |

<span data-ttu-id="ad801-245">*ベスト プラクティス ディスカッション*: アプリの設定ポリシーは、Microsoft Teams 管理センターで管理します。</span><span class="sxs-lookup"><span data-stu-id="ad801-245">*Best Practice Discussion*: You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ad801-246">PowerShell を使用して作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="ad801-246">They aren't able to be created with PowerShell.</span></span> <span data-ttu-id="ad801-247">グローバル (組織全体の既定) ポリシーを使用することも、カスタム ポリシーを作成してユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="ad801-247">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="ad801-248">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ad801-248">Users in your organization will automatically be assigned to the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="ad801-249">ここでは、Firstline Workers と Firstline Managers に 2 つの新しいポリシーを作成し、多数のユーザーの同時登録を容易にする、よりシンプルで合理的なエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ad801-249">For our purposes, we are creating two new policies for Firstline Workers and Firstline Managers, in order to provide them a simpler and more streamlined experience to ease onboarding a large number of users simultaneously.</span></span> <span data-ttu-id="ad801-250">ビジネスニーズに合わせて、エクスペリエンスをカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad801-250">You can choose to customize the experience as your business needs.</span></span>

#### <a name="create-the-firstline-manager-app-setup-policy"></a><span data-ttu-id="ad801-251">Firstline Manager アプリのセットアップポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-251">Create the Firstline Manager app setup policy</span></span>

<span data-ttu-id="ad801-252">ビジネス ニーズに合わせて、次の設定をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad801-252">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="ad801-253">ベスト プラクティスに基づいて、大規模な新規ユーザーの登録を容易にするために、いくつかの推奨オプションを選択しました。</span><span class="sxs-lookup"><span data-stu-id="ad801-253">We have chosen some recommended options based on best practices and to improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="ad801-254">詳細については、[こちら](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="ad801-254">For more information, click [here](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).</span></span>

1. <span data-ttu-id="ad801-255">Microsoft Teams 管理センターの左側のナビゲーションで、 **[Teams アプリ]** > **[ポリシーの設定]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ad801-255">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="ad801-256"> *\*[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad801-256">Click **Add**.</span></span>  
3. <span data-ttu-id="ad801-257">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad801-257">Enter a name and description for the policy.</span></span> <span data-ttu-id="ad801-258">例: **Firstline Manager アプリのセットアップポリシー**。</span><span class="sxs-lookup"><span data-stu-id="ad801-258">As an example: **Firstline Manager App Setup Policy**.</span></span>
<span data-ttu-id="ad801-259">![Firstline Manager アプリのセットアップポリシーの画像。](media/FLW-FLM-App-Setup-Policy.png)</span><span class="sxs-lookup"><span data-stu-id="ad801-259">![Firstline manager app setup policy image.](media/FLW-FLM-App-Setup-Policy.png)</span></span>

4. <span data-ttu-id="ad801-260">**[カスタム アプリのアップロード]** をオフにします。</span><span class="sxs-lookup"><span data-stu-id="ad801-260">Turn off **Upload custom apps**.</span></span>
5. <span data-ttu-id="ad801-261">**[ユーザーのピン留めを許可]** をオフにします。</span><span class="sxs-lookup"><span data-stu-id="ad801-261">Turn off **Allow user pinning**.</span></span>
<span data-ttu-id="ad801-262">![ユーザーのピン留めを許可の切り替えの画像。](media/FLW-Allow-User-Pinning.png)</span><span class="sxs-lookup"><span data-stu-id="ad801-262">![Allow user pinning switch image.](media/FLW-Allow-User-Pinning.png)</span></span>

6. <span data-ttu-id="ad801-263">一覧表示されていない場合は、**Shifts** アプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="ad801-263">If it's not already listed, add the **Shifts** app.</span></span> <span data-ttu-id="ad801-264">**Shifts** の詳細については、[ここ](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="ad801-264">For more information about **Shifts**, click [here](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md).</span></span>
<span data-ttu-id="ad801-265">![[追加] ボタンの横に Shifts アプリが表示されているピン留めされたアプリ画面を追加します。](media/FLW-Add-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="ad801-265">![Add pinned apps screen, showing the Shifts app listed next to an Add button.](media/FLW-Add-Pinned-Apps.png)</span></span>

7. <span data-ttu-id="ad801-266">通話が表示されている場合は削除します。</span><span class="sxs-lookup"><span data-stu-id="ad801-266">Remove Calling, if it appears.</span></span> <span data-ttu-id="ad801-267">注: この機能を削除しても、ユーザーに対して無効になることはありませんが、アプリ バーに表示されないので、エンド ユーザー エクスペリエンスが簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="ad801-267">Note: removing this feature will not disable it for the user, but will prevent it from appearing on the app bar to simplify the end user experience.</span></span>
8. <span data-ttu-id="ad801-268">アプリを次の順序で配置して、Teams アプリ バーでの順序を指定し、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad801-268">Arrange the apps in the following order to dictate their order in the Teams App Bar, and then click **Save**.</span></span>
    1. <span data-ttu-id="ad801-269">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="ad801-269">Activity</span></span>
    1. <span data-ttu-id="ad801-270">チャット</span><span class="sxs-lookup"><span data-stu-id="ad801-270">Chat</span></span>
    1. <span data-ttu-id="ad801-271">Teams</span><span class="sxs-lookup"><span data-stu-id="ad801-271">Teams</span></span>
    1. <span data-ttu-id="ad801-272">カレンダー</span><span class="sxs-lookup"><span data-stu-id="ad801-272">Calendar</span></span>
    1. <span data-ttu-id="ad801-273">![マネージャー アプリ リストのスクリーンショットを順番に](media/FLW-Manager-Pinned-Apps.png)シフトします。</span><span class="sxs-lookup"><span data-stu-id="ad801-273">Shifts ![Screenshot of the manager apps list in order.](media/FLW-Manager-Pinned-Apps.png)</span></span>

#### <a name="create-the-firstline-worker-app-setup-policy"></a><span data-ttu-id="ad801-274">Firstline Worker アプリのセットアップ ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-274">Create the Firstline Worker app setup policy</span></span>

<span data-ttu-id="ad801-275">ビジネス ニーズに合わせて、次の設定をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad801-275">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="ad801-276">ベスト プラクティスに基づいて、大規模な新規ユーザーの登録を容易にするために、いくつかの推奨オプションを選択しました。</span><span class="sxs-lookup"><span data-stu-id="ad801-276">We have chosen some recommended options based on best practices and to improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="ad801-277">詳細については、[こちら](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="ad801-277">For more information, click [here](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).</span></span>

1. <span data-ttu-id="ad801-278">Microsoft Teams 管理センターの左側のナビゲーションで、 **[Teams アプリ]** > **[ポリシーの設定]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ad801-278">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="ad801-279"> *\*[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad801-279">Click **Add**.</span></span>
3. <span data-ttu-id="ad801-280">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad801-280">Enter a name and description for the policy.</span></span> <span data-ttu-id="ad801-281">例: **Firstline Worker アプリのセットアップポリシー**。</span><span class="sxs-lookup"><span data-stu-id="ad801-281">As an example: **Firstline Worker App Setup Policy**.</span></span>
<span data-ttu-id="ad801-282">![Firstline Worker アプリのセットアップポリシーの画像。](media/FLW-FLW-App-Setup-Policy.png)</span><span class="sxs-lookup"><span data-stu-id="ad801-282">![Firstline worker app setup policy image.](media/FLW-FLW-App-Setup-Policy.png)</span></span>

4. <span data-ttu-id="ad801-283">**[カスタム アプリのアップロード]** をオフにします。</span><span class="sxs-lookup"><span data-stu-id="ad801-283">Turn off **Upload custom apps**.</span></span>
5. <span data-ttu-id="ad801-284">**[ユーザーのピン留めを許可]** をオフにします。</span><span class="sxs-lookup"><span data-stu-id="ad801-284">Turn off **Allow user pinning**.</span></span>
<span data-ttu-id="ad801-285">![ユーザーのピン留めを許可の切り替えの画像。](media/FLW-Allow-User-Pinning.png)</span><span class="sxs-lookup"><span data-stu-id="ad801-285">![Allow user pinning switch image.](media/FLW-Allow-User-Pinning.png)</span></span>

6. <span data-ttu-id="ad801-286">一覧表示されていない場合は、**Shifts** アプリを追加します。</span><span class="sxs-lookup"><span data-stu-id="ad801-286">If it's not already listed, add the **Shifts** app.</span></span> <span data-ttu-id="ad801-287">**Shifts** の詳細については、ここをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="ad801-287">For more information about **Shifts**, click here.</span></span>
<span data-ttu-id="ad801-288">![[追加] ボタンの横に Shifts アプリが表示されているピン留めされたアプリ画面を追加します。](media/FLW-Add-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="ad801-288">![Add pinned apps screen, showing the Shifts app listed next to an Add button.](media/FLW-Add-Pinned-Apps.png)</span></span>

7. <span data-ttu-id="ad801-289">会議と通話が表示されている場合は削除します。</span><span class="sxs-lookup"><span data-stu-id="ad801-289">Remove Meetings and Calling, if they appear.</span></span> <span data-ttu-id="ad801-290">注: これらの機能を削除しても、ユーザーに対して無効になることはありませんが、アプリ バーに表示されないので、エンド ユーザー エクスペリエンスが簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="ad801-290">Note: removing these features will not disable them for the user, but will prevent them from appearing on the app bar to simplify the end user experience.</span></span>
8. <span data-ttu-id="ad801-291">アプリを次の順序で配置して、Teams アプリ バーでの順序を指定し、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad801-291">Arrange the apps in the following order to dictate their order in the Teams App Bar, and then click **Save**.</span></span>
    1. <span data-ttu-id="ad801-292">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="ad801-292">Activity</span></span>
    1. <span data-ttu-id="ad801-293">チャット</span><span class="sxs-lookup"><span data-stu-id="ad801-293">Chat</span></span>
    1. <span data-ttu-id="ad801-294">Teams</span><span class="sxs-lookup"><span data-stu-id="ad801-294">Teams</span></span>
    1. <span data-ttu-id="ad801-295">![ワーカー アプリ リストのスクリーンショットを順番に](media/FLW-Worker-Pinned-Apps.png)シフトします。</span><span class="sxs-lookup"><span data-stu-id="ad801-295">Shifts ![Screenshot of the worker apps list in order.](media/FLW-Worker-Pinned-Apps.png)</span></span>

### <a name="create-app-permission-policies"></a><span data-ttu-id="ad801-296">アプリのアクセス許可ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-296">Create app permission policies</span></span>

<span data-ttu-id="ad801-297">管理者であれば、アプリのアクセス許可ポリシーを使用して、組織の Microsoft Teams ユーザーが使用できるアプリを制御できます。</span><span class="sxs-lookup"><span data-stu-id="ad801-297">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="ad801-298">すべてのアプリ、または Microsoft、第三者、お客様の組織によって公開されている特定のアプリを許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad801-298">You can allow or block all apps, or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="ad801-299">アプリをブロックした場合、ポリシーを持つユーザーは、Teams アプリ ストアからアプリをインストールできません。</span><span class="sxs-lookup"><span data-stu-id="ad801-299">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="ad801-300">これらのポリシーを管理するには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad801-300">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="ad801-301">*ベスト プラクティス ディスカッション*: アプリの設定ポリシーは、Microsoft Teams 管理センターで管理します。</span><span class="sxs-lookup"><span data-stu-id="ad801-301">*Best Practice Discussion*: You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ad801-302">PowerShell を使用して作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="ad801-302">They aren't able to be created with PowerShell.</span></span> <span data-ttu-id="ad801-303">グローバル (組織全体の既定) ポリシーを使用することも、カスタム ポリシーを作成してユーザーに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="ad801-303">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="ad801-304">カスタム ポリシーを作成して割り当てていない場合、組織内のユーザーにはグローバル ポリシーが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ad801-304">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="ad801-305">ここでは、Firstline Workers と Firstline Managers に 2 つの新しいポリシーを作成し、多数のユーザーの同時登録を容易にする、より安全で合理的なエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ad801-305">For our purposes, we are creating two new policies for Firstline Workers and Firstline Managers in order to provide a secure and more streamlined experience to ease onboarding a large number of users simultaneously.</span></span> <span data-ttu-id="ad801-306">もちろん、ビジネスニーズに合わせて、エクスペリエンスをカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad801-306">You can of course choose to customize the experience as your business needs.</span></span>

#### <a name="create-the-firstline-manager-app-permission-policy"></a><span data-ttu-id="ad801-307">Firstline Manager アプリのアクセス許可ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-307">Create the Firstline Manager app permission policy</span></span>

<span data-ttu-id="ad801-308">ビジネス ニーズに合わせて、次の設定をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad801-308">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="ad801-309">これらは、ベスト プラクティスに基づいて、大規模な新規ユーザーの登録を容易にするためのいくつかの推奨オプションです。</span><span class="sxs-lookup"><span data-stu-id="ad801-309">These are some recommended options based on best practices that can improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="ad801-310">詳細については、[こちら](teams-app-permission-policies.md)をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="ad801-310">For more information, click [here](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="ad801-311">Microsoft Teams 管理センターの左側のナビゲーションで、 **[Teams アプリ]** > **[アクセス許可ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ad801-311">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="ad801-312"> *\*[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad801-312">Click **Add**.</span></span>
<span data-ttu-id="ad801-313">![Microsoft、サード パーティ、テナントのアプリのセクションを含む、[アプリのアクセス許可ポリシーの追加] ページを示します。](media/FLW-add-app-permission-policy.png)</span><span class="sxs-lookup"><span data-stu-id="ad801-313">![Shows the add app permission policy page, with sections for Microsoft, third-party, and tenant apps.](media/FLW-add-app-permission-policy.png)</span></span>

3. <span data-ttu-id="ad801-314">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad801-314">Enter a name and description for the policy.</span></span> <span data-ttu-id="ad801-315">例: Firstline Manager アプリのアクセス許可ポリシー。</span><span class="sxs-lookup"><span data-stu-id="ad801-315">As an example: Firstline Manager App Permission Policy.</span></span>
4. <span data-ttu-id="ad801-316">[Microsoft アプリ] の下で、**[すべてのアプリを許可]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad801-316">Under Microsoft apps, select **Allow all apps**.</span></span>
5. <span data-ttu-id="ad801-317">[サード パーティ製のアプリ] の下で、[**すべてのアプリを許可**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad801-317">Under Third-party apps, select **Allow all apps**.</span></span>
6. <span data-ttu-id="ad801-318">[テナント アプリ] の下で、**[すべてのアプリを許可]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad801-318">Under Tenant apps, select **Allow all apps**.</span></span>
7. <span data-ttu-id="ad801-319"> *\*[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad801-319">Click **Save**.</span></span>

#### <a name="create-the-firstline-worker-app-permission-policy"></a><span data-ttu-id="ad801-320">Firstline Worker アプリのアクセス許可ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-320">Create the Firstline Worker App Permission Policy</span></span>

<span data-ttu-id="ad801-321">ビジネス ニーズに合わせて、次の設定をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad801-321">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="ad801-322">これらは、ベスト プラクティスに基づいて、大規模な新規ユーザーの登録を容易にするためのいくつかの推奨オプションです。</span><span class="sxs-lookup"><span data-stu-id="ad801-322">These are some recommended options based on best practices that can improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="ad801-323">詳細については、[こちら](teams-app-permission-policies.md)をクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="ad801-323">For more information, click [here](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="ad801-324">Microsoft Teams 管理センターの左側のナビゲーションで、 **[Teams アプリ]** > **[アクセス許可ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ad801-324">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="ad801-325"> *\*[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad801-325">Click **Add**.</span></span>
<span data-ttu-id="ad801-326">![Microsoft、サード パーティ、テナントのアプリのセクションを含む、[アプリのアクセス許可ポリシーの追加] ページを示します。](media/FLW-add-app-permission-policy.png)</span><span class="sxs-lookup"><span data-stu-id="ad801-326">![Shows the add app permission policy page, with sections for Microsoft, third-party, and tenant apps.](media/FLW-add-app-permission-policy.png)</span></span>

3. <span data-ttu-id="ad801-327">ポリシーの名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad801-327">Enter a name and description for the policy.</span></span> <span data-ttu-id="ad801-328">例: Firstline Worker アプリのアクセス許可ポリシー。</span><span class="sxs-lookup"><span data-stu-id="ad801-328">As an example: Firstline Worker App Permission Policy.</span></span>
4. <span data-ttu-id="ad801-329">[Microsoft アプリ] の下で、**[すべてのアプリを許可]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad801-329">Under Microsoft apps, select **Allow all apps**.</span></span>
5. <span data-ttu-id="ad801-330">[サード パーティ製のアプリ] の下で、**[すべてのアプリをブロック]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad801-330">Under Third-party apps, select **Block all apps**.</span></span>
6. <span data-ttu-id="ad801-331">[テナント アプリ] の下で、**[すべてのアプリを許可]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad801-331">Under Tenant apps, select **Allow all apps**.</span></span>
7. <span data-ttu-id="ad801-332"> *\*[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad801-332">Click **Save**.</span></span>

## <a name="create-and-set-up-users"></a><span data-ttu-id="ad801-333">ユーザーを作成して設定する</span><span class="sxs-lookup"><span data-stu-id="ad801-333">Create and set up users</span></span>

### <a name="create-user-and-security-groups"></a><span data-ttu-id="ad801-334">ユーザーとセキュリティ グループを作成する</span><span class="sxs-lookup"><span data-stu-id="ad801-334">Create user and security groups</span></span>

<span data-ttu-id="ad801-335">Teams で大量のユーザーと共同作業するには、最初に Azure AD でユーザーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad801-335">To work with a large amount of users in Teams you first need to have the users created in Azure AD.</span></span> <span data-ttu-id="ad801-336">多数のユーザーをプロビジョニングする方法はたくさんありますが、以下を強調しておきます。</span><span class="sxs-lookup"><span data-stu-id="ad801-336">There are many ways to provision a large number of users, but we're going to highlight the following:</span></span>

- <span data-ttu-id="ad801-337">これらのユーザーが、次の人事システムのいずれかに既に存在している場合は、次のリンクを使用してユーザーのプロビジョニングを設定します。</span><span class="sxs-lookup"><span data-stu-id="ad801-337">If these users already exist in one of the following HR systems, use the following links to set up user provisioning:</span></span>
  - <span data-ttu-id="ad801-338">SAP SuccessFactors - [チュートリアル: SAP SuccessFactors を Active Directory ユーザー プロビジョニングに構成します](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial)。</span><span class="sxs-lookup"><span data-stu-id="ad801-338">SAP Success Factors - [Tutorial: Configure SAP SuccessFactors to Active Directory user provisioning](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial).</span></span>
  - <span data-ttu-id="ad801-339">Workday - [チュートリアル: Workday を自動ユーザー プロビジョニング用に構成します](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial)。</span><span class="sxs-lookup"><span data-stu-id="ad801-339">Workday - [Tutorial: Configure Workday for automatic user provisioning](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial).</span></span>
- <span data-ttu-id="ad801-340">他のシステムにユーザー情報がある場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="ad801-340">If you have your user information in other systems, proceed with the following steps.</span></span>

<span data-ttu-id="ad801-341">これらのユーザーをより効果的に大規模に管理するには、Firstline Workers と Firstline Managers の 2 つのセキュリティ グループを作成し、次の手順に従って、これらのユーザーをセキュリティ グループに直接プロビジョニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad801-341">In order to manage these users at scale more effectively, you need to create two security groups for Firstline Workers and Firstline Managers, and provision those users into the security groups directly, following these steps:</span></span>

1. <span data-ttu-id="ad801-342">.zip ファイル資産に含まれる **SecurityGroups.csv** ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="ad801-342">Find the **SecurityGroups.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="ad801-343">組織固有の情報を使用して、**Teams SecurityGroups.csv** ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="ad801-343">Update the **SecurityGroups.csv** file with your organization's specific information.</span></span>
    1. <span data-ttu-id="ad801-344">**MessagePolicy**、**AppPermissionPolicy**、**AppSetupPolicy** フィールドを更新して、前に作成した適切なポリシーにマップしてください。</span><span class="sxs-lookup"><span data-stu-id="ad801-344">Make sure to update the **MessagePolicy**, **AppPermissionPolicy**, and **AppSetupPolicy** fields to map to the appropriate policies you created earlier.</span></span>
    1. <span data-ttu-id="ad801-345">**LicensePlan** フィールドを更新して、これらのユーザーに付与する予定のライセンスを反映してください。</span><span class="sxs-lookup"><span data-stu-id="ad801-345">Make sure to update the **LicensePlan** field to reflect the licensing that you intend to give each of these users.</span></span> <span data-ttu-id="ad801-346">製品名とサービス プラン識別子の詳細については、[こちら](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ad801-346">For more information on product names and service plan identifiers, review the documentation [here](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>
1. <span data-ttu-id="ad801-347">.zip ファイル資産に含まれる **Users.csv** ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="ad801-347">Find the **Users.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="ad801-348">組織固有の情報を使用して、**Users.csv** ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="ad801-348">Update the **Users.csv** file with your organization's specific information.</span></span>
    1. <span data-ttu-id="ad801-349">既定で、提供されるスクリプトは、初回ログイン時に変更する必要のある一時的なパスワードを持つユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ad801-349">By default, the script we've provided will create a user with a temporary password that must be changed on first login.</span></span> <span data-ttu-id="ad801-350">既定のパスワードを使用しない場合は、**CreateUsers.ps1** スクリプトを編集して要件に合わせます。</span><span class="sxs-lookup"><span data-stu-id="ad801-350">If you don't want to use the default password, edit the **CreateUsers.ps1** script to meet your requirements.</span></span>
    1. <span data-ttu-id="ad801-351">SecurityGroup フィールドを更新して、前に作成した適切な名前を反映させます。</span><span class="sxs-lookup"><span data-stu-id="ad801-351">Make sure to update the SecurityGroup field to reflect the appropriate name created earlier.</span></span>
1. <span data-ttu-id="ad801-352">PowerShell から、資産の **CreateUsers.ps1** スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad801-352">From PowerShell, run the script **CreateUsers.ps1** from assets.</span></span>

### <a name="assign-licensing-to-users-by-group-based-licensing"></a><span data-ttu-id="ad801-353">グループベースのライセンスによりユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ad801-353">Assign licensing to users by Group-Based licensing</span></span>

<span data-ttu-id="ad801-354">Office 365、Enterprise Mobility + Security、Dynamics 365 などの Microsoft 有料クラウドサービス、およびその他の同様の製品にはライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ad801-354">Microsoft paid cloud services, such as Office 365, Enterprise Mobility + Security, Dynamics 365, and other similar products, require licenses.</span></span> <span data-ttu-id="ad801-355">これらのライセンスは、これらのサービスにアクセスする必要がある各ユーザーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ad801-355">These licenses are assigned to each user who needs access to these services.</span></span> <span data-ttu-id="ad801-356">ライセンスを管理するために、管理者は、管理ポータル (Office または Azure) と PowerShell コマンドレットのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="ad801-356">To manage licenses, administrators use one of the management portals (Office or Azure) and PowerShell cmdlets.</span></span> <span data-ttu-id="ad801-357">Azure Active Directory (Azure AD) は、すべての Microsoft クラウド サービスの ID 管理をサポートする基盤となるインフラストラクチャです。</span><span class="sxs-lookup"><span data-stu-id="ad801-357">Azure Active Directory (Azure AD) is the underlying infrastructure that supports identity management for all Microsoft cloud services.</span></span> <span data-ttu-id="ad801-358">Azure AD には、ユーザーのライセンスの割り当て状態に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="ad801-358">Azure AD stores information about license assignment states for users.</span></span>

<span data-ttu-id="ad801-359">規模に応じてライセンスを有効にするために、Azure AD にはグループベースのライセンスが含まれています。このため、この記事の前半でセキュリティ グループを作成しました。</span><span class="sxs-lookup"><span data-stu-id="ad801-359">In order to enable licensing at scale, Azure AD now includes group-based licensing, and for this reason we created the security groups earlier in this article.</span></span> <span data-ttu-id="ad801-360">1 つ以上の製品ライセンスをグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ad801-360">You can assign one or more product licenses to a group.</span></span> <span data-ttu-id="ad801-361">Azure AD では、グループのメンバー全員にライセンスが割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad801-361">Azure AD ensures that the licenses are assigned to all members of the group.</span></span> <span data-ttu-id="ad801-362">グループに参加する新しいメンバー全員に、適切なライセンスが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ad801-362">Any new members who join the group are assigned the appropriate licenses.</span></span> <span data-ttu-id="ad801-363">グループを脱退するメンバーからライセンスが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ad801-363">Licenses are removed from members who leave the group.</span></span> <span data-ttu-id="ad801-364">このライセンス管理により、PowerShell を介してライセンス管理を自動化し、組織および部門構造の変更をユーザーごとに反映する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="ad801-364">This licensing management eliminates the need for automating license management via PowerShell to reflect changes in the organization and departmental structure on a per-user basis.</span></span>

## <a name="assign-users-and-policies"></a><span data-ttu-id="ad801-365">ユーザーとポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ad801-365">Assign Users and Policies</span></span>

### <a name="assigning-users-to-teams"></a><span data-ttu-id="ad801-366">チームにユーザーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ad801-366">Assigning users to teams</span></span>

<span data-ttu-id="ad801-367">ユーザーを作成してチームを作成したので、今度はすべてのユーザーを適切なチームに配置します。</span><span class="sxs-lookup"><span data-stu-id="ad801-367">Now that you've created the users and created the Teams, it's time to put all the users in the appropriate Teams.</span></span>

1. <span data-ttu-id="ad801-368">.zip ファイル資産に含まれる **Users.csv** ファイルを見つけて、このファイルのチームに正確にマップしてください。</span><span class="sxs-lookup"><span data-stu-id="ad801-368">Find the **Users.csv** file in the .zip file assets and make sure you have accurate mapping to Teams in this file.</span></span>
1. <span data-ttu-id="ad801-369">PowerShell から .zip ファイル資産に含まれる **AssignUserstoTeams.ps1** スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad801-369">From PowerShell, run the script **AssignUserstoTeams.ps1** from the .zip file assets.</span></span>

### <a name="assign-teams-policies-to-users"></a><span data-ttu-id="ad801-370">ユーザーにチーム ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ad801-370">Assign Teams policies to users</span></span>

<span data-ttu-id="ad801-371">Teams でユーザー エクスペリエンスを変更するためのユーザーとポリシーを作成したので、次に、それらのポリシーを正しいユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ad801-371">Now that you've created the users and the policies to modify their experience in Teams, it's time to assign those policies to the correct users.</span></span>

1. <span data-ttu-id="ad801-372">.zip ファイル資産に含まれる **SecurityGroups.csv** ファイルを見つけて、グループにポリシーを正確にマップしてください。</span><span class="sxs-lookup"><span data-stu-id="ad801-372">Find the **SecurityGroups.csv** file in the .zip file assets and make sure you have accurate mapping of the policies to the groups.</span></span>
1. <span data-ttu-id="ad801-373">PowerShell から .zip ファイル資産に含まれる **AssignPoliciestoUsers.ps1** スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad801-373">From PowerShell, run the script **AssignPoliciestoUsers.ps1** from the .zip file assets.</span></span>

## <a name="test-and-validate"></a><span data-ttu-id="ad801-374">テストと検証</span><span class="sxs-lookup"><span data-stu-id="ad801-374">Test and validate</span></span>

### <a name="check-for-errors"></a><span data-ttu-id="ad801-375">エラーをチェックする</span><span class="sxs-lookup"><span data-stu-id="ad801-375">Check for errors</span></span>

<span data-ttu-id="ad801-376">以前のスクリプトを実行したときに、.zip ファイル資産のログ フォルダーにある .csv ファイルにエラーまたは例外が書き込まれました。</span><span class="sxs-lookup"><span data-stu-id="ad801-376">As you ran the earlier scripts, errors or exceptions were written to a .csv file located in the logs folder of the .zip file assets.</span></span> <span data-ttu-id="ad801-377">このファイルは、発生する可能性がある問題を調査するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="ad801-377">This file can be used to investigate any issues that may have occurred.</span></span>

<span data-ttu-id="ad801-378">例外の例としては、テナントに既に存在するチームを作成しようとした場合があります。</span><span class="sxs-lookup"><span data-stu-id="ad801-378">An example of an exception could be if you tried to create a team that already existed in your tenant.</span></span>

1. <span data-ttu-id="ad801-379">[**Logs**] フォルダーを見つけ、それに含まれている .csv ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad801-379">Find the **Logs** folder and review any .csv file it may contain.</span></span> <span data-ttu-id="ad801-380">例外がない場合は、ここに例外ファイルが見つからない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ad801-380">If there are no exceptions, you may not find an exception file here.</span></span>

### <a name="login-to-teams-with-a-test-user"></a><span data-ttu-id="ad801-381">テスト ユーザーで Teams にログインする</span><span class="sxs-lookup"><span data-stu-id="ad801-381">Login to Teams with a test user</span></span>

<span data-ttu-id="ad801-382">すべての手順を完了したので、完了した作業を確認します。</span><span class="sxs-lookup"><span data-stu-id="ad801-382">Now that you've completed all the steps, it's time to verify the work you've completed.</span></span>

1. <span data-ttu-id="ad801-383">以前のリストからユーザーを選択し、そのユーザーの資格情報を使用して Teams にログインします。</span><span class="sxs-lookup"><span data-stu-id="ad801-383">Select a user from your earlier list and log into Teams with that user's credentials.</span></span>
1. <span data-ttu-id="ad801-384">Teams のルックアンドフィールが期待どおりであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad801-384">Verify the look and feel of Teams is what you expected.</span></span> <span data-ttu-id="ad801-385">そうでない場合、**[チームポリシーを作成する]** と **[ユーザーにチーム ポリシーを割り当てる]** のセクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ad801-385">If not, review the **Create Teams Policies** and the **Assign Teams Policies to Users** sections.</span></span>
1. <span data-ttu-id="ad801-386">ユーザーが正しいチームに属していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad801-386">Verify the user is in the correct team.</span></span> <span data-ttu-id="ad801-387">そうでない場合、**[ユーザーを作成し設定する]** と **[チームにユーザーを割り当てる]** のセクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ad801-387">If not, review the **Create and Setup Users** and **Assign Users to Teams** sections.</span></span>
