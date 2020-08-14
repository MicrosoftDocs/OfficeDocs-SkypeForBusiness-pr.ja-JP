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
ms.openlocfilehash: 90e8ab26782424c6cc341936f185a253c6d1fbe6
ms.sourcegitcommit: eb8b573a426b6a68c763968c4cd2d45bc0d6a4b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46672858"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="b2c7f-103">Microsoft Teams のリソースのアカウントの管理</span><span class="sxs-lookup"><span data-stu-id="b2c7f-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="b2c7f-104">リソースアカウントは、Azure AD で *無効になったユーザーオブジェクト* とも呼ばれ、一般にリソースを表すために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="b2c7f-105">Exchange では、会議室の代表として使用され、電話番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="b2c7f-106">リソースアカウントは、Skype for Business Server 2019 を使って、Microsoft 365 またはオンプレミスのホームにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="b2c7f-107">Microsoft Teams または Skype for Business Online では、各電話システムの通話キューまたは自動応答に、少なくとも1つのリソースアカウントが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have at least one associated resource account.</span></span> <span data-ttu-id="b2c7f-108">リソースアカウントが割り当てられた電話番号を必要とするかどうかは、次の図に示すように、関連付けられた通話キューまたは自動応答の用途によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="b2c7f-109">また、リソースアカウントに電話番号を割り当てる前に、この記事の下部にある通話キューと自動応答の記事を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

