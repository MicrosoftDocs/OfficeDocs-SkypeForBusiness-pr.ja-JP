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
description: この記事では、Microsoft Teams でリソースアカウントを作成、編集、管理する方法について説明します。
ms.openlocfilehash: 2a043b608dfe311003dea26acc8a0c236460fad5
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031023"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="90130-103">Microsoft Teams のリソースのアカウントの管理</span><span class="sxs-lookup"><span data-stu-id="90130-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="90130-104">リソースアカウントは、Azure AD で無効になったユーザーオブジェクトであり、一般的なリソースを表すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="90130-104">A resource account is a disabled user object in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="90130-105">たとえば、リソースアカウントを Exchange で使って会議室を表示し、電話番号と予定表を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="90130-105">For example, a resource account may be used in Exchange to represent conference rooms and allow them to have a phone number and calendar.</span></span> <span data-ttu-id="90130-106">リソースアカウントは、Skype for Business Server 2019 を使って、Microsoft 365 またはオンプレミスのホームにすることができます。</span><span class="sxs-lookup"><span data-stu-id="90130-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="90130-107">Microsoft Teams では、各自動応答または通話キューにリソースアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="90130-107">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="90130-108">リソースアカウントには、サービスの電話番号を割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="90130-108">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="90130-109">これは、外部のチームからの発信者が自動応答または通話キューに到達することを許可する自動応答と通話キューに電話番号を割り当てる方法です。</span><span class="sxs-lookup"><span data-stu-id="90130-109">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

<span data-ttu-id="90130-110">この記事では、リソースアカウントを作成し、自動応答と通話キューで使用できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90130-110">This article covers how to create resource accounts and ready them for use with auto attendants and call queues.</span></span>

<span data-ttu-id="90130-111">この記事の手順を開始する前に、次の操作を実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="90130-111">Before you start the procedures in this article, ensure you've done the following:</span></span>

