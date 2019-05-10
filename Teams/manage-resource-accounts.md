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
ms.openlocfilehash: dea4a154e25c719ddabc572ba26ddb7d25c43d71
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835419"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="6f597-103">Microsoft Teams のリソースのアカウントの管理</span><span class="sxs-lookup"><span data-stu-id="6f597-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="6f597-104">リソース アカウントとも呼ばれる、一般にリソースを表すために使用できます、Azure Active Directory 内の無効なユーザー オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="6f597-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="6f597-105">Exchange ホスト ・ エージェントを使用するには、たとえば、会議室を表すし、電話番号を許可するようにすることがあります。</span><span class="sxs-lookup"><span data-stu-id="6f597-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="6f597-106">Microsoft 365 またはビジネス サーバーでは、Skype を使用して社内のリソース アカウントが所属することができ、Powershell コマンドを使用してこれらのアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="6f597-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="6f597-107">マイクロソフト チームまたは Skype のオンライン ビジネス、各呼び出しキュー、または自動アテンダントに関連するリソース アカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f597-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="6f597-108">リソース アカウントに、割り当てられた電話番号が必要かどうか、関連付けられている呼び出しキューの使用目的に依存しているまたは自動アテンダントです。</span><span class="sxs-lookup"><span data-stu-id="6f597-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="6f597-109">呼び出しキューでの記事を参照してくださいし、自動アテンダントのリソース アカウントに電話番号を割り当てる前に、この資料の下部にあるリンクされています。</span><span class="sxs-lookup"><span data-stu-id="6f597-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="6f597-110">この資料は、オンライン ビジネスは、マイクロソフトのチームと Skype の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6f597-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="6f597-111">リソース アカウントに電話番号を割り当てるための前提条件</span><span class="sxs-lookup"><span data-stu-id="6f597-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="6f597-112">開始することに注意することが重要。</span><span class="sxs-lookup"><span data-stu-id="6f597-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="6f597-113">自動アテンダントまたは呼び出しキューは、関連するリソース アカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f597-113">An auto attendant or call queue is required to have an associated resource account.</span></span> <span data-ttu-id="6f597-114">リソース アカウントの詳細については、[チーム内のリソース アカウントの管理](manage-resource-accounts.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f597-114">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="6f597-115">取得し、リソース アカウントに次のライセンスを割り当てる必要があります直接ルーティング番号を割り当てる場合は、 \(Office 365 エンタープライズ E1、E3、E5、電話システムのアドオンを\)。</span><span class="sxs-lookup"><span data-stu-id="6f597-115">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="6f597-116">取得し、リソース アカウントに次のライセンスを割り当てる必要がある場合は代わりに、マイクロソフトのサービス番号を割り当てることは、 \(Office 365 エンタープライズ E1、E3、E5、電話システムのアドオンを呼び出す計画と\)。</span><span class="sxs-lookup"><span data-stu-id="6f597-116">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="6f597-117">のみ、電話番号が割り当てられているリソース アカウントのライセンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f597-117">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="6f597-118">入れ子になった自動アテンダントまたは呼び出しキューでは自動応答の残りの部分にライセンスを取得またはそれに関連付けられた電話番号がない場合は、キューを呼び出す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6f597-118">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them</span></span>

> [!NOTE] 
> <span data-ttu-id="6f597-119">自動アテンダントおよび呼び出しキューの直接のルーティング サービスの番号は、マイクロソフトのチームのユーザーとエージェントだけでサポートされてです。</span><span class="sxs-lookup"><span data-stu-id="6f597-119">Direct Routing service numbers for auto attendant and call queues is supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE] 
> <span data-ttu-id="6f597-120">マイクロソフトは、ユーザー数ライセンス モデルを使用する必要がありますのクラウドの自動応答、通話キューなどのアプリケーションの適切なライセンス ・ モデルの中です。</span><span class="sxs-lookup"><span data-stu-id="6f597-120">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6f597-121">オンラインにいる人が、組織内への呼び出しをリダイレクトするには、エンタープライズ VoIP を有効にするし、Office 365 のプランを呼び出すことがある、**電話システム**のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="6f597-121">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="6f597-122">[マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f597-122">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="6f597-123">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6f597-123">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="6f597-124">たとえば、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6f597-124">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="6f597-125">リソース アカウントに直接ルーティング ハイブリッドの番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6f597-125">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="6f597-126">詳細については、[直接ルーティングの計画](direct-routing-plan.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f597-126">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="6f597-127">マイクロソフトの通話プランを割り当てることができますのみ有料電話番号と**マイクロソフトのチーム管理センター**にするか、または移植するフリー ダイヤル サービスの電話番号別のサービス プロバイダーからリソース アカウントにします。</span><span class="sxs-lookup"><span data-stu-id="6f597-127">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="6f597-128">取得し、サービスのフリー ダイヤル番号を使用して、通信のクレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f597-128">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="6f597-129">(サブスクライバー) をユーザーの電話番号は、リソース アカウントに割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="6f597-129">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="6f597-130">サービスの有料または無料の電話番号のみを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6f597-130">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="6f597-131">リソース アカウントに電話番号を割り当てる、する必要が取得するか、既存の有料または無料のサービスのポート番号です。</span><span class="sxs-lookup"><span data-stu-id="6f597-131">To assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="6f597-132">有料または無料のサービスの電話番号を取得した後表示されます**マイクロソフトのチーム管理センター**の > **音声** > **の電話番号**、および記述されている**数値型**は、**サービスのフリー ダイヤル**として一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f597-132">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="6f597-133">サービス番号を取得するには、[取得サービスの電話番号](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)を参照するか、既存のサービス番号に転送する場合は、 [Office 365 に転送電話の番号](transfer-phone-numbers-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f597-133">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6f597-134">米国以外のユーザーは、サービス番号を取得するマイクロソフトのチームの管理センターを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="6f597-134">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="6f597-135">[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する代わりに、米国の外側から行う方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f597-135">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="6f597-136">マイクロソフトのチーム管理センターのリソース アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="6f597-136">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="6f597-137">マイクロソフトのチーム管理センターでは、**組織全体の設定**に移動 > **リソースのアカウント**です。</span><span class="sxs-lookup"><span data-stu-id="6f597-137">In Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**.</span></span> 