![リソースアカウントとユーザーライセンスの例](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="b2c7f-111">この記事は、Microsoft Teams と Skype for Business Online の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-111">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="b2c7f-112">Skype for Business Server 2019 を使用しているリソースアカウントの場合は、「 [リソースアカウントを構成する](/SkypeForBusiness/hybrid/configure-onprem-ra)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-112">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="assign-a-phone-number-to-a-phone-system-call-queue"></a><span data-ttu-id="b2c7f-113">電話システムの通話キューに電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="b2c7f-113">Assign a phone number to a Phone System call queue</span></span>

<span data-ttu-id="b2c7f-114">組織が既に少なくとも1つの電話システムライセンスを使用している場合、電話システムの通話キューに電話番号を割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-114">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue the process is:</span></span>

1. <span data-ttu-id="b2c7f-115">サービス番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-115">Obtain a service number.</span></span>
2. <span data-ttu-id="b2c7f-116">リソースアカウントまたは電話システムのライセンスと共に使用する、無料の電話システム [仮想ユーザーライセンス](teams-add-on-licensing/virtual-user.md) または有料電話システムライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-116">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="b2c7f-117">リソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-117">Create the resource account.</span></span> <span data-ttu-id="b2c7f-118">関連付けられているリソースアカウントを持つには、自動応答または通話キューが必要です。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-118">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="b2c7f-119">電話システムまたは電話システム仮想ユーザーライセンスをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-119">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="b2c7f-120">ライセンスを割り当てたリソースアカウントにサービスの電話番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-120">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="b2c7f-121">電話システムの通話キューまたは自動応答を作成する</span><span class="sxs-lookup"><span data-stu-id="b2c7f-121">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="b2c7f-122">リソースアカウントを通話キューまたは自動応答にリンクします。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-122">Link the resource account with a call queue or auto attendant.</span></span>

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

<span data-ttu-id="b2c7f-123">自動応答または通話キューが最上位の自動応答の下に入れ子になっている場合、関連付けられたリソースアカウントには、自動応答と通話キューの構造に複数のエントリポイントを追加する必要がある場合は、電話番号のみが必要です。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-123">If the auto attendant or call queue is nested under a top-level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="b2c7f-124">インターネットに接続している組織内のユーザーに通話をリダイレクトするには、 **電話システム** のライセンスが必要です。また、エンタープライズ voip を有効にするか、Microsoft 365 または Office 365 の通話プランを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-124">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Microsoft 365 or Office 365 Calling Plans.</span></span> <span data-ttu-id="b2c7f-125">「 [Microsoft Teams のアドオンライセンスを割り当てる](teams-add-on-licensing/assign-teams-add-on-licenses.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-125">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span> <span data-ttu-id="b2c7f-126">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="b2c7f-127">たとえば、次のように実行します。 `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="b2c7f-127">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="b2c7f-128">リソースアカウントで問題が発生しないようにするには、次の手順を順番に実行します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-128">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="b2c7f-129">作成している電話システムの通話キューまたは自動応答がネストされ、電話番号が必要ない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-129">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="b2c7f-130">リソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b2c7f-130">Create the resource account</span></span>
2. <span data-ttu-id="b2c7f-131">電話システムの通話キューまたは自動応答を作成する</span><span class="sxs-lookup"><span data-stu-id="b2c7f-131">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="b2c7f-132">リソースアカウントを電話システムの通話キューまたは自動応答に関連付ける</span><span class="sxs-lookup"><span data-stu-id="b2c7f-132">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="b2c7f-133">電話番号を使用してリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b2c7f-133">Create a resource account with a phone number</span></span>

<span data-ttu-id="b2c7f-134"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="b2c7f-134"><a name="phonenumber"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2c7f-135">電話番号は、自動応答または通話キューに直接割り当てられるのではなく、自動応答または通話キューに関連付けられているリソースアカウントに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-135">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

<span data-ttu-id="b2c7f-136">トップレベルの自動応答または通話キューでは、電話番号を自動応答にリンクさせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-136">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="b2c7f-137">電話番号を使用するリソースアカウントを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-137">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="b2c7f-138">有料または無料の有料サービス番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-138">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="b2c7f-139">この番号は、他のボイスサービスやリソースアカウントに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="b2c7f-140">リソースアカウントに電話番号を割り当てる前に、既存の有料または無料サービス番号を取得または移植する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-140">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="b2c7f-141">有料またはフリーダイヤルのサービス電話番号を取得すると、 **Microsoft Teams 管理センター**のボイス電話番号が表示され、  >  **Voice**  >  **Phone numbers\*\*\*\*番号の種類**は [**サービスの有料**電話] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-141">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="b2c7f-142">サービス番号を取得するには、「 [サービスの電話番号を取得](getting-service-phone-numbers.md) する」または「既存のサービス番号を移行する」を参照してください。「 [チームに電話番号を移行](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

   <span data-ttu-id="b2c7f-143">リソースアカウントに電話番号を割り当てる場合は、無料電話システムの仮想ユーザーライセンスを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-143">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="b2c7f-144">これにより、組織レベルで電話番号に電話システム機能が提供され、自動応答と通話キュー機能を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-144">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="b2c7f-145">電話システムの仮想ユーザーライセンスまたは通常の電話システムのライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-145">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span>

   <span data-ttu-id="b2c7f-146">仮想ユーザーライセンスを取得するには、Microsoft 365 管理センターで、[**課金**  >  **購入サービス**  >  **アドオンサブスクリプション**] に移動して、最後までスクロールします。 "電話システム-仮想ユーザー" ライセンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-146">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="b2c7f-147">[ **今すぐ購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-147">Select **Buy now**.</span></span> <span data-ttu-id="b2c7f-148">料金はゼロですが、ライセンスを取得するには、次の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-148">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="b2c7f-149">新しいリソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-149">Create a new resource account.</span></span> <span data-ttu-id="b2c7f-150">「 [Microsoft Teams 管理センターでリソースアカウントを作成](#create-a-resource-account-in-the-microsoft-teams-admin-center) する」または「 [PowerShell でリソースアカウントを作成](#create-a-resource-account-in-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-150">See [Create a resource account in the Microsoft Teams admin center](#create-a-resource-account-in-the-microsoft-teams-admin-center) or [Create a resource account in PowerShell](#create-a-resource-account-in-powershell).</span></span>
4. <span data-ttu-id="b2c7f-151">電話システムの [仮想ユーザーライセンス](teams-add-on-licensing/virtual-user.md) または電話システムのライセンスをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-151">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="b2c7f-152">「 [Microsoft Teams のアドオンライセンスの割り当て](teams-add-on-licensing/assign-teams-add-on-licenses.md) 」および「 [ユーザーへのライセンスの割り当て」を](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-152">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md) and [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>
5. <span data-ttu-id="b2c7f-153">サービス番号をリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-153">Assign the service number to the resource account.</span></span> <span data-ttu-id="b2c7f-154">「 [電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-154">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="b2c7f-155">次のいずれかを設定します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-155">Set up one of the following:</span></span>
   - [<span data-ttu-id="b2c7f-156">クラウド自動応答</span><span class="sxs-lookup"><span data-stu-id="b2c7f-156">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="b2c7f-157">クラウド通話キュー</span><span class="sxs-lookup"><span data-stu-id="b2c7f-157">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="b2c7f-158">リソースアカウントを自動応答または通話キューにリンクします。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-158">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="b2c7f-159">「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-159">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

<span data-ttu-id="b2c7f-160">自動応答の作成中にリソースアカウントを作成すると、ライセンスが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-160">When you create a resource account while creating an auto attendant, the licenses are applied automatically.</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="b2c7f-161">電話番号のないリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b2c7f-161">Create a resource account without a phone number</span></span>

<span data-ttu-id="b2c7f-162">入れ子になった自動応答または通話キューにはリソースアカウントが必要ですが、多くの場合、対応するリソースアカウントには電話番号とライセンスが必要であり、電話番号をサポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-162">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="b2c7f-163">電話番号を必要としないリソースアカウントを作成する場合は、次の手順で次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-163">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="b2c7f-164">新しいリソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-164">Create a new resource account.</span></span> <span data-ttu-id="b2c7f-165">「 [Microsoft Teams 管理センターでリソースアカウントを作成](#create-a-resource-account-in-the-microsoft-teams-admin-center) する」または「 [PowerShell でリソースアカウントを作成](#create-a-resource-account-in-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-165">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-the-microsoft-teams-admin-center) or [Create a resource account in PowerShell](#create-a-resource-account-in-powershell).</span></span>

2. <span data-ttu-id="b2c7f-166">次のいずれかを設定します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-166">Set up one of the following:</span></span>
   - [<span data-ttu-id="b2c7f-167">クラウド自動応答</span><span class="sxs-lookup"><span data-stu-id="b2c7f-167">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="b2c7f-168">クラウド通話キュー</span><span class="sxs-lookup"><span data-stu-id="b2c7f-168">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
   
3. <span data-ttu-id="b2c7f-169">リソースアカウントを通話キューまたは自動応答に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-169">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="b2c7f-170">「 [電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-170">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>


## <a name="create-a-resource-account-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="b2c7f-171">Microsoft Teams 管理センターでリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b2c7f-171">Create a resource account in the Microsoft Teams admin center</span></span>

<span data-ttu-id="b2c7f-172">電話システムのライセンスを購入したら、Microsoft Teams 管理センターの左側のナビゲーションで、[**組織全体の設定**]  >  **リソースアカウント**に移動します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-172">After you've bought a Phone System license, in the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Resource accounts**.</span></span>

![[リソースアカウント] ページのスクリーンショット](media/r-a-master.png)

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/teamscallout1.png)

<span data-ttu-id="b2c7f-175">新しいリソースアカウントを作成するには、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-175">To create a new resource account, click **Add**.</span></span> <span data-ttu-id="b2c7f-176">[ **リソースアカウントの追加** ] ウィンドウで、[ **表示名**]、[ **ユーザー名** ] (ドメイン名は自動的に設定されます)、リソースアカウントの **リソースアカウントの種類** を入力します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-176">In the **Add resource account** pane, fill out **Display name**, **Username** (the domain name should populate automatically), and **Resource account type** for the resource account.</span></span> <span data-ttu-id="b2c7f-177">リソースアカウントの種類は、リソースアカウントに関連付けるアプリに応じて、 **自動応答** または **通話キュー**のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-177">The resource account type can be either **Auto attendant** or **Call queue**, depending on the app you intend to associate to the resource account.</span></span> <span data-ttu-id="b2c7f-178">準備ができたら、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-178">When you're ready, click **Save**.</span></span>

![新しいリソースアカウントオプションのスクリーンショット](media/res-acct.png)

<span data-ttu-id="b2c7f-180">次に、「 [ユーザーにライセンスを割り当てる](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)」の説明に従って、Microsoft 365 管理センターのリソースアカウントにライセンスを適用します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-180">Next, apply a license to the resource account in the Microsoft 365 Admin center, as described in [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="edit-resource-account"></a><span data-ttu-id="b2c7f-181">リソースアカウントを編集する</span><span class="sxs-lookup"><span data-stu-id="b2c7f-181">Edit resource account</span></span> 

<span data-ttu-id="b2c7f-182">![数字2のアイコン。前のスクリーンショットで吹き出しを参照 ](media/teamscallout2.png) すると、[**編集**] オプションを使用してリソースアカウントの**表示名**と**リソースアカウント**の種類を編集できます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-182">![Icon of the number 2, referencing a callout in the previous screenshot](media/teamscallout2.png) You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="b2c7f-183">完了したら、[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-183">Click **Save** when you are done.</span></span>

![[リソースアカウントの編集] オプションのスクリーンショット](media/r-a-edit.png)

<span data-ttu-id="b2c7f-185"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="b2c7f-185"><a name="phonenumber"> </a></span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="b2c7f-186">電話番号とサービスの割り当て/割り当て解除を行う</span><span class="sxs-lookup"><span data-stu-id="b2c7f-186">Assign/unassign phone numbers and services</span></span>

<span data-ttu-id="b2c7f-187">![数値3のアイコン。 ](media/teamscallout3.png) リソースアカウントを作成してライセンスを割り当てた後、[ **割り当て/割り当て解除** ] をクリックして、リソースアカウントにサービス番号を割り当てるか、電話番号の種類を設定するか、または既に存在する特定の自動応答または通話キューにリソースアカウントを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-187">![Icon of the number 3, referencing a callout in the previous screenshot](media/teamscallout3.png) After you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, set the phone number type, or assign the resource account to a specific auto attendant or call queue that already exists.</span></span> <span data-ttu-id="b2c7f-188">直接ルーティング番号の割り当ては、コマンドレットを使用する場合にのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-188">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="b2c7f-189">リソースアカウントに関連付ける通話キューまたは自動応答をまだ作成していない場合は、このフィールドを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-189">If you haven't yet created the  call queue or auto attendant you will associate to the resource account, leave that field blank.</span></span> <span data-ttu-id="b2c7f-190">リソースアカウントを作成するときに、リンクを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-190">You can link the resource account while you create it.</span></span> <span data-ttu-id="b2c7f-191">完了したら、[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-191">Click **Save** when you are done.</span></span>

<span data-ttu-id="b2c7f-192">**電話番号の種類**のオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-192">Options for the **Phone number type** are:</span></span>

- <span data-ttu-id="b2c7f-193">なし</span><span class="sxs-lookup"><span data-stu-id="b2c7f-193">None</span></span>
- <span data-ttu-id="b2c7f-194">オンライン</span><span class="sxs-lookup"><span data-stu-id="b2c7f-194">Online</span></span>
- <span data-ttu-id="b2c7f-195">フリーダイヤル</span><span class="sxs-lookup"><span data-stu-id="b2c7f-195">Toll-free</span></span>
- <span data-ttu-id="b2c7f-196">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="b2c7f-196">On-premises</span></span>

![[割り当て/割り当て解除] オプションのスクリーンショット](media/r-a-assign.png)

<span data-ttu-id="b2c7f-198">リソースアカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、PowerShell を使用する必要があります。次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-198">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2c7f-199">リソースアカウントに有効なライセンスがない場合は、リソースアカウントに電話番号を割り当てようとしたときに、内部チェックによってエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-199">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="b2c7f-200">番号を割り当てることも、リソースアカウントを通話キューまたは自動応答に関連付けることもできません。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-200">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2c7f-201">電話番号は、自動応答または通話キューに直接割り当てられるのではなく、自動応答または通話キューに関連付けられているリソースアカウントに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-201">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="b2c7f-202">仮想ユーザーライセンスを使用するように既存のリソースアカウントを変更する</span><span class="sxs-lookup"><span data-stu-id="b2c7f-202">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="b2c7f-203">既存のリソースアカウントのライセンスを電話システムのライセンスから仮想ユーザーライセンスに切り替える場合は、無料の仮想ユーザーライセンスを取得してから、Microsoft 365 管理センターの手順に従って、 [ユーザーを別のサブスクリプションに移動](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-203">If you decide to switch the licenses on your existing resource account from a Phone System license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="b2c7f-204">常に完全な電話システムのライセンスを削除し、同じライセンスアクティビティに仮想ユーザーライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-204">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="b2c7f-205">古いライセンスを削除した場合は、アカウントの変更を保存し、新しいライセンスを追加してから、アカウント設定をもう一度保存すると、リソースアカウントが予期したとおりに機能しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-205">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="b2c7f-206">この問題が発生した場合は、仮想ユーザーライセンス用の新しいリソースアカウントを作成し、破損したリソースアカウントを削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-206">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="b2c7f-207">PowerShell でリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b2c7f-207">Create a resource account in PowerShell</span></span>

<span data-ttu-id="b2c7f-208">リソースアカウントがオンラインであるか、Skype for Business Server 2019 にあるかに応じて、管理者特権で適切な PowerShell プロンプトに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-208">Depending on whether your resource account is located online or on Skype for Business Server 2019, you would need to connect to the appropriate PowerShell prompt with Admin privileges.</span></span>

- <span data-ttu-id="b2c7f-209">次の PowerShell コマンドレットの例は、 [新しい-csonline Applicationinstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)を使って、オンラインでホームリソースアカウントを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-209">The following PowerShell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="b2c7f-210">クラウド通話キューとクラウド自動応答で使用できる Skype For Business Server 2019 上のリソースアカウントの場合は、「 [クラウド通話キューの計画](/SkypeforBusiness/hybrid/plan-call-queue) 」または「 [クラウド自動応答の計画](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-210">For resource accounts homed on Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="b2c7f-211">ハイブリッド実装 (直接ルーティングによる番号) は、オンプレミスの Skype for Business Server 2019 サーバー上の [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) コマンドレットを使用して構成されます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-211">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="b2c7f-212">アプリケーションインスタンスの作成時に使う必要があるアプリケーション ID は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-212">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="b2c7f-213">**自動応答:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="b2c7f-213">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="b2c7f-214">**通話キュー:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="b2c7f-214">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="b2c7f-215">Skype For Business Server 2019 ユーザーが通話キューまたは自動応答を検索できるようにするには、オンラインリソースアカウントが Active Directory に同期されていないため、Skype For Business Server 2019 でリソースアカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-215">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="b2c7f-216">Sipfederationtls 用の DNS SRV レコードが Skype for Business Server 2019 に解決される場合は、SfB 管理シェルを使用して、オンライン Azure AD に同期されるように、Skype For Business Server 2019 でリソースアカウントを作成する **必要があり** ます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-216">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to online Azure AD.</span></span>

 

1. <span data-ttu-id="b2c7f-217">自動応答で使用するためにオンラインでリソースアカウントを作成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-217">To create a resource account online for use with an auto attendant, use the following command:</span></span>

    ```powershell
    New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId "ce933385-9390-45d1-9512-c8d228074e07" -DisplayName "Resource account 1"
    ```

2. <span data-ttu-id="b2c7f-218">リソースアカウントは、ライセンスが適用されるまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-218">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="b2c7f-219">Microsoft 365 管理センターのアカウントにライセンスを適用する方法については、「[ユーザーへ](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) のライセンスの割り当て、および [Skype for business のライセンスの割り当て](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-219">To learn how to apply a license to an account in the Microsoft 365 admin center, see[Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="b2c7f-220">省略適切なライセンスをリソースアカウントに適用した後、次に示すように、リソースアカウントに電話番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-220">(Optional) After the correct license is applied to the resource account, you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="b2c7f-221">すべてのリソースアカウントで電話番号が必要になるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-221">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="b2c7f-222">リソースアカウントにライセンスを適用していない場合、電話番号の割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-222">If you didn't apply a license to the resource account, the phone number assignment will fail.</span></span>

   ```powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="b2c7f-223">このコマンドの詳細については [、「Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-223">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b2c7f-224">前に説明したように、Microsoft Teams 管理センターを使用してオンライン電話番号を設定するのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-224">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="b2c7f-225">Microsoft Teams または Skype For Business Server 2019 でのリソースアカウントに直接ルーティング電話番号を割り当てるには、次のコマンドレットを使用して Skype for Business Online PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-225">To assign a direct routing phone number to a resource account (homed either in Microsoft Teams or Skype For Business Server 2019), use the following cmdlet for Skype for Business Online PowerShell:</span></span>

   ```powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="b2c7f-226">Microsoft Teams 管理センターでリソースアカウント設定を管理する</span><span class="sxs-lookup"><span data-stu-id="b2c7f-226">Manage resource account settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="b2c7f-227">Microsoft Teams 管理センターでリソースアカウントの設定を管理するには、[**組織全体の設定**]  >  **リソースアカウント**に移動し、設定を変更する必要があるリソースアカウントを選び、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-227">To manage resource account settings in Microsoft Teams admin center, go to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click **Edit**.</span></span> <span data-ttu-id="b2c7f-228">[ **リソースアカウントの編集** ] ウィンドウで、次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-228">On the **Edit resource account** pane, you can change these settings:</span></span>

- <span data-ttu-id="b2c7f-229">アカウントの**表示名**</span><span class="sxs-lookup"><span data-stu-id="b2c7f-229">**Display name** for the account</span></span>
- <span data-ttu-id="b2c7f-230">アカウントを使う通話キューまたは自動応答</span><span class="sxs-lookup"><span data-stu-id="b2c7f-230">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="b2c7f-231">アカウントに割り当てられている電話番号</span><span class="sxs-lookup"><span data-stu-id="b2c7f-231">Phone number assigned to the account</span></span>

<span data-ttu-id="b2c7f-232">完了したら、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-232">When finished, click **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="b2c7f-233">リソースアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="b2c7f-233">Delete a resource account</span></span>

<span data-ttu-id="b2c7f-234">サービス番号が保留モードで停止しないようにするには、削除する前に必ず電話番号とリソースアカウントの関連付けを解除してください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-234">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="b2c7f-235">これは、次のコマンドレットを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-235">You can do that using the following cmdlet:</span></span>

```powershell
Set-CsOnlineVoiceApplicationInstance -Identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="b2c7f-236">この操作を行うと、Microsoft 365 管理センターの [ユーザー] タブでリソースアカウントを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-236">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="b2c7f-237">リソースアカウントから直接ルーティングする電話番号との関連付けを解除するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-237">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="b2c7f-238">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b2c7f-238">Troubleshooting</span></span>

### <a name="you-dont-see-the-phone-number-assigned-to-the-resource-account-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="b2c7f-239">Microsoft Teams 管理センターのリソースアカウントに割り当てられている電話番号が表示されない</span><span class="sxs-lookup"><span data-stu-id="b2c7f-239">You don't see the phone number assigned to the resource account in the Microsoft Teams admin center</span></span>

<span data-ttu-id="b2c7f-240">Microsoft Teams 管理センターのリソースアカウントに割り当てられている電話番号が表示されず、その番号を割り当てることができない場合は、次の点を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-240">If you don't see the phone number assigned to the resource account in the Microsoft Teams admin center and you are unable to assign the number from there, check the following:</span></span>

```powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="b2c7f-241">Department 属性で Skype for Business アプリケーションエンドポイントが表示される場合は、次のコマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-241">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below:</span></span>

```powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="b2c7f-242">Cmldet を実行した後に Teams 管理センターの web ページを更新すると、番号を正しく割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-242">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

### <a name="you-get-a-we-cant-use-this-resource-account-for-services-error-message"></a><span data-ttu-id="b2c7f-243">「このリソースアカウントをサービスに使用できません。」という説明が表示できます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-243">You get a "We can't use this resource account for services."</span></span> <span data-ttu-id="b2c7f-244">エラーメッセージ</span><span class="sxs-lookup"><span data-stu-id="b2c7f-244">error message</span></span>

<span data-ttu-id="b2c7f-245"><a name="blocksignin"> </a></span><span class="sxs-lookup"><span data-stu-id="b2c7f-245"><a name="blocksignin"> </a></span></span>

<span data-ttu-id="b2c7f-246">リソースアカウントを使用しようとすると、次のエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-246">You get the following error message when you try to use a resource account:</span></span>

<span data-ttu-id="b2c7f-247">"このリソースアカウントをサービスに使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-247">"We can't use this resource account for services.</span></span> <span data-ttu-id="b2c7f-248">リソースアカウントを無効にしてサインインをブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-248">The resource account must be DISABLED and BLOCKED from signing in.</span></span> <span data-ttu-id="b2c7f-249">Microsoft 365 管理センターの [ユーザー] ページで、このリソースアカウントのサインインをブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-249">You must BLOCK sign-ins for this resource account on the Users page in the Microsoft 365 admin center."</span></span>

<span data-ttu-id="b2c7f-250">既定では、リソースアカウントを作成すると、そのアカウントは無効になり、サインインはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-250">When you create a resource account, by default, it's disabled and sign in is blocked for the account.</span></span> <span data-ttu-id="b2c7f-251">これらの設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-251">These settings shouldn't be changed.</span></span> <span data-ttu-id="b2c7f-252">このエラーメッセージを解決するには、リソースアカウントがサインインするのをブロックします。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-252">To resolve this error message, block the resource account from signing in.</span></span> <span data-ttu-id="b2c7f-253">その手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-253">To do this:</span></span>

1. <span data-ttu-id="b2c7f-254">Microsoft 365 管理センターで、[ **ユーザー**]、[検索] の順に移動して、リソースアカウントを選びます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-254">In the Microsoft 365 admin center, go to **Users**, search for, and then select the resource account.</span></span>
2. <span data-ttu-id="b2c7f-255">表示名の下にあるウィンドウの上部で、[ **このユーザーをブロック**] をクリックし、[ **このユーザーをブロック** する] チェックボックスをオンにして、[ **変更を保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-255">At the top of the pane under the display name, click **Block this user?**, select the **Block this user from signing in** check box, and then select **Save changes**.</span></span>

   ![[このユーザーをブロック] オプションのスクリーンショット](media/res-acct-block.png)

    <span data-ttu-id="b2c7f-257">この操作を行うと、表示名の下に「サインインがブロックされました」と表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2c7f-257">After you do this, you'll see "Sign in blocked" under the display name.</span></span>

      ![サインインがブロックされたメッセージのスクリーンショット](media/res-acct-sign-in-blocked.png)

## <a name="related-information"></a><span data-ttu-id="b2c7f-259">関連情報</span><span class="sxs-lookup"><span data-stu-id="b2c7f-259">Related Information</span></span>

<span data-ttu-id="b2c7f-260">Skype for Business Server とハイブリッドの実装の場合:</span><span class="sxs-lookup"><span data-stu-id="b2c7f-260">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="b2c7f-261">クラウド自動応答の計画</span><span class="sxs-lookup"><span data-stu-id="b2c7f-261">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="b2c7f-262">クラウド通話キューの計画</span><span class="sxs-lookup"><span data-stu-id="b2c7f-262">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="b2c7f-263">オンプレミスのリソースアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="b2c7f-263">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="b2c7f-264">Teams または Skype for Business Online の実装の場合:</span><span class="sxs-lookup"><span data-stu-id="b2c7f-264">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="b2c7f-265">クラウドの自動応答とは</span><span class="sxs-lookup"><span data-stu-id="b2c7f-265">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="b2c7f-266">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="b2c7f-266">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="b2c7f-267">小規模ビジネスの例: 自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="b2c7f-267">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="b2c7f-268">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="b2c7f-268">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="b2c7f-269">新規-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="b2c7f-269">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="b2c7f-270">新しい Csonline Applicationinstance</span><span class="sxs-lookup"><span data-stu-id="b2c7f-270">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="b2c7f-271">新しい-Csonline Applicationinstanceassociation</span><span class="sxs-lookup"><span data-stu-id="b2c7f-271">New-CsOnlineApplicationInstanceAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstanceassociation?view=skype-ps)

[<span data-ttu-id="b2c7f-272">電話システム-仮想ユーザーライセンス</span><span class="sxs-lookup"><span data-stu-id="b2c7f-272">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