- [<span data-ttu-id="90130-112">仮想ユーザーライセンスを取得する</span><span class="sxs-lookup"><span data-stu-id="90130-112">Obtain virtual user licenses</span></span>](#obtain-virtual-user-licenses)
- [<span data-ttu-id="90130-113">サービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="90130-113">Obtain service numbers</span></span>](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="90130-114">仮想ユーザーライセンスを取得する</span><span class="sxs-lookup"><span data-stu-id="90130-114">Obtain virtual user licenses</span></span>

<span data-ttu-id="90130-115">自動応答と通話キューを使用するためには、各リソースアカウントにライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="90130-115">Each resource account requires a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="90130-116">無料の *Microsoft 365 電話システム仮想ユーザー* ライセンスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="90130-116">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span> <span data-ttu-id="90130-117">これらのライセンスを取得するには、「 [仮想ユーザーライセンス](teams-add-on-licensing/virtual-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90130-117">To obtain these licenses, see [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="90130-118">この記事で後述するリソースアカウントにライセンスを割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90130-118">We cover how to assign the license to a resource account later in this article.</span></span>

<span data-ttu-id="90130-119">仮想ユーザーライセンスを取得するには、Microsoft 365 管理センターで [ **課金**  >  **購入サービス**  >  **アドオンサブスクリプション** ] に移動し、[ *電話システム-仮想ユーザー* ライセンス] と表示されるまでスクロールします。</span><span class="sxs-lookup"><span data-stu-id="90130-119">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see *Phone System - Virtual User* license.</span></span> <span data-ttu-id="90130-120">[ **今すぐ購入** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="90130-120">Select **Buy now**.</span></span> <span data-ttu-id="90130-121">料金はゼロですが、ライセンスを取得するには、次の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="90130-121">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>

### <a name="obtain-service-numbers"></a><span data-ttu-id="90130-122">サービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="90130-122">Obtain service numbers</span></span>

<span data-ttu-id="90130-123">サービス番号は自動応答と通話キューではオプションですが、発信者が自動応答と通話キューの構成に到達するためには、少なくとも1つのサービス番号が必要です。</span><span class="sxs-lookup"><span data-stu-id="90130-123">Service numbers are optional for auto attendants and call queues, however you will need at least one service number in order for callers to reach your auto attendant and call queue configuration.</span></span> <span data-ttu-id="90130-124">サービス番号によって直接アクセスできるようにする自動応答または通話キューについては、関連付けられたサービス番号を持つリソースアカウントを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="90130-124">For any auto attendant or call queue that you want to be reachable directly by a service number, you must have a resource account with an associated service number.</span></span>

<span data-ttu-id="90130-125">リソースアカウントでは、有料または無料のサービス番号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="90130-125">Resource accounts can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="90130-126">別の電話会社から新しい番号を要求するか、既存の電話番号を移植できます。</span><span class="sxs-lookup"><span data-stu-id="90130-126">You can request new numbers or port existing numbers from another carrier.</span></span>

<span data-ttu-id="90130-127">新しいサービス番号を取得するには、「 [サービスの電話番号を取得](getting-service-phone-numbers.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90130-127">To get new service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="90130-128">別の電話会社の番号を移植するには、「 [電話番号を Teams に転送](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90130-128">To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="90130-129">リソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="90130-129">Create a resource account</span></span>

<span data-ttu-id="90130-130">Teams 管理センターでリソースアカウントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="90130-130">You can create a resource account in the Teams admin center.</span></span>

![リソースアカウントの追加のユーザーインターフェイスのスクリーンショット](media/resource-account-add.png)

1. <span data-ttu-id="90130-132">Teams 管理センターで、[ **組織全体の設定** ] を展開し、[ **リソースアカウント** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90130-132">In the Teams admin center, expand **Org-wide settings** , and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="90130-133">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90130-133">Click **Add**.</span></span>

3. <span data-ttu-id="90130-134">[ **リソースアカウントの追加** ] ウィンドウで、 **表示名** 、 **ユーザー名** 、 **リソースアカウントの種類** を入力します。</span><span class="sxs-lookup"><span data-stu-id="90130-134">In the **Add resource account** pane, fill out **Display name** , **Username** , and the **Resource account type**.</span></span> <span data-ttu-id="90130-135">リソースアカウントの種類は、このリソースアカウントの使用方法に応じて、 **自動応答** または **通話キュー** のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="90130-135">The resource account type can be either **Auto attendant** or **Call queue** , depending how you intend to use this resource account.</span></span>

4. <span data-ttu-id="90130-136">[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90130-136">Click **Save**.</span></span>

![リソースアカウントの一覧のスクリーンショット](media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="90130-138">ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="90130-138">Assign a license</span></span>

<span data-ttu-id="90130-139">リソースアカウントごとに、 *Microsoft 365 電話システム仮想ユーザー* ライセンスまたは *電話システム* ライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="90130-139">For each resource account, you must assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Microsoft 365 管理センターのライセンスの割り当てユーザーインターフェイスのスクリーンショット](media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="90130-141">Microsoft 365 管理センターで、ライセンスを割り当てるリソースアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="90130-141">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="90130-142">[ **ライセンスとアプリ** ] タブの [ **ライセンス** ] で、[ **Microsoft 365 Phone システム仮想ユーザー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="90130-142">On the **Licenses and Apps** tab, under **Licenses** , select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="90130-143">[ **Save changes** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90130-143">Click **Save changes**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="90130-144">サービス番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="90130-144">Assign a service number</span></span>

<span data-ttu-id="90130-145">自動応答または通話キューでサービス番号を必要とするリソースアカウントの使用を計画している場合は、リソースアカウントに番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="90130-145">If you're planning to use the resource account with an auto attendant or call queue that requires a service number, assign a number to the resource account.</span></span>

![サービス番号の割り当てユーザーインターフェイスのスクリーンショット](media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="90130-147">Teams 管理センターの [ **リソースアカウント** ] ページで、サービス番号を割り当てるリソースアカウントを選び、[ **割り当て/割り当て解除** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90130-147">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="90130-148">[ **電話番号の種類** ] ドロップダウンで、使用する番号の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="90130-148">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="90130-149">[ **割り当てられた電話番号** ] ボックスで、使用する番号を検索して [ **追加** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90130-149">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

4. <span data-ttu-id="90130-150">[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90130-150">Click **Save**.</span></span>


<span data-ttu-id="90130-151">リソースアカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90130-151">To assign a direct routing or hybrid number to a resource account you need to use PowerShell:</span></span>

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a><span data-ttu-id="90130-152">次のステップ</span><span class="sxs-lookup"><span data-stu-id="90130-152">Next steps</span></span>

<span data-ttu-id="90130-153">リソースアカウントの設定が完了し、必要に応じてサービス番号を割り当てると、自動応答または通話キューでリソースアカウントを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="90130-153">Once you've completed the resource account setup and assigning a service number if needed, you're ready to use the resource account with an auto attendant or call queue.</span></span>

<span data-ttu-id="90130-154">次の参考資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90130-154">See the following references:</span></span>

 - [<span data-ttu-id="90130-155">クラウド自動応答</span><span class="sxs-lookup"><span data-stu-id="90130-155">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

 - [<span data-ttu-id="90130-156">クラウド通話キュー</span><span class="sxs-lookup"><span data-stu-id="90130-156">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)

<span data-ttu-id="90130-157">[ **編集** ] オプションを使用して、リソースアカウントの **表示名** と **リソースアカウント** の種類を編集できます。</span><span class="sxs-lookup"><span data-stu-id="90130-157">You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="90130-158">完了したら、[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90130-158">Click **Save** when you are done.</span></span>

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="90130-159">仮想ユーザーライセンスを使用するように既存のリソースアカウントを変更する</span><span class="sxs-lookup"><span data-stu-id="90130-159">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="90130-160">既存のリソースアカウントのライセンスを **電話システム** のライセンスから仮想ユーザーライセンスに切り替える場合は、無料の仮想ユーザーライセンスを取得してから、Microsoft 365 管理センターの手順に従って、 [ユーザーを別のサブスクリプションに移動](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90130-160">If you decide to switch the licenses on your existing resource account from a **Phone System** license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="90130-161">常に完全な電話システムのライセンスを削除し、同じライセンスアクティビティに仮想ユーザーライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="90130-161">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="90130-162">古いライセンスを削除した場合は、アカウントの変更を保存し、新しいライセンスを追加してから、アカウント設定をもう一度保存すると、リソースアカウントが予期したとおりに機能しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="90130-162">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="90130-163">この問題が発生した場合は、仮想ユーザーライセンス用の新しいリソースアカウントを作成し、破損したリソースアカウントを削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90130-163">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="skype-for-business-server-2019"></a><span data-ttu-id="90130-164">Skype For Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="90130-164">Skype For Business Server 2019</span></span>

<span data-ttu-id="90130-165">クラウド通話キューとクラウド自動応答で使用できる Skype For Business Server 2019 上のリソースアカウントの場合は、「 [クラウド通話キューの計画](/SkypeforBusiness/hybrid/plan-call-queue) 」または「 [クラウド自動応答の計画](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90130-165">For resource accounts homed on Skype For Business Server 2019 that can be used with cloud call queues and cloud auto attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="90130-166">ハイブリッド実装 (直接ルーティングによる番号) は、オンプレミスの Skype for Business Server 2019 サーバー上の [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) コマンドレットを使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="90130-166">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="90130-167">アプリケーションインスタンスの作成時に使用する必要があるアプリケーション Id は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="90130-167">The application IDs that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="90130-168">**自動応答:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="90130-168">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="90130-169">**通話キュー:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="90130-169">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="90130-170">Skype For Business Server 2019 ユーザーが通話キューまたは自動応答を検索できるようにするには、オンラインリソースアカウントが Active Directory に同期されていないため、Skype For Business Server 2019 でリソースアカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90130-170">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="90130-171">Sipfederationtls 用の DNS SRV レコードが Skype for Business Server 2019 に解決された場合、SfB 管理シェルを使用して、Azure AD に同期されるように、Skype For Business Server 2019 でリソースアカウントを作成する **必要があり** ます。</span><span class="sxs-lookup"><span data-stu-id="90130-171">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to Azure AD.</span></span>

<span data-ttu-id="90130-172">Skype for Business Server とハイブリッドの実装の場合:</span><span class="sxs-lookup"><span data-stu-id="90130-172">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="90130-173">クラウド自動応答の計画</span><span class="sxs-lookup"><span data-stu-id="90130-173">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="90130-174">クラウド通話キューの計画</span><span class="sxs-lookup"><span data-stu-id="90130-174">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="90130-175">オンプレミスのリソースアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="90130-175">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a><span data-ttu-id="90130-176">リソースアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="90130-176">Delete a resource account</span></span>

<span data-ttu-id="90130-177">サービス番号が保留モードで停止しないようにするには、削除する前に必ず電話番号とリソースアカウントの関連付けを解除してください。</span><span class="sxs-lookup"><span data-stu-id="90130-177">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span>

<span data-ttu-id="90130-178">この操作を行うと、Microsoft 365 管理センターの [ユーザー] タブでリソースアカウントを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="90130-178">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="90130-179">リソースアカウントから直接ルーティングする電話番号との関連付けを解除するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="90130-179">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
