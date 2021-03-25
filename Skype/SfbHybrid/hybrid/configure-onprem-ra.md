---
title: Skype for Business Server 2019 でリソース アカウントを構成する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Skype for Business Server 2019 のリソース アカウントを設定します。
ms.openlocfilehash: eb8f82a9551c3607068b0d62cc04518d58d09987
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118936"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="dad5c-103">リソース アカウントの構成</span><span class="sxs-lookup"><span data-stu-id="dad5c-103">Configure resource accounts</span></span>

<span data-ttu-id="dad5c-104">Skype for Business Server 2019 ハイブリッド実装では、電話システムが提供するクラウド サービスのみをユニファイド メッセージングに使用し、Exchange Online と統合しません。</span><span class="sxs-lookup"><span data-stu-id="dad5c-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="dad5c-105">Skype for Business Server 2019 では [、「Microsoft 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)または Office 365 の電話システムで取得する内容」で説明されているクラウド通話キューと自動応答を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dad5c-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Microsoft 365 or Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="dad5c-106">Skype for Business Server 2019 で電話システム自動応答または通話キューを使用するには、アプリケーション エンドポイントとして機能し、電話番号を割り当て可能なリソース アカウントを作成し、オンライン Teams 管理センターを使用して通話キューまたは自動応答を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dad5c-106">To use an Phone System auto attendant or call queue with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="dad5c-107">このリソース アカウントは、この記事で説明するように、オンライン [(「Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) でリソース アカウントを管理してオンラインでリソース アカウントを作成する」を参照)、またはオンプレミスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="dad5c-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premises as described in this article.</span></span> <span data-ttu-id="dad5c-108">通常、複数の電話システム自動応答ノードまたは通話キュー ノードが用意され、それぞれがリソース アカウントにマップされ、オンラインまたは Skype for Business Server 2019 に保存できます。</span><span class="sxs-lookup"><span data-stu-id="dad5c-108">Typically you will have multiple Phone System auto attendant or call queue nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="dad5c-109">既存の Exchange UM 自動応答と通話キュー システムがある場合は、Exchange Server 2019 または Exchange online に切り替える前に、以下の説明に従って詳細を手動で記録し、Teams 管理センターを使用して完全に新しいシステムを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dad5c-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="dad5c-110">概要</span><span class="sxs-lookup"><span data-stu-id="dad5c-110">Overview</span></span>

<span data-ttu-id="dad5c-111">電話システムの自動応答または通話キューにサービス番号が必要な場合は、次の順序でさまざまな依存関係を満たします。</span><span class="sxs-lookup"><span data-stu-id="dad5c-111">If your Phone System auto attendant or call queue will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="dad5c-112">サービス番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-112">Obtain a service number.</span></span>
2. <span data-ttu-id="dad5c-113">リソース アカウントで使用する無料の電話システム - [仮想](/MicrosoftTeams/teams-add-on-licensing/virtual-user) ユーザー ライセンスまたは有料電話システム ライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-113">Obtain a free Phone System - [Virtual User license](/MicrosoftTeams/teams-add-on-licensing/virtual-user) or a paid Phone System license to use with the resource account.</span></span>
3. <span data-ttu-id="dad5c-114">リソース アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-114">Create the resource account.</span></span> <span data-ttu-id="dad5c-115">関連付けられたリソース アカウントを持つには、自動応答キューまたは通話キューが必要です。</span><span class="sxs-lookup"><span data-stu-id="dad5c-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="dad5c-116">オンラインとオンプレミスの間でアクティブなディレクトリの同期を待ちます。</span><span class="sxs-lookup"><span data-stu-id="dad5c-116">Wait for an active directory sync between online and on premises.</span></span>
5. <span data-ttu-id="dad5c-117">電話システム ライセンスをリソース アカウントに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dad5c-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="dad5c-118">リソース アカウントにサービス番号を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dad5c-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="dad5c-119">電話システム通話キューまたは自動応答を作成します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-119">Create a Phone System call queue or auto attendant.</span></span>
8. <span data-ttu-id="dad5c-120">リソース アカウントを自動応答キューまたは通話キューに関連付けます。(New-CsApplicationInstanceAssociation)。</span><span class="sxs-lookup"><span data-stu-id="dad5c-120">Associate the resource account with an auto attendant or call queue: (New-CsApplicationInstanceAssociation).</span></span>