![asd](media/r-a-master.png)

![番号 1](media/sfbcallout1.png)

<span data-ttu-id="6f597-140">新しいリソースを作成するには、アカウント**と新しいアカウント**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f597-140">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="6f597-141">、ポップアップで表示名を入力し、(ドメイン名を自動的に設定する必要があります)、リソース アカウントのユーザー名、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f597-141">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![リソース アカウント](media/res-acct.png)

<span data-ttu-id="6f597-143">次に、する必要があります、リソース アカウントにライセンスを適用する[ビジネス向けの Office 365 のユーザーにライセンスを割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)で説明するよう</span><span class="sxs-lookup"><span data-stu-id="6f597-143">Next, you will  need to apply a license to the resource account, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

<span data-ttu-id="6f597-144">![番号の 3](media/sfbcallout3.png) 、リソース アカウントを作成すると、ライセンスが割り当てられているアカウントに割り当てるサービス番号を呼び出すことを計画、リソース、**割り当て/割り当て解除**をクリックしてしたり、自動アテンダントまたは呼び出しキューにリソース アカウントを割り当てる既に存在します。</span><span class="sxs-lookup"><span data-stu-id="6f597-144">![number 3](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a Calling Plan service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="6f597-145">直接ルーティング番号を割り当てることを実行するコマンドレットを使用するだけです。</span><span class="sxs-lookup"><span data-stu-id="6f597-145">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="6f597-146">場合、呼び出しキューまたは自動アテンダントを作成する必要がある、それを作成するときにリソース アカウントをリンクすることができます。</span><span class="sxs-lookup"><span data-stu-id="6f597-146">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="6f597-147">終わったら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f597-147">Click **Save** when you are done.</span></span>

![リソース アカウントを割り当てる](media/r-a-assign.png)

<span data-ttu-id="6f597-149">![番号の 2](media/sfbcallout2.png) **の編集**] オプションを使用してリソース アカウントの表示名を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="6f597-149">![number 2](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span>  <span data-ttu-id="6f597-150">終わったら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f597-150">Click **Save** when you are done.</span></span>
<span data-ttu-id="6f597-151">![リソース アカウントを編集します。](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="6f597-151">![edit resource account](media/r-a-edit.png)</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="6f597-152">Powershell でのリソース アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="6f597-152">Create a resource account in Powershell</span></span>

<span data-ttu-id="6f597-153">マイクロソフトの通話プランを割り当てることができますのみ有料電話番号と**マイクロソフトのチーム管理センター**にするか、または移植するフリー ダイヤル サービスの電話番号別のサービス プロバイダーからリソース アカウントにします。</span><span class="sxs-lookup"><span data-stu-id="6f597-153">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="6f597-154">取得し、サービスのフリー ダイヤル番号を使用して、通信のクレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f597-154">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

<span data-ttu-id="6f597-155">かどうかによって、リソース アカウントにあるオンライン施設内で、適切な管理者特権を持つ Powershell プロンプトに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f597-155">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span> 
- <span data-ttu-id="6f597-156">[新規 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)を使用してオンラインのホーム リソース アカウントを作成するのには次の Powershell コマンドレットの例は、リソース アカウントのオンライン ホームをしました。</span><span class="sxs-lookup"><span data-stu-id="6f597-156">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="6f597-157">リソース アカウント ホーム設置型では、Skype のビジネス サーバー 2019 を呼び出してキューのクラウドとクラウドの自動応答で使用できる、[クラウドを呼び出してキューの構成](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md)や[クラウドの自動応答の構成](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f597-157">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="6f597-158">(番号が置かれている直接ルーティング) ハイブリッド実装では、[新しい CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f597-158">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="6f597-159">アプリケーション ID のインスタンスは、アプリケーションの作成時に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f597-159">The application ID's that you need to use while creating the application instances are:</span></span>
- <span data-ttu-id="6f597-160">**自動応答:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="6f597-160">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="6f597-161">**キューの呼び出し:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="6f597-161">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="6f597-162">呼び出しキューを選択した場合、または自動アテンダントのオンプレミスのユーザーが検索できるようにする場合は、オンラインのリソース アカウントが Active Directory に同期されていないため、リソース アカウントの設置型を作成してください。</span><span class="sxs-lookup"><span data-stu-id="6f597-162">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="6f597-163">作成するには、オンライン リソース アカウントを使用、自動アテンダントを使用して次のコマンドです。</span><span class="sxs-lookup"><span data-stu-id="6f597-163">To create a resource account online for use with an auto attendant, use the following command.</span></span>  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="6f597-164">ライセンスを適用するまで、リソース アカウントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="6f597-164">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="6f597-165">方法については O365 管理センターのアカウントにライセンスを適用するには、[ビジネス向けの Office 365 のユーザーにライセンスを割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user)と、[ビジネス ライセンスの割り当ての Skype](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f597-165">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="6f597-166">(省略可能)リソース アカウントに適切なライセンスが適用されるとは、次のように、リソース アカウントに電話番号を設定できます。</span><span class="sxs-lookup"><span data-stu-id="6f597-166">(Optional) Once the correct license is applied to the resource account you can  set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="6f597-167">すべてのリソース アカウントには、電話番号が必要となります。</span><span class="sxs-lookup"><span data-stu-id="6f597-167">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="6f597-168">リソース アカウントにライセンスを適用しなかった場合は、電話番号の割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="6f597-168">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="6f597-169">このコマンドの詳細については、[一連の CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f597-169">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="6f597-170">前述のように、マイクロソフトのチーム管理センターを使用してオンラインの電話番号を設定するのには最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="6f597-170">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="6f597-171">マイクロソフトのチーム管理センターのリソース アカウントの設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="6f597-171">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="6f597-172">マイクロソフトのチーム管理センターのリソース アカウントの設定を管理する**組織全体の設定**に移動  > **リソース アカウント**、リソース アカウントの設定を変更する必要があり、[**編集**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f597-172">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="6f597-173">**リソース アカウントの編集**画面で、これらの設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="6f597-173">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="6f597-174">アカウントの**表示名**</span><span class="sxs-lookup"><span data-stu-id="6f597-174">**Display name** for the account</span></span>
- <span data-ttu-id="6f597-175">キューを呼び出したり、自動アテンダント アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f597-175">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="6f597-176">アカウントに割り当てられた電話番号</span><span class="sxs-lookup"><span data-stu-id="6f597-176">Phone number assigned to the account</span></span>

<span data-ttu-id="6f597-177">終了したら、**保存**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f597-177">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="6f597-178">リソース アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="6f597-178">Delete a resource account</span></span>

<span data-ttu-id="6f597-179">保留中のモードでスタックしている、サービス番号が表示されないようにするのには、それを削除する前にリソース アカウントの電話番号の関連付けを解除することを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f597-179">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="6f597-180">次の内線番号を使用することを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6f597-180">You can do that using the following commandlet:</span></span> 

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```
                
<span data-ttu-id="6f597-181">その後は、O365 の管理者用ポータルの [ユーザー] タブから、リソース アカウントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="6f597-181">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>


## <a name="related-information"></a><span data-ttu-id="6f597-182">関連情報</span><span class="sxs-lookup"><span data-stu-id="6f597-182">Related Information</span></span>

<span data-ttu-id="6f597-183">ハイブリッド ビジネス サーバーの Skype では、実装。</span><span class="sxs-lookup"><span data-stu-id="6f597-183">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="6f597-184">クラウド自動応答の計画</span><span class="sxs-lookup"><span data-stu-id="6f597-184">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="6f597-185">クラウド自動応答の構成</span><span class="sxs-lookup"><span data-stu-id="6f597-185">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="6f597-186">チームまたは Skype のオンライン ビジネスの実装では。</span><span class="sxs-lookup"><span data-stu-id="6f597-186">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="6f597-187">クラウドの自動応答とは</span><span class="sxs-lookup"><span data-stu-id="6f597-187">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="6f597-188">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="6f597-188">Set up a Cloud auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="6f597-189">小規模ビジネスの例: 自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="6f597-189">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="6f597-190">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="6f597-190">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="6f597-191">新しい-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="6f597-191">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="6f597-192">新しい-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="6f597-192">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
