---
title: Teams のリソース アカウントを管理する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: この記事では、リソース アカウントを作成、編集、管理する方法についてMicrosoft Teams。
ms.openlocfilehash: 21824c360e26e568ae47a9729960fca01a100ae8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094247"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="32369-103">Microsoft Teams のリソースのアカウントの管理</span><span class="sxs-lookup"><span data-stu-id="32369-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="32369-104">リソース アカウントは、Azure AD の無効なユーザー オブジェクトであり、一般的なリソースを表す場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="32369-104">A resource account is a disabled user object in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="32369-105">たとえば、会議室を表し、電話番号と予定表Exchangeリソース アカウントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="32369-105">For example, a resource account may be used in Exchange to represent conference rooms and allow them to have a phone number and calendar.</span></span> <span data-ttu-id="32369-106">リソース アカウントは、Microsoft 365 2019 を使用して、Skype for Business Serverできます。</span><span class="sxs-lookup"><span data-stu-id="32369-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="32369-107">このMicrosoft Teams、自動応答または通話キューごとにリソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="32369-107">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="32369-108">リソース アカウントには、サービスの電話番号が割り当て済みである場合があります。</span><span class="sxs-lookup"><span data-stu-id="32369-108">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="32369-109">これは、外部の発信者が自動応答または通話キューに到達できるように、Teamsに電話番号を自動応答と通話キューに割り当てる方法です。</span><span class="sxs-lookup"><span data-stu-id="32369-109">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

<span data-ttu-id="32369-110">この記事では、リソース アカウントを作成し、自動応答と通話キューで使用する準備をする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32369-110">This article covers how to create resource accounts and ready them for use with auto attendants and call queues.</span></span>

<span data-ttu-id="32369-111">この記事の手順を開始する前に、次の手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="32369-111">Before you start the procedures in this article, ensure you've done the following:</span></span>

