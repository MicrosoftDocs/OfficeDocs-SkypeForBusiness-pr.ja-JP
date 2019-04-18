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
ms.openlocfilehash: e8d3da4938a5040972b3c4853434808ca7457c90
ms.sourcegitcommit: 6949c957224949ccc6f5958d3c84294d382ee405
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "31914595"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="ec007-103">Microsoft Teams のリソースのアカウントの管理</span><span class="sxs-lookup"><span data-stu-id="ec007-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="ec007-104">リソース アカウントとも呼ばれる、一般にリソースを表すために使用できます、Azure Active Directory 内の無効なユーザー オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="ec007-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="ec007-105">Exchange ホスト ・ エージェントを使用するには、たとえば、会議室を表すし、電話番号を許可するようにすることがあります。</span><span class="sxs-lookup"><span data-stu-id="ec007-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="ec007-106">Microsoft 365 またはビジネス サーバーでは、Skype を使用して社内のリソース アカウントが所属することができ、Powershell コマンドを使用してこれらのアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="ec007-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="ec007-107">マイクロソフト チームまたは Skype のオンライン ビジネス、各呼び出しキュー、または自動アテンダントに関連するリソース アカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec007-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="ec007-108">リソース アカウントに、割り当てられた電話番号が必要かどうか、関連付けられている呼び出しキューの使用目的に依存しているまたは自動アテンダントです。</span><span class="sxs-lookup"><span data-stu-id="ec007-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="ec007-109">呼び出しキューでの記事を参照してくださいし、自動アテンダントのリソース アカウントに電話番号を割り当てる前に、この資料の下部にあるリンクされています。</span><span class="sxs-lookup"><span data-stu-id="ec007-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="ec007-110">この資料は、オンライン ビジネスは、マイクロソフトのチームと Skype の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ec007-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="ec007-111">リソース アカウントに電話番号を割り当てるための前提条件</span><span class="sxs-lookup"><span data-stu-id="ec007-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="ec007-112">開始することに注意することが重要。</span><span class="sxs-lookup"><span data-stu-id="ec007-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="ec007-113">自動アテンダントまたは呼び出しキューは、関連するリソース アカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec007-113">An auto attendant or call queue is required to have an associated resource account.</span></span> <span data-ttu-id="ec007-114">リソース アカウントの詳細については、[チーム内のリソース アカウントの管理](manage-resource-accounts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec007-114">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="ec007-115">取得し、リソース アカウントに次のライセンスを割り当てる必要があります直接ルーティング番号を割り当てる場合は、 \(Office 365 エンタープライズ E1、E3、E5、電話システムのアドオンを\)。</span><span class="sxs-lookup"><span data-stu-id="ec007-115">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="ec007-116">取得し、リソース アカウントに次のライセンスを割り当てる必要がある場合は代わりに、マイクロソフトのサービス番号を割り当てることは、 \(Office 365 エンタープライズ E1、E3、E5、電話システムのアドオンを呼び出す計画と\)。</span><span class="sxs-lookup"><span data-stu-id="ec007-116">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="ec007-117">のみ、電話番号が割り当てられているリソース アカウントのライセンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec007-117">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="ec007-118">入れ子になった自動アテンダントまたは呼び出しキューでは自動応答の残りの部分にライセンスを取得またはそれに関連付けられた電話番号がない場合は、キューを呼び出す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ec007-118">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them</span></span>

> [!NOTE] 
> <span data-ttu-id="ec007-119">直接ルーティング サービス番号の自動アテンダントと時点でのみマイクロソフトのチームのユーザーとエージェントのキューの呼び出しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ec007-119">Direct Routing service numbers for auto attendant and call queues is supported for Microsoft Teams users and agents only at the moment.</span></span>

