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
ms.openlocfilehash: 947f01f6a305c723558273feb5da477078c4fd71
ms.sourcegitcommit: baa425d7a07429e6fe84b4f27c76243cf755c1a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643172"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="cb95d-103">Microsoft Teams のリソースのアカウントの管理</span><span class="sxs-lookup"><span data-stu-id="cb95d-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="cb95d-104">リソースアカウントは、Azure Active Directory で無効になったユーザーオブジェクトとも呼ばれ、一般にリソースを表すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="cb95d-105">Exchange では、会議室の代表として使用され、電話番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="cb95d-106">リソースアカウントは、Skype for Business Server 2019 を使って、Microsoft 365 またはオンプレミスのホームにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="cb95d-107">Microsoft Teams または Skype for Business Online では、各通話キューまたは自動応答に、関連するリソースアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="cb95d-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="cb95d-108">リソースアカウントに割り当てられた電話番号が必要かどうかは、関連付けられた通話キューまたは自動応答の用途によって異なります。</span><span class="sxs-lookup"><span data-stu-id="cb95d-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="cb95d-109">リソースアカウントに電話番号を割り当てる前に、この記事の下部にある「通話キューと自動応答」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="cb95d-110">この記事は、Microsoft Teams と Skype for Business Online の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="cb95d-111">Skype for Business Server 2019 を使用しているリソースアカウントの場合は、「[リソースアカウントを構成する](/SkypeForBusiness/hybrid/configure-onprem-ra)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-111">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="overview"></a><span data-ttu-id="cb95d-112">概要</span><span class="sxs-lookup"><span data-stu-id="cb95d-112">Overview</span></span>

<span data-ttu-id="cb95d-113">電話システムサービスにサービス番号が必要な場合は、次の順序でさまざまな依存関係を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-113">If your Phone System service will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="cb95d-114">サービス番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-114">Obtain a service number.</span></span>
2. <span data-ttu-id="cb95d-115">リソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-115">Create the resource account.</span></span> <span data-ttu-id="cb95d-116">関連付けられているリソースアカウントを持つには、自動応答または通話キューが必要です。</span><span class="sxs-lookup"><span data-stu-id="cb95d-116">An auto attendant or call queue is required to have an associated resource account.</span></span>
3. <span data-ttu-id="cb95d-117">電話システムまたは電話システムの仮想ユーザーライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-117">Obtain a Phone System or Phone System Virtual User license.</span></span>
4. <span data-ttu-id="cb95d-118">国内または国際通話プランを購入します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-118">Buy a Domestic or International Calling Plan.</span></span>
5. <span data-ttu-id="cb95d-119">電話システムまたは電話システムの仮想ユーザーライセンスをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-119">Assign the Phone System or a Phone System Virtual User license to the resource account.</span></span>
6. <span data-ttu-id="cb95d-120">通話プランのライセンスをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-120">Assign a calling plan license to the resource account.</span></span>
7. <span data-ttu-id="cb95d-121">通信クレジットのライセンスをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-121">Assign a Communications Credits license to the resource account.</span></span>
8. <span data-ttu-id="cb95d-122">通信クレジットを設定して、組織の自動再充電を設定します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-122">Set up Communication Credits and set up auto-recharge for your organization.</span></span>
9. <span data-ttu-id="cb95d-123">ライセンスを割り当てたリソースアカウントにサービスの電話番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-123">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
10. <span data-ttu-id="cb95d-124">電話システムサービス (通話キューまたは自動応答) を作成します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-124">Create a Phone System service (a call queue or auto attendant).</span></span>
11. <span data-ttu-id="cb95d-125">リソースアカウントとサービスをリンクします。</span><span class="sxs-lookup"><span data-stu-id="cb95d-125">Link the resource account with a service.</span></span>