- [<span data-ttu-id="32369-112">仮想ユーザー ライセンスの取得</span><span class="sxs-lookup"><span data-stu-id="32369-112">Obtain virtual user licenses</span></span>](#obtain-virtual-user-licenses)
- [<span data-ttu-id="32369-113">サービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="32369-113">Obtain service numbers</span></span>](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="32369-114">仮想ユーザー ライセンスの取得</span><span class="sxs-lookup"><span data-stu-id="32369-114">Obtain virtual user licenses</span></span>

<span data-ttu-id="32369-115">各リソース アカウントでは、自動応答と通話キューを操作するためにライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="32369-115">Each resource account requires a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="32369-116">無料の仮想マシン Microsoft 365 電話システム *ライセンスを使用* できます。</span><span class="sxs-lookup"><span data-stu-id="32369-116">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span> <span data-ttu-id="32369-117">これらのライセンスを取得するには、仮想ユーザー ライセンス [に関するページを参照してください](teams-add-on-licensing/virtual-user.md)。</span><span class="sxs-lookup"><span data-stu-id="32369-117">To obtain these licenses, see [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="32369-118">この記事の後半では、リソース アカウントにライセンスを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="32369-118">We cover how to assign the license to a resource account later in this article.</span></span>

<span data-ttu-id="32369-119">仮想ユーザー ライセンスを取得するには、Microsoft 365 管理センターで [課金購入サービス アドオン サブスクリプション] に移動し、最後までスクロールします。[電話システム - 仮想ユーザー ライセンス] が表示されます  >    >  。 </span><span class="sxs-lookup"><span data-stu-id="32369-119">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see *Phone System - Virtual User* license.</span></span> <span data-ttu-id="32369-120">[今 **すぐ購入] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="32369-120">Select **Buy now**.</span></span> <span data-ttu-id="32369-121">コストはかからないが、ライセンスを取得するには引き続き次の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="32369-121">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>

### <a name="obtain-service-numbers"></a><span data-ttu-id="32369-122">サービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="32369-122">Obtain service numbers</span></span>

<span data-ttu-id="32369-123">サービス番号は自動応答と通話キューでは省略可能ですが、発信者が自動応答と通話キューの構成に到達するには、少なくとも 1 つのサービス番号が必要です。</span><span class="sxs-lookup"><span data-stu-id="32369-123">Service numbers are optional for auto attendants and call queues, however you will need at least one service number in order for callers to reach your auto attendant and call queue configuration.</span></span> <span data-ttu-id="32369-124">サービス番号で直接到達できる自動応答または通話キューの場合は、関連付けられたサービス番号を持つリソース アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="32369-124">For any auto attendant or call queue that you want to be reachable directly by a service number, you must have a resource account with an associated service number.</span></span>

<span data-ttu-id="32369-125">リソース アカウントでは、有料または無料のサービス番号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="32369-125">Resource accounts can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="32369-126">新しい番号を要求したり、別の運送業者に既存の番号を移植したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="32369-126">You can request new numbers or port existing numbers from another carrier.</span></span>

<span data-ttu-id="32369-127">新しいサービス番号を取得するには、「サービス電話番号 [を取得する」を参照してください](getting-service-phone-numbers.md)。</span><span class="sxs-lookup"><span data-stu-id="32369-127">To get new service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="32369-128">別の運送業者から番号を移植するには、「電話番号を別の会社に転送[する」をTeams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="32369-128">To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="32369-129">リソース アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="32369-129">Create a resource account</span></span>

<span data-ttu-id="32369-130">リソース アカウントは、管理センター Teams作成できます。</span><span class="sxs-lookup"><span data-stu-id="32369-130">You can create a resource account in the Teams admin center.</span></span>

![リソース アカウントのユーザー インターフェイスの追加のスクリーンショット](media/resource-account-add.png)

1. <span data-ttu-id="32369-132">管理センター Teams、[組織全体の設定]**を展開し**、[リソース アカウント]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="32369-132">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="32369-133">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32369-133">Click **Add**.</span></span>

3. <span data-ttu-id="32369-134">[リソース **アカウントの追加] ウィンドウ** で、[表示名 **]、ユーザー** 名、および [リソース アカウントの種類]**に入力します**。</span><span class="sxs-lookup"><span data-stu-id="32369-134">In the **Add resource account** pane, fill out **Display name**, **Username**, and the **Resource account type**.</span></span> <span data-ttu-id="32369-135">リソース アカウントの種類は、**このリソース** アカウントの使い方に応じて、[自動応答] または [通話キュー] のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="32369-135">The resource account type can be either **Auto attendant** or **Call queue**, depending how you intend to use this resource account.</span></span>

4. <span data-ttu-id="32369-136">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32369-136">Click **Save**.</span></span>

![リソース アカウントの一覧のスクリーンショット](media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="32369-138">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="32369-138">Assign a license</span></span>

<span data-ttu-id="32369-139">リソース アカウントごとに、仮想ユーザー ライセンスまたは仮想ユーザー ライセンスMicrosoft 365 電話システム *割* り当てる *電話システム* があります。</span><span class="sxs-lookup"><span data-stu-id="32369-139">For each resource account, you must assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![管理センターでのライセンスの割り当てユーザー インターフェイスMicrosoft 365スクリーンショット](media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="32369-141">管理センター Microsoft 365、ライセンスを割り当てるリソース アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="32369-141">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="32369-142">[ライセンスと **アプリ] タブの**[ライセンス]**で**、[仮想Microsoft 365 電話システム **- 仮想ユーザー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="32369-142">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="32369-143">[変更の **保存] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="32369-143">Click **Save changes**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="32369-144">サービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="32369-144">Assign a service number</span></span>

<span data-ttu-id="32369-145">サービス番号を必要とする自動応答または通話キューでリソース アカウントを使用する予定がある場合は、リソース アカウントに番号を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="32369-145">If you're planning to use the resource account with an auto attendant or call queue that requires a service number, assign a number to the resource account.</span></span>

![サービス番号の割り当てユーザー インターフェイスのスクリーンショット](media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="32369-147">管理センター Teamsの [リソース アカウント]ページで、サービス番号を割り当てるリソース アカウントを選択し、[割り当て/割り当て解除]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="32369-147">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="32369-148">[数値 **電話] ドロップダウンで**、使用する数値の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="32369-148">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="32369-149">[割 **り当てられた電話番号]** ボックスで、使用する番号を検索し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="32369-149">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

4. <span data-ttu-id="32369-150">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32369-150">Click **Save**.</span></span>


<span data-ttu-id="32369-151">リソース アカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32369-151">To assign a direct routing or hybrid number to a resource account you need to use PowerShell:</span></span>

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a><span data-ttu-id="32369-152">次の手順</span><span class="sxs-lookup"><span data-stu-id="32369-152">Next steps</span></span>

<span data-ttu-id="32369-153">リソース アカウントのセットアップを完了し、必要に応じてサービス番号を割り当てると、自動応答または通話キューでリソース アカウントを使用する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="32369-153">Once you've completed the resource account setup and assigning a service number if needed, you're ready to use the resource account with an auto attendant or call queue.</span></span>

<span data-ttu-id="32369-154">次のリファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="32369-154">See the following references:</span></span>

 - [<span data-ttu-id="32369-155">クラウド自動応答</span><span class="sxs-lookup"><span data-stu-id="32369-155">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

 - [<span data-ttu-id="32369-156">クラウド通話キュー</span><span class="sxs-lookup"><span data-stu-id="32369-156">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)

<span data-ttu-id="32369-157">[編集] オプションを使用して、リソース アカウント **の** [表示名] と **[リソース** アカウントの種類] **を編集** できます。</span><span class="sxs-lookup"><span data-stu-id="32369-157">You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="32369-158">完了 **したら、[** 保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="32369-158">Click **Save** when you are done.</span></span>

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="32369-159">仮想ユーザー ライセンスを使用するために既存のリソース アカウントを変更する</span><span class="sxs-lookup"><span data-stu-id="32369-159">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="32369-160">既存のリソース アカウントのライセンスを 電話システム ライセンスから **仮想** ユーザー ライセンスに切り替える場合は、無料の仮想ユーザー ライセンスを取得し、Microsoft 365 管理センターの手順に従ってユーザーを別のサブスクリプションに移動する必要 [があります。](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)</span><span class="sxs-lookup"><span data-stu-id="32369-160">If you decide to switch the licenses on your existing resource account from a **Phone System** license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="32369-161">常に完全なライセンス 電話システム削除し、同じライセンス アクティビティで仮想ユーザー ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="32369-161">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="32369-162">古いライセンスを削除し、アカウントの変更を保存し、新しいライセンスを追加して、アカウント設定を再度保存すると、リソース アカウントが期待した通り機能しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="32369-162">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="32369-163">このような場合は、仮想ユーザー ライセンスの新しいリソース アカウントを作成し、壊れたリソース アカウントを削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="32369-163">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="skype-for-business-server-2019"></a><span data-ttu-id="32369-164">SkypeBusiness Server 2019 の場合</span><span class="sxs-lookup"><span data-stu-id="32369-164">Skype For Business Server 2019</span></span>

<span data-ttu-id="32369-165">クラウド通話キューとクラウド自動応答で使用できる Skype For Business Server 2019 にホームされているリソース アカウントについては、「クラウド[](/SkypeforBusiness/hybrid/plan-call-queue)通話キューの計画」または「クラウド自動応答を計画する」を参照[してください。](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)</span><span class="sxs-lookup"><span data-stu-id="32369-165">For resource accounts homed on Skype For Business Server 2019 that can be used with cloud call queues and cloud auto attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="32369-166">ハイブリッド実装 (ダイレクト ルーティングに含む番号) は、オンプレミスの Skype for Business Server 2019 サーバーで[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint)コマンドレットを使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="32369-166">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="32369-167">アプリケーション インスタンスの作成時に使用する必要があるアプリケーションの ID は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="32369-167">The application IDs that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="32369-168">**自動応答:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="32369-168">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="32369-169">**通話キュー:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="32369-169">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="32369-170">Skype For Business Server 2019 ユーザーが通話キューまたは自動応答を検索可能にしたい場合は、オンライン リソース アカウントが Active Directory に同期されないので、Skype For Business Server 2019 でリソース アカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32369-170">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="32369-171">sipfederationtls の DNS SRV レコードが Skype for Business Server 2019 に解決された場合は、SfB 管理シェルを使用して Skype For Business Server 2019 でリソース アカウントを作成し、Azure AD に同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="32369-171">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to Azure AD.</span></span>

<span data-ttu-id="32369-172">アプリケーションとハイブリッドである実装のSkype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="32369-172">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="32369-173">クラウド自動応答の計画</span><span class="sxs-lookup"><span data-stu-id="32369-173">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="32369-174">クラウド通話キューの計画</span><span class="sxs-lookup"><span data-stu-id="32369-174">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="32369-175">On-prem リソース アカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="32369-175">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a><span data-ttu-id="32369-176">リソース アカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="32369-176">Delete a resource account</span></span>

<span data-ttu-id="32369-177">サービス番号が保留中モードでスタックしないように、リソース アカウントを削除する前に、リソース アカウントから電話番号の関連付け解除を行います。</span><span class="sxs-lookup"><span data-stu-id="32369-177">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span>

<span data-ttu-id="32369-178">その後、管理センターの [ユーザー] タブでMicrosoft 365アカウントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="32369-178">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="32369-179">直接ルーティングの電話番号とリソース アカウントの関連付けを解除するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="32369-179">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```