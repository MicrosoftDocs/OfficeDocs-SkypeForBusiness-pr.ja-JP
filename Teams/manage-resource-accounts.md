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
ms.openlocfilehash: f2c7b03f79a29b89c94266359f21571b1994e82a
ms.sourcegitcommit: 4b8350e5bb2ef138dcc0204d764bdf85bae539ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2019
ms.locfileid: "34334928"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="c65f5-103">Microsoft Teams のリソースのアカウントの管理</span><span class="sxs-lookup"><span data-stu-id="c65f5-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="c65f5-104">リソースアカウントは、Azure Active Directory で無効になったユーザーオブジェクトとも呼ばれ、一般にリソースを表すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="c65f5-105">Exchange では、会議室の代表として使用され、電話番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="c65f5-106">リソースアカウントは、Skype for Business server を使って Microsoft 365 またはオンプレミスで使用することができ、これらのアカウントは Powershell コマンドを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="c65f5-107">Microsoft Teams または Skype for Business Online では、各通話キューまたは自動応答に、関連するリソースアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="c65f5-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="c65f5-108">リソースアカウントに割り当てられた電話番号が必要かどうかは、関連付けられた通話キューまたは自動応答の用途によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c65f5-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="c65f5-109">リソースアカウントに電話番号を割り当てる前に、この記事の下部にある「通話キューと自動応答」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65f5-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="c65f5-110">この記事は、Microsoft Teams と Skype for Business Online の両方に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="c65f5-111">Skype for Business Server 2019 をホームにしたリソースアカウントの場合は、「[クラウド自動応答を構成する](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65f5-111">For resource accounts homed on Skype for Business Server 2019, see [Configure Cloud auto attendants](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant).</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="c65f5-112">リソースアカウントに電話番号を割り当てるための前提条件</span><span class="sxs-lookup"><span data-stu-id="c65f5-112">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="c65f5-113">開始するには、次の点を忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="c65f5-113">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="c65f5-114">関連付けられているリソースアカウントを持つには、自動応答または通話キューが必要です。</span><span class="sxs-lookup"><span data-stu-id="c65f5-114">An auto attendant or call queue is required to have an associated resource account.</span></span> 
- <span data-ttu-id="c65f5-115">リソースアカウントがトップレベルの自動応答または通話キューに割り当てられている場合は、その電話番号が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65f5-115">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> 
- <span data-ttu-id="c65f5-116">自動応答または通話キューが最上位レベルの自動応答の下に入れ子になっている場合、関連付けられたリソースアカウントには、自動応答と通話キューの構造に複数のエントリポイントが必要な場合は、電話番号のみが必要になります。</span><span class="sxs-lookup"><span data-stu-id="c65f5-116">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>
- <span data-ttu-id="c65f5-117">リソースアカウントには、電話番号が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65f5-117">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="c65f5-118">入れ子になった自動応答または通話キューでは、電話番号が関連付けられていない場合、自動応答または通話キューの残りのライセンスを取得する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c65f5-118">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them.</span></span>
- <span data-ttu-id="c65f5-119">直接ルーティングで使用される電話番号を割り当てる場合、Enterprise E1 または E3 ライセンスをお持ちの場合は、電話システムのライセンスを購入して、使用するリソースアカウントに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65f5-119">If you are assigning a phone number that is used with Direct Routing and you have an Enterprise E1 or E3 licenses you must buy and assign a Phone System license to your the resource account that you will be using.</span></span> <span data-ttu-id="c65f5-120">Enterprise E5 ライセンスをお持ちの場合、電話システムは既に含まれているため、購入する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c65f5-120">If you have an Enterprise E5 license, Phone System is already included so there's no need to buy one.</span></span> 
- <span data-ttu-id="c65f5-121">代わりに Microsoft サービス番号を割り当てる場合は、電話システムアドオンと通話プラン\(\)を使用して、次のライセンスを取得して、Office 365 Enterprise E1、E3、または E5 に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65f5-121">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="c65f5-122">リソースアカウントには、直通ルーティングハイブリッド番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-122">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="c65f5-123">詳しくは、「[ダイレクトルーティングを計画](direct-routing-plan.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c65f5-123">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="c65f5-124">Microsoft の通話プランでは、 **Microsoft Teams 管理センター**で入手した有料および有料サービスの電話番号を割り当てることができます。また、別のサービスプロバイダからリソースアカウントに移植することもできます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-124">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="c65f5-125">無料サービス番号を取得して使用するには、通信クレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65f5-125">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="c65f5-126">自動応答と通話キューのリソースアカウントに割り当てられている直接ルーティングサービス番号は、Microsoft Teams ユーザーとエージェントに対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-126">Direct Routing service numbers assigned to resource accounts for auto attendant and call queues is supported for Microsoft Teams users and agents only.</span></span>
>
> <span data-ttu-id="c65f5-127">Microsoft は、クラウド自動応答や通話キューなどのアプリケーションに適切なライセンスモデルを開発しています。これで、ユーザーライセンスモデルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65f5-127">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>
>
> <span data-ttu-id="c65f5-128">組織内のユーザーにオンラインで接続されているユーザーに通話をリダイレクトするには、**電話システム**のライセンスが必要です。また、エンタープライズボイスに対して有効になっているか、Office 365 通話プランを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65f5-128">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="c65f5-129">「 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65f5-129">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="c65f5-130">エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c65f5-131">たとえば、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c65f5-131">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
>
> <span data-ttu-id="c65f5-132">ユーザー (サブスクライバー) の電話番号をリソースアカウントに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="c65f5-132">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="c65f5-133">サービスの有料電話番号または無料電話番号のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-133">Only service toll or toll-free phone numbers can be used.</span></span>
>
> <span data-ttu-id="c65f5-134">米国外の場合は、Microsoft Teams 管理センターを使用してサービス番号を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="c65f5-134">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="c65f5-135">「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」に移動して、米国以外の地域での実行方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="c65f5-135">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

### <a name="phone-numbers"></a><span data-ttu-id="c65f5-136">電話番号</span><span class="sxs-lookup"><span data-stu-id="c65f5-136">Phone numbers</span></span>

<span data-ttu-id="c65f5-137">電話番号を使用するリソースアカウントを作成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65f5-137">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="c65f5-138">有料または無料のサービス番号を転送または取得します。</span><span class="sxs-lookup"><span data-stu-id="c65f5-138">Transfer or get a toll or toll-free service number.</span></span> <span data-ttu-id="c65f5-139">この番号は、他のボイスサービスやリソースアカウントに割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="c65f5-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="c65f5-140">リソースアカウントに電話番号を割り当てる前に、既存の有料または無料サービス番号を取得または移植する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65f5-140">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="c65f5-141">有料またはフリーダイヤルのサービス電話番号を取得すると、 **Microsoft Teams 管理センター** > **ボイス** > **電話番号**が表示され、一覧表示される [**番号の種類**] は [サービスとして**無料**] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-141">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="c65f5-142">サービス番号を取得するには、「[サービスの電話番号を取得](getting-service-phone-numbers.md)する」または「既存のサービス番号を移行する」を参照してください。「 [Office 365 に電話番号を転送](transfer-phone-numbers-to-office-365.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65f5-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

2. <span data-ttu-id="c65f5-143">電話システムのライセンスと通話プランを購入します。</span><span class="sxs-lookup"><span data-stu-id="c65f5-143">Buy a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="c65f5-144">て</span><span class="sxs-lookup"><span data-stu-id="c65f5-144">See:</span></span>  
   - [<span data-ttu-id="c65f5-145">Office 365 Enterprise E1 および E3</span><span class="sxs-lookup"><span data-stu-id="c65f5-145">Office 365 Enterprise E1 and E3</span></span>](teams-add-on-licensing/office-365-enterprise-e1-e3.md)
   - [<span data-ttu-id="c65f5-146">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="c65f5-146">Office 365 Enterprise E5</span></span>](teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing.md)
   - <span data-ttu-id="c65f5-147">[Office 365 Enterprise E5 ビジネスソフトウェア](https://products.office.com/business/office-365-enterprise-e5-business-software)- [の office 365 の通話プラン](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="c65f5-147">[Office 365 Enterprise E5 Business Software](https://products.office.com/business/office-365-enterprise-e5-business-software)- [Calling Plans for Office 365](calling-plans-for-office-365.md)</span></span>

3. <span data-ttu-id="c65f5-148">新しいリソースアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="c65f5-148">Create a new resource account.</span></span> <span data-ttu-id="c65f5-149">「 [Microsoft Teams 管理センターでリソースアカウントを作成](#create-a-resource-account-in-microsoft-teams-admin-center)する」または「 [Powershell でリソースアカウントを作成](#create-a-resource-account-in-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65f5-149">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="c65f5-150">電話システムのライセンスと通話プランをリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-150">Assign the Phone System license and the Calling Plan to the resource account.</span></span> <span data-ttu-id="c65f5-151">「 [Microsoft Teams ライセンスを割り当て](assign-teams-licenses.md)て、 [1 人のユーザーにライセンスを割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65f5-151">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="c65f5-152">サービス番号をリソースアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-152">Assign the service number to the resource account.</span></span> <span data-ttu-id="c65f5-153">「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65f5-153">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>

<span data-ttu-id="c65f5-154">電話番号を必要としないリソースアカウントでは、手順1、2、5が省略されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c65f5-154">A resource account that doesn't require a phone number can omit steps 1,2, and 5.</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="c65f5-155">Microsoft Teams 管理センターでリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="c65f5-155">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="c65f5-156">Microsoft Teams 管理センターを使用して電話システムのライセンスと通話プランを購入した後、[**組織全体の設定** > ]**リソースアカウント**に移動します。</span><span class="sxs-lookup"><span data-stu-id="c65f5-156">After you've bought a Phone System license and a Calling Plan, using Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**.</span></span> 

![.asd](media/r-a-master.png)

![数値1](media/sfbcallout1.png)

<span data-ttu-id="c65f5-159">新しいリソースアカウントを作成するには、[ **+ 新しいアカウント**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c65f5-159">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="c65f5-160">ポップアップで、リソースアカウントの表示名とユーザー名 (ドメイン名が自動的に入力されます) を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c65f5-160">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![リソースアカウント](media/res-acct.png)

<span data-ttu-id="c65f5-162">次に、「一般[法人向け Office 365 でライセンスをユーザーに割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)」の説明に従って、O365 管理センターのリソースアカウントにライセンスを適用します。</span><span class="sxs-lookup"><span data-stu-id="c65f5-162">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="c65f5-163">電話番号とサービスの割り当て/割り当て解除を行う</span><span class="sxs-lookup"><span data-stu-id="c65f5-163">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="c65f5-164">![数値 3](media/sfbcallout3.png)リソースアカウントを作成してライセンスを割り当てたら、[**割り当て/割り当て解除**] をクリックして、通話プランサービス番号をリソースアカウントに割り当てるか、またはリソースアカウントを自動応答または通話キューに割り当てることができます。すでに存在します。</span><span class="sxs-lookup"><span data-stu-id="c65f5-164">![number 3](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a Calling Plan service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="c65f5-165">直接ルーティング番号の割り当ては、コマンドレットを使用する場合にのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-165">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="c65f5-166">通話キューまたは自動応答をまだ作成する必要がある場合は、作成時にリソースアカウントをリンクすることができます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-166">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="c65f5-167">完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c65f5-167">Click **Save** when you are done.</span></span>

<span data-ttu-id="c65f5-168">次のコマンドレットを使用して、直接ルーティング番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-168">Use the following cmdlet to assign a direct routing number:</span></span> 
``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

> [!IMPORTANT]
> <span data-ttu-id="c65f5-169">テナントが電話システムのライセンスと通話プランを購入していない場合は、リソースアカウントに電話番号を割り当てようとしたときに、内部チェックによってエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c65f5-169">If your tenant hasn't bought a Phone System license and a Calling Plan, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="c65f5-170">電話番号を割り当てたり、リソースアカウントをサービスに関連付けたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c65f5-170">You won't be able to assign the number or associate the resource account with a service.</span></span>

![リソースアカウントの割り当て](media/r-a-assign.png)

<span data-ttu-id="c65f5-172">![番号 2](media/sfbcallout2.png) [**編集**] オプションを使用して、リソースアカウントの表示名を編集できます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-172">![number 2](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span>  <span data-ttu-id="c65f5-173">完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c65f5-173">Click **Save** when you are done.</span></span>
<span data-ttu-id="c65f5-174">![リソースアカウントを編集する](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="c65f5-174">![edit resource account](media/r-a-edit.png)</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="c65f5-175">Powershell でリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="c65f5-175">Create a resource account in Powershell</span></span>

<span data-ttu-id="c65f5-176">Microsoft の通話プランでは、 **Microsoft Teams 管理センター**で入手した有料および有料サービスの電話番号を割り当てることができます。また、別のサービスプロバイダからリソースアカウントに移植することもできます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-176">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="c65f5-177">無料サービス番号を取得して使用するには、通信クレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65f5-177">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

<span data-ttu-id="c65f5-178">リソースアカウントがオンラインとオンプレミスのどちらであるかに応じて、管理者特権で適切な Powershell プロンプトに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65f5-178">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span> 
- <span data-ttu-id="c65f5-179">次の Powershell コマンドレットの例では、リソースアカウントが、オンラインになっているリソースアカウントを作成するために、[新しい-csonline Applicationinstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)を使用してオンラインであることが前提となっています。</span><span class="sxs-lookup"><span data-stu-id="c65f5-179">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="c65f5-180">Skype For Business Server 2019 でホームオンプレミスのリソースアカウントを使って、クラウド通話キューとクラウド自動応答と共に使用できる場合は、「[クラウド通話キューを構成](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md)する、[クラウド自動応答を構成](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65f5-180">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="c65f5-181">ハイブリッド実装 (直接ルーティングによる番号) では[、CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-181">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="c65f5-182">アプリケーションインスタンスの作成時に使う必要があるアプリケーション ID は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c65f5-182">The application ID's that you need to use while creating the application instances are:</span></span>
- <span data-ttu-id="c65f5-183">**自動応答:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="c65f5-183">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="c65f5-184">**通話キュー:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="c65f5-184">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="c65f5-185">オンプレミスのユーザーが通話キューまたは自動応答を検索できるようにする場合は、オンラインリソースアカウントが Active Directory に同期されていないため、リソースアカウントをオンプレミスで作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c65f5-185">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="c65f5-186">自動応答で使用するためにオンラインでリソースアカウントを作成するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c65f5-186">To create a resource account online for use with an auto attendant, use the following command.</span></span>  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="c65f5-187">リソースアカウントは、ライセンスが適用されるまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="c65f5-187">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="c65f5-188">O365 管理センターのアカウントにライセンスを適用する方法については、「一般[法人向け Office 365 のライセンスをユーザーに割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user)」および「 [Skype for business のライセンスを割り当てる](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65f5-188">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="c65f5-189">省略リソースアカウントに適切なライセンスが適用されたら、以下に示すように、リソースアカウントに電話番号を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-189">(Optional) Once the correct license is applied to the resource account you can  set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="c65f5-190">すべてのリソースアカウントで電話番号が必要になるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="c65f5-190">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="c65f5-191">リソースアカウントにライセンスが適用されていない場合、電話番号の割り当ては失敗します。</span><span class="sxs-lookup"><span data-stu-id="c65f5-191">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="c65f5-192">このコマンドの詳細については[、「Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c65f5-192">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="c65f5-193">前に説明したように、Microsoft Teams 管理センターを使用してオンライン電話番号を設定するのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="c65f5-193">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="c65f5-194">Microsoft Teams 管理センターでリソースアカウント設定を管理する</span><span class="sxs-lookup"><span data-stu-id="c65f5-194">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="c65f5-195">Microsoft Teams 管理センターでリソースアカウントの設定を管理するには、[**組織全体の設定**  > ]**リソースアカウント**に移動し、設定を変更する必要があるリソースアカウントを選び、[**編集**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c65f5-195">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="c65f5-196">[**リソースアカウントの編集**] 画面では、次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-196">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="c65f5-197">アカウントの**表示名**</span><span class="sxs-lookup"><span data-stu-id="c65f5-197">**Display name** for the account</span></span>
- <span data-ttu-id="c65f5-198">アカウントを使う通話キューまたは自動応答</span><span class="sxs-lookup"><span data-stu-id="c65f5-198">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="c65f5-199">アカウントに割り当てられている電話番号</span><span class="sxs-lookup"><span data-stu-id="c65f5-199">Phone number assigned to the account</span></span>

<span data-ttu-id="c65f5-200">完了したら、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c65f5-200">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="c65f5-201">リソースアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="c65f5-201">Delete a resource account</span></span>

<span data-ttu-id="c65f5-202">サービス番号が保留モードで停止しないようにするには、削除する前に必ず電話番号とリソースアカウントの関連付けを解除してください。</span><span class="sxs-lookup"><span data-stu-id="c65f5-202">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="c65f5-203">これは、次のレットを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-203">You can do that using the following commandlet:</span></span> 

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="c65f5-204">この操作を行うと、O365 管理ポータルの [ユーザー] タブでリソースアカウントを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="c65f5-204">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

## <a name="related-information"></a><span data-ttu-id="c65f5-205">関連情報</span><span class="sxs-lookup"><span data-stu-id="c65f5-205">Related Information</span></span>

<span data-ttu-id="c65f5-206">Skype for Business Server とハイブリッドの実装の場合:</span><span class="sxs-lookup"><span data-stu-id="c65f5-206">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="c65f5-207">クラウド自動応答の計画</span><span class="sxs-lookup"><span data-stu-id="c65f5-207">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="c65f5-208">クラウド自動応答の構成</span><span class="sxs-lookup"><span data-stu-id="c65f5-208">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="c65f5-209">Teams または Skype for Business Online の実装の場合:</span><span class="sxs-lookup"><span data-stu-id="c65f5-209">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="c65f5-210">クラウドの自動応答とは</span><span class="sxs-lookup"><span data-stu-id="c65f5-210">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="c65f5-211">クラウドの自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="c65f5-211">Set up a Cloud auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="c65f5-212">小規模ビジネスの例: 自動応答をセットアップする</span><span class="sxs-lookup"><span data-stu-id="c65f5-212">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

[<span data-ttu-id="c65f5-213">クラウドの通話キューを作成する</span><span class="sxs-lookup"><span data-stu-id="c65f5-213">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="c65f5-214">新規-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="c65f5-214">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="c65f5-215">新しい Csonline Applicationinstance</span><span class="sxs-lookup"><span data-stu-id="c65f5-215">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