<span data-ttu-id="cb95d-126">自動応答または通話キューが最上位レベルの自動応答の下に入れ子になっている場合、関連付けられたリソースアカウントには、自動応答と通話キューの構造に複数のエントリポイントが必要な場合は、電話番号のみが必要になります。</span><span class="sxs-lookup"><span data-stu-id="cb95d-126">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="cb95d-127">組織内のユーザーにオンラインで接続されているユーザーに通話をリダイレクトするには、**電話システム**のライセンスが必要です。また、エンタープライズボイスに対して有効になっているか、Office 365 通話プランを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb95d-127">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="cb95d-128">「 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-128">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="cb95d-129">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-129">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="cb95d-130">たとえば、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-130">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="cb95d-131">作成している電話システムサービスがネストされ、電話番号は不要な場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-131">If the Phone system service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="cb95d-132">リソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="cb95d-132">Create the resource account</span></span>  
2. <span data-ttu-id="cb95d-133">電話システムサービスを作成する</span><span class="sxs-lookup"><span data-stu-id="cb95d-133">Create a Phone System service</span></span>
3. <span data-ttu-id="cb95d-134">リソースアカウントを電話システムサービスに関連付ける</span><span class="sxs-lookup"><span data-stu-id="cb95d-134">Associate the resource account with a Phone System service</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="cb95d-135">電話番号を使用してリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="cb95d-135">Create a resource account with a phone number</span></span>

