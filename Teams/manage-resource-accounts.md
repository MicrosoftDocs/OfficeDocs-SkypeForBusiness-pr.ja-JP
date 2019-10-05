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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Microsoft Teams でリソースアカウントを管理する方法について説明します。
ms.openlocfilehash: 022163de7c3674fa0123927bad09a389514cc107
ms.sourcegitcommit: d349922409f49b52048597a56b81501163749a69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2019
ms.locfileid: "37401850"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="b52c6-103">Microsoft Teams のリソースのアカウントの管理</span><span class="sxs-lookup"><span data-stu-id="b52c6-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="b52c6-104">リソースアカウントは、Azure AD で*無効になったユーザーオブジェクト*とも呼ばれ、一般にリソースを表すために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="b52c6-105">Exchange では、会議室の代表として使用され、電話番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="b52c6-106">リソースアカウントは、Microsoft 365 または Skype for Business Server 2019 でホームにできます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-106">A resource account can be homed in Microsoft 365 or on Skype for Business Server 2019.</span></span>

<span data-ttu-id="b52c6-107">Microsoft Teams または Skype for Business Online では、各電話システムの通話キューまたは自動応答に、少なくとも1つのリソースアカウントが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b52c6-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have at least one associated resource account.</span></span> <span data-ttu-id="b52c6-108">リソースアカウントが割り当てられた電話番号を必要とするかどうかは、次の図に示すように、関連付けられた通話キューまたは自動応答の用途によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b52c6-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="b52c6-109">また、リソースアカウントに電話番号を割り当てる前に、この記事の下部にある通話キューと自動応答の記事を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b52c6-110">電話番号は、自動応答または通話キューに直接割り当てられるのではなく、自動応答または通話キューに関連付けられているリソースアカウントに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-110">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

