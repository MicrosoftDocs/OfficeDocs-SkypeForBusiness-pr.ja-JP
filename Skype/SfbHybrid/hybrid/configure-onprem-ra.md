---
title: Skype for Business Server 2019 でリソースアカウントを構成する
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Skype for Business Server 2019 のリソースアカウントをセットアップします。
ms.openlocfilehash: 33211f7dcd56e402167a3c810343947d4dfe0954
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2019
ms.locfileid: "36160666"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="afd0f-103">リソースアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="afd0f-103">Configure resource accounts</span></span>

<span data-ttu-id="afd0f-104">Skype for Business Server 2019 ハイブリッド実装では、ユニファイドメッセージング用の電話システムで提供されるクラウドサービスのみを使用し、Exchange Online とは統合されません。</span><span class="sxs-lookup"><span data-stu-id="afd0f-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="afd0f-105">Skype for Business Server 2019 では、「 [Office で電話システムを](/MicrosoftTeams/here-s-what-you-get-with-phone-system)使用する方法」で説明されているクラウド通話キューと自動応答を使用できるようになりました365。</span><span class="sxs-lookup"><span data-stu-id="afd0f-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="afd0f-106">Skype for Business Server 2019 でこれらの電話システムサービスを使用するには、アプリケーションエンドポイントとして機能し、電話番号を割り当てることができるリソースアカウントを作成する必要があります。その後、オンライン Teams 管理センターを使用して、通話キューまたは自動応答を構成します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-106">To use these Phone System services with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="afd0f-107">このリソースアカウントは、この記事に記載されているように、オンラインにすることができます (「 [Microsoft Teams で](/MicrosoftTeams/manage-resource-accounts)リソースアカウントを管理する」を参照して、オンラインでリソースアカウントを作成してください)。</span><span class="sxs-lookup"><span data-stu-id="afd0f-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premise as described in this article.</span></span> <span data-ttu-id="afd0f-108">通常、複数の電話システムサービスノードがあり、それぞれがリソースアカウントにマップされています。各ノードは、オンラインまたは Skype for Business Server 2019 に所属することができます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-108">Typically you will have multiple Phone System service nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="afd0f-109">既存の Exchange UM 自動応答と呼び出しキューシステムがある場合は、Exchange Server 2019 または Exchange online に切り替える前に、以下の説明に従って詳細を手動で記録し、Teams 管理センターを使用して完全に新しいシステムを実装する必要があります。.</span><span class="sxs-lookup"><span data-stu-id="afd0f-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="afd0f-110">概要</span><span class="sxs-lookup"><span data-stu-id="afd0f-110">Overview</span></span>

<span data-ttu-id="afd0f-111">電話システムサービスにサービス番号が必要な場合は、さまざまな依存関係を次の順序で満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-111">If your Phone System service will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="afd0f-112">サービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="afd0f-112">Obtain a service number</span></span>
2. <span data-ttu-id="afd0f-113">電話システムのライセンスを購入する</span><span class="sxs-lookup"><span data-stu-id="afd0f-113">Buy a Phone System license</span></span>
3. <span data-ttu-id="afd0f-114">リソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-114">Create the resource account.</span></span> <span data-ttu-id="afd0f-115">関連付けられたリソースアカウントを持つには、自動応答または呼び出しキューが必要です。</span><span class="sxs-lookup"><span data-stu-id="afd0f-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="afd0f-116">オンラインとオンプレミスの間で active directory の同期を待つ</span><span class="sxs-lookup"><span data-stu-id="afd0f-116">Wait for an active directory sync between online and on premise</span></span>
5. <span data-ttu-id="afd0f-117">電話システムのライセンスをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="afd0f-118">リソースアカウントにサービス番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="afd0f-119">電話システムサービス (通話キューまたは自動応答) を作成する</span><span class="sxs-lookup"><span data-stu-id="afd0f-119">Create a Phone System service (a call queue or auto attendant)</span></span>
8. <span data-ttu-id="afd0f-120">リソースアカウントをサービスに関連付ける: (新規-CsApplicationInstanceAssociation)</span><span class="sxs-lookup"><span data-stu-id="afd0f-120">Associate the resource account with a service: (New-CsApplicationInstanceAssociation)</span></span>

