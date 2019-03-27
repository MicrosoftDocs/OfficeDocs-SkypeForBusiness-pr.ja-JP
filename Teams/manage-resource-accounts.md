---
title: Teams のリソース アカウントを管理する
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: マイクロソフトのチーム内のリソース アカウントの管理についてください。
ms.openlocfilehash: ad435a812191cc8f7b9061ac5fba2bbe626b908e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886062"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="a46e9-103">Microsoft Teams のリソースのアカウントの管理</span><span class="sxs-lookup"><span data-stu-id="a46e9-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="a46e9-104">リソース アカウントとも呼ばれる、一般にリソースを表すために使用できます、Azure Active Directory 内の無効なユーザー オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="a46e9-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="a46e9-105">Exchange ホスト ・ エージェントを使用するには、たとえば、会議室を表すし、電話番号を許可するようにすることがあります。</span><span class="sxs-lookup"><span data-stu-id="a46e9-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="a46e9-106">Microsoft 365 またはビジネス サーバーでは、Skype を使用して社内のリソース アカウントが所属することができ、Powershell コマンドを使用してこれらのアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a46e9-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="a46e9-107">マイクロソフト チームまたは Skype のオンライン ビジネス、各呼び出しキュー、または自動アテンダントに関連するリソース アカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a46e9-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="a46e9-108">リソース アカウントに、割り当てられた電話番号が必要かどうか、関連付けられている呼び出しキューの使用目的に依存しているまたは自動アテンダントです。</span><span class="sxs-lookup"><span data-stu-id="a46e9-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="a46e9-109">呼び出しキューでの記事を参照してくださいし、自動アテンダントのリソース アカウントに電話番号を割り当てる前に、この資料の下部にあるリンクされています。</span><span class="sxs-lookup"><span data-stu-id="a46e9-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="a46e9-110">この資料は、オンライン ビジネスは、マイクロソフトのチームと Skype の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a46e9-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="a46e9-111">リソース アカウントに電話番号を割り当てるための前提条件</span><span class="sxs-lookup"><span data-stu-id="a46e9-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="a46e9-112">開始することに注意することが重要。</span><span class="sxs-lookup"><span data-stu-id="a46e9-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="a46e9-113">電話システムのライセンスを割り当てる、自動アテンダントまたは呼び出しキューに関連付けられますリソース アカウントにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a46e9-113">You need to assign a Phone System license to a resource account that will be associated with your auto attendant or call queue.</span></span> <span data-ttu-id="a46e9-114">ライセンスに関する詳細については、[マイクロソフトのチームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46e9-114">To learn more about licensing, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    

    > [!NOTE]
    > <span data-ttu-id="a46e9-115">オンラインにいる人が、組織内への呼び出しをリダイレクトするには、エンタープライズ VoIP を有効にするし、Office 365 のプランを呼び出すことがある、**電話システム**のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="a46e9-115">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="a46e9-116">[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46e9-116">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="a46e9-117">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a46e9-117">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="a46e9-118">たとえば、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a46e9-118">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="a46e9-119">リソース アカウントに直接ルーティング ハイブリッドの番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a46e9-119">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="a46e9-120">詳細については、[直接ルーティングの計画](direct-routing-plan.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46e9-120">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="a46e9-121">マイクロソフトの通話プランの有料電話番号と**マイクロソフトのチーム管理センター**でまたは別のサービス プロバイダーからリソースのアカウントに転送する電話番号をフリー ダイヤル サービスをのみ割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a46e9-121">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to a resource account.</span></span> <span data-ttu-id="a46e9-122">取得し、サービスのフリー ダイヤル番号を使用して、通信のクレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a46e9-122">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="a46e9-123">(サブスクライバー) をユーザーの電話番号は、リソース アカウントに割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="a46e9-123">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="a46e9-124">サービスの有料または無料の電話番号のみを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a46e9-124">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="a46e9-125">リソース アカウントに電話番号を割り当てる、取得、または、既存の有料または無料のサービスに転送する必要がある数値です。</span><span class="sxs-lookup"><span data-stu-id="a46e9-125">To assign a phone number to a resource account, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="a46e9-126">有料または無料のサービスの電話番号を取得した後表示されます**マイクロソフトのチーム管理センター**の > **音声** > **の電話番号**、および記述されている**数値型**は、**サービスのフリー ダイヤル**として一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a46e9-126">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="a46e9-127">サービス番号を取得するには、[取得サービスの電話番号](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)を参照するか、既存のサービス番号に転送する場合は、 [Office 365 に転送電話の番号](transfer-phone-numbers-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46e9-127">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a46e9-128">米国以外のユーザーは、サービス番号を取得するマイクロソフトのチームの管理センターを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="a46e9-128">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="a46e9-129">[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する代わりに、米国の外側から行う方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46e9-129">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="a46e9-130">Powershell でのリソース アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a46e9-130">Create a resource account in Powershell</span></span>

 <span data-ttu-id="a46e9-131">(1 つまたは複数リソース アカウント用)、必要に応じて該当する Powershell コマンドレットを実行して、リソース アカウントを作成し、名前 1 つずつというようにします。</span><span class="sxs-lookup"><span data-stu-id="a46e9-131">You would create a resource account by running the appropriate Powershell cmdlet as needed (for one or more resource accounts), and give each one a name and so on.</span></span> <span data-ttu-id="a46e9-132">現在、マイクロソフトのチーム管理センターで、リソース アカウントを作成するためのオプションはありませんが、電話番号を編集し、呼び出しキュー] または [自動アテンダントの割り当て、リソース アカウントを変更できます。</span><span class="sxs-lookup"><span data-stu-id="a46e9-132">There is currently no option for creating a resource account in the Microsoft Teams admin center, but you can edit phone numbers and change the call queue or auto attendant assignments for a resource account.</span></span>

<span data-ttu-id="a46e9-133">によってかどうか、電話番号のオンラインまたは設置型で、適切な管理者特権を持つ Powershell プロンプトに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a46e9-133">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="a46e9-134">(番号の数字が置かれている直接ルーティングでは、OPCH、CCE) ハイブリッド実装は、社内設置型のホーム サーバーがリソース アカウントを作成するのに[新規 CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)を使用します。</span><span class="sxs-lookup"><span data-stu-id="a46e9-134">Hybrid implementations (numbers numbers homed on Direct Routing, OPCH and CCE) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="a46e9-135">オンラインでだけは[新しい CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)を使用してオンライン ホーム サーバーは、リソース アカウントを持っています。</span><span class="sxs-lookup"><span data-stu-id="a46e9-135">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="a46e9-136">リソース アカウントを作成するオンライン環境例は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="a46e9-136">The following is an online environment example of creating a resource account:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

<span data-ttu-id="a46e9-137">このコマンドの詳細については、[新規 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46e9-137">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="a46e9-138">次のセクションで説明したように、マイクロソフトのチーム管理センターを使用してオンラインの電話番号を設定するのには最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="a46e9-138">It's easiest to set the online phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="a46e9-139">使用することも、`Set-CsOnlineVoiceApplicationInstance`コマンドを割り当てるリソース アカウントに電話番号の最初の作成にようにします。</span><span class="sxs-lookup"><span data-stu-id="a46e9-139">You can also use the `Set-CsOnlineVoiceApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber 19294450177
```

<span data-ttu-id="a46e9-140">このコマンドの詳細については、[一連の CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a46e9-140">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="a46e9-141">マイクロソフトのチーム管理センターのリソース アカウントの設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="a46e9-141">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="a46e9-142">マイクロソフトのチーム管理センターのリソース アカウントの設定を管理する**組織全体の設定**に移動  > **リソース アカウント**、リソース アカウントの設定を変更する必要があり、[**編集**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a46e9-142">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="a46e9-143">**リソース アカウントの編集**画面で、ことができますを変更します。</span><span class="sxs-lookup"><span data-stu-id="a46e9-143">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="a46e9-144">アカウントの**表示名**</span><span class="sxs-lookup"><span data-stu-id="a46e9-144">**Display name** for the account</span></span>
- <span data-ttu-id="a46e9-145">キューを呼び出したり、自動アテンダント アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="a46e9-145">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="a46e9-146">アカウントに割り当てられた電話番号</span><span class="sxs-lookup"><span data-stu-id="a46e9-146">Phone number assigned to the account</span></span>

<span data-ttu-id="a46e9-147">終了したら、**保存**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a46e9-147">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="a46e9-148">関連情報</span><span class="sxs-lookup"><span data-stu-id="a46e9-148">Related Information</span></span>

<span data-ttu-id="a46e9-149">ハイブリッド ビジネス サーバーの Skype では、実装。</span><span class="sxs-lookup"><span data-stu-id="a46e9-149">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="a46e9-150">クラウド自動応答の計画</span><span class="sxs-lookup"><span data-stu-id="a46e9-150">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="a46e9-151">クラウド自動応答の構成</span><span class="sxs-lookup"><span data-stu-id="a46e9-151">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="a46e9-152">チームまたは Skype のオンライン ビジネスの実装では。</span><span class="sxs-lookup"><span data-stu-id="a46e9-152">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="a46e9-153">電話システムの自動応答とは</span><span class="sxs-lookup"><span data-stu-id="a46e9-153">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="a46e9-154">電話システムの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="a46e9-154">Set up a Phone System auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="a46e9-155">小規模ビジネスの例: 自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="a46e9-155">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="a46e9-156">電話システムの呼び出しキューを作成する</span><span class="sxs-lookup"><span data-stu-id="a46e9-156">Create a Phone System call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="a46e9-157">新しい-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="a46e9-157">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="a46e9-158">新しい-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="a46e9-158">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