![リソースアカウントとユーザーライセンスの例](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="b52c6-112">この記事は、Microsoft Teams と Skype for Business Online の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-112">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="b52c6-113">Skype for Business Server 2019 を使用しているリソースアカウントの場合は、「[リソースアカウントを構成する](/SkypeForBusiness/hybrid/configure-onprem-ra)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-113">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="overview"></a><span data-ttu-id="b52c6-114">概要</span><span class="sxs-lookup"><span data-stu-id="b52c6-114">Overview</span></span>

<span data-ttu-id="b52c6-115">組織が既に少なくとも1つの電話システムライセンスを使用している場合、電話システムの通話キューに電話番号を割り当てるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-115">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue the process is:</span></span>

1. <span data-ttu-id="b52c6-116">サービス番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-116">Obtain a service number.</span></span>
2. <span data-ttu-id="b52c6-117">リソースアカウントまたは電話システムのライセンスと共に使用する、無料の電話システム[仮想ユーザーライセンス](teams-add-on-licensing/virtual-user.md)または有料電話システムライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-117">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="b52c6-118">リソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-118">Create the resource account.</span></span> <span data-ttu-id="b52c6-119">関連付けられているリソースアカウントを持つには、自動応答または通話キューが必要です。</span><span class="sxs-lookup"><span data-stu-id="b52c6-119">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="b52c6-120">電話システムまたは電話システム仮想ユーザーライセンスをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-120">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="b52c6-121">ライセンスを割り当てたリソースアカウントにサービスの電話番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-121">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="b52c6-122">電話システムの通話キューまたは自動応答を作成する</span><span class="sxs-lookup"><span data-stu-id="b52c6-122">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="b52c6-123">リソースアカウントを通話キューまたは自動応答にリンクします。</span><span class="sxs-lookup"><span data-stu-id="b52c6-123">Link the resource account with a call queue or auto attendant.</span></span>

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

<span data-ttu-id="b52c6-124">自動応答または通話キューが最上位レベルの自動応答の下に入れ子になっている場合、関連付けられたリソースアカウントには、自動応答と通話キューの構造に複数のエントリポイントが必要な場合は、電話番号のみが必要になります。</span><span class="sxs-lookup"><span data-stu-id="b52c6-124">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="b52c6-125">組織内のユーザーにオンラインで接続されているユーザーに通話をリダイレクトするには、**電話システム**のライセンスが必要です。また、エンタープライズボイスに対して有効になっているか、Office 365 通話プランを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b52c6-125">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="b52c6-126">「 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-126">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="b52c6-127">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-127">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="b52c6-128">たとえば、次のように実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="b52c6-128">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="b52c6-129">リソースアカウントで問題が発生しないようにするには、次の手順を順番に実行します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-129">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="b52c6-130">作成している電話システムの通話キューまたは自動応答がネストされ、電話番号が必要ない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-130">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="b52c6-131">リソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b52c6-131">Create the resource account</span></span>
2. <span data-ttu-id="b52c6-132">電話システムの通話キューまたは自動応答を作成する</span><span class="sxs-lookup"><span data-stu-id="b52c6-132">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="b52c6-133">リソースアカウントを電話システムの通話キューまたは自動応答に関連付ける</span><span class="sxs-lookup"><span data-stu-id="b52c6-133">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="b52c6-134">電話番号を使用してリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b52c6-134">Create a resource account with a phone number</span></span>

<span data-ttu-id="b52c6-135"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="b52c6-135"></span></span>

> [!IMPORTANT]
> <span data-ttu-id="b52c6-136">電話番号は、自動応答または通話キューに直接割り当てられるのではなく、自動応答または通話キューに関連付けられているリソースアカウントに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-136">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

<span data-ttu-id="b52c6-137">トップレベルの自動応答または通話キューでは、電話番号を自動応答にリンクさせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b52c6-137">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="b52c6-138">電話番号を使用するリソースアカウントを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-138">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="b52c6-139">有料または無料の有料サービス番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-139">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="b52c6-140">この番号は、他のボイスサービスやリソースアカウントに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="b52c6-140">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="b52c6-141">リソースアカウントに電話番号を割り当てる前に、既存の有料または無料サービス番号を取得または移植する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b52c6-141">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="b52c6-142">有料またはフリーダイヤルのサービス電話番号を取得すると、 **Microsoft Teams 管理センター** > **のボイス** > **電話番号**が表示され、**番号の種類**は [**サービスの有料**電話] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-142">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="b52c6-143">サービス番号を取得するには、「[サービスの電話番号を取得](getting-service-phone-numbers.md)する」または「既存のサービス番号を移行する」を参照してください。「 [Office 365 に電話番号を転送](transfer-phone-numbers-to-office-365.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-143">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

   <span data-ttu-id="b52c6-144">リソースアカウントに電話番号を割り当てる場合は、無料電話システムの仮想ユーザーライセンスを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b52c6-144">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="b52c6-145">これにより、組織レベルで電話番号に電話システム機能が提供され、自動応答と通話キュー機能を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-145">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="b52c6-146">電話システムの仮想ユーザーライセンスまたは通常の電話システムのライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-146">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span>

   <span data-ttu-id="b52c6-147">仮想ユーザーライセンスを取得するには、Microsoft 365 管理センターから開始し、[**課金** > **購入サービス** > **アドオンサブスクリプション**] に移動して、"電話システム-仮想ユーザー" ライセンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-147">To get the Virtual User license, starting from the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="b52c6-148">[**今すぐ購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-148">Select **Buy now**.</span></span> <span data-ttu-id="b52c6-149">料金はゼロですが、ライセンスを取得するには、次の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b52c6-149">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="b52c6-150">新しいリソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-150">Create a new resource account.</span></span> <span data-ttu-id="b52c6-151">「 [Microsoft Teams 管理センターでリソースアカウントを作成](#create-a-resource-account-in-microsoft-teams-admin-center)する」または「 [Powershell でリソースアカウントを作成](#create-a-resource-account-in-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-151">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="b52c6-152">電話システムの[仮想ユーザーライセンス](teams-add-on-licensing/virtual-user.md)または電話システムのライセンスをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-152">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="b52c6-153">「 [Microsoft Teams ライセンスを割り当て](assign-teams-licenses.md)て、 [1 人のユーザーにライセンスを割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-153">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="b52c6-154">サービス番号をリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-154">Assign the service number to the resource account.</span></span> <span data-ttu-id="b52c6-155">「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-155">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="b52c6-156">次のいずれかを設定します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-156">Set up one of the following:</span></span>
   - [<span data-ttu-id="b52c6-157">クラウド自動応答</span><span class="sxs-lookup"><span data-stu-id="b52c6-157">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="b52c6-158">クラウド通話キュー</span><span class="sxs-lookup"><span data-stu-id="b52c6-158">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="b52c6-159">リソースアカウントを自動応答または通話キューにリンクします。</span><span class="sxs-lookup"><span data-stu-id="b52c6-159">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="b52c6-160">「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-160">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

<span data-ttu-id="b52c6-161">自動応答の作成中にリソースアカウントを作成すると、ライセンスが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-161">When you create a resource account while creating an auto attendant, the licenses are applied automatically.</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="b52c6-162">電話番号のないリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b52c6-162">Create a resource account without a phone number</span></span>

<span data-ttu-id="b52c6-163">入れ子になった自動応答または通話キューにはリソースアカウントが必要ですが、多くの場合、対応するリソースアカウントには電話番号とライセンスが必要であり、電話番号をサポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b52c6-163">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="b52c6-164">電話番号を必要としないリソースアカウントを作成する場合は、次の手順で次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b52c6-164">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="b52c6-165">新しいリソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-165">Create a new resource account.</span></span> <span data-ttu-id="b52c6-166">「 [Microsoft Teams 管理センターでリソースアカウントを作成](#create-a-resource-account-in-microsoft-teams-admin-center)する」または「 [Powershell でリソースアカウントを作成](#create-a-resource-account-in-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-166">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="b52c6-167">次のいずれかを設定します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-167">Set up one of the following:</span></span>
   - [<span data-ttu-id="b52c6-168">クラウド自動応答</span><span class="sxs-lookup"><span data-stu-id="b52c6-168">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="b52c6-169">クラウド通話キュー</span><span class="sxs-lookup"><span data-stu-id="b52c6-169">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="b52c6-170">リソースアカウントを通話キューまたは自動応答に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-170">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="b52c6-171">「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-171">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="b52c6-172">Microsoft Teams 管理センターでリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b52c6-172">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="b52c6-173">電話システムのライセンスを購入した後、Microsoft Teams 管理センターを使用して、[**組織全体の設定** > ]**リソースアカウント**に移動します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-173">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![[リソースアカウント] ページのスクリーンショット](media/r-a-master.png)

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="b52c6-176">新しいリソースアカウントを作成するには、[ **+ 新しいアカウント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b52c6-176">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="b52c6-177">ポップアップで、リソースアカウントの表示名とユーザー名 (ドメイン名が自動的に入力されます) を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b52c6-177">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![新しいリソースアカウントオプションのスクリーンショット](media/res-acct.png)

<span data-ttu-id="b52c6-179">次に、「一般[法人向け Office 365 でライセンスをユーザーに割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)」の説明に従って、O365 管理センターのリソースアカウントにライセンスを適用します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-179">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account-name"></a><span data-ttu-id="b52c6-180">リソースアカウント名を編集する</span><span class="sxs-lookup"><span data-stu-id="b52c6-180">Edit resource account name</span></span>

<span data-ttu-id="b52c6-181">![数字2のアイコン。前のスクリーンショット](media/sfbcallout2.png)で吹き出しを参照すると、[**編集**] オプションを使用してリソースアカウントの表示名を編集できます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-181">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span> <span data-ttu-id="b52c6-182">完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b52c6-182">Click **Save** when you are done.</span></span>
<span data-ttu-id="b52c6-183">![[リソースアカウントの編集] オプションのスクリーンショット](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="b52c6-183">![Screenshot of the Edit resource account option](media/r-a-edit.png)</span></span>

<a name="phonenumber"></a>
### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="b52c6-184">電話番号とサービスの割り当て/割り当て解除を行う</span><span class="sxs-lookup"><span data-stu-id="b52c6-184">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="b52c6-185">![番号3のアイコン、前のスクリーンショット](media/sfbcallout3.png)での吹き出しの参照リソースアカウントを作成してライセンスを割り当てた後、[**割り当て/割り当て解除**] をクリックして、リソースアカウントにサービス番号を割り当てるか、リソースを割り当てることができます。既に存在する自動応答または通話キューのアカウント。</span><span class="sxs-lookup"><span data-stu-id="b52c6-185">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="b52c6-186">直接ルーティング番号の割り当ては、コマンドレットを使用する場合にのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-186">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="b52c6-187">通話キューまたは自動応答をまだ作成する必要がある場合は、作成時にリソースアカウントをリンクすることができます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-187">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="b52c6-188">完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b52c6-188">Click **Save** when you are done.</span></span>

<span data-ttu-id="b52c6-189">リソースアカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、PowerShell を使用する必要があります。次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-189">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b52c6-190">リソースアカウントに有効なライセンスがない場合は、リソースアカウントに電話番号を割り当てようとしたときに、内部チェックによってエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-190">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="b52c6-191">番号を割り当てることも、リソースアカウントを通話キューまたは自動応答に関連付けることもできません。</span><span class="sxs-lookup"><span data-stu-id="b52c6-191">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

![[割り当て/割り当て解除] オプションのスクリーンショット](media/r-a-assign.png)

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="b52c6-193">仮想ユーザーライセンスを使用するように既存のリソースアカウントを変更する</span><span class="sxs-lookup"><span data-stu-id="b52c6-193">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="b52c6-194">既存のリソースアカウントのライセンスを電話システムのライセンスから仮想ユーザーライセンスに切り替える場合は、無料の仮想ユーザーライセンスを取得し、Microsoft 365 管理センターのリンクされた手順に従ってユーザーをに移行する必要があります。 [別](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription)の月額プラン。</span><span class="sxs-lookup"><span data-stu-id="b52c6-194">If you decide to switch the licenses on your existing resource account from a Phone system license to a Virtual User license, you'll need to acquire the free Virtual User license, then follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="b52c6-195">常に完全な電話システムのライセンスを削除し、同じライセンスアクティビティに仮想ユーザーライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-195">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="b52c6-196">古いライセンスを削除した場合は、アカウントの変更を保存し、新しいライセンスを追加してから、アカウント設定をもう一度保存すると、リソースアカウントが予期したとおりに機能しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="b52c6-196">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="b52c6-197">この問題が発生した場合は、仮想ユーザーライセンス用の新しいリソースアカウントを作成し、破損したリソースアカウントを削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b52c6-197">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="b52c6-198">Powershell でリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b52c6-198">Create a resource account in Powershell</span></span>

<span data-ttu-id="b52c6-199">リソースアカウントがオンラインであるか、Skype for Business Server 2019 にあるかに応じて、管理者特権で適切な Powershell プロンプトに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b52c6-199">Depending on whether your resource account is located online or on Skype for Business Server 2019, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="b52c6-200">次の Powershell コマンドレットの例は、[新しい-csonline Applicationinstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)を使って、オンラインでホームリソースアカウントを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b52c6-200">The following Powershell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="b52c6-201">クラウド通話キューとクラウド自動応答で使用できる Skype For Business Server 2019 上のリソースアカウントの場合は、「[クラウド通話キューを構成](/skypeforbusiness/hybrid/configure-call-queue.md)する、[クラウド自動応答を構成](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-201">For resource accounts homed on Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="b52c6-202">ハイブリッド実装 (直接ルーティングによる番号) では[、CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-202">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="b52c6-203">アプリケーションインスタンスの作成時に使う必要があるアプリケーション ID は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b52c6-203">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="b52c6-204">**自動応答:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="b52c6-204">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="b52c6-205">**通話キュー:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="b52c6-205">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="b52c6-206">Skype For Business Server 2019 ユーザーが通話キューまたは自動応答を検索できるようにするには、オンラインリソースアカウントが Active Directory に同期されていないため、Skype For Business Server 2019 でリソースアカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b52c6-206">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="b52c6-207">Sipfederationtls 用の DNS SRV レコードが Skype for Business Server 2019 に解決される場合は、SfB 管理シェルを使用して、オンライン Azure AD に同期されるように、Skype For Business Server 2019 でリソースアカウントを作成する**必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-207">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to online Azure AD.</span></span>

 

1. <span data-ttu-id="b52c6-208">自動応答で使用するためにオンラインでリソースアカウントを作成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-208">To create a resource account online for use with an auto attendant, use the following command:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="b52c6-209">リソースアカウントは、ライセンスが適用されるまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="b52c6-209">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="b52c6-210">O365 管理センターのアカウントにライセンスを適用する方法については、「一般[法人向け Office 365 のライセンスをユーザーに割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user)」および「 [Skype for business のライセンスを割り当てる](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-210">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="b52c6-211">省略リソースアカウントに適切なライセンスが適用されると、次に示すように、リソースアカウントに電話番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-211">(Optional) Once the correct license is applied to the resource account you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="b52c6-212">すべてのリソースアカウントで電話番号が必要になるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="b52c6-212">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="b52c6-213">リソースアカウントにライセンスが適用されていない場合、電話番号の割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-213">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="b52c6-214">このコマンドの詳細については[、「Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-214">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b52c6-215">前に説明したように、Microsoft Teams 管理センターを使用してオンライン電話番号を設定するのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="b52c6-215">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="b52c6-216">Microsoft Teams または Skype For Business Server 2019 でのリソースアカウントに直接ルーティング電話番号を割り当てるには、次のコマンドレットを使用して Skype for Business Online Powershell を使用します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-216">To assign a direct routing phone number to a resource account (homed either in Microsoft Teams or Skype For Business Server 2019), use the following cmdlet for Skype for Business Online Powershell:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="b52c6-217">Microsoft Teams 管理センターでリソースアカウント設定を管理する</span><span class="sxs-lookup"><span data-stu-id="b52c6-217">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="b52c6-218">Microsoft Teams 管理センターでリソースアカウントの設定を管理するには、[**組織全体の設定** > ]**リソースアカウント**に移動し、設定を変更する必要があるリソースアカウントを選び、[**編集**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b52c6-218">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="b52c6-219">[**リソースアカウントの編集**] 画面では、次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-219">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="b52c6-220">アカウントの**表示名**</span><span class="sxs-lookup"><span data-stu-id="b52c6-220">**Display name** for the account</span></span>
- <span data-ttu-id="b52c6-221">アカウントを使う通話キューまたは自動応答</span><span class="sxs-lookup"><span data-stu-id="b52c6-221">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="b52c6-222">アカウントに割り当てられている電話番号</span><span class="sxs-lookup"><span data-stu-id="b52c6-222">Phone number assigned to the account</span></span>

<span data-ttu-id="b52c6-223">完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b52c6-223">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="b52c6-224">リソースアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="b52c6-224">Delete a resource account</span></span>

<span data-ttu-id="b52c6-225">サービス番号が保留モードで停止しないようにするには、削除する前に必ず電話番号とリソースアカウントの関連付けを解除してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-225">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="b52c6-226">これは、次のレットを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-226">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="b52c6-227">この操作を行うと、O365 管理ポータルの [ユーザー] タブでリソースアカウントを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-227">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

<span data-ttu-id="b52c6-228">リソースアカウントから直接ルーティングする電話番号との関連付けを解除するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b52c6-228">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="b52c6-229">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b52c6-229">Troubleshooting</span></span>

<span data-ttu-id="b52c6-230">Teams 管理センターのリソースアカウントに割り当てられている電話番号が表示されず、その番号を割り当てることができない場合は、次の点を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-230">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="b52c6-231">Department 属性で Skype for Business アプリケーションエンドポイントが表示される場合は、次のコマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="b52c6-231">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="b52c6-232">Cmldet を実行した後に Teams 管理センターの web ページを更新すると、番号を正しく割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b52c6-232">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="b52c6-233">関連情報</span><span class="sxs-lookup"><span data-stu-id="b52c6-233">Related Information</span></span>

<span data-ttu-id="b52c6-234">Skype for Business Server とハイブリッドの実装の場合:</span><span class="sxs-lookup"><span data-stu-id="b52c6-234">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="b52c6-235">クラウド自動応答の計画</span><span class="sxs-lookup"><span data-stu-id="b52c6-235">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="b52c6-236">クラウド通話キューの計画</span><span class="sxs-lookup"><span data-stu-id="b52c6-236">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="b52c6-237">オンプレミスのリソースアカウントを構成する</span><span class="sxs-lookup"><span data-stu-id="b52c6-237">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="b52c6-238">Teams または Skype for Business Online の実装の場合:</span><span class="sxs-lookup"><span data-stu-id="b52c6-238">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="b52c6-239">クラウドの自動応答とは</span><span class="sxs-lookup"><span data-stu-id="b52c6-239">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="b52c6-240">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="b52c6-240">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="b52c6-241">小規模ビジネスの例: 自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="b52c6-241">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="b52c6-242">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="b52c6-242">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="b52c6-243">新規-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="b52c6-243">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="b52c6-244">新しい Csonline Applicationinstance</span><span class="sxs-lookup"><span data-stu-id="b52c6-244">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="b52c6-245">電話システム-仮想ユーザーライセンス</span><span class="sxs-lookup"><span data-stu-id="b52c6-245">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
