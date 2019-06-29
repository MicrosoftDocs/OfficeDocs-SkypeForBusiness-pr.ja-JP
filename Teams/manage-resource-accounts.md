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
ms.openlocfilehash: 4dcb9327efba7be70628ad71a90734940fc3317e
ms.sourcegitcommit: 016beacc8b64eaeeaefb641360dd9bb8d2191c4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394501"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="b34fe-103">Microsoft Teams のリソースのアカウントの管理</span><span class="sxs-lookup"><span data-stu-id="b34fe-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="b34fe-104">リソースアカウントは、Azure Active Directory で無効になったユーザーオブジェクトとも呼ばれ、一般にリソースを表すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="b34fe-105">Exchange では、会議室の代表として使用され、電話番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="b34fe-106">リソースアカウントは、Skype for Business Server 2019 を使って、Microsoft 365 またはオンプレミスのホームにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="b34fe-107">Microsoft Teams または Skype for Business Online では、各通話キューまたは自動応答に、関連するリソースアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="b34fe-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="b34fe-108">リソースアカウントに割り当てられた電話番号が必要かどうかは、関連付けられた通話キューまたは自動応答の用途によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b34fe-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="b34fe-109">リソースアカウントに電話番号を割り当てる前に、この記事の下部にある「通話キューと自動応答」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="b34fe-110">この記事は、Microsoft Teams と Skype for Business Online の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="b34fe-111">Skype for Business Server 2019 を使用しているリソースアカウントの場合は、「[リソースアカウントを構成する](/SkypeForBusiness/hybrid/configure-onprem-ra)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-111">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="overview"></a><span data-ttu-id="b34fe-112">概要</span><span class="sxs-lookup"><span data-stu-id="b34fe-112">Overview</span></span>

<span data-ttu-id="b34fe-113">電話システムサービスにサービス番号が必要な場合は、次の順序でさまざまな依存関係を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-113">If your Phone System service will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="b34fe-114">サービス番号を取得する</span><span class="sxs-lookup"><span data-stu-id="b34fe-114">Obtain a service number</span></span>
2. <span data-ttu-id="b34fe-115">電話システムのライセンスを購入する (電話システムが追加されている Office 365 Enterprise E1 または E3、または電話システムを含む Office 365 Enterprise E5)</span><span class="sxs-lookup"><span data-stu-id="b34fe-115">Buy a Phone System license (Office 365 Enterprise E1 or E3 with Phone System added, or Office 365 Enterprise E5 which includes Phone System)</span></span>
3. <span data-ttu-id="b34fe-116">リソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b34fe-116">Create the resource account.</span></span> <span data-ttu-id="b34fe-117">関連付けられているリソースアカウントを持つには、自動応答または通話キューが必要です。</span><span class="sxs-lookup"><span data-stu-id="b34fe-117">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="b34fe-118">電話システムのライセンスをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-118">Assign the Phone System license to the resource account.</span></span>
5. <span data-ttu-id="b34fe-119">リソースアカウントに電話番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-119">Assign a phone number to the resource account.</span></span>
6. <span data-ttu-id="b34fe-120">電話システムサービス (通話キューまたは自動応答) を作成する</span><span class="sxs-lookup"><span data-stu-id="b34fe-120">Create a Phone System service (a call queue or auto attendant)</span></span>
7. <span data-ttu-id="b34fe-121">リソースアカウントをサービスに関連付ける: (新しい-CsApplicationInstanceAssociation)</span><span class="sxs-lookup"><span data-stu-id="b34fe-121">Associate the resource account with a service: (New-CsApplicationInstanceAssociation)</span></span>