<span data-ttu-id="afd0f-121">自動応答または呼び出しキューが最上位の自動応答の下にネストされている場合、関連付けられたリソースアカウントには、自動応答とコールキューの構造に複数のエントリポイントが必要な場合にのみ、電話番号が必要になります。</span><span class="sxs-lookup"><span data-stu-id="afd0f-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="afd0f-122">オンラインに所属している組織内のユーザーに通話をリダイレクトするには、**電話システム**のライセンスが必要であり、エンタープライズ voip を有効にするか、Office 365 通話プランを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afd0f-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="afd0f-123">「 [Microsoft Teams ライセンスを割り当てる](/MicrosoftTeams/assign-teams-licenses)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afd0f-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="afd0f-124">エンタープライズ Voip を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="afd0f-125">たとえば、次のように実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="afd0f-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="afd0f-126">作成している電話システムサービスがネストされていて、電話番号が必要ない場合は、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-126">If the Phone system service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="afd0f-127">リソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="afd0f-127">Create the resource account</span></span>  
2. <span data-ttu-id="afd0f-128">オンラインとオンプレミスの間で active directory の同期を待つ</span><span class="sxs-lookup"><span data-stu-id="afd0f-128">Wait for an active directory sync between online and on premise</span></span>
3. <span data-ttu-id="afd0f-129">電話システムサービスを作成する</span><span class="sxs-lookup"><span data-stu-id="afd0f-129">Create a Phone System service</span></span>
4. <span data-ttu-id="afd0f-130">リソースアカウントを電話システムサービスに関連付ける</span><span class="sxs-lookup"><span data-stu-id="afd0f-130">Associate the resource account with a Phone System service</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="afd0f-131">電話番号を使用してリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="afd0f-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="afd0f-132">電話番号を使用するリソースアカウントを作成するには、次の順序でタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afd0f-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="afd0f-133">有料または無料のサービス番号を取得または取得します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="afd0f-134">この番号は、他の音声サービスまたはリソースアカウントに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="afd0f-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="afd0f-135">リソースアカウントに電話番号を割り当てる前に、既存の有料または無料のサービス番号を取得または移植する必要があります。</span><span class="sxs-lookup"><span data-stu-id="afd0f-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="afd0f-136">有料またはフリーダイヤルのサービス電話番号を取得すると、 **Microsoft Teams の管理センター** > **の音声** > **電話番号**が表示され、一覧表示されている**番号の種類**が [サービス]**フリーダイヤル**として表示されます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="afd0f-137">サービス番号を取得するには、「[サービス電話番号を取得](/MicrosoftTeams/getting-service-phone-numbers)する」または「既存のサービス番号を移行する場合は、「[電話番号を Office 365 に移行](/MicrosoftTeams/transfer-phone-numbers-to-office-365)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afd0f-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365).</span></span>

   <span data-ttu-id="afd0f-138">米国以外の地域では、Microsoft Teams 管理センターを使用してサービス番号を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="afd0f-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="afd0f-139">代わりに、「[組織の電話番号を管理](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)する」に移動して、米国外からその方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="afd0f-140">電話システムのライセンスを購入します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-140">Buy a Phone System license.</span></span> <span data-ttu-id="afd0f-141">参照:</span><span class="sxs-lookup"><span data-stu-id="afd0f-141">See:</span></span>  
   - [<span data-ttu-id="afd0f-142">Office 365 Enterprise E1 および E3</span><span class="sxs-lookup"><span data-stu-id="afd0f-142">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="afd0f-143">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="afd0f-143">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="afd0f-144">Office 365 Enterprise E5 ビジネスソフトウェア</span><span class="sxs-lookup"><span data-stu-id="afd0f-144">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="afd0f-145">各電話システムサービスに対して`New-CsHybridApplicationEndpoint`コマンドレットを実行し、それぞれに名前、sip アドレスなどを指定することによって、オンプレミスのリソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-145">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="afd0f-146">このコマンドの詳細については[、「CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afd0f-146">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="afd0f-147">オプションリソースアカウントを作成したら、オンラインとオンプレミスの間で AD が同期されるまで待機するか、同期を強制して、電話システムサービスのオンライン構成に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-147">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="afd0f-148">同期を強制的に実行するには、AAD Connect を実行しているコンピュータで次のコマンドを実行します (まだ行っ`import-module adsync`ていない場合は、コマンドを実行するためにロードする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="afd0f-148">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="afd0f-149">このコマンドの詳細については[、「Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afd0f-149">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

5. <span data-ttu-id="afd0f-150">電話システムのライセンスをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-150">Assign the Phone System license to the resource account.</span></span> <span data-ttu-id="afd0f-151">「 [Microsoft Teams のライセンスを割り当て](/MicrosoftTeams/assign-teams-licenses)、[ライセンスを1ユーザーに割り当てる」を](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)参照してください。</span><span class="sxs-lookup"><span data-stu-id="afd0f-151">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>

    <span data-ttu-id="afd0f-152">リソースアカウントに電話番号を割り当てる場合は、費用がかからない電話システムの仮想ユーザーライセンスを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="afd0f-152">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="afd0f-153">これにより、組織レベルで電話番号に電話システム機能が提供され、自動応答と通話キュー機能を作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="afd0f-153">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="afd0f-154">サービス番号をリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-154">Assign the service number to the resource account.</span></span> <span data-ttu-id="afd0f-155">`Set-CsHybridApplicationEndpoint`コマンドを使用して、リソースアカウントに電話番号 (-lineuri オプションを指定) を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-155">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="afd0f-156">このコマンドの詳細については[、「CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afd0f-156">See [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="afd0f-157">直接ルーティングまたはハイブリッド番号をリソースアカウントに割り当てるには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-157">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

<span data-ttu-id="afd0f-158">トップレベルの自動応答または呼び出しキューに割り当てられる場合は、リソースアカウントに、割り当てられた電話番号が必要です。</span><span class="sxs-lookup"><span data-stu-id="afd0f-158">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="afd0f-159">ユーザー (購読者) の電話番号をリソースアカウントに割り当てることはできません。サービスの有料またはフリーダイヤルの電話番号のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-159">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

    You can assign a Direct Routing Hybrid number to your resource account.  See [Plan Direct Routing](direct-routing-plan) for details.

    > [!NOTE]
    > Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.

    > [!NOTE]
    > Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.

7. <span data-ttu-id="afd0f-160">電話システムサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-160">Create the Phone system service.</span></span> <span data-ttu-id="afd0f-161">次のいずれかをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="afd0f-161">See one of the following:</span></span>

   - [<span data-ttu-id="afd0f-162">クラウドの自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="afd0f-162">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="afd0f-163">クラウド通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="afd0f-163">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="afd0f-164">以前に選択した電話システムサービスにリソースアカウントを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-164">Associate the resource account with the Phone system service you chose previously.</span></span>

<span data-ttu-id="afd0f-165">小規模ビジネスの実装の例については、Small business の例を参照してください。[自動応答](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml)および小規模ビジネスの例-設定するには、[通話キューを](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml)設定します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-165">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="afd0f-166">電話番号なしでリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="afd0f-166">Create a resource account without a phone number</span></span>

<span data-ttu-id="afd0f-167">このセクションでは、オンプレミスのリソースアカウントを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-167">This section discusses creating a resource account that is homed on premise.</span></span> <span data-ttu-id="afd0f-168">オンラインに所属するリソースアカウントを作成する方法については、「 [Manage resource accounts In Microsoft Teams」](/MicrosoftTeams/manage-resource-accounts)をご説明します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-168">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="afd0f-169">これらの手順は、新しい電話システムのサービスシステムを作成しているか、Exchange UM で作成された元の構造を再構築している場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="afd0f-169">These steps are necessary whether you are creating a brand new Phone System service system, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="afd0f-170">Skype for Business フロントエンドサーバーにログインし、次の PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-170">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="afd0f-171">各電話システムサービスに対して`New-CsHybridApplicationEndpoint`コマンドレットを実行し、それぞれに名前、sip アドレスなどを指定することによって、オンプレミスのリソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-171">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="afd0f-172">このコマンドの詳細については[、「CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afd0f-172">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="afd0f-173">オプションリソースアカウントを作成したら、オンラインとオンプレミスの間で AD が同期されるまで待機するか、同期を強制して、電話システムサービスのオンライン構成に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-173">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="afd0f-174">同期を強制的に実行するには、AAD Connect を実行しているコンピュータで次のコマンドを実行します (まだ行っ`import-module adsync`ていない場合は、コマンドを実行するためにロードする必要があります)。</span><span class="sxs-lookup"><span data-stu-id="afd0f-174">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="afd0f-175">このコマンドの詳細については[、「Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afd0f-175">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="afd0f-176">電話システムサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-176">Create the Phone system service.</span></span> <span data-ttu-id="afd0f-177">次のいずれかをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="afd0f-177">See one of the following:</span></span>
   - [<span data-ttu-id="afd0f-178">クラウドの自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="afd0f-178">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="afd0f-179">クラウド通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="afd0f-179">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="afd0f-180">以前に選択したリソースアカウントと電話システムサービスを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-180">Associate the resource account and the Phone System service you chose previously.</span></span>

<span data-ttu-id="afd0f-181">小規模ビジネスの実装の例については、Small business の例を参照してください。[自動応答](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml)および小規模ビジネスの例-設定するには、[通話キューを](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml)設定します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-181">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="afd0f-182">実装をテストする</span><span class="sxs-lookup"><span data-stu-id="afd0f-182">Test the implementation</span></span>

<span data-ttu-id="afd0f-183">実装をテストする最善の方法は、電話システムサービスに対して構成された番号を呼び出し、エージェントまたはメニューの1つに接続することです。</span><span class="sxs-lookup"><span data-stu-id="afd0f-183">The best way to test the implementation is to call the number configured for a Phone System service and connect to one of the agents or menus.</span></span> <span data-ttu-id="afd0f-184">[管理センター] 操作ウィンドウの [**テスト] ボタン**を使用して、テスト通話をすばやく配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-184">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="afd0f-185">電話システムサービスを変更する場合は、それを選択してから、操作ウィンドウで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="afd0f-185">If you want to make changes to a Phone System service, select it and then in the Action pane click **Edit**.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="afd0f-186">電話システムへの Exchange UM 自動応答またはコールキューの移動</span><span class="sxs-lookup"><span data-stu-id="afd0f-186">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="afd0f-187">Exchange UM から電話システムへの移行では、通話キューと自動応答構造を再作成する必要があります。一方から他方へ直接移行することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="afd0f-187">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="afd0f-188">呼び出しキューと自動応答のセットを再実装するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="afd0f-188">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="afd0f-189">管理者としてログインしているときに、Exchange 2013 または2016システムで次のコマンドを実行して、すべての Exchange UM 自動応答とコールキューの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-189">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="afd0f-190">一覧表示されている Exchange UM 呼び出しキューまたは自動応答のそれぞれについて、構造、設定、および関連する音声または音声合成ファイルのコピーを取得します (出力の guid は、ファイルが格納されているフォルダーの名前になります)。</span><span class="sxs-lookup"><span data-stu-id="afd0f-190">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="afd0f-191">これらの詳細を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-191">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="afd0f-192">このコマンドの詳細については[、「Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afd0f-192">See [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="afd0f-193">取得する必要があるオプションの完全なリストは、 [Umautoattendant メンバー](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx)ですが、メモするための最も重要なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="afd0f-193">A complete list of options you might need to capture is at [UMAutoAttendant members](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) but the most important options to note down are:</span></span>

    - <span data-ttu-id="afd0f-194">勤務時間</span><span class="sxs-lookup"><span data-stu-id="afd0f-194">Business hours</span></span>
    - <span data-ttu-id="afd0f-195">勤務時間外</span><span class="sxs-lookup"><span data-stu-id="afd0f-195">Non-business hours</span></span>
    - <span data-ttu-id="afd0f-196">Language</span><span class="sxs-lookup"><span data-stu-id="afd0f-196">Language</span></span>
    - <span data-ttu-id="afd0f-197">休日のスケジュール</span><span class="sxs-lookup"><span data-stu-id="afd0f-197">Holiday schedule</span></span>

3. <span data-ttu-id="afd0f-198">前述したように、新しいオンプレミスエンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-198">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="afd0f-199">テストのために、最上位レベルの自動応答を一時的な番号に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="afd0f-199">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="afd0f-200">前述したエンドポイントを使用する電話システムサービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="afd0f-200">Configure a Phone system service that uses the endpoints as previously described.</span></span>

   <span data-ttu-id="afd0f-201">「 [Small business example」と](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml)いうタイトルのチュートリアルの演習を使用すると、古い Exchange UM システムで階層の論理マップを作成するための手順がわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="afd0f-201">You may find it useful to use the exercises in the tutorial titled [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) to create a logical map of the hierarchies in your old Exchange UM system.</span></span>
5. <span data-ttu-id="afd0f-202">電話システムサービスをテストします。</span><span class="sxs-lookup"><span data-stu-id="afd0f-202">Test the Phone System service.</span></span>
6. <span data-ttu-id="afd0f-203">Exchange UM 呼び出しキューまたは自動応答にリンクされている電話番号を、対応する電話システムサービスに再割り当てします。</span><span class="sxs-lookup"><span data-stu-id="afd0f-203">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone system service.</span></span>  

   <span data-ttu-id="afd0f-204">この時点で、既に UM ボイスメールを移行している場合は、Exchange Server 2019 に移行する立場にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="afd0f-204">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="afd0f-205">関連項目</span><span class="sxs-lookup"><span data-stu-id="afd0f-205">See Also</span></span>

[<span data-ttu-id="afd0f-206">クラウド通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="afd0f-206">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="afd0f-207">クラウド自動応答とは</span><span class="sxs-lookup"><span data-stu-id="afd0f-207">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="afd0f-208">クラウドの自動応答を設定する</span><span class="sxs-lookup"><span data-stu-id="afd0f-208">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="afd0f-209">クラウド自動応答を計画する</span><span class="sxs-lookup"><span data-stu-id="afd0f-209">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="afd0f-210">クラウド通話キューを計画する</span><span class="sxs-lookup"><span data-stu-id="afd0f-210">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="afd0f-211">オンプレミスユーザー用にクラウドボイスメールサービスを計画する</span><span class="sxs-lookup"><span data-stu-id="afd0f-211">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="afd0f-212">CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="afd0f-212">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="afd0f-213">新しい-Csonline Applicationinstance</span><span class="sxs-lookup"><span data-stu-id="afd0f-213">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="afd0f-214">[Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(のリソースアカウントを管理して、オンラインでリソースアカウントを作成する\)</span><span class="sxs-lookup"><span data-stu-id="afd0f-214">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>