<span data-ttu-id="dad5c-121">自動応答または通話キューがトップ レベルの自動応答の下に入れ子になっている場合は、自動応答と通話キューの構造に複数のエントリ ポイントが必要な場合にのみ、関連付けられたリソース アカウントに電話番号が必要です。</span><span class="sxs-lookup"><span data-stu-id="dad5c-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="dad5c-122">オンラインに所属する組織内のユーザーに通話をリダイレクトするには、電話システム ライセンスを持ち、エンタープライズ VoIP で有効にするか、Microsoft 365 または Office 365 通話プランを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dad5c-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="dad5c-123">「Microsoft [Teams ライセンスの割り当て」を参照してください](/MicrosoftTeams/assign-teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="dad5c-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="dad5c-124">これらの機能を有効にするにはエンタープライズ VoIPを使用Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="dad5c-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="dad5c-125">たとえば、次のコマンドを実行します。  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="dad5c-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="dad5c-126">作成する電話システムの自動応答キューまたは通話キューが入れ子にされ、電話番号が必要ない場合は、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="dad5c-126">If the Phone system auto attendant or call queue you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="dad5c-127">リソース アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="dad5c-127">Create the resource account</span></span>  
2. <span data-ttu-id="dad5c-128">オンラインとオンプレミスの間でアクティブなディレクトリの同期を待つ</span><span class="sxs-lookup"><span data-stu-id="dad5c-128">Wait for an active directory sync between online and on premises</span></span>
3. <span data-ttu-id="dad5c-129">電話システムの自動応答または通話キューの作成</span><span class="sxs-lookup"><span data-stu-id="dad5c-129">Create a Phone System auto attendant or call queue</span></span>
4. <span data-ttu-id="dad5c-130">リソース アカウントを電話システムの自動応答または通話キューに関連付ける</span><span class="sxs-lookup"><span data-stu-id="dad5c-130">Associate the resource account with a Phone System auto attendant or call queue</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="dad5c-131">電話番号を使用してリソース アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="dad5c-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="dad5c-132">電話番号を使用するリソース アカウントを作成するには、次の順序で次のタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dad5c-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="dad5c-133">有料または無料のサービス番号をポートまたは取得します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="dad5c-134">この番号は、他の音声サービスまたはリソース アカウントには割り当てできません。</span><span class="sxs-lookup"><span data-stu-id="dad5c-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="dad5c-135">電話番号をリソース アカウントに割り当てる前に、既存の有料または無料のサービス番号を取得または移植する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dad5c-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="dad5c-136">有料またはフリーダイヤルサービスの電話番号を取得すると **、Microsoft Teams** 管理センターの音声電話番号に表示され、リストされている番号の種類が [サービス - 無料] として表示されます  >    >  。 </span><span class="sxs-lookup"><span data-stu-id="dad5c-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="dad5c-137">サービス番号を取得するには、「 [サービス](/MicrosoftTeams/getting-service-phone-numbers) 電話番号の取得」または「既存のサービス番号を転送する場合」を参照してください。「電話番号を Teams に転送する」を [参照してください](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)。</span><span class="sxs-lookup"><span data-stu-id="dad5c-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

   <span data-ttu-id="dad5c-138">米国外の場合は、Microsoft Teams 管理センターを使用してサービス番号を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="dad5c-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="dad5c-139">代わりに [[組織の電話番号の](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) 管理] に移動して、米国外から行う方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="dad5c-140">電話システム ライセンスを購入します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-140">Buy a Phone System license.</span></span> <span data-ttu-id="dad5c-141">参照:</span><span class="sxs-lookup"><span data-stu-id="dad5c-141">See:</span></span>  
   - [<span data-ttu-id="dad5c-142">電話システム-仮想ユーザー ライセンス</span><span class="sxs-lookup"><span data-stu-id="dad5c-142">Phone System–Virtual User license</span></span>](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [<span data-ttu-id="dad5c-143">Office 365 Enterprise E1 および E3</span><span class="sxs-lookup"><span data-stu-id="dad5c-143">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="dad5c-144">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="dad5c-144">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="dad5c-145">Office 365 Enterprise E5 Business Software</span><span class="sxs-lookup"><span data-stu-id="dad5c-145">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="dad5c-146">電話システムの自動応答または通話キューごとにコマンドレットを実行して、オンプレミスのリソース アカウントを作成し、それぞれに名前 `New-CsHybridApplicationEndpoint` 、sip アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-146">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="dad5c-147">この [コマンドの詳細については、「New-CsHybridApplicationEndpoint」](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dad5c-147">See [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="dad5c-148">(省略可能)リソース アカウントを作成したら、AD がオンラインとオンプレミスの間で同期するのを待つか、同期を強制して電話システムの自動応答または通話キューのオンライン構成に進みます。</span><span class="sxs-lookup"><span data-stu-id="dad5c-148">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="dad5c-149">同期を強制するには、AAD Connect を実行しているコンピューターで次のコマンドを実行します (まだ実行していない場合は、コマンドを実行するために読み込む `import-module adsync` 必要があります)。</span><span class="sxs-lookup"><span data-stu-id="dad5c-149">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="dad5c-150">この [コマンドの詳細については、「Start-ADSyncSyncCycle」](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dad5c-150">See [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>
    
    <span data-ttu-id="dad5c-151">この時点で、アカウントが同期されている可能性がありますが、プロビジョニングが完了していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dad5c-151">Note-at this point, the account may have synced, but provisioning may not be complete.</span></span>  <span data-ttu-id="dad5c-152">[Get-CsOnlineApplicationEndpoint の出力を確認します](/powershell/module/skype/get-csonlineapplicationendpoint)。</span><span class="sxs-lookup"><span data-stu-id="dad5c-152">Check the output of [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint).</span></span>  <span data-ttu-id="dad5c-153">同期されたエンドポイントがまだプロビジョニングを完了していない場合、ここには表示されません。</span><span class="sxs-lookup"><span data-stu-id="dad5c-153">If the synced endpoint has not completed provisioning yet, then it will not appear here.</span></span>  <span data-ttu-id="dad5c-154">プロビジョニング要求の状態は、M365 ポータルの [Teams セットアップの状態] [で確認できます](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)。</span><span class="sxs-lookup"><span data-stu-id="dad5c-154">You can check the status of the provisioning requests in the M365 portal under [Teams Setup Status](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning).</span></span>  <span data-ttu-id="dad5c-155">このプロビジョニング フェーズには最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dad5c-155">This provisioning phase can take up to 24 hours.</span></span>

5. <span data-ttu-id="dad5c-156">電話システム - 仮想ユーザーまたは電話システム のライセンスをリソース アカウントに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dad5c-156">Assign the Phone System - Virtual User or Phone System license to the resource account.</span></span> <span data-ttu-id="dad5c-157">「Microsoft [Teams アドオン ライセンスの割り当て」および「](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses)[ユーザーにライセンスを割り当てる」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="dad5c-157">See [Assign Microsoft Teams add-on licenses](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) and [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

   <span data-ttu-id="dad5c-158">電話番号をリソース アカウントに割り当てる場合は、コストフリーの電話システム - 仮想ユーザー ライセンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dad5c-158">If you are assigning a phone number to a resource account you can now use the cost-free Phone System - Virtual User license.</span></span> <span data-ttu-id="dad5c-159">これにより、組織レベルの電話番号に電話システム機能が提供され、自動応答機能と通話キュー機能を作成できます。</span><span class="sxs-lookup"><span data-stu-id="dad5c-159">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="dad5c-160">サービス番号をリソース アカウントに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dad5c-160">Assign the service number to the resource account.</span></span> <span data-ttu-id="dad5c-161">このコマンド `Set-CsHybridApplicationEndpoint` を使用して、電話番号 (-LineURI オプション付き) をリソース アカウントに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dad5c-161">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="dad5c-162">この [コマンドの詳細については、「Set-CsHybridApplicationEndpoint」](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dad5c-162">See [Set-CsHybridApplicationEndpoint](/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="dad5c-163">リソース アカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-163">To assign a Direct Routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   <span data-ttu-id="dad5c-164">リソース アカウントがトップ レベルの自動応答または通話キューに割り当てられる場合は、割り当てられた電話番号が必要です。</span><span class="sxs-lookup"><span data-stu-id="dad5c-164">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="dad5c-165">ユーザー (サブスクライバー) の電話番号をリソース アカウントに割り当て、サービスの有料電話番号またはフリーダイヤル電話番号のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dad5c-165">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

     <span data-ttu-id="dad5c-166">リソース アカウントに直接ルーティング番号またはハイブリッド番号を割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="dad5c-166">You can assign a Direct Routing or hybrid number to your resource account.</span></span> <span data-ttu-id="dad5c-167">詳細については、「Plan [Direct Routing and](/MicrosoftTeams/direct-routing-plan) Plan Cloud auto [attendants」を参照してください](plan-cloud-auto-attendant.md)。</span><span class="sxs-lookup"><span data-stu-id="dad5c-167">For details, see [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) and [Plan Cloud auto attendants](plan-cloud-auto-attendant.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="dad5c-168">自動応答と通話キューのリソース アカウントに割り当てられた直接ルーティング サービス番号は、Microsoft Teams のユーザーとエージェントでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="dad5c-168">Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.</span></span>

7. <span data-ttu-id="dad5c-169">電話システムの自動応答または通話キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-169">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="dad5c-170">次のいずれかをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dad5c-170">See one of the following:</span></span>

   - [<span data-ttu-id="dad5c-171">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="dad5c-171">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="dad5c-172">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="dad5c-172">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="dad5c-173">リソース アカウントを、以前に選択した電話システム自動応答または通話キューに関連付ける。</span><span class="sxs-lookup"><span data-stu-id="dad5c-173">Associate the resource account with the Phone System auto attendant or call queue you chose previously.</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="dad5c-174">電話番号のないリソース アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="dad5c-174">Create a resource account without a phone number</span></span>

<span data-ttu-id="dad5c-175">このセクションでは、オンプレミスのリソース アカウントの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-175">This section discusses creating a resource account that is homed on premises.</span></span> <span data-ttu-id="dad5c-176">オンラインでホームされているリソース アカウントの作成については、「Microsoft Teams のリソース アカウント [の管理」で説明します](/MicrosoftTeams/manage-resource-accounts)。</span><span class="sxs-lookup"><span data-stu-id="dad5c-176">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="dad5c-177">これらの手順は、新しい電話システム自動応答または通話キュー構造を作成するか、Exchange UM で最初に作成された構造を再構築するかに関して必要です。</span><span class="sxs-lookup"><span data-stu-id="dad5c-177">These steps are necessary whether you are creating a brand new Phone System auto attendant or call queue structure, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="dad5c-178">Skype for Business フロントエンド サーバーにログインし、次の PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-178">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="dad5c-179">電話システムの自動応答または通話キューごとにコマンドレットを実行して、オンプレミスのリソース アカウントを作成し、それぞれに名前 `New-CsHybridApplicationEndpoint` 、sip アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-179">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="dad5c-180">この [コマンドの詳細については、「New-CsHybridApplicationEndpoint」](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dad5c-180">See [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="dad5c-181">(省略可能)リソース アカウントを作成したら、AD がオンラインとオンプレミスの間で同期するのを待つか、同期を強制して電話システムの自動応答または通話キューのオンライン構成に進みます。</span><span class="sxs-lookup"><span data-stu-id="dad5c-181">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="dad5c-182">同期を強制するには、AAD Connect を実行しているコンピューターで次のコマンドを実行します (まだ実行していない場合は、コマンドを実行するために読み込む `import-module adsync` 必要があります)。</span><span class="sxs-lookup"><span data-stu-id="dad5c-182">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="dad5c-183">この [コマンドの詳細については、「Start-ADSyncSyncCycle」](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dad5c-183">See [Start-ADSyncSyncCycle](/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="dad5c-184">電話システムの自動応答または通話キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-184">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="dad5c-185">次のいずれかをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dad5c-185">See one of the following:</span></span>
   - [<span data-ttu-id="dad5c-186">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="dad5c-186">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="dad5c-187">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="dad5c-187">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="dad5c-188">以前に選択したリソース アカウントと電話システムの自動応答または通話キューを関連付ける。</span><span class="sxs-lookup"><span data-stu-id="dad5c-188">Associate the resource account and the Phone System auto attendant or call queue you chose previously.</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="dad5c-189">実装をテストする</span><span class="sxs-lookup"><span data-stu-id="dad5c-189">Test the implementation</span></span>

<span data-ttu-id="dad5c-190">実装をテストする最善の方法は、電話システム自動応答または通話キュー用に構成された番号を呼び出し、エージェントまたはメニューの 1 つに接続する方法です。</span><span class="sxs-lookup"><span data-stu-id="dad5c-190">The best way to test the implementation is to call the number configured for a Phone System auto attendant or call queue and connect to one of the agents or menus.</span></span> <span data-ttu-id="dad5c-191">管理センターの [操作] ウィンドウの [テスト] ボタンを使用して、 **テスト呼び** 出しをすばやく実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="dad5c-191">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="dad5c-192">電話システムの自動応答または通話キューに変更を加える場合は、そのキューを選択し、[操作] ウィンドウで [編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="dad5c-192">If you want to make changes to a Phone System auto attendant or call queue, select it and then in the Action pane click **Edit**.</span></span> 

> [!TIP]
> <span data-ttu-id="dad5c-193">リソース アカウントが通話キューまたは自動応答に割り当てられていない場合は、「Microsoft Teams の既知の問題」[](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)および[「Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system)ブログのハイブリッド アプリケーション インスタンスを修正する方法」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dad5c-193">If your resource account has difficulties with being assigned to a call queue or auto attendant, see [Known issues for Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) and the [How to fix my hybrid application instances](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) section in the Microsoft Teams Blog.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="dad5c-194">Exchange UM 自動応答または通話キューを電話システムに移動する</span><span class="sxs-lookup"><span data-stu-id="dad5c-194">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="dad5c-195">Exchange UM から電話システムへの移行では、通話キューと自動応答構造を再作成する必要があります。一方から別のキューへの直接移行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="dad5c-195">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="dad5c-196">一連の通話キューと自動応答を再実装するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-196">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="dad5c-197">管理者としてログインしている間、Exchange 2013 または 2016 システムで次のコマンドを実行して、すべての Exchange UM 自動応答と通話キューの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-197">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="dad5c-198">リストされている Exchange UM 通話キューまたは自動応答ごとに、構造、設定内の場所をメモし、関連付けられた音声ファイルまたは音声合成ファイルのコピーを取得します (出力の GUID は、ファイルが保存されているフォルダーの名前です)。</span><span class="sxs-lookup"><span data-stu-id="dad5c-198">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="dad5c-199">これらの詳細は、次のコマンドを実行して取得できます。</span><span class="sxs-lookup"><span data-stu-id="dad5c-199">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="dad5c-200">この [コマンドの詳細については、「Get-UMAutoAttendant」](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dad5c-200">See [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="dad5c-201">キャプチャする必要があるオプションの完全なリストは [UMAutoAttendant](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) メンバーですが、メモする最も重要なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dad5c-201">A complete list of options you might need to capture is at [UMAutoAttendant members](/previous-versions/office/exchange-server-api/ff340649(v=exchg.150)) but the most important options to note down are:</span></span>

    - <span data-ttu-id="dad5c-202">勤務時間</span><span class="sxs-lookup"><span data-stu-id="dad5c-202">Business hours</span></span>
    - <span data-ttu-id="dad5c-203">営業時間外</span><span class="sxs-lookup"><span data-stu-id="dad5c-203">Non-business hours</span></span>
    - <span data-ttu-id="dad5c-204">言語</span><span class="sxs-lookup"><span data-stu-id="dad5c-204">Language</span></span>
    - <span data-ttu-id="dad5c-205">休日のスケジュール</span><span class="sxs-lookup"><span data-stu-id="dad5c-205">Holiday schedule</span></span>

3. <span data-ttu-id="dad5c-206">前に説明したように、新しいオンプレミス エンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-206">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="dad5c-207">テストの目的で、一時的な番号をトップ レベルの自動応答に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="dad5c-207">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="dad5c-208">前述のように、エンドポイントを使用する電話システムの自動応答または通話キューを構成します。</span><span class="sxs-lookup"><span data-stu-id="dad5c-208">Configure a Phone System auto attendant or call queue that uses the endpoints as previously described.</span></span>

5. <span data-ttu-id="dad5c-209">電話システムの自動応答または通話キューをテストします。</span><span class="sxs-lookup"><span data-stu-id="dad5c-209">Test the Phone System auto attendant or call queue.</span></span>

6. <span data-ttu-id="dad5c-210">Exchange UM 通話キューまたは自動応答にリンクされている電話番号を、対応する電話システム自動応答または通話キューに再割り当てします。</span><span class="sxs-lookup"><span data-stu-id="dad5c-210">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone System auto attendant or call queue.</span></span>  

   <span data-ttu-id="dad5c-211">この時点で、UM ボイスメールを既に移行している場合は、2019 年に移行するExchange Serverがあります。</span><span class="sxs-lookup"><span data-stu-id="dad5c-211">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="dad5c-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="dad5c-212">See Also</span></span>

[<span data-ttu-id="dad5c-213">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="dad5c-213">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="dad5c-214">クラウドの自動応答とは</span><span class="sxs-lookup"><span data-stu-id="dad5c-214">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="dad5c-215">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="dad5c-215">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="dad5c-216">クラウド自動応答の計画</span><span class="sxs-lookup"><span data-stu-id="dad5c-216">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="dad5c-217">クラウド通話キューの計画</span><span class="sxs-lookup"><span data-stu-id="dad5c-217">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="dad5c-218">オンプレミス ユーザー向けクラウド ボイスメール サービスを計画する</span><span class="sxs-lookup"><span data-stu-id="dad5c-218">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="dad5c-219">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="dad5c-219">New-CsHybridApplicationEndpoint</span></span>](/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="dad5c-220">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="dad5c-220">New-CsOnlineApplicationInstance</span></span>](/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="dad5c-221">[Microsoft Teams でリソース アカウントを管理する](/MicrosoftTeams/manage-resource-accounts)  -  \(オンラインでホームのリソース アカウントを作成するには\)</span><span class="sxs-lookup"><span data-stu-id="dad5c-221">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>