<span data-ttu-id="b34fe-122">自動応答または通話キューが最上位レベルの自動応答の下に入れ子になっている場合、関連付けられたリソースアカウントには、自動応答と通話キューの構造に複数のエントリポイントが必要な場合は、電話番号のみが必要になります。</span><span class="sxs-lookup"><span data-stu-id="b34fe-122">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="b34fe-123">組織内のユーザーにオンラインで接続されているユーザーに通話をリダイレクトするには、**電話システム**のライセンスが必要です。また、エンタープライズボイスに対して有効になっているか、Office 365 通話プランを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b34fe-123">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="b34fe-124">「 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-124">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="b34fe-125">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-125">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="b34fe-126">たとえば、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="b34fe-126">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="b34fe-127">作成している電話システムサービスがネストされ、電話番号は不要な場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b34fe-127">If the Phone system service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="b34fe-128">リソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b34fe-128">Create the resource account</span></span>  
2. <span data-ttu-id="b34fe-129">電話システムサービスを作成する</span><span class="sxs-lookup"><span data-stu-id="b34fe-129">Create a Phone System service</span></span>
3. <span data-ttu-id="b34fe-130">リソースアカウントを電話システムサービスに関連付ける</span><span class="sxs-lookup"><span data-stu-id="b34fe-130">Associate the resource account with a Phone System service</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="b34fe-131">電話番号を使用してリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b34fe-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="b34fe-132">電話番号を使用するリソースアカウントを作成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b34fe-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="b34fe-133">有料または無料の有料サービス番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="b34fe-134">この番号は、他のボイスサービスやリソースアカウントに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="b34fe-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="b34fe-135">リソースアカウントに電話番号を割り当てる前に、既存の有料または無料サービス番号を取得または移植する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b34fe-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="b34fe-136">有料またはフリーダイヤルのサービス電話番号を取得すると、 **Microsoft Teams 管理センター** > **ボイス** > **電話番号**が表示され、一覧表示される [**番号の種類**] は [サービスとして**無料**] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="b34fe-137">サービス番号を取得するには、「[サービスの電話番号を取得](getting-service-phone-numbers.md)する」または「既存のサービス番号を移行する」を参照してください。「 [Office 365 に電話番号を転送](transfer-phone-numbers-to-office-365.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-137">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

