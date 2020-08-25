---
title: Skype for Business Server 2019 でリソースアカウントを構成する
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
description: Skype for Business Server 2019 のリソースアカウントをセットアップします。
ms.openlocfilehash: f3a9166f6e1bb9659a7fb43b9e7c35dba673f176
ms.sourcegitcommit: 32023931b607542cffadef74383e3ecd47db4ab6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868686"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="1c25f-103">リソース アカウントの構成</span><span class="sxs-lookup"><span data-stu-id="1c25f-103">Configure resource accounts</span></span>

<span data-ttu-id="1c25f-104">Skype for Business Server 2019 ハイブリッド実装では、ユニファイドメッセージング用の電話システムで提供されるクラウドサービスのみを使用し、Exchange Online とは統合されません。</span><span class="sxs-lookup"><span data-stu-id="1c25f-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="1c25f-105">Skype for Business Server 2019 では、「 [Microsoft 365 または Office 365 で電話システムを](/MicrosoftTeams/here-s-what-you-get-with-phone-system)使用する」で説明されているクラウド通話キューおよび自動応答を使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1c25f-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Microsoft 365 or Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="1c25f-106">Skype for Business Server 2019 で電話システムの自動応答または通話キューを使用するには、アプリケーションエンドポイントとして機能し、電話番号を割り当てることができるリソースアカウントを作成する必要があります。その後、オンライン Teams 管理センターを使用して、通話キューまたは自動応答を構成します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-106">To use an Phone System auto attendant or call queue with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="1c25f-107">このリソースアカウントは、この記事に記載されているように、オンラインにすることができます (「 [Microsoft Teams で](/MicrosoftTeams/manage-resource-accounts) リソースアカウントをホームにする」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="1c25f-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premises as described in this article.</span></span> <span data-ttu-id="1c25f-108">通常、複数の電話システムの自動応答または通話キューノードがあります。各ノードは、オンラインまたは Skype for Business Server 2019 に所属するリソースアカウントにマップされます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-108">Typically you will have multiple Phone System auto attendant or call queue nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="1c25f-109">既存の Exchange UM 自動応答と呼び出しキューシステムがある場合は、Exchange Server 2019 または Exchange online に切り替える前に、以下の説明に従って詳細を手動で記録し、Teams 管理センターを使用して完全に新しいシステムを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c25f-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="1c25f-110">概要</span><span class="sxs-lookup"><span data-stu-id="1c25f-110">Overview</span></span>

<span data-ttu-id="1c25f-111">電話システムの自動応答または呼び出しキューにサービス番号が必要な場合は、さまざまな依存関係を次の順序で満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-111">If your Phone System auto attendant or call queue will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="1c25f-112">サービス番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-112">Obtain a service number.</span></span>
2. <span data-ttu-id="1c25f-113">リソースアカウントで使用する無料電話システムの [仮想ユーザーライセンス](/MicrosoftTeams/teams-add-on-licensing/virtual-user) または有料電話システムのライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-113">Obtain a free Phone System - [Virtual User license](/MicrosoftTeams/teams-add-on-licensing/virtual-user) or a paid Phone System license to use with the resource account.</span></span>
3. <span data-ttu-id="1c25f-114">リソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-114">Create the resource account.</span></span> <span data-ttu-id="1c25f-115">関連付けられたリソースアカウントを持つには、自動応答または呼び出しキューが必要です。</span><span class="sxs-lookup"><span data-stu-id="1c25f-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="1c25f-116">オンラインとオンプレミスの間で active directory の同期が完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-116">Wait for an active directory sync between online and on premises.</span></span>
5. <span data-ttu-id="1c25f-117">電話システムのライセンスをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="1c25f-118">リソースアカウントにサービス番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="1c25f-119">電話システムの通話キューまたは自動応答を作成します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-119">Create a Phone System call queue or auto attendant.</span></span>
8. <span data-ttu-id="1c25f-120">リソースアカウントを自動応答または通話キューに関連付けます。 (新規-CsApplicationInstanceAssociation)。</span><span class="sxs-lookup"><span data-stu-id="1c25f-120">Associate the resource account with an auto attendant or call queue: (New-CsApplicationInstanceAssociation).</span></span>

<span data-ttu-id="1c25f-121">自動応答または呼び出しキューが最上位の自動応答の下にネストされている場合、関連付けられたリソースアカウントには、自動応答とコールキューの構造に複数のエントリポイントが必要な場合にのみ、電話番号が必要になります。</span><span class="sxs-lookup"><span data-stu-id="1c25f-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="1c25f-122">オンラインに所属している組織内のユーザーに通話をリダイレクトするには、 **電話システム** のライセンスが必要であり、エンタープライズ voip を有効にするか、Microsoft 365 または Office 365 の通話プランを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c25f-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="1c25f-123">「 [Microsoft Teams ライセンスを割り当てる](/MicrosoftTeams/assign-teams-licenses)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c25f-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="1c25f-124">エンタープライズ Voip を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="1c25f-125">たとえば、次のように実行します。  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="1c25f-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="1c25f-126">作成している電話システムの自動応答または呼び出しキューがネストされていて、電話番号は必要ない場合は、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="1c25f-126">If the Phone system auto attendant or call queue you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="1c25f-127">リソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="1c25f-127">Create the resource account</span></span>  
2. <span data-ttu-id="1c25f-128">オンラインとオンプレミスの間で active directory の同期を待つ</span><span class="sxs-lookup"><span data-stu-id="1c25f-128">Wait for an active directory sync between online and on premises</span></span>
3. <span data-ttu-id="1c25f-129">電話システムの自動応答または通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="1c25f-129">Create a Phone System auto attendant or call queue</span></span>
4. <span data-ttu-id="1c25f-130">リソースアカウントを電話システムの自動応答または通話キューに関連付ける</span><span class="sxs-lookup"><span data-stu-id="1c25f-130">Associate the resource account with a Phone System auto attendant or call queue</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="1c25f-131">電話番号を使用してリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="1c25f-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="1c25f-132">電話番号を使用するリソースアカウントを作成するには、次の順序でタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c25f-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="1c25f-133">有料または無料のサービス番号を取得または取得します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="1c25f-134">この番号は、他の音声サービスまたはリソースアカウントに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="1c25f-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="1c25f-135">リソースアカウントに電話番号を割り当てる前に、既存の有料または無料のサービス番号を取得または移植する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c25f-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="1c25f-136">有料またはフリーダイヤルのサービス電話番号を取得すると、 **Microsoft Teams の管理センター**の音声電話番号が表示され、一覧表示されて  >  **Voice**  >  **Phone numbers**いる**番号の種類**が [**サービス] フリーダイヤル**として表示されます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="1c25f-137">サービス番号を取得するには、「 [サービス電話番号を取得](/MicrosoftTeams/getting-service-phone-numbers) する」または「既存のサービス番号を移行する場合は、「 [電話番号を Teams に移行](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c25f-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](/MicrosoftTeams/phone-number-calling-plans/transfer-phone-numbers-to-teams).</span></span>

   <span data-ttu-id="1c25f-138">米国以外の地域では、Microsoft Teams 管理センターを使用してサービス番号を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="1c25f-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="1c25f-139">代わりに、「 [組織の電話番号を管理](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) する」に移動して、米国外からその方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="1c25f-140">電話システムのライセンスを購入します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-140">Buy a Phone System license.</span></span> <span data-ttu-id="1c25f-141">参照:</span><span class="sxs-lookup"><span data-stu-id="1c25f-141">See:</span></span>  
   - [<span data-ttu-id="1c25f-142">電話システム–仮想ユーザーライセンス</span><span class="sxs-lookup"><span data-stu-id="1c25f-142">Phone System–Virtual User license</span></span>](/MicrosoftTeams/teams-add-on-licensing/virtual-user)
   - [<span data-ttu-id="1c25f-143">Office 365 Enterprise E1 および E3</span><span class="sxs-lookup"><span data-stu-id="1c25f-143">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="1c25f-144">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="1c25f-144">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="1c25f-145">Office 365 Enterprise E5 ビジネスソフトウェア</span><span class="sxs-lookup"><span data-stu-id="1c25f-145">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="1c25f-146">`New-CsHybridApplicationEndpoint`各電話システムの自動応答またはコールキューに対してコマンドレットを実行し、それぞれの名前、sip アドレスなどを指定することによって、オンプレミスのリソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-146">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -ApplicationID <GUID> -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="1c25f-147">このコマンドの詳細については [、「CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c25f-147">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="1c25f-148">オプションリソースアカウントを作成したら、オンラインとオンプレミスの間で AD が同期されるまで待機するか、同期を強制して、電話システムの自動応答または呼び出しキューのオンライン構成に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-148">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="1c25f-149">同期を強制的に実行するには、AAD Connect を実行しているコンピュータで次のコマンドを実行します (まだ行っていない場合は `import-module adsync` 、コマンドを実行するためにロードする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="1c25f-149">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="1c25f-150">このコマンドの詳細については [、「Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c25f-150">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>
    
    <span data-ttu-id="1c25f-151">注: この時点で、アカウントは同期されていても、プロビジョニングが完了しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c25f-151">Note-at this point, the account may have synced, but provisioning may not be complete.</span></span>  <span data-ttu-id="1c25f-152">"Get-help" と [いう外部アプリケーションエンドポイント](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint)の出力を確認します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-152">Check the output of [Get-CsOnlineApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/get-csonlineapplicationendpoint).</span></span>  <span data-ttu-id="1c25f-153">同期されたエンドポイントの準備がまだ完了していない場合は、ここに表示されません。</span><span class="sxs-lookup"><span data-stu-id="1c25f-153">If the synced endpoint has not completed provisioning yet, then it will not appear here.</span></span>  <span data-ttu-id="1c25f-154">M365 ポータルの [ [Teams のセットアップの状態](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning)] で、プロビジョニング要求の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-154">You can check the status of the provisioning requests in the M365 portal under [Teams Setup Status](https://admin.microsoft.com/AdminPortal/Home#/teamsprovisioning).</span></span>  <span data-ttu-id="1c25f-155">このプロビジョニングフェーズには最大24時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1c25f-155">This provisioning phase can take up to 24 hours.</span></span>

5. <span data-ttu-id="1c25f-156">[電話システム-仮想ユーザーまたは電話システムのライセンスをリソースアカウントに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="1c25f-156">Assign the Phone System - Virtual User or Phone System license to the resource account.</span></span> <span data-ttu-id="1c25f-157">「 [Microsoft Teams アドオンライセンスを割り当てる](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) 」および「 [ユーザーにライセンスを割り当てる」を](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c25f-157">See [Assign Microsoft Teams add-on licenses](/MicrosoftTeams/teams-add-on-licensing/assign-teams-add-on-licenses) and [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

   <span data-ttu-id="1c25f-158">リソースアカウントに電話番号を割り当てる場合は、費用がかからない電話システム仮想ユーザーライセンスを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1c25f-158">If you are assigning a phone number to a resource account you can now use the cost-free Phone System - Virtual User license.</span></span> <span data-ttu-id="1c25f-159">これにより、組織レベルで電話番号に電話システム機能が提供され、自動応答と通話キュー機能を作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1c25f-159">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="1c25f-160">サービス番号をリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-160">Assign the service number to the resource account.</span></span> <span data-ttu-id="1c25f-161">コマンドを使用して、 `Set-CsHybridApplicationEndpoint` リソースアカウントに電話番号 (-LineURI オプションを指定) を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-161">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="1c25f-162">このコマンドの詳細については [、「CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c25f-162">See [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="1c25f-163">直接ルーティングまたはハイブリッド番号をリソースアカウントに割り当てるには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-163">To assign a Direct Routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

   <span data-ttu-id="1c25f-164">トップレベルの自動応答または呼び出しキューに割り当てられる場合は、リソースアカウントに、割り当てられた電話番号が必要です。</span><span class="sxs-lookup"><span data-stu-id="1c25f-164">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="1c25f-165">ユーザー (購読者) の電話番号をリソースアカウントに割り当てることはできません。サービスの有料またはフリーダイヤルの電話番号のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-165">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

     <span data-ttu-id="1c25f-166">直接ルーティングまたはハイブリッド番号をリソースアカウントに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-166">You can assign a Direct Routing or hybrid number to your resource account.</span></span> <span data-ttu-id="1c25f-167">詳細については、「 [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) And [plan Cloud auto アテンダント](plan-cloud-auto-attendant.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c25f-167">For details, see [Plan Direct Routing](/MicrosoftTeams/direct-routing-plan) and [Plan Cloud auto attendants](plan-cloud-auto-attendant.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="1c25f-168">自動応答および通話キューのリソースアカウントに割り当てられている直接ルーティングサービス番号は、Microsoft Teams のユーザーおよびエージェントに対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-168">Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.</span></span>

7. <span data-ttu-id="1c25f-169">電話システムの自動応答または通話キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-169">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="1c25f-170">次のいずれかをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1c25f-170">See one of the following:</span></span>

   - [<span data-ttu-id="1c25f-171">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="1c25f-171">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="1c25f-172">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="1c25f-172">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="1c25f-173">以前に選択した電話システム自動応答または通話キューに、リソースアカウントを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-173">Associate the resource account with the Phone System auto attendant or call queue you chose previously.</span></span>

<span data-ttu-id="1c25f-174">小規模ビジネスの実装の例については、Small business の例を参照してください。  [自動応答](/microsoftteams/tutorial-org-aa) および小規模ビジネスの例-設定するには、 [通話キューを](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq)設定します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-174">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="1c25f-175">電話番号なしでリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="1c25f-175">Create a resource account without a phone number</span></span>

<span data-ttu-id="1c25f-176">このセクションでは、オンプレミスに所属するリソースアカウントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-176">This section discusses creating a resource account that is homed on premises.</span></span> <span data-ttu-id="1c25f-177">オンラインに所属するリソースアカウントを作成する方法については、「 [Manage resource accounts In Microsoft Teams」](/MicrosoftTeams/manage-resource-accounts)をご説明します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-177">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="1c25f-178">これらの手順は、新しい電話システムの自動応答または呼び出しキューの構造を作成しているか、Exchange UM で作成された元の構造を再構築している場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="1c25f-178">These steps are necessary whether you are creating a brand new Phone System auto attendant or call queue structure, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="1c25f-179">Skype for Business フロントエンドサーバーにログインし、次の PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-179">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="1c25f-180">`New-CsHybridApplicationEndpoint`各電話システムの自動応答またはコールキューに対してコマンドレットを実行し、それぞれの名前、sip アドレスなどを指定することによって、オンプレミスのリソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-180">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System auto attendant or call queue, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="1c25f-181">このコマンドの詳細については [、「CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c25f-181">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="1c25f-182">オプションリソースアカウントを作成したら、オンラインとオンプレミスの間で AD が同期されるまで待機するか、同期を強制して、電話システムの自動応答または呼び出しキューのオンライン構成に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-182">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premises, or force a sync and proceed to online configuration of Phone System auto attendant or call queues.</span></span> <span data-ttu-id="1c25f-183">同期を強制的に実行するには、AAD Connect を実行しているコンピュータで次のコマンドを実行します (まだ行っていない場合は `import-module adsync` 、コマンドを実行するためにロードする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="1c25f-183">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="1c25f-184">このコマンドの詳細については [、「Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c25f-184">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="1c25f-185">電話システムの自動応答または通話キューを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-185">Create the Phone System auto attendant or call queue.</span></span> <span data-ttu-id="1c25f-186">次のいずれかをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1c25f-186">See one of the following:</span></span>
   - [<span data-ttu-id="1c25f-187">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="1c25f-187">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="1c25f-188">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="1c25f-188">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="1c25f-189">以前に選択した [リソースアカウント] および [電話システム] 自動応答または呼び出しキューを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-189">Associate the resource account and the Phone System auto attendant or call queue you chose previously.</span></span>

<span data-ttu-id="1c25f-190">小規模ビジネスの実装の例については、Small business の例を参照してください。  [自動応答](/microsoftteams/tutorial-org-aa) および小規模ビジネスの例-設定するには、 [通話キューを](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq)設定します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-190">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq).</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="1c25f-191">実装をテストする</span><span class="sxs-lookup"><span data-stu-id="1c25f-191">Test the implementation</span></span>

<span data-ttu-id="1c25f-192">実装をテストする最善の方法は、電話システムの自動応答または通話キュー用に構成された番号を呼び出して、いずれかのエージェントまたはメニューに接続することです。</span><span class="sxs-lookup"><span data-stu-id="1c25f-192">The best way to test the implementation is to call the number configured for a Phone System auto attendant or call queue and connect to one of the agents or menus.</span></span> <span data-ttu-id="1c25f-193">[管理センター] 操作ウィンドウの [ **テスト] ボタン** を使用して、テスト通話をすばやく配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-193">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="1c25f-194">電話システムの自動応答または通話キューを変更する場合は、それを選択し、操作ウィンドウで [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c25f-194">If you want to make changes to a Phone System auto attendant or call queue, select it and then in the Action pane click **Edit**.</span></span> 

> [!TIP]
> <span data-ttu-id="1c25f-195">リソースアカウントが通話キューまたは自動応答に割り当てられていない場合は、「microsoft [teams の既知の問題](/MicrosoftTeams/Known-issues#phone-system) 」および「Microsoft teams ブログの [ハイブリッドアプリケーションインスタンスを修正する方法](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c25f-195">If your resource account has difficulties with being assigned to a call queue or auto attendant, see [Known issues for Microsoft Teams](/MicrosoftTeams/Known-issues#phone-system) and the [How to fix my hybrid application instances](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521) section in the Microsoft Teams Blog.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="1c25f-196">電話システムへの Exchange UM 自動応答またはコールキューの移動</span><span class="sxs-lookup"><span data-stu-id="1c25f-196">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="1c25f-197">Exchange UM から電話システムへの移行では、通話キューと自動応答構造を再作成する必要があります。一方から他方へ直接移行することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1c25f-197">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="1c25f-198">呼び出しキューと自動応答のセットを再実装するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="1c25f-198">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="1c25f-199">管理者としてログインしているときに、Exchange 2013 または2016システムで次のコマンドを実行して、すべての Exchange UM 自動応答とコールキューの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-199">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="1c25f-200">一覧表示されている Exchange UM 呼び出しキューまたは自動応答のそれぞれについて、構造、設定、および関連する音声または音声合成ファイルのコピーを取得します (出力の guid は、ファイルが格納されているフォルダーの名前になります)。</span><span class="sxs-lookup"><span data-stu-id="1c25f-200">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="1c25f-201">これらの詳細を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-201">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="1c25f-202">このコマンドの詳細については [、「Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c25f-202">See [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="1c25f-203">取得する必要があるオプションの完全なリストは、 [Umautoattendant メンバー](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) ですが、メモするための最も重要なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1c25f-203">A complete list of options you might need to capture is at [UMAutoAttendant members](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) but the most important options to note down are:</span></span>

    - <span data-ttu-id="1c25f-204">勤務時間</span><span class="sxs-lookup"><span data-stu-id="1c25f-204">Business hours</span></span>
    - <span data-ttu-id="1c25f-205">勤務時間外</span><span class="sxs-lookup"><span data-stu-id="1c25f-205">Non-business hours</span></span>
    - <span data-ttu-id="1c25f-206">言語</span><span class="sxs-lookup"><span data-stu-id="1c25f-206">Language</span></span>
    - <span data-ttu-id="1c25f-207">休日のスケジュール</span><span class="sxs-lookup"><span data-stu-id="1c25f-207">Holiday schedule</span></span>

3. <span data-ttu-id="1c25f-208">前述したように、新しいオンプレミスエンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-208">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="1c25f-209">テストのために、最上位レベルの自動応答を一時的な番号に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1c25f-209">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="1c25f-210">前述のエンドポイントを使用する電話システムの自動応答または呼び出しキューを構成します。</span><span class="sxs-lookup"><span data-stu-id="1c25f-210">Configure a Phone System auto attendant or call queue that uses the endpoints as previously described.</span></span>

   <span data-ttu-id="1c25f-211">「 [Small business example」と](/microsoftteams/tutorial-org-aa) いうタイトルのチュートリアルの演習を使用すると、古い Exchange UM システムで階層の論理マップを作成するための手順がわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="1c25f-211">You may find it useful to use the exercises in the tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) to create a logical map of the hierarchies in your old Exchange UM system.</span></span>
5. <span data-ttu-id="1c25f-212">電話システムの自動応答または通話キューをテストします。</span><span class="sxs-lookup"><span data-stu-id="1c25f-212">Test the Phone System auto attendant or call queue.</span></span>
6. <span data-ttu-id="1c25f-213">Exchange UM 呼び出しキューまたは自動応答にリンクされている電話番号を、対応する電話システムの自動応答または通話キューに再割り当てします。</span><span class="sxs-lookup"><span data-stu-id="1c25f-213">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone System auto attendant or call queue.</span></span>  

   <span data-ttu-id="1c25f-214">この時点で、既に UM ボイスメールを移行している場合は、Exchange Server 2019 に移行する立場にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c25f-214">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c25f-215">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c25f-215">See Also</span></span>

[<span data-ttu-id="1c25f-216">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="1c25f-216">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="1c25f-217">クラウドの自動応答とは</span><span class="sxs-lookup"><span data-stu-id="1c25f-217">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="1c25f-218">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="1c25f-218">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="1c25f-219">クラウド自動応答の計画</span><span class="sxs-lookup"><span data-stu-id="1c25f-219">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="1c25f-220">クラウド通話キューの計画</span><span class="sxs-lookup"><span data-stu-id="1c25f-220">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="1c25f-221">オンプレミスユーザー用にクラウドボイスメールサービスを計画する</span><span class="sxs-lookup"><span data-stu-id="1c25f-221">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="1c25f-222">CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="1c25f-222">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="1c25f-223">新しい-Csonline Applicationinstance</span><span class="sxs-lookup"><span data-stu-id="1c25f-223">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="1c25f-224">[Microsoft Teams](/MicrosoftTeams/manage-resource-accounts)  -  \( でリソースアカウントを管理するオンラインになっているリソースアカウントを作成するには\)</span><span class="sxs-lookup"><span data-stu-id="1c25f-224">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>