> [!NOTE] 
> <span data-ttu-id="ec007-120">マイクロソフトは、ユーザー数ライセンス モデルを使用する必要がありますのクラウドの自動応答、通話キューなどのアプリケーションの適切なライセンス ・ モデルの中です。</span><span class="sxs-lookup"><span data-stu-id="ec007-120">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ec007-121">オンラインにいる人が、組織内への呼び出しをリダイレクトするには、エンタープライズ VoIP を有効にするし、Office 365 のプランを呼び出すことがある、**電話システム**のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="ec007-121">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="ec007-122">[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec007-122">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="ec007-123">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec007-123">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="ec007-124">たとえば、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ec007-124">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="ec007-125">リソース アカウントに直接ルーティング ハイブリッドの番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ec007-125">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="ec007-126">詳細については、[直接ルーティングの計画](direct-routing-plan.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec007-126">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="ec007-127">マイクロソフトの通話プランを割り当てることができますのみ有料電話番号と**マイクロソフトのチーム管理センター**にするか、または移植するフリー ダイヤル サービスの電話番号別のサービス プロバイダーからリソース アカウントにします。</span><span class="sxs-lookup"><span data-stu-id="ec007-127">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="ec007-128">取得し、サービスのフリー ダイヤル番号を使用して、通信のクレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec007-128">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="ec007-129">(サブスクライバー) をユーザーの電話番号は、リソース アカウントに割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="ec007-129">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="ec007-130">サービスの有料または無料の電話番号のみを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ec007-130">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="ec007-131">リソース アカウントに電話番号を割り当てる、する必要が取得するか、既存の有料または無料のサービスのポート番号です。</span><span class="sxs-lookup"><span data-stu-id="ec007-131">To assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="ec007-132">有料または無料のサービスの電話番号を取得した後表示されます**マイクロソフトのチーム管理センター**の > **音声** > **の電話番号**、および記述されている**数値型**は、**サービスのフリー ダイヤル**として一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec007-132">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="ec007-133">サービス番号を取得するには、[取得サービスの電話番号](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)を参照するか、既存のサービス番号に転送する場合は、 [Office 365 に転送電話の番号](transfer-phone-numbers-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec007-133">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec007-134">米国以外のユーザーは、サービス番号を取得するマイクロソフトのチームの管理センターを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="ec007-134">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="ec007-135">[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する代わりに、米国の外側から行う方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec007-135">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="ec007-136">マイクロソフトのチーム管理センターのリソース アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="ec007-136">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="ec007-137">マイクロソフトのチーム管理センターのリソース アカウントを作成するには、**組織全体の設定**に移動 > **リソース アカウント**を [ **+ 追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec007-137">To create a resource account  in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, then click **+ Add**.</span></span> <span data-ttu-id="ec007-138">、ポップアップで表示名を入力し、(ドメイン名を自動的に設定する必要があります)、リソース アカウントのユーザー名、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec007-138">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![リソース アカウント](media/res-acct.png)

<span data-ttu-id="ec007-140">必要、リソース アカウントにライセンスを適用する[ビジネス向けの Office 365 のユーザーにライセンスを割り当てる](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)で説明するよう</span><span class="sxs-lookup"><span data-stu-id="ec007-140">You will also need to apply a license to the resource account, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)</span></span>

<span data-ttu-id="ec007-141">リソース アカウントを作成し、ライセンスが割り当てられているまで、**割り当て/割り当て解除**または自動アテンダントまたは呼び出しキューにリソース アカウントを割り当てるには、リソース アカウントに電話番号を割り当てるにをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec007-141">Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a phone number to the resource account, or to assign the resource account to an auto attendant or call queue.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="ec007-142">Powershell でのリソース アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="ec007-142">Create a resource account in Powershell</span></span>

<span data-ttu-id="ec007-143">マイクロソフトの通話プランを割り当てることができますのみ有料電話番号と**マイクロソフトのチーム管理センター**にするか、または移植するフリー ダイヤル サービスの電話番号別のサービス プロバイダーからリソース アカウントにします。</span><span class="sxs-lookup"><span data-stu-id="ec007-143">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="ec007-144">取得し、サービスのフリー ダイヤル番号を使用して、通信のクレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec007-144">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

<span data-ttu-id="ec007-145">によってかどうか、電話番号のオンラインまたは設置型で、適切な管理者特権を持つ Powershell プロンプトに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec007-145">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>