2. <span data-ttu-id="b34fe-138">電話システムのライセンスを購入します。</span><span class="sxs-lookup"><span data-stu-id="b34fe-138">Buy a Phone System license.</span></span> <span data-ttu-id="b34fe-139">て</span><span class="sxs-lookup"><span data-stu-id="b34fe-139">See:</span></span>  
   - [<span data-ttu-id="b34fe-140">Office 365 Enterprise E1 および E3</span><span class="sxs-lookup"><span data-stu-id="b34fe-140">Office 365 Enterprise E1 and E3</span></span>](teams-add-on-licensing/office-365-enterprise-e1-e3.md)
   - [<span data-ttu-id="b34fe-141">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="b34fe-141">Office 365 Enterprise E5</span></span>](teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing.md)
   - [<span data-ttu-id="b34fe-142">Office 365 Enterprise E5 ビジネスソフトウェア</span><span class="sxs-lookup"><span data-stu-id="b34fe-142">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="b34fe-143">新しいリソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b34fe-143">Create a new resource account.</span></span> <span data-ttu-id="b34fe-144">「 [Microsoft Teams 管理センターでリソースアカウントを作成](#create-a-resource-account-in-microsoft-teams-admin-center)する」または「 [Powershell でリソースアカウントを作成](#create-a-resource-account-in-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-144">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="b34fe-145">電話システムのライセンスをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-145">Assign the Phone System license to the resource account.</span></span> <span data-ttu-id="b34fe-146">「 [Microsoft Teams ライセンスを割り当て](assign-teams-licenses.md)て、 [1 人のユーザーにライセンスを割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-146">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="b34fe-147">サービス番号をリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-147">Assign the service number to the resource account.</span></span> <span data-ttu-id="b34fe-148">「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-148">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="b34fe-149">次のいずれかを設定します。</span><span class="sxs-lookup"><span data-stu-id="b34fe-149">Set up one of the following:</span></span>
   - [<span data-ttu-id="b34fe-150">クラウド自動応答</span><span class="sxs-lookup"><span data-stu-id="b34fe-150">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="b34fe-151">クラウド通話キュー</span><span class="sxs-lookup"><span data-stu-id="b34fe-151">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="b34fe-152">リソースアカウントをサービスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-152">Assign the resource account to the service.</span></span> <span data-ttu-id="b34fe-153">「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-153">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="b34fe-154">電話番号のないリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b34fe-154">Create a resource account without a phone number</span></span>

<span data-ttu-id="b34fe-155">電話番号を必要としないリソースアカウントを作成する場合は、次の手順で次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b34fe-155">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="b34fe-156">新しいリソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="b34fe-156">Create a new resource account.</span></span> <span data-ttu-id="b34fe-157">「 [Microsoft Teams 管理センターでリソースアカウントを作成](#create-a-resource-account-in-microsoft-teams-admin-center)する」または「 [Powershell でリソースアカウントを作成](#create-a-resource-account-in-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-157">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="b34fe-158">次のいずれかを設定します。</span><span class="sxs-lookup"><span data-stu-id="b34fe-158">Set up one of the following:</span></span>
   - [<span data-ttu-id="b34fe-159">クラウド自動応答</span><span class="sxs-lookup"><span data-stu-id="b34fe-159">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="b34fe-160">クラウド通話キュー</span><span class="sxs-lookup"><span data-stu-id="b34fe-160">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="b34fe-161">リソースアカウントをサービスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-161">Assign the resource account to the service.</span></span> <span data-ttu-id="b34fe-162">「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-162">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="b34fe-163">Microsoft Teams 管理センターでリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b34fe-163">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="b34fe-164">Microsoft Teams 管理センターを使用して電話システムのライセンスと通話プランを購入した後、[**組織全体の設定** > ]**リソースアカウント**に移動します。</span><span class="sxs-lookup"><span data-stu-id="b34fe-164">After you've bought a Phone System license and a Calling Plan, using Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![[リソースアカウント] ページのスクリーンショット](media/r-a-master.png)

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="b34fe-167">新しいリソースアカウントを作成するには、[ **+ 新しいアカウント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b34fe-167">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="b34fe-168">ポップアップで、リソースアカウントの表示名とユーザー名 (ドメイン名が自動的に入力されます) を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b34fe-168">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![新しいリソースアカウントオプションのスクリーンショット](media/res-acct.png)

<span data-ttu-id="b34fe-170">次に、「一般[法人向け Office 365 でライセンスをユーザーに割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)」の説明に従って、O365 管理センターのリソースアカウントにライセンスを適用します。</span><span class="sxs-lookup"><span data-stu-id="b34fe-170">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account-name"></a><span data-ttu-id="b34fe-171">リソースアカウント名を編集する</span><span class="sxs-lookup"><span data-stu-id="b34fe-171">Edit resource account name</span></span>

<span data-ttu-id="b34fe-172">![数字2のアイコン。前のスクリーンショット](media/sfbcallout2.png)で吹き出しを参照すると、[**編集**] オプションを使用してリソースアカウントの表示名を編集できます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-172">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span>  <span data-ttu-id="b34fe-173">完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b34fe-173">Click **Save** when you are done.</span></span>
<span data-ttu-id="b34fe-174">![[リソースアカウントの編集] オプションのスクリーンショット](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="b34fe-174">![Screen shot of the Edit resource account option](media/r-a-edit.png)</span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="b34fe-175">電話番号とサービスの割り当て/割り当て解除を行う</span><span class="sxs-lookup"><span data-stu-id="b34fe-175">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="b34fe-176">![番号3のアイコン、前のスクリーンショット](media/sfbcallout3.png)での吹き出しの参照リソースアカウントを作成してライセンスを割り当てた後、[**割り当て/割り当て解除**] をクリックして、リソースアカウントにサービス番号を割り当てるか、リソースを割り当てることができます。既に存在する自動応答または通話キューのアカウント。</span><span class="sxs-lookup"><span data-stu-id="b34fe-176">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="b34fe-177">直接ルーティング番号の割り当ては、コマンドレットを使用する場合にのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-177">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="b34fe-178">通話キューまたは自動応答をまだ作成する必要がある場合は、作成時にリソースアカウントをリンクすることができます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-178">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="b34fe-179">完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b34fe-179">Click **Save** when you are done.</span></span>

<span data-ttu-id="b34fe-180">リソースアカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、PowerShell を使用する必要があります。次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-180">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b34fe-181">テナントが電話システムのライセンスを持っていない場合は、リソースアカウントに電話番号を割り当てようとしたときに、内部チェックによってエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b34fe-181">If your tenant doesn't have a Phone System license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="b34fe-182">電話番号を割り当てたり、リソースアカウントをサービスに関連付けたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b34fe-182">You won't be able to assign the number or associate the resource account with a service.</span></span>

![[割り当て/割り当て解除] オプションのスクリーンショット](media/r-a-assign.png)

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="b34fe-184">Powershell でリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="b34fe-184">Create a resource account in Powershell</span></span>

<span data-ttu-id="b34fe-185">リソースアカウントがオンラインとオンプレミスのどちらであるかに応じて、管理者特権で適切な Powershell プロンプトに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b34fe-185">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="b34fe-186">次の Powershell コマンドレットの例では、リソースアカウントが、オンラインになっているリソースアカウントを作成するために、[新しい-csonline Applicationinstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)を使用してオンラインであることが前提となっています。</span><span class="sxs-lookup"><span data-stu-id="b34fe-186">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="b34fe-187">Skype For Business Server 2019 でホームオンプレミスのリソースアカウントを使って、クラウド通話キューとクラウド自動応答と共に使用できる場合は、「[クラウド通話キューを構成](/skypeforbusiness/hybrid/configure-call-queue.md)する、[クラウド自動応答を構成](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-187">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="b34fe-188">ハイブリッド実装 (直接ルーティングによる番号) では[、CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-188">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="b34fe-189">アプリケーションインスタンスの作成時に使う必要があるアプリケーション ID は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b34fe-189">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="b34fe-190">**自動応答:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="b34fe-190">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="b34fe-191">**通話キュー:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="b34fe-191">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="b34fe-192">オンプレミスのユーザーが通話キューまたは自動応答を検索できるようにする場合は、オンラインリソースアカウントが Active Directory に同期されていないため、リソースアカウントをオンプレミスで作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b34fe-192">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="b34fe-193">自動応答で使用するためにオンラインでリソースアカウントを作成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b34fe-193">To create a resource account online for use with an auto attendant, use the following command.</span></span>  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="b34fe-194">リソースアカウントは、ライセンスが適用されるまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="b34fe-194">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="b34fe-195">O365 管理センターのアカウントにライセンスを適用する方法については、「一般[法人向け Office 365 のライセンスをユーザーに割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user)」および「 [Skype for business のライセンスを割り当てる](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-195">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="b34fe-196">省略リソースアカウントに適切なライセンスが適用されたら、以下に示すように、リソースアカウントに電話番号を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-196">(Optional) Once the correct license is applied to the resource account you can  set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="b34fe-197">すべてのリソースアカウントで電話番号が必要になるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="b34fe-197">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="b34fe-198">リソースアカウントにライセンスが適用されていない場合、電話番号の割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="b34fe-198">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="b34fe-199">このコマンドの詳細については[、「Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-199">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="b34fe-200">前に説明したように、Microsoft Teams 管理センターを使用してオンライン電話番号を設定するのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="b34fe-200">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

<span data-ttu-id="b34fe-201">リソースアカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b34fe-201">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="b34fe-202">Microsoft Teams 管理センターでリソースアカウント設定を管理する</span><span class="sxs-lookup"><span data-stu-id="b34fe-202">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="b34fe-203">Microsoft Teams 管理センターでリソースアカウントの設定を管理するには、[**組織全体の設定**  > ]**リソースアカウント**に移動し、設定を変更する必要があるリソースアカウントを選び、[**編集**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b34fe-203">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="b34fe-204">[**リソースアカウントの編集**] 画面では、次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-204">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="b34fe-205">アカウントの**表示名**</span><span class="sxs-lookup"><span data-stu-id="b34fe-205">**Display name** for the account</span></span>
- <span data-ttu-id="b34fe-206">アカウントを使う通話キューまたは自動応答</span><span class="sxs-lookup"><span data-stu-id="b34fe-206">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="b34fe-207">アカウントに割り当てられている電話番号</span><span class="sxs-lookup"><span data-stu-id="b34fe-207">Phone number assigned to the account</span></span>

<span data-ttu-id="b34fe-208">完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b34fe-208">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="b34fe-209">リソースアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="b34fe-209">Delete a resource account</span></span>

<span data-ttu-id="b34fe-210">サービス番号が保留モードで停止しないようにするには、削除する前に必ず電話番号とリソースアカウントの関連付けを解除してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-210">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="b34fe-211">これは、次のレットを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-211">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="b34fe-212">この操作を行うと、O365 管理ポータルの [ユーザー] タブでリソースアカウントを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-212">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b34fe-213">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b34fe-213">Troubleshooting</span></span>

<span data-ttu-id="b34fe-214">Teams 管理センターのリソースアカウントに割り当てられている電話番号が表示されず、その番号を割り当てることができない場合は、次の点を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-214">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="b34fe-215">Department 属性で Skype for Business アプリケーションエンドポイントが表示される場合は、次のコマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="b34fe-215">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId  -Department "Microsoft Communication Application Instance"
```
> [!NOTE]
> <span data-ttu-id="b34fe-216">Cmldet を実行した後に Teams 管理センターの web ページを更新すると、番号を正しく割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b34fe-216">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="b34fe-217">関連情報</span><span class="sxs-lookup"><span data-stu-id="b34fe-217">Related Information</span></span>

<span data-ttu-id="b34fe-218">Skype for Business Server とハイブリッドの実装の場合:</span><span class="sxs-lookup"><span data-stu-id="b34fe-218">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="b34fe-219">クラウド自動応答の計画</span><span class="sxs-lookup"><span data-stu-id="b34fe-219">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="b34fe-220">クラウド自動応答の構成</span><span class="sxs-lookup"><span data-stu-id="b34fe-220">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="b34fe-221">Teams または Skype for Business Online の実装の場合:</span><span class="sxs-lookup"><span data-stu-id="b34fe-221">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="b34fe-222">クラウドの自動応答とは</span><span class="sxs-lookup"><span data-stu-id="b34fe-222">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="b34fe-223">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="b34fe-223">Set up a Cloud auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="b34fe-224">小規模ビジネスの例: 自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="b34fe-224">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

[<span data-ttu-id="b34fe-225">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="b34fe-225">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="b34fe-226">新規-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="b34fe-226">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="b34fe-227">新しい Csonline Applicationinstance</span><span class="sxs-lookup"><span data-stu-id="b34fe-227">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