<span data-ttu-id="cb95d-136">電話番号を使用するリソースアカウントを作成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb95d-136">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="cb95d-137">有料または無料の有料サービス番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-137">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="cb95d-138">この番号は、他のボイスサービスやリソースアカウントに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="cb95d-138">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="cb95d-139">リソースアカウントに電話番号を割り当てる前に、既存の有料または無料サービス番号を取得または移植する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb95d-139">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="cb95d-140">有料またはフリーダイヤルのサービス電話番号を取得すると、 **Microsoft Teams 管理センター** > **ボイス** > **電話番号**が表示され、一覧表示される [**番号の種類**] は [サービスとして**無料**] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-140">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="cb95d-141">サービス番号を取得するには、「[サービスの電話番号を取得](getting-service-phone-numbers.md)する」または「既存のサービス番号を移行する」を参照してください。「 [Office 365 に電話番号を転送](transfer-phone-numbers-to-office-365.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-141">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

   <span data-ttu-id="cb95d-142">リソースアカウントに電話番号を割り当てる場合は、無料電話システムの仮想ユーザーライセンスを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="cb95d-142">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="cb95d-143">これにより、組織レベルで電話番号に電話システム機能が提供され、自動応答と通話キュー機能を作成できます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-143">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="cb95d-144">新しいリソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-144">Create a new resource account.</span></span> <span data-ttu-id="cb95d-145">「 [Microsoft Teams 管理センターでリソースアカウントを作成](#create-a-resource-account-in-microsoft-teams-admin-center)する」または「 [Powershell でリソースアカウントを作成](#create-a-resource-account-in-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-145">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
3. <span data-ttu-id="cb95d-146">電話システムまたは電話システムの仮想ユーザーライセンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-146">Obtain a Phone System or Phone System Virtual User license.</span></span> <span data-ttu-id="cb95d-147">Microsoft 365 管理センターで、[**課金** > **購入サービス** > **アドオンサブスクリプション**] に移動し、[電話システム-仮想ユーザー] ライセンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-147">From the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="cb95d-148">[**今すぐ購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-148">Select **Buy now**.</span></span>
4. <span data-ttu-id="cb95d-149">国内または国際[通話プラン](calling-plans-for-office-365.md)を購入します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-149">Buy a Domestic or International [Calling Plan](calling-plans-for-office-365.md).</span></span>
5. <span data-ttu-id="cb95d-150">電話システムのライセンスをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-150">Assign the Phone System license to the resource account.</span></span> <span data-ttu-id="cb95d-151">「 [Microsoft Teams ライセンスを割り当て](assign-teams-licenses.md)て、 [1 人のユーザーにライセンスを割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-151">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
6. <span data-ttu-id="cb95d-152">通話プランのライセンスをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-152">Assign a calling plan license to the resource account.</span></span> <span data-ttu-id="cb95d-153">詳細については、「 [Microsoft Teams ライセンスを割り当てる](assign-teams-licenses.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-153">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) for more information.</span></span>
7. <span data-ttu-id="cb95d-154">サービス番号をリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-154">Assign the service number to the resource account.</span></span> <span data-ttu-id="cb95d-155">「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-155">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
8. <span data-ttu-id="cb95d-156">通信クレジットを設定して、組織の自動再充電を設定します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-156">Set up Communication Credits and set up auto-recharge for your organization.</span></span> <span data-ttu-id="cb95d-157">[通信クレジットのライセンス](set-up-communications-credits-for-your-organization.md#step-3-assign-a-communications-credits-license-to-users)をリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-157">[Assign a Communications Credits license](set-up-communications-credits-for-your-organization.md#step-3-assign-a-communications-credits-license-to-users) to the resource account.</span></span>
9. <span data-ttu-id="cb95d-158">ライセンスを割り当てたリソースアカウントに[サービスの電話番号を割り当て](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge)ます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-158">[Assign a service phone number](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge) to the resource account you just assigned licenses to.</span></span> 
10. <span data-ttu-id="cb95d-159">次のいずれかを設定します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-159">Set up one of the following:</span></span>
   - [<span data-ttu-id="cb95d-160">クラウド自動応答</span><span class="sxs-lookup"><span data-stu-id="cb95d-160">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="cb95d-161">クラウド通話キュー</span><span class="sxs-lookup"><span data-stu-id="cb95d-161">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
11. <span data-ttu-id="cb95d-162">リソースアカウントを自動応答または通話キューにリンクします。</span><span class="sxs-lookup"><span data-stu-id="cb95d-162">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="cb95d-163">「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-163">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="cb95d-164">電話番号のないリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="cb95d-164">Create a resource account without a phone number</span></span>

<span data-ttu-id="cb95d-165">電話番号を必要としないリソースアカウントを作成する場合は、次の手順で次の作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb95d-165">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="cb95d-166">新しいリソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-166">Create a new resource account.</span></span> <span data-ttu-id="cb95d-167">「 [Microsoft Teams 管理センターでリソースアカウントを作成](#create-a-resource-account-in-microsoft-teams-admin-center)する」または「 [Powershell でリソースアカウントを作成](#create-a-resource-account-in-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-167">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="cb95d-168">次のいずれかを設定します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-168">Set up one of the following:</span></span>
   - [<span data-ttu-id="cb95d-169">クラウド自動応答</span><span class="sxs-lookup"><span data-stu-id="cb95d-169">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="cb95d-170">クラウド通話キュー</span><span class="sxs-lookup"><span data-stu-id="cb95d-170">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="cb95d-171">リソースアカウントをサービスに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-171">Assign the resource account to the service.</span></span> <span data-ttu-id="cb95d-172">「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-172">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="cb95d-173">Microsoft Teams 管理センターでリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="cb95d-173">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="cb95d-174">電話システムのライセンスを購入した後、Microsoft Teams 管理センターを使用して、[**組織全体の設定** > ]**リソースアカウント**に移動します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-174">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![[リソースアカウント] ページのスクリーンショット](media/r-a-master.png)

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

<span data-ttu-id="cb95d-177">新しいリソースアカウントを作成するには、[ **+ 新しいアカウント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb95d-177">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="cb95d-178">ポップアップで、リソースアカウントの表示名とユーザー名 (ドメイン名が自動的に入力されます) を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb95d-178">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![新しいリソースアカウントオプションのスクリーンショット](media/res-acct.png)

<span data-ttu-id="cb95d-180">次に、「一般[法人向け Office 365 でライセンスをユーザーに割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)」の説明に従って、O365 管理センターのリソースアカウントにライセンスを適用します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-180">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account-name"></a><span data-ttu-id="cb95d-181">リソースアカウント名を編集する</span><span class="sxs-lookup"><span data-stu-id="cb95d-181">Edit resource account name</span></span>

<span data-ttu-id="cb95d-182">![数字2のアイコン。前のスクリーンショット](media/sfbcallout2.png)で吹き出しを参照すると、[**編集**] オプションを使用してリソースアカウントの表示名を編集できます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-182">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span>  <span data-ttu-id="cb95d-183">完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb95d-183">Click **Save** when you are done.</span></span>
<span data-ttu-id="cb95d-184">![[リソースアカウントの編集] オプションのスクリーンショット](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="cb95d-184">![Screen shot of the Edit resource account option](media/r-a-edit.png)</span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="cb95d-185">電話番号とサービスの割り当て/割り当て解除を行う</span><span class="sxs-lookup"><span data-stu-id="cb95d-185">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="cb95d-186">![番号3のアイコン、前のスクリーンショット](media/sfbcallout3.png)での吹き出しの参照リソースアカウントを作成してライセンスを割り当てた後、[**割り当て/割り当て解除**] をクリックして、リソースアカウントにサービス番号を割り当てるか、リソースを割り当てることができます。既に存在する自動応答または通話キューのアカウント。</span><span class="sxs-lookup"><span data-stu-id="cb95d-186">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="cb95d-187">直接ルーティング番号の割り当ては、コマンドレットを使用する場合にのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-187">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="cb95d-188">通話キューまたは自動応答をまだ作成する必要がある場合は、作成時にリソースアカウントをリンクすることができます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-188">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="cb95d-189">完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb95d-189">Click **Save** when you are done.</span></span>

<span data-ttu-id="cb95d-190">リソースアカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、PowerShell を使用する必要があります。次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-190">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb95d-191">テナントが電話システムのライセンスを持っていない場合は、リソースアカウントに電話番号を割り当てようとしたときに、内部チェックによってエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-191">If your tenant doesn't have a Phone System license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="cb95d-192">電話番号を割り当てたり、リソースアカウントをサービスに関連付けたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cb95d-192">You won't be able to assign the number or associate the resource account with a service.</span></span>

![[割り当て/割り当て解除] オプションのスクリーンショット](media/r-a-assign.png)

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="cb95d-194">Powershell でリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="cb95d-194">Create a resource account in Powershell</span></span>

<span data-ttu-id="cb95d-195">リソースアカウントがオンラインとオンプレミスのどちらであるかに応じて、管理者特権で適切な Powershell プロンプトに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb95d-195">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="cb95d-196">次の Powershell コマンドレットの例では、リソースアカウントが、オンラインになっているリソースアカウントを作成するために、[新しい-csonline Applicationinstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)を使用してオンラインであることが前提となっています。</span><span class="sxs-lookup"><span data-stu-id="cb95d-196">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="cb95d-197">Skype For Business Server 2019 でホームオンプレミスのリソースアカウントを使って、クラウド通話キューとクラウド自動応答と共に使用できる場合は、「[クラウド通話キューを構成](/skypeforbusiness/hybrid/configure-call-queue.md)する、[クラウド自動応答を構成](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-197">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="cb95d-198">ハイブリッド実装 (直接ルーティングによる番号) では[、CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-198">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="cb95d-199">アプリケーションインスタンスの作成時に使う必要があるアプリケーション ID は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cb95d-199">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="cb95d-200">**自動応答:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="cb95d-200">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="cb95d-201">**通話キュー:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="cb95d-201">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="cb95d-202">オンプレミスのユーザーが通話キューまたは自動応答を検索できるようにする場合は、オンラインリソースアカウントが Active Directory に同期されていないため、リソースアカウントをオンプレミスで作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb95d-202">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="cb95d-203">自動応答で使用するためにオンラインでリソースアカウントを作成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-203">To create a resource account online for use with an auto attendant, use the following command.</span></span>  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="cb95d-204">リソースアカウントは、ライセンスが適用されるまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="cb95d-204">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="cb95d-205">O365 管理センターのアカウントにライセンスを適用する方法については、「一般[法人向け Office 365 のライセンスをユーザーに割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user)」および「 [Skype for business のライセンスを割り当てる](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-205">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="cb95d-206">省略リソースアカウントに適切なライセンスが適用されたら、以下に示すように、リソースアカウントに電話番号を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-206">(Optional) Once the correct license is applied to the resource account you can  set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="cb95d-207">すべてのリソースアカウントで電話番号が必要になるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="cb95d-207">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="cb95d-208">リソースアカウントにライセンスが適用されていない場合、電話番号の割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-208">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="cb95d-209">このコマンドの詳細については[、「Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-209">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="cb95d-210">前に説明したように、Microsoft Teams 管理センターを使用してオンライン電話番号を設定するのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="cb95d-210">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

<span data-ttu-id="cb95d-211">リソースアカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb95d-211">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="cb95d-212">Microsoft Teams 管理センターでリソースアカウント設定を管理する</span><span class="sxs-lookup"><span data-stu-id="cb95d-212">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="cb95d-213">Microsoft Teams 管理センターでリソースアカウントの設定を管理するには、[**組織全体の設定**  > ]**リソースアカウント**に移動し、設定を変更する必要があるリソースアカウントを選び、[**編集**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb95d-213">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="cb95d-214">[**リソースアカウントの編集**] 画面では、次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-214">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="cb95d-215">アカウントの**表示名**</span><span class="sxs-lookup"><span data-stu-id="cb95d-215">**Display name** for the account</span></span>
- <span data-ttu-id="cb95d-216">アカウントを使う通話キューまたは自動応答</span><span class="sxs-lookup"><span data-stu-id="cb95d-216">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="cb95d-217">アカウントに割り当てられている電話番号</span><span class="sxs-lookup"><span data-stu-id="cb95d-217">Phone number assigned to the account</span></span>

<span data-ttu-id="cb95d-218">完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb95d-218">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="cb95d-219">リソースアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="cb95d-219">Delete a resource account</span></span>

<span data-ttu-id="cb95d-220">サービス番号が保留モードで停止しないようにするには、削除する前に必ず電話番号とリソースアカウントの関連付けを解除してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-220">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="cb95d-221">これは、次のレットを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-221">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="cb95d-222">この操作を行うと、O365 管理ポータルの [ユーザー] タブでリソースアカウントを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-222">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="cb95d-223">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="cb95d-223">Troubleshooting</span></span>

<span data-ttu-id="cb95d-224">Teams 管理センターのリソースアカウントに割り当てられている電話番号が表示されず、その番号を割り当てることができない場合は、次の点を確認してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-224">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="cb95d-225">Department 属性で Skype for Business アプリケーションエンドポイントが表示される場合は、次のコマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="cb95d-225">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId  -Department "Microsoft Communication Application Instance"
```
> [!NOTE]
> <span data-ttu-id="cb95d-226">Cmldet を実行した後に Teams 管理センターの web ページを更新すると、番号を正しく割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="cb95d-226">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="cb95d-227">関連情報</span><span class="sxs-lookup"><span data-stu-id="cb95d-227">Related Information</span></span>

<span data-ttu-id="cb95d-228">Skype for Business Server とハイブリッドの実装の場合:</span><span class="sxs-lookup"><span data-stu-id="cb95d-228">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="cb95d-229">クラウド自動応答の計画</span><span class="sxs-lookup"><span data-stu-id="cb95d-229">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="cb95d-230">クラウド自動応答の構成</span><span class="sxs-lookup"><span data-stu-id="cb95d-230">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="cb95d-231">Teams または Skype for Business Online の実装の場合:</span><span class="sxs-lookup"><span data-stu-id="cb95d-231">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="cb95d-232">クラウドの自動応答とは</span><span class="sxs-lookup"><span data-stu-id="cb95d-232">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="cb95d-233">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="cb95d-233">Set up a Cloud auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="cb95d-234">小規模ビジネスの例: 自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="cb95d-234">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

[<span data-ttu-id="cb95d-235">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="cb95d-235">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="cb95d-236">新規-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="cb95d-236">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="cb95d-237">新しい Csonline Applicationinstance</span><span class="sxs-lookup"><span data-stu-id="cb95d-237">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