- <span data-ttu-id="ec007-146">(番号が置かれている直接ルーティング) ハイブリッド実装は、設置型のホーム サーバーは、リソース アカウントを作成するのに[新規 CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)を使用します。</span><span class="sxs-lookup"><span data-stu-id="ec007-146">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="ec007-147">オンラインでだけは[新しい CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)を使用してオンライン ホーム サーバーは、リソース アカウントを持っています。</span><span class="sxs-lookup"><span data-stu-id="ec007-147">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="ec007-148">次は、自動アテンダント付きアプリケーション Id を持つリソース アカウントを作成するオンライン環境例です。</span><span class="sxs-lookup"><span data-stu-id="ec007-148">The following is an online environment example of creating resource account with an auto attendant ApplicationID.</span></span> <span data-ttu-id="ec007-149">呼び出しキューは、次付きアプリケーション Id 11cd3e2e-fccb-42ad-ad00-878b93575e07 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec007-149">For a call queue, you can use the following ApplicationID 11cd3e2e-fccb-42ad-ad00-878b93575e07:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

<span data-ttu-id="ec007-150">このコマンドの詳細については、[新規 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec007-150">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="ec007-151">次のセクションで説明したように、マイクロソフトのチーム管理センターを使用してオンラインの電話番号を設定するのには最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="ec007-151">It's easiest to set the online phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="ec007-152">使用することも、`Set-CsOnlineVoiceApplicationInstance`コマンドを割り当てるリソース アカウントに電話番号の最初の作成にようにします。</span><span class="sxs-lookup"><span data-stu-id="ec007-152">You can also use the `Set-CsOnlineVoiceApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="ec007-153">リソース アカウントを作成するときにライセンスを適用しない場合は、電話番号の割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="ec007-153">If you do not apply a license while creating the resource account the phone number assignment will fail.</span></span> 

<span data-ttu-id="ec007-154">このコマンドの詳細については、[一連の CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec007-154">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>



## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="ec007-155">マイクロソフトのチーム管理センターのリソース アカウントの設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="ec007-155">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="ec007-156">マイクロソフトのチーム管理センターのリソース アカウントの設定を管理する**組織全体の設定**に移動  > **リソース アカウント**、リソース アカウントの設定を変更する必要があり、[**編集**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec007-156">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="ec007-157">**リソース アカウントの編集**画面で、ことができますを変更します。</span><span class="sxs-lookup"><span data-stu-id="ec007-157">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="ec007-158">アカウントの**表示名**</span><span class="sxs-lookup"><span data-stu-id="ec007-158">**Display name** for the account</span></span>
- <span data-ttu-id="ec007-159">キューを呼び出したり、自動アテンダント アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="ec007-159">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="ec007-160">アカウントに割り当てられた電話番号</span><span class="sxs-lookup"><span data-stu-id="ec007-160">Phone number assigned to the account</span></span>

<span data-ttu-id="ec007-161">終了したら、**保存**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec007-161">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="ec007-162">関連情報</span><span class="sxs-lookup"><span data-stu-id="ec007-162">Related Information</span></span>

<span data-ttu-id="ec007-163">ハイブリッド ビジネス サーバーの Skype では、実装。</span><span class="sxs-lookup"><span data-stu-id="ec007-163">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="ec007-164">クラウド自動応答の計画</span><span class="sxs-lookup"><span data-stu-id="ec007-164">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="ec007-165">クラウド自動応答の構成</span><span class="sxs-lookup"><span data-stu-id="ec007-165">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="ec007-166">チームまたは Skype のオンライン ビジネスの実装では。</span><span class="sxs-lookup"><span data-stu-id="ec007-166">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="ec007-167">自動応答をクラウドとは?</span><span class="sxs-lookup"><span data-stu-id="ec007-167">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="ec007-168">クラウドの自動応答を設定します</span><span class="sxs-lookup"><span data-stu-id="ec007-168">Set up a Cloud auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="ec007-169">小規模ビジネスの例: 自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="ec007-169">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="ec007-170">クラウド呼び出しキューを作成します。</span><span class="sxs-lookup"><span data-stu-id="ec007-170">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="ec007-171">新しい-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="ec007-171">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="ec007-172">新しい-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="ec007-172">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